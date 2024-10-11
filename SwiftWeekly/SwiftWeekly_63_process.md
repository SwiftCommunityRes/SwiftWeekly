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
1) 提议[字符串编码名称](https://forums.swift.org/t/pitch-foundation-string-encoding-names/74623 "字符串编码名称")
**内容大概**
很高兴看到这个API的提案！正如你所提到的，这确实是String中一个重要的缺失功能，相较于CFString，它将非常有用。

决定哪些编码应该可用（例如用于String(data:encoding:)）是“未来的方向”。

我不确定是否应该立即添加静态属性。如果可能的话：

* FoundationEssentials 将仅为内置编码提供静态属性。
* FoundationInternationalization 可能会为ICU编码提供静态属性，或者这些编码可能仅动态可用？
* 当同时导入这两个模块时，现有API将支持额外的编码。

我倾向于赞同这种方法。背景是，CoreFoundation 提供比 Foundation 更多的编码，因为 CoreFoundation 是为旧版macOS应用程序实现的，依赖Carbon提供的编码转换。Foundation本身仅支持少量编码，这些编码大致相当于 NSStringEncoding/String.Encoding 常量中定义的编码。我认为，如果 String.Encoding 包含所有这些编码，而 Foundation API 从未支持这些编码，可能会引起混淆。

对于一些常见编码，我们可以考虑将它们降级到 FoundationEssentials，或者如果我们认为转换足够重要，可以添加新的 String.Encoding 选项（例如，在 Swift 6 中，我们将 isoLatin1 和 macOSRoman 编码转换从 Foundation 降级到 FoundationEssentials，因为这些编码转换常用于URL相关的API）。最终，我希望能实现 @benrimmington 提到的方法，在 FoundationEssentials 中，String.Encoding 仅提供 FoundationEssentials 提供的编码转换，而 FoundationInternationalization 可以添加额外的ICU编码。

@YOCKOW，你认为仅使用当前可用的 String.Encoding API，而不添加新静态属性（因为这就是 Foundation 当前支持的转换）是否有价值？

首先，日本有15%的网站仍然使用 Shift JIS。（UTF-8占80%。）

他们真的使用标准的 Shift JIS，还是使用带有微软扩展的CP932（Windows-31J）版本？你的来源没有提到，但确实指出Shift JIS曾被广泛使用是因为Windows的普及。

编辑：根据维基百科的回答——“许多用户和软件包（包括微软库）将 Shift JIS 编码声明为 Windows-31J 数据，尽管它包含一些额外字符，而且某些现有字符映射到 Unicode 时有所不同。这导致了WHATWG HTML标准将编码标签 shift_jis 和 windows-31j 视为可互换的，并在其‘Shift_JIS’编码器和解码器中使用了Windows变体。”

因此，现有行为更具互操作性，如果新增的API未保留这种行为，可能会导致混淆。

编辑2：根据提供的来源，WHATWG 似乎有一个新的编码标准（https://encoding.spec.whatwg.org/），故意偏离IANA，以解决用户代理之间的互操作性问题。标准的语言表明，它有意取代IANA（包括取消对其注册表的任何依赖，并出于安全原因移除字符集的可扩展性）。Rust 的实现详细说明了具体的区别——

在某些情况下，编码标准指定了常用的未扩展编码名称，而在IANA术语中，考虑到编码标准统一到编码中的扩展，另一个标签可能更为精确。

编码	IANA
Big5	Big5-HKSCS
EUC-KR	windows-949
Shift_JIS	windows-31j
x-mac-cyrillic	x-mac-ukrainian

在其他情况下，编码标准统一了编码的未扩展和扩展版本，编码获得了扩展版本的名称。

IANA	统一到编码
ISO-8859-1	windows-1252
ISO-8859-9	windows-1254
TIS-620	windows-874

既然相关的Web标准似乎已经超越了IANA字符集，特别是Swift现有API已经与其对齐，我们是否应该实现这一取代标准？

编辑3：该取代标准还有一个优点，即它使用“编码”一词，而非“字符集”——这已经与Swift的用法一致。确实，越思考，越觉得 String.Encoding 的行为是故意设计成反映当前编码标准的。

2) 提议进展[SE-0446：Nonescapable 类型](https://forums.swift.org/t/se-0446-nonescapable-types/74666 "SE-0446：Nonescapable 类型")
**内容大概**
SE-0446: 非逃逸类型的审查现已开始，将持续到2024年10月1日。

本提案涵盖了对非逃逸类型支持的第一阶段；它涵盖了限制在当前作用域内的非逃逸类型的基本语义。然而，该提案本身不提供超出此范围的生命周期依赖表达机制，这意味着目前没有安全的方法来初始化或返回Escapable类型的值。为了便于对此功能进行实验，上述工具链还提供了对@lifetime属性的一些支持，该属性必须用于表达由初始化器或返回值生成的Escapable值的生命周期依赖。然而，该属性的确切行为不包括在此次审查中，可能会在未来单独审查并接受之前发生变化。

3) 提议进展[SE-0447：跨度：安全访问连续存储](https://forums.swift.org/t/se-0447-span-safe-access-to-contiguous-storage/74676 "SE-0447：跨度：安全访问连续存储")
**内容大概**
SE-0447 “Span：安全访问连续存储” 的审查现已开始，将持续到2024年10月1日。

本提案是SE-0446 “非逃逸类型”的库对照部分，也是首个采用此类型的提案。在这些工具链中，withSpan() 函数可用于数组系列类型（如 Array、ArraySlice、ContiguousArray），以及 UTF8View（如 String.UTF8View、Substring.UTF8View）和 UnsafeBufferPointer 系列。如果元素类型是 BitwiseCopyable，则还可以使用 withBytes() 函数，提供一个 RawSpan。虽然这些 with(Raw)Span 操作并未专门提出，但它们提供了一种方法来试用 Span、其API以及它作为非逃逸类型如何与Swift代码交互。

4) 讨论[Swift 6 是一门好的首选语言吗？](https://forums.swift.org/t/is-swift-6-a-good-first-language/74384/83 "Swift 6 是一门好的首选语言吗？")
**内容大概**
Swift 6 是否适合作为第一编程语言？

要求初学者不使用全局变量，这与“简单”和“作为第一编程语言”的理念有些冲突。

虽然一些教材（如《计算机程序的构造与解释》）早期引入了全局变量，但通常是为了说明其弊端，随后转向更好的技术。虽然这本书使用了不少赋值操作，但并不依赖于全局变量。

如今，大多数流行语言都支持词法作用域和闭包，因此在教授其他语言时，也没有必要依赖全局变量。此外，专为儿童设计的编程语言Smalltalk完全没有全局变量。

然而，这些教材通常针对大学课程，而这里讨论的是“Swift 6 适合作为第一编程语言吗？”的问题。现今的孩子，可能在上大学之前（甚至8到12岁时）就接触编程了。相比之下，尽管Smalltalk最初是为孩子设计的，但如今很少有人推荐它作为儿童的第一编程语言。

我并不建议一种理想的课程设计，更多的是分享我在培养自己孩子学习编程时的经验。比如，Arduino编程（青少年常见的STEM入口点）经常使用顶层变量（通常用于定义常量或数据）。

对于从零开始学习编程的人来说，单线程编程更容易理解，因此全局变量在初学阶段既不危险又容易掌握。尽管我认为今天的孩子可能有不同的学习愿望和切入点，但我仍会建议家长为10至12岁的孩子选择Python，它比Swift简单得多，不用担心多线程、数据竞争等复杂概念。

（当然，在专业代码中，全局变量是不好的，但我们这里讨论的是初学者学习编程的第一步——“第一编程语言”）

总的来说，我认为Swift不应该在初学者学习过程中因为并发问题对他们发出警告，除非他们确实在编写涉及并发的代码。

5) 讨论[有没有办法在不使用 SWIFT_STRICT_CONCURRENCY=COMPLETE 的情况下使用 Swift 6](https://forums.swift.org/t/is-there-a-way-to-use-swift-6-without-swift-strict-concurrency-complete/74677 "有没有办法在不使用 SWIFT_STRICT_CONCURRENCY=COMPLETE 的情况下使用 Swift 6")
**内容大概**
Swift 6 引入了许多新功能，我很想使用，但由于严格的并发检查，我的项目（约1万行代码）无法在 Swift 6 模式下成功编译。我确信我的代码是安全且无错误的，并且通过动态手段来保证这一点。我不愿意使用基于 actor 的同步模型，也不打算采用 Swift 的结构化并发。因此，我的目标是迁移到 Swift 6，但不使用“严格并发检查”。

如何在不启用严格并发检查的情况下使用 Swift 6？

你可以通过逐步迁移到 Swift 6，而不必立即启用严格的并发检查。虽然 Swift 6 强制并发检查，但你可以参考 Swift 官方的迁移指南，逐步处理并发问题，而不是一次性解决所有问题。这样做可以让你在使用新特性的同时，避免对现有代码做大规模的修改。

对于全局可变的、非 actor 隔离的变量，可以暂时通过 nonisolated(unsafe) 来避免严格的并发检查。这个注解会告诉编译器，不对这些变量进行并发安全性检查，即使在 Swift 6 模式下也能起作用。这是一个临时解决方案，适合在迁移过程中使用。

未来计划：Swift 6 之后

如果你计划继续使用 Swift 6 的并发特性，最终还是需要迁移到严格的并发检查。即便在短期内通过 nonisolated(unsafe) 绕过了严格检查，长期来看，完全迁移到严格检查模式是非常有必要的。这不仅可以利用编译器的检查功能来避免潜在的并发错误，还可以确保你在 Swift 新的并发模型中不会错过重要的优化和安全机制。

对于大型项目而言，逐步迁移的时间表可能需要一到两年，但在这期间，通过正确的规划和步骤，可以确保迁移过程平稳且可控，最终享受到 Swift 并发模型带来的好处。

6) 讨论[为什么actor允许使用“非隔离惰性变量”？](https://forums.swift.org/t/why-nonisolated-lazy-var-is-allowed-on-actor/74609 "为什么actor允许使用“非隔离惰性变量”？")
**内容大概**
在 Swift 6 中，编译器不允许 nonisolated 修饰符用于 actor 中的可变存储属性，因为这会导致共享可变状态，这与 Swift 的并发模型相违背。然而，当属性声明为 lazy 时，编译器允许 nonisolated lazy var 的声明，这可能会导致数据竞争问题。

问题分析

lazy 仅影响变量的初始化方式，但在初始化后，属性的行为与普通的 nonisolated var 类似。换句话说，lazy 属性的初始值是延迟计算的，但一旦初始化，后续的读写行为不再受 lazy 修饰符的影响。因此，允许 nonisolated lazy var 可能导致数据竞争，正如以下代码展示的那样：
```Swift
actor A {
    var i = 0
    nonisolated lazy var k = 0
    
    nonisolated func readK() -> Int {
        k += 1
        return k
    }
}

func run() {
    let a = A()
    Task.detached {
        let result = a.readK()
        print("\(result)")
    }
    Task.detached {
        let result = a.readK()
        print("\(result)")
    }
}
```
在这个例子中，nonisolated lazy var k 允许多个任务并发访问 k，导致数据竞争。两个并发任务可能同时读取和修改 k，导致不安全的共享状态，从而违反 Swift 的并发安全原则。

为什么会发生？

lazy 属性的本质是通过隐藏的存储属性来缓存值，编译器为该属性生成一个 getter 和 setter，这看起来像是计算属性。当 lazy 属性标记为 nonisolated 时，编译器可能没有正确处理它背后的存储属性，因此没有触发错误检查。通常，如果这种模式是手动编写的，编译器会拒绝访问这种非隔离的存储属性或阻止 getter。

可能的解决方案:

1.	编译器修复：这可能是编译器中的一个 bug，编译器应该明确处理 lazy 属性，尤其是在涉及 nonisolated 的情况下。正如讨论中提到的，如果编译器检查了手动编写的 lazy 模式，它可能会报错，因此对 lazy 属性的检查可能需要改进。
2.	规避方法：在当前的 Swift 版本中，开发者应避免使用 nonisolated lazy var 这种模式，尤其是在并发场景中，以防止数据竞争问题。

总的来说，这是一个潜在的编译器问题，可能需要修复。

7) 讨论[SDL、游戏循环和 Swift 并发](https://forums.swift.org/t/sdl-game-loop-and-swift-concurrency/74692 "SDL、游戏循环和 Swift 并发")
**内容大概**
在使用 Swift 并发和 SDL 进行游戏开发时，游戏循环存在一些问题。通常，游戏循环要么是繁忙等待循环，要么是阻塞循环（例如使用 WaitMessage 让线程暂停），这对 Swift 并发机制不友好，因为它会导致主 Actor 执行器集中在游戏循环上，忽视了其他需要调度的任务。

为了解决这个问题，可以在游戏循环中使用 Task.yield()，以便给执行器机会去处理其他任务。这种方法目前看来是可行的。

另一个问题是，Swift 的主 Actor 并不绑定到主线程，这会引发一些问题，因为某些 Win32 API 和第三方库（包括 SDL）要求从主线程调用它们。如果使用 Swift 并发或 DispatchQueue，一旦脱离了真正的主线程，似乎就无法再回到主线程。

此外，线程阻塞也会导致问题。为避免这种情况，可以使用定时器而不是繁忙等待，这样可以避免长时间阻塞主线程，从而避免对 Swift 的任务调度队列产生影响。

## 推荐博文

[Swift6 的发布](https://www.swift.org/blog/announcing-swift-6/ "Swift6 的发布")

**摘要：** 这篇官方文章讲解了 Swift6 带来了多项重要更新，扩展了语言的功能和平台支持：

1. **并发和数据竞争安全**：引入了新的并发模型，防止数据竞争，并新增了低级别的同步库。
2. **类型化异常**：允许函数明确指定抛出错误的类型，提高错误处理的精确性。
3. **所有权管理**：支持非复制类型，优化内存管理，提升性能。
4. **C++互操作性**：改进与 C++ 的互操作，支持更多类型和功能。
5. **嵌入式Swift**：引入嵌入式 Swift ，适用于内存有限的系统。
6. **128位整数**：新增128位整数类型，支持低级别编程。
7. **调试增强**：通过`@DebugDescription`简化调试，提升调试启动性能。
8. **统一的Foundation库**：跨平台一致性增强，所有平台共享现代化实现。
9. **Swift Testing**：新测试库，更简洁的API和更详细的测试输出。

 Swift6 进一步提升了跨平台开发和嵌入式应用的能力。

[Swift @resultBuilder](https://juejin.cn/post/7415660986982252598/ "Swift @resultBuilder")

**摘要：** Swift 的 @resultBuilder 是一项强大的语言特性，允许开发者以声明式的方式构建复杂的数据结构。它常用于创建 DSL、构建 UI 组件和生成配置文件等场景。@resultBuilder 通过静态方法如 buildBlock、buildIf 和 buildEither 等将多个代码块组合成一个结果。本文通过示例展示了如何定义和使用自定义结果构建器，以及它在处理条件语句和构建复杂结构中的应用。该特性可以简化代码、提升可读性，并在实际开发中提高效率。

[@inlinable 和 @usableFromInline 内联](https://juejin.cn/post/7414030456294834239 "@inlinable 和 @usableFromInline 内联")

**摘要：**  这篇博客主要介绍了 Swift 中的两个修饰符：**@inlinable** 和 **@usableFromInline**，并详细解释了它们的作用及使用场景。

- **@inlinable**：允许编译器将函数或方法的实现暴露给其他模块，从而进行**跨模块内联优化**。这可以减少函数调用的开销，特别是对于轻量、频繁调用的小函数。它还支持**泛型函数优化**，提高性能。然而，使用时需注意可能带来的**封装性降低**、**代码膨胀**、**编译时间增加**及**二进制兼容性问题**。

- **@usableFromInline**：用于限制符号的可见性，仅在当前模块内可见，但当与 **@inlinable** 一起使用时，允许它在其他模块内联使用，**不暴露实现细节**。

文章还分析了**@inlinable** 在不同场景中的实际使用方法，指出其可以用于小型、性能关键的代码，但应避免过度使用，以免导致二进制文件膨胀和维护困难。


## 话题讨论

**近期股市经历暴涨后暴跌,专家称因前期涨速过快及市场情绪紧张。业内认为调整非牛市结束，建议投资者保持冷静。你认为今年会有牛市吗？**

1. 有：政策面的利好不断落地，经济逐步复苏。即将迎来大牛市。
2. 没有：当前经济环境依旧不乐观，基本面支撑不足。

欢迎在文末留言参与讨论。


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
