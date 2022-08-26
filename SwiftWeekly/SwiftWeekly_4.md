
## 前言

最近 Swift.org 进行了一些非常好的改进，包括对 `dark mode` 的支持。 对于在 iOS 上使用 `dark mode` 的用户，该网站将自动切换模式以匹配。

> 为了 Swift 社区周报持续稳定的发布更新，我们希望邀请 Swift 爱好者参与**周报编辑**，同时邀请赞助商对我们平台赞助支持。

## 入门任务

**SR-15271** [Compiler] [当 CodingKeys 与属性不匹配时改进可编码诊断](https://bugs.swift.org/browse/SR-15271 "Improve Codable Diagnostics When CodingKeys Do Not Match Properties")

## 新闻和社区

**Ted Kremenek** 写了一篇关于 [Swift 5.5 版本](https://swift.org/blog/swift-5-5-released/ "Swift 5.5 Released")的文章。

**Bruno Rocha** 发表了一篇优秀的文章，解释了 [AsyncSequence 在 Swift 内部是如何工作](https://swiftrocks.com/how-asyncsequence-works-internally-in-swift "How AsyncSequence works internally in Swift")的。

**Lee Kah Seng** 写了一篇文章，描述了 [Swift 中的 Actor Reentrancy 问题](https://swiftsenpai.com/swift/actor-reentrancy-problem/ "The Actor Reentrancy Problem in Swift")。

**Amritpan Kaur** 解释了她如何参与首届 [Swift 导师，并致力于编译器开发和语言设计](https://forums.swift.org/t/swift-mentorship-compiler-language-design/52522 "Swift Mentorship - Compiler & Language Design")。

## Commits 和 pull requests

**Michael Ilseman** 合并了一个为 [String 实现原生规范化](https://github.com/apple/swift/pull/38922 "[stdlib] Implement native normalization for String")的 pull request。

**Doug Gregor** 创建了一个 pull request，[向后兼容  @objc actor 类型](https://github.com/apple/swift/pull/39609 "Back-deploy @objc actor types")。

## 同意的提案

**SE-0322** [临时未初始化缓冲区](https://forums.swift.org/t/accepted-with-modifications-se-0322-temporary-uninitialized-buffers/52532 "Temporary Uninitialized Buffers")已接受修改。

**SE-0323** [Asynchronous Main 语义](https://forums.swift.org/t/accepted-se-0323-asynchronous-main-semantics/52531 "Asynchronous Main Semantics")已接受。

**SE-0324** 接受了[对 C 函数的指针参数放宽诊断](https://forums.swift.org/t/accepted-se-0324-relax-diagnostics-for-pointer-arguments-to-c-functions/52599 "Relax diagnostics for pointer arguments to C functions")提案。

## 正在审查的提案

**SSWG-0017**：[MultipartKit](https://forums.swift.org/t/sswg-0017-multipartkit/52586 "MultipartKit") 正在审查中。

`MultipartKit` 提供 `Multipart` 数据的低级解析和序列化，以及对 `Multipart` 表单数据的编码和解码的高级 `Codable` 支持。

## Swift 论坛

**1. Karoy Lorentey** 询问什么时候将 `ManagedAtomic/UnsafeAtomic` 标记为 `Sendable`？

刚刚提交了[问题 #45](https://github.com/apple/swift-atomics/issues/45 "The constructs provided by this package need to be marked Sendable")，要求将 `UnsafeAtomic`、`ManagedAtomic` 和朋友标记为 `Sendable`，这反映了它们可以安全地跨并发域传输。

**2. Kavon Farvardin** 提议定义 [actor 初始化器](https://forums.swift.org/t/proposal-actor-initializers-and-deinitializers/52322 "[proposal] Actor Initializers and Deinitializers")在 `Swift` 中的工作方式。

目前，本提案中描述的一些问题的建议解决方案通过警告反映在 `Swift 5.5` 中，但是审查 `Swift 6` 的这些更改很重要。此外，该提案为 `MainActor` 隔离类的 `deinit` 增加了额外的功能，这样可以更容易、更安全地编写。如果有新的想法和评论可以在[这里提出来](https://github.com/kavon/swift-evolution/blob/actor-init-proposal2/proposals/nnnn-actor-initializers.md "Actor Initializers and Deinitializers")。

**3. Kelvin Ma** 发现 [Swift 5.5 存在严重的堆栈损坏错误](https://forums.swift.org/t/swift-5-5-has-serious-stack-corruption-bugs/52344 "Swift 5.5 has serious stack corruption bugs!")。

我发现了几个与 async/await 相关的堆栈损坏错误，这些错误可以在使用最近的夜间工具链编译的简单测试程序中重现。 我已经确认 5.5-RELEASE 工具链中存在这些错误中的两个三四个。

我发现了几个与 `async/await` 相关的堆栈损坏错误，可以在 `recent nightly toolchains` 的简单测试程序中重现问题。**我已确认 `5.5-RELEASE toolchain` 中存在多个错误**。

**4. Becca Royal-Gordon** 提出了在[Sendable 检查中添加暂存](https://forums.swift.org/t/pitch-2-staging-in-sendable-checking/52413 "Staging in Sendable checking")的建议。

几周前，**@Douglas_Gregor** [提出了一些更改](https://forums.swift.org/t/pitch-staging-in-sendable-checking/51341 "[Pitch] Staging in Sendable checking")，试图解决在一些客户端或依赖项可能尚未更新时在模块中采用 Sendable 检查所涉及的一些问题。当模块最终更新时，这种方法可能会出现问题和隐藏的 BUG，以及 `Objective-C` 库如何能够控制其类型的可发送性。

**5. YR Chen** 开始讨论[解决 Swift 6 发布时的不一致问题](https://forums.swift.org/t/upon-swift-6-solve-inconsistency-within-the-language/52437 "Upon Swift 6: Solve inconsistency within the language")。

一些 API 破损的语言设计可以在 3 年后 `Swift 6` 的发布中修复。这是一个相当长的时间，通过 `Swift 3.2` 和 `Swift 4.2` 事实证明，过渡到 Swift 突破性发布要顺畅的多。

建议我们选择一些延迟的断点，目的是消除语言中的不一致。这些想法已经得到了社区的积极反馈，但是还是没有开始实施。

**6. Philippe Hausler** 提出了[定义 Clock, Instant, Date 和 Duration ](https://forums.swift.org/t/pitch-clock-instant-date-and-duration/52451 "[Pitch] Clock, Instant, Date, and Duration")的提案。

**时间的概念可以分为三个不同的部分：**

* 提供现在概念的项目加上一个在给定时间点后醒来的方法，* 时间点的概念
* 时间测量的概念

这三项分别是时钟、瞬间和持续时间。时间的测量可用于许多类型的 API，从高级网络连接超时概念到休眠任务的时间量。目前，测量时间类型的 API 采用 `NSTimeInterval` 又名 `TimeInterval`、`DispatchTimeInterval`，甚至像 `timespec` 这样的类型。

**7. Michael Ilseman** 提出了[实现声明性字符串处理](https://forums.swift.org/t/declarative-string-processing-overview/52459 "Declarative String Processing Overview") API 的想法。

字符串处理很困难，Swift 标准库目前提供的功能不足。我们建议添加两个新的声明性字符串处理 API，一个是熟悉的 `Regex` 文本，一个是更强大的 `Pattern` 结果生成器，以便 Swift 字符串处理起来更快速简便。

这是一个大型功能，最终将分为多个 `Swift Evolution` 提案。主要目的在于推动高级方向的讨论，并介绍该功能的关键点及其相互关系。

**8. Kelvin Ma** 开始讨论[长期支持 (“LTS”) 版本](https://forums.swift.org/t/we-need-long-term-support-lts-releases/52462 "long-term-support (“LTS”) releases.")。

对于那些没有关注开发主题的人，@mickeyl，@timdecode，我最近在 `Swift 5.5` 发布工具链中发现了数量惊人的高危险的堆栈损坏 BUG。

撇开 `Swift 5.5` 中堆栈损坏问题的技术方面不谈，在我们发布周期中采用某种形式的[“长期支持”（LTS）版本8](https://forums.swift.org/t/we-need-long-term-support-lts-releases/52462 "“Long-Term Support” (LTS) release 8 ")的概念是否值得，就像 Ubuntu 一直以来所做的那样。

**9. Anders Bertelrud** 提出了扩展插件 [SwiftPM 插件 API ](https://forums.swift.org/t/pitch-additional-api-available-to-swiftpm-plugins/52494 "pitch additional api available to swiftpm plugins")以提供更多上下文的提案。

`SE-0303` 引入了 SwiftPM 插件，特别关注构建工具插件（尤其是那些生成源代码的插件）。为了保持该提案的界限，插件可用的信息类型和数量针对生成构建命令的任务。

在开始考虑新类型的插件之前，扩展所有类型插件可用的信息似乎是明智的。未来的提案可能会为特定类型的插件添加特定的 API，但在此之前，一个好的起点似乎是让所有插件访问 SwiftPM 内部已经拥有的包图的提炼形式。这应该允许任何特定插件有很大的自由度。

我提出一份提案草案，用于扩展可用于 SwiftPM 插件的 API，并且很想听听大家的想法。在 SwiftPM 存储库中的 PR 中有一个实现。

**10. Guillaume Lessard** 提出了一项[扩大 withMemoryRebound 可用性](https://forums.swift.org/t/pitch-expand-usability-of-withmemoryrebound/52500 "expand usability of withMemoryRebound")的提案。

函数 `withMemoryRebound(to:capacity:_ body:)` 执行一个闭包，同时将一定范围的内存临时绑定到与被调用者绑定的类型不同的类型。

我们建议解除 `withMemoryRebound` 的一些显着限制，并启用重新绑定到更大的类型集，以及从原始内存指针和缓冲区重新绑定。

**11. Tim Condon** 向我们介绍了 [async/await 和 Vapor 的未来](https://forums.swift.org/t/async-await-and-the-future-of-vapor/52590 "async/await and the future of Vapor.")。

**12. Drew McCormack** 提出了一项提案，该提案将创建用于[在并发系统中处理共享数据的标准库数据结构](https://forums.swift.org/t/proposal-a-standard-library-type-for-working-with-shared-data-in-a-concurrent-system/52603 "standard library data structures designed for working with shared data in a concurrent system.")。

我想在这里提出这样一种类型：分支资源。

`BranchingResource` 将是一种类型，其携带的有效负载（即资源）具有通用参数。 资源将从单个分支开始，称为“`main`”或“`trunk`”或“`truth`”。 该应用程序可以添加任意数量的辅助命名分支。

**13. Pavel Yaskevich** 提出了[启用 multi-statement closure parameter/result type 推断](https://forums.swift.org/t/pitch-enable-multi-statement-closure-parameter-result-type-inference/52619 "enable multi-statement closure parameter/result type")的想法。

我建议通过从闭包主体中启用参数和结果类型推断来改进多语句闭包的推理行为。

这将使开发人员的类型推断不那么令人惊讶，并消除了在闭包中添加多一个表达式或语句可能会导致编译失败的问题。

## 推荐博文

### iOS 系列

[百度一面总结（含答案）](https://mp.weixin.qq.com/s/ZprPxK8NbMqpP9flmWRagg)

[使用 Swift 实现 Promise](https://mp.weixin.qq.com/s/PYzQN5HYXLU1JuXBAZNyhQ)

我最近在找如何使用 Swift 实现 `Promise` 的资料，因为没找到好的文章，所以我想自己写一篇。通过本文，我们将实现自己的 `Promise` 类型，以便明了其背后的逻辑。

[用 Swift 实现轻量的属性监听系统](https://mp.weixin.qq.com/s/8_utYi3y7I3ukh4VpnIM3A)

本文的主要目的是解决客户端开发中对“模型的一处修改，UI 要多处更新”的问题。当然，我们要知晓解决方案的细节和思考过程，以及看到其能达到的效果。我们会用到函数式编程的思想，以及伟大的“泛型”。


### SwiftUI 系列

[用 SwiftUI 实现 3D Scroll 效果](https://mp.weixin.qq.com/s/hfe1m5bNiA0DzdFTEvi9sQ)

学完本教程后，你就可以在你的 App 中把这种 `3D` 效果加入任何自定义的 SwiftUI 视图。

[如何让 SwiftUI 的列表变得更加灵活](https://mp.weixin.qq.com/s/TD0I96HSUoTNmOmfySCtYQ)

`List` 可能是 `SwiftUI` 附带的内置视图中最常用的一种，它使我们能够在任何 `Apple` 平台上呈现“类似于表格视图”的用户界面。今年，`List` 获得了许多非常重要的升级，使其更加灵活和易于定制。让我们看看都有哪些新功能。

[使用 SwiftUI 创建万花尺](https://mp.weixin.qq.com/s/snJJi9KYViFErdJAP1HEPQ)

为了完成一些真正意义上的绘图工作，我将带您通过创建一个简单的带 SwiftUI 的 `spirograph`。“Spirograph”是一种玩具的商标名称，你把一支铅笔放在一个圆圈里，然后绕着另一个圆圈的圆周旋转，创造出各种几何图案，称为轮盘赌——就像赌场游戏一样。

## 关于我们

公众号是由 Swift 爱好者共同维护，我们会分享以 Swift 实战、SwiftUI、Swift 基础为核心的技术内容，也整理收集优秀的学习资料。欢迎关注公众号：**Swift社区**，后台点击进群，联系我们获取更多内容。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">


感谢 SwiftWeekly 与我们的合作，开启 Swift 周报中文版发布之旅。周报仓库：https://github.com/SwiftCommunityRes

后续还会翻译大量资料到我们公众号，有感兴趣的朋友，可以加入我们，扫码添加微信

<img width="300" alt="fzhanfei" src="https://files.mdnice.com/user/17787/9a7911bf-75f2-40f5-866b-3171868bb92c.jpg">
