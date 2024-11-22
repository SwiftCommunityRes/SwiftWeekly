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
1) 评论[SF-0011：并发安全通知](https://forums.swift.org/t/review-sf-0011-concurrency-safe-notifications/75975 "SF-0011：并发安全通知")
Swift Foundation 提案 SF-0011: 并发安全通知 的评审已开启，将持续至 2024 年 11 月 19 日。该提案旨在通过新的 API 提升通知在并发场景中的处理能力，并引入以下三个协议：
1.	Message：基础协议，用于定义通用消息结构。
2.	MainActorMessage：继承自 Message，用于需要在主线程上接收的消息。
3.	AsyncMessage：继承自 Message 和 Sendable，用于支持异步接收的消息。
同时，提案设计了两种 addObserver 方法，分别处理 MainActorMessage 和 AsyncMessage。
关键反馈：
1.	关于 MainActorMessage 的约束：
•	提案需要进一步澄清 MainActorMessage 的 post() 方法是否应被限制为仅在 @MainActor 环境中调用，以确保观察闭包能够同步触发。
•	应明确 MainActorMessage 是否允许在非 @MainActor 环境中构建，但要求在主线程上观察。
2.	关于 AsyncMessage 协议的必要性：
•	有建议认为 AsyncMessage 协议的 Sendable 要求可能是多余的，可以直接使用 Message 协议，并通过对方法的参数施加约束来满足需求。
•	如果未来语言支持动态隔离（如 @isolated(parameter)），可能可以通过 Message 协议中的属性进一步简化设计。
3.	异步消息处理的优化建议：
•	当前的 addObserver 方法使用异步观察者闭包，但该闭包可能通过非结构化任务执行，容易引发性能问题，例如过多任务创建销毁会导致开销增加，甚至可能导致拒绝服务攻击。
•	建议通过结构化并发重新设计 API，例如引入 AsyncSequence 来处理消息观察，从而移除对非结构化任务的依赖并避免引入额外的 ObservationToken。
4.	关于 ObservationToken：
•	当前 ObservationToken 用于支持快速注销观察者，但需要明确在未调用 removeObserver 的情况下，观察者何时被自动取消注册。
•	提议将 ObservationToken 设计为 ~Copyable 类型，以确保其仅能使用一次并防止被意外丢弃。
总结：
该提案为并发通知管理带来了重要改进，但仍有设计细节需要完善，例如协议的约束合理性、API 的性能及安全性优化，以及观察者生命周期管理的明确性。

2) 讨论[随机“Clock”持续时间](https://forums.swift.org/t/random-clock-duration/75937 "随机“Clock”持续时间")
用户尝试实现一个函数，基于通用 Clock 生成一个从零到指定上限的随机持续时间 (Duration)。由于 Clock.Duration 仅受限于 DurationProtocol，直接实现这一功能存在挑战。幸运的是，Swift.Duration 提供了 seconds 和 attoseconds 两个 Int64 组件，可以通过组合它们生成一个随机的 Int128 值（Swift 6 中新增支持），实现随机持续时间计算。
```Swift
extension Clock where Duration == Swift.Duration {
  func randomDuration(upTo maxDuration: Duration) -> Duration {
    let random = Int128.random(in: 0..<(Int128(maxDuration.components.seconds) * 1_000_000_000_000_000_000 + Int128(maxDuration.components.attoseconds)))
    return Duration(secondsComponent: Int64(random / 1_000_000_000_000_000_000), attosecondsComponent: Int64(random % 1_000_000_000_000_000_000))
  }
}
```
关键问题与讨论：
1.	通用性限制：
•	此实现仅适用于 Duration 为 Swift.Duration 的时钟，不适用于其他 DurationProtocol 实现。用户希望找到更通用的方法。
2.	非均匀性与运行时性能：
•	有人指出该方法可能具有非均匀的运行时，且在理论上可能出现运行时间非常长的情况。
•	然而，在实际应用中，这种情况极少发生。例如，使用简单的拒绝采样算法时，97.5% 的情况下只需一次采样，99.95% 的情况下两次采样即可完成。因此，这种“不均匀性”在实际意义上几乎可以忽略不计。
3.	效率与可行性：
•	尽管方法在某些情况下理论上不够优雅，但其实际运行效率足够高，对绝大多数应用场景而言是合理的解决方案。
总结：
该方法利用 Swift.Duration 的组件生成随机持续时间，但受限于特定类型的 Clock，不够通用。此外，尽管存在理论上的非均匀性问题，但在实践中这种方法的效率和可靠性可以满足需求。进一步优化可能需要考虑更通用的 DurationProtocol 支持，以及潜在的性能改进方向。

3) 讨论[`withCheckedContinuation(isolation:function:_:)` 中的 SIGSEGV](https://forums.swift.org/t/sigsegv-in-withcheckedcontinuation-isolation/75898/1 "`withCheckedContinuation(isolation:function:_:)` 中的 SIGSEGV")
团队在将代码库迁移到 Swift 6 语言模式 时，发现使用 withCheckedContinuation(isolation:function:_:) 的网络接口与基于 Combine 的任务发布器同时支持的实现，在迁移到 Xcode 16 后，出现了一些 tvOS 18.0 上的崩溃问题。以下是问题描述与社区反馈总结：
问题概述：
1.	崩溃日志指向 withCheckedContinuation(isolation:function:_:) 函数，相关调用栈位于 swift::runJobInEstablishedExecutorContext。
2.	该问题出现在 Xcode 16 及其后续版本（如 16.1），影响从 iOS 18 开发者测试版 1 至 4 的客户端。
3.	崩溃的根本原因与并发全局函数（如 withThrowingTaskGroup、withCheckedThrowingContinuation）在引入 isolation 参数后的行为变化相关。
社区反馈与应对建议：
1. 升级与回滚策略：
•	建议升级至 Xcode 16.1：尽管某些问题依旧未解决，但部分用户报告升级后稳定性有所改善。
•	回滚到 Xcode 15.4：因 Xcode 16 在特定环境中的兼容性问题，一些团队选择回滚以降低崩溃率，尽管开发人员在升级后可能难以回退。
2. 直接修复方法：
•	将 stdlib 中的崩溃函数直接复制到本地并进行调整（通过复写方式规避问题）。此方法在部分生产环境中已稳定运行数周。
•	对外部依赖的适配方法：
•	如果依赖库是预构建的，可以尝试修改符号引用以指向本地修复版本。
•	注意避免全局替换定义（如使用 @_dynamicReplacement 或类似 fishhook 的动态链接库替换工具）。
3. 对每个函数问题的单独解决：
•	相关函数：包括 withThrowingTaskGroup、withCheckedThrowingContinuation、withCheckedContinuation 等。
•	独立处理的必要性：这些函数引发崩溃的原因相似，但解决方法可能需要针对每个函数的具体实现进行单独的调整。
4. 函数定义与参数顺序的影响：
•	某些函数（如 TaskLocal.withValue）虽然也添加了 isolation 参数，但因参数顺序不同而避免了崩溃。例如：
•	当 isolation 被解释为其他类型（如 String）且未被函数主体读取时，崩溃未发生。
•	而 withCheckedContinuation 将 isolation 放置在闭包之前，导致其尝试将传入的隔离上下文作为闭包使用，从而引发崩溃。
总结：
该问题源于并发函数在 Swift 6 中的实现变化，对特定上下文的兼容性不足。尽管有升级工具链的建议，但实际生产中需依赖本地修复和对依赖库的定制适配。此外，函数参数顺序设计和隔离上下文的解析方式也是影响崩溃的潜在原因。开发者需在迁移到 Swift 6 或 Xcode 16 时进行充分测试并实施必要的兼容性修复。

4) 提议[SE-0453：向量，固定大小的数组](https://forums.swift.org/t/se-0453-vector-a-fixed-size-array/76004 "SE-0453：向量，固定大小的数组")
Swift 论坛对提案 SE-0453: Vector（固定大小数组） 的首次评审已开启，将持续至 2024 年 11 月 27 日。本次评审专注于类型的 API 表面和基本行为，暂不讨论名称 Vector 的相关反馈。后续评审会专门讨论命名问题。
提案概述：
提案引入了固定大小的 Vector 类型，其特点是：
•	固定大小：一旦创建，大小不可更改。
•	完全初始化：所有元素必须在初始化时完成初始化，不能动态添加或移除元素。
•	非可复制性（潜在特性）：虽然 Vector 可能不可复制，但其主要独特性在于其固定大小和初始化需求。
核心反馈与讨论：
1.	初始化的特殊性：
•	与其他数据结构不同，Vector 无法通过常规方法（如 init()、reserveCapacity()、append()）操作，因此初始化器需要支持直接生成元素集合。
•	提案中的初始化器适合 Vector 的独特性，但可能仍不足以覆盖更复杂的初始化模式。
2.	关于通用初始化器的建议：
•	当前的初始化器虽然足够实用，但建议引入更底层的初始化方法，类似于 Array 的 init(unsafeUninitializedCapacity:initializingWith:)，允许开发者通过 UnsafeMutableBufferPointer 手动初始化。
•	一个更安全的方案是引入一个闭包初始化器，按元素顺序初始化，同时提供对已初始化元素的访问（例如通过未来可能支持的 Span 或 MutableSpan 类型）。这种方法可以让初始化过程利用已有元素，实现排序、打乱等操作。
3.	适配性与灵活性：
•	提案的初始化器被认为过于具体，可能限制开发者实现更复杂的功能场景。设计更通用的基础功能有助于提升 Vector 的适配性。
总结：
提案为 Swift 引入了一个高效的固定大小数组类型，适用于需要确定大小且不可变的数据场景。然而，初始化器的设计需要进一步讨论，以支持更多复杂的模式和用例。评审社区还需探讨是否应该提供更通用的底层功能来满足多样化需求。

5) 提议[修改和读取访问器](https://forums.swift.org/t/pitch-modify-and-read-accessors/75627 "修改和读取访问器")
论坛中，针对提案**“修改和读取访问器”**的讨论主要集中在访问器的命名、语义区分以及潜在的未来扩展。以下是提案要点与社区反馈的总结：
提案要点
1.	目标版本与时间表：
•	该提案未计划纳入 Swift 6.1，即使在接近的分支切割时间（2024 年 11 月 13 日）后，也不会立即生效。
2.	是否支持 async 访问器：
•	当前提案未引入异步访问器（如异步 read 和/或 modify）。
•	提到这是未来可能探索的方向，同时需要考虑与现有功能的痛点进行整合。
3.	命名建议：borrow 和 mutate 替代 read 和 modify：
•	提案计划将 borrow（借用）和 mutate（变更） 用于更加基础的访问器，这些访问器提供对 self 组件的直接借用或可变借用。
•	而 read 和 modify 更适合描述基于协程（coroutine）的访问器行为，它们强调操作的临时性和持续时长。
4.	语义区分：
•	get 和 set：
•	表示访问器的瞬时性和最终性，传递数据的所有权，而无需持续的操作。
•	read 和 modify：
•	强调活动的持续时间，为某一实体提供临时直接访问权限，而非所有权转移。
•	举例：读取朋友的表情或让锁匠修改前门，均是具有开始和结束时间的活动，不涉及对象所有权转移。
5.	未来方向：投影访问器（Projection Accessors）：
•	投影访问器可返回与基础对象等长的借用值，使用**borrow 和 mutate**更符合其语义。
•	此类访问器能拓展当前存储属性的语义，并为 Swift 提供更灵活的借用模型。
反馈与讨论
1.	关于词汇选择的细致区分：
•	社区成员建议 borrow 和 mutate 是否能替代 read 和 modify，但提案认为它们有显著的语义差异：
•	read 和 modify 强调基于协程的临时性与操作持续时长；
•	borrow 和 mutate 则适合表示直接的内存借用。
2.	词义对比与命名合理性：
•	提案反驳了将 read 视为 get 同义词的观点，强调了两者的语义细微差异。
•	参考词典，read 和 borrow 或 modify 和 mutate 并非严格同义，且其语境含义差异足以避免长期混淆。
3.	生命周期与类型安全性：
•	基于协程的 read 和 modify 访问器，其操作对象仅在访问期间物化，不适合用于建模包含关系（containment）。
•	在处理非可逃类型（non-escapable types）时，这种差异会影响生命周期语义，成为至关重要的问题。
总结
提案中的命名设计从语义、生命周期管理与未来扩展性等角度出发，避免了简单的词汇替换以确保语义精确性。当前提案专注于基础访问器功能，但也为未来的功能（如异步访问器与投影访问器）留出了扩展空间。

## 推荐博文

[Swift 指针基础](https://juejin.cn/post/7281117754898825255/ "Swift 指针基础")

**摘要：** 本文深入探讨了Swift中的指针基础知识，包括指针的分类（raw pointer和typed pointer）及其在Swift中的表示方式。通过与Objective-C的对比，阐述了原生指针的使用方法和场景。文章详细介绍了如何创建类型指针，包括单一表达式和泛型指针的创建方式，并通过多个实战案例展示了指针在Swift中的具体应用。实战案例涵盖了将变量绑定到特定内存、使用assumingMemoryBound进行内存假定绑定、以及通过原生指针和偏移量获取结构体类型的指针等操作。这些案例不仅展示了指针的强大功能，还通过代码和输出结果帮助读者更好地理解指针在内存管理和数据操作中的作用。

[swiftc-Swift 编译器详解](https://juejin.cn/post/7247073344439697464/ "swiftc-Swift 编译器详解")

**摘要：** 这篇博客详细介绍了Swift编译器的使用方法及其底层原理。首先，通过编译一个简单的"Hello world!"程序展示了Swift编译器（swiftc）的基本用法。接着，介绍了如何使用条件编译标志（-D）来控制代码的编译，例如在某些条件下编译调试信息。博客还演示了如何编译多个Swift文件并将它们链接成一个可执行程序。

此外，文章深入解释了Swift编译器的工作原理，包括前后端分离的设计，以及如何将Swift代码转换为LLVM中间表示（IR），再进一步编译成不同架构的可执行程序。为了让读者更好地理解编译过程，博客还提供了详细的步骤来展示从语法分析生成抽象语法树（AST），到生成中间层代码（SIL），再到生成LLVM IR、汇编代码和目标文件的整个过程。

[Swift 编译之 SIL(Swift Intermediate Language)](https://juejin.cn/post/7302781262321696803/ "Swift 编译之 SIL(Swift Intermediate Language)")

**摘要：**  这篇博客详细介绍了Swift编译过程中的一个重要环节——Swift中间语言（SIL）的生成和使用。文章从Swift编译的完整流程开始，逐步深入到SIL的生成方法和常见语法。通过多个实例，包括Person类的多种方法，展示了SIL代码的实际应用。


为了更直观地展示SIL的应用，文章以Person类为例，提供了该类中多个方法的SIL实现，包括属性的getter和setter方法、动态方法、初始化方法以及析构方法等。通过这些实例，读者可以清晰地看到Swift源代码是如何被编译成SIL代码的。

此外，文章还介绍了SIL中的vtable（虚函数表）和witness_table（协议见证表）的概念，并展示了它们在实际代码中的映射关系。最后，文章通过文件映射关系部分，说明了如何在SIL代码中引用源文件。


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
