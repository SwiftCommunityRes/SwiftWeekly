## 前言

**本期是 Swift 编辑组自主整理周报的第五十期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

间歇性的努力和蒙混过日子，都是对之前努力的清零。时间永不停歇，社会时刻发展，**Swift社区**也在华丽蜕变！👊👊👊

> **周报精选**
>
> 新闻和社区：
> 
> 提案：
> 
> Swift 论坛：
>
> 推荐博文：
>
> **话题讨论：** 
> 
> 
>
>**上期话题结果**


## 新闻和社区  


## 提案


## Swift论坛
1) 讨论[为什么`AsyncStream`会破坏结构化并发?](https://forums.swift.org/t/why-asyncstream-breaks-structured-concurrency/71477 "为什么`AsyncStream`会破坏结构化并发?")
**内容概括**
讨论文章描述了一个情况,在AsyncStream的继续块中使用`for await`循环时,如果外部任务被取消,则该循环并没有被取消。这种行为与结构化并发的规则相悖,因为结构化并发通常确保子任务在父任务被取消时也被取消。

```Swift
func makeStream() -> AsyncStream<Int> {
    return AsyncStream { continuation in
        Task {
            var n = 0
            while !Task.isCancelled {
                print("Sending", n)
                continuation.yield(n)
                try? await Task.sleep(nanoseconds: 1_000_000_000)
                n += 1
            }
            print("Cancelled!")
        }
    }
}

let outerTask = Task {
    for await n in makeStream() {
        print("Received", n)
    }
}

try? await Task.sleep(nanoseconds: 3_500_000_000)
outerTask.cancel()
try? await Task.sleep(nanoseconds: 5_000_000_000)
```

多个用户,包括Gwendal Roué(gwendal.roue),Nikolai Ruhe(nikolai.ruhe)和Wouter Hennen(Wouter01)提供了解释和解决办法。

Roué解释说,由于流中的任务没有与外部任务联系,因此外部任务被取消并没有传播到内部任务。Ruhe澄清了结构化与无结构化任务之间的区别,指出只有使用async let或任务群组时,子任务才能从异步上下文中被创建。父任务从父任务继承了取消,优先级和任务本地值也是如此。

Hennen建议设置继续的`onTermination`属性的闭包,当父任务被取消时就会立即运行。FranzBusch建议使用`AsyncStream`的`makeStream(of:)`工厂方法,把继续传递给一个产生元素的子任务,把流传递给另一个消费事件的子任务。

Bash表示认为把`Task`的初始化方法设置为`@discardableResult`可能是一个错误。Shier问如果强制用户使用`_ = Task {}`来获得异步上下文会有帮助吗?Bash回答说,它强制用户有一个可用的手柄,可以更有效地控制任务执行过程。

讨论继续下去,Vasenin更新了对情况的理解并感谢所有提供帮助的人。

这次讨论提供了有关AsyncStream和结构化并发行为的深刻见解,强调了理解结构化与无结构化任务之间的区别以及使用正确的API来创建和取消任务的重要性。

2) 讨论[融合闭包与协议](https://forums.swift.org/t/merging-closure-into-protocols/71499 "融合闭包与协议")
**内容概括**
关于闭包与协议的合并

aetherealtech提出了一个想法,建议函数类型是协议的隐式糖。该提议建议编译器把函数 SYNTAX 翻译成相应的协议代码,这种等价性可以被正式化,从而使得现在的函数 SYNTAX 变成了对应协议代码的隐式糖。

演进

这一提议是在“等价函数”讨论板上发生的对话的结果。

提议

函数协议很有趣,如果添加一个伴随错误类型,我们就能支持抛出错误的函数。

异步函数可能只需要一个叫做AsyncFunction协议的协议即可。

函数的等价性

这一提议是在“函数的等价性”讨论板上发生的对话的结果。

匿名结构体

有人提出了一个提议,希望Swift能够引入匿名结构体,以减轻使用协议导向设计的API的用户遭受的语法负担。在许多情况下,匿名结构体的使用方式和闭包方式相当。

结论

经过所有这些步骤,该提议建议,这将使得客户端代码完全透明,只是把泛型参数的函数,比如map,提升到包围类型上以保持类型信息。

3) 讨论[SE-0435：每个target的Swift语言版本](https://forums.swift.org/t/se-0435-swift-language-version-per-target/71546 "SE-0435：每个target的Swift语言版本")
**内容概括**
Swift 社区目前正在审查“每个目标的 Swift 语言版本”，截止日期为 2024 年 5 月 13 日。该提案旨在允许在每个目标的基础上指定 Swift 语言版本。对提案的反馈应在论坛帖子上分享或直接通过电子邮件分享给审核经理，并在主题行中包含“SE-0435”。

可以下载支持该提案的工具链用于测试目的。用户报告了该工具链的积极体验，确认可以更改目标语言版本而不会导致重建，并且使用“#if swift(...)”进行条件编译按预期工作。

此外，还讨论了进一步增强的建议，​​例如将包目标默认为 Swift 6 或简化消费者和库提供者的版本控制。然而，由于潜在的复杂性，这些建议可能会推迟到以后考虑。

4) 讨论[“标准”vapor 网站会丢弃 1.5% 的请求，即使并发数为 100！](https://forums.swift.org/t/se-0435-swift-language-version-per-target/71546 "“标准”vapor 网站会丢弃 1.5% 的请求，即使并发数为 100！")
**内容概括**
深入探讨了“标准”Vapor 网站所面临的挑战，即使在 100 并发负载下，该网站的请求下降率也高达 1.5%。这表明 Vapor 正在积累积压的任务，导致与连续请求相比，请求处理时间显着增加。这种延迟归因于从 Future 到 Concurrency 的过渡，这被视为性能瓶颈的主要原因。

进一步的分析表明，虽然底层网络框架 NIO 运行平稳，但由于 CPU 资源在响应请求之前需要等待一段时间才能用于斐波那契计算等任务，因此过渡到 async/await 会带来延迟。 Wireshark 的执行跟踪表明，早期的 HTTP 请求终止相对较快（约 70 毫秒），但后续请求需要更长的时间（约 110 毫秒），这表明响应时间有恶化的趋势。

为了解决这个问题，建议优化斐波那契计算，例如使用 BigUInt 通过消除符号位处理和补码操作来潜在地提高速度。此外，建议包括通过将结果流回 Vapor 而不是同时存储来优化内存使用，这可能会提高整体效率并减少内存开销。

在实现细节方面，建议重构“generateAllFibonacci”函数以增量生成结果并将其流回Vapor，从而避免需要同时存储所有结果。然而，文档中并没有提供如何在 Vapor 中实现这种流式传输方法的具体细节。

讨论强调了优化 Vapor 应用程序性能的必要性，特别是从 Future 到并发的过渡，并提供了一些可行的建议来解决观察到的延迟和丢弃率问题。

5) 提议[Metatype Keypaths](https://forums.swift.org/t/pitch-metatype-keypaths/70767 "Metatype Keypaths")
**内容概括**
本次投稿中讨论的是一个新功能,称为metatype keypaths,旨在扩展Swift编程语言中的keypath表达式。与普通keypath表达式类似,metatype keypath表达式可以动态访问属性,但它们还可以直接引用静态属性。

为什么要做这个改变

投稿指出,在讨论过去的一个投稿中曾经探讨过metatype keypaths,但最终被推荐作为未来方向。在讨论过去的投稿中曾经讨论过允许key path表达式直接引用静态属性,并且与@dynamicMemberLookup和静态属性通过另一个计算属性引用的诸多繁琐方案。

提案的具体方案

投稿建议允许keypath表达式定义静态属性的引用,以改善语言语义。这样做可以允许keypath表达式直接引用静态属性,而不需要使用技巧或绕过。

详细设计

metatype语法

metatype keypath表达式,其中首部分引用静态属性,将包含在根类型上声明的key path contextual type或key path literal中的.Type标识符。例如:

```Swift
let kp = .someType[.staticProperty]

```

若首部分引用静态属性并非第一个部分,则不需要包含.Type标识符。例如:

```Swift
let kp = .someType[staticProperty].someOtherProperty

```

访问语义

静态属性与不可变实例属性一样,都形成只读的keypaths。但与实例成员不同,可变静态属性的keypaths将遵守ReferenceWritableKeyPath协议,因为metatype是引用类型。

影响源代码兼容性

该功能破坏了静态属性被subscript扩展的源代码兼容性,因为旧版本的库无法使用该功能。

未来方向

枚举案例的key path

已有讨论过支持只读的key paths访问枚举案例,但尚未纳入本次投稿,因为这需要单独讨论 SYNTAX和设计细节。

总结

metatype keypaths在Swift编程语言中的投稿得到了积极反馈,拥有53个赞同和14条评论。该功能允许keypath表达式直接引用静态属性,而不需要使用技巧或绕过。该功能的实现将需要对Swift标准库中的KeyPath类型和新的运行时进行改变,旧版本的编译器无法保证对静态属性的keypath引用的操作比较是否正确。

6) 讨论[Linux 上 NSLock 的可发送一致性](https://forums.swift.org/t/sendable-conformance-of-nslock-on-linux/71506 "Linux 上 NSLock 的可发送一致性")
**内容概括**
该提案 SE-0433 向 Swift 标准库引入了互斥锁（通常称为互斥锁）。 “Mutex”将作为新的同步原语包含在同步模块中。这一添加背后的动机源于保护并发程序中共享可变状态的需要，这对于确保数据完整性至关重要。虽然 Actor 提供了用于保护可变状态的默认解决方案，但由于各种原因（例如需要同步执行或与遗留代码兼容），并非所有代码库都能够采用 Actor。在这种情况下，互斥体提供了一个标准化的解决方案来确保正确的同步。目前，Swift 缺乏互斥量的标准化实现，导致 Swift 程序中临时实现的激增。 “Mutex”的引入旨在通过提供简单且标准化的同步原语来保护共享的可变数据来解决这一差距。

7) 讨论[应用 MPSMatrixDescriptor 的 rowBytes 方法进行矩阵乘法](https://forums.swift.org/t/use-rowbytes-method-from-mpsmatrixdescriptor-for-matrix-multiplication/71513 "应用 MPSMatrixDescriptor 的 rowBytes 方法进行矩阵乘法")
**内容概括**
论坛讨论中讨论了使用MPSMatrixDescriptor的rowBytes方法来进行矩阵乘法,使用Metal。Gavin Wiggins(wigging)正在使用Metal Performance Shaders(MPS)来执行矩阵乘法并遇到困难确定推荐的矩阵行间隔使用rowBytes()方法。他怀疑在内存中的矩阵行字节数和原始数组长度之间存在差异是导致错误的打印值的原因。

Lincoln Wu(CrystDragon)建议,当使用自定义行间隔时,数据源必须匹配该值。Steve Canon(scanon)解释说传递的数据必须匹配指定的布局,而Tera注意到Metal偏爱除了一个列外的四数倍的列数。

Gavin Wiggins(wigging)提出了正确的步骤,涉及将输入数组扩充以基于rowBytes的方式填充,创建MPSMatrix从填充数组中,执行Metal矩阵乘法,将结果转换为普通的Swift数组,并将最终数组扩充到预期维度。

Steve Canon(scanon)提到,填充是独立于操作的,并且操作使用每个元素仅O(1)次时更有可能出现差异。他还解释说,类似的API通常是为了未来硬件的保障,而且性能不应该依赖于填充。

然后讨论转向了性能方面Tera和Gavin Wiggins(wigging)对带和不带填充的矩阵进行了测试并没有发现速度差异在M1上。Steve Canon(scanon)提到,类似的API通常是为了未来硬件而设计的,而且最优性能可能不可能实现。

## 推荐博文


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
