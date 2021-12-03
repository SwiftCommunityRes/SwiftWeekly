
## 前言

在 199 期的 Swift 周报中，负责人 [Kristaps Grinbergs](https://twitter.com/fassko) 向所有读者发出邀请，内容如下：
> 大家好！ 我真心希望你们享受完感恩节，并且能够和你所爱的人一起度过这个假期。 也许你们中的一些人甚至玩过钱德勒发明的在 6 分钟内命名所有 50 个州的游戏。

> 感恩节之后的这段时间对 Swift 团队来说收获颇丰，今天有很多活动要讨论。 但在我们开始之前，我想利用这个机会说下一期将是我的最后一期，也许是这个项目的最后一期。 如果有人有兴趣接替我的职责，请告诉我。 我很想看到这个项目在我离开后继续存在并蓬勃发展。


> 为了 Swift 社区周报持续稳定的发布更新，我们希望邀请 Swift 爱好者参与**周报编辑**，同时邀请赞助商对我们平台赞助支持。

## 新闻和社区

**Keith Smiley** 分享了有关 Swift 5.5 的更新及其[精选分类过程](https://forums.swift.org/t/5-5-cherry-pick-triage-process/53574 "5.5 cherry pick triage process")。

**John Sundell** 写了[一篇文章](https://www.swiftbysundell.com/articles/count-vs-isEmpty/ "Using count vs isEmpty to check whether a collection contains any elements")，探讨如何使用 `count` 与 `isEmpty` 来检查集合是否包含任意元素。

**Will Lisac** 在推特上表示，适用于 `Raspberry Pi` 的 [Swift 5.5 Docker 镜像](https://github.com/wlisac/swift-on-balena "Swift on Balena") 现已可用。

由 **Feli** 创作的精彩[插图](https://fbernutz.github.io/images/summaries-ios-interview-topics/swift-evolution.jpg)。 她在各种会议上的[绘画作品](https://fbernutz.github.io/sketchnotes/)值得一看。

**Max Desiatov** 宣布 [SwiftWasm 5.5.0](https://blog.swiftwasm.org/posts/5-5-released/ "SwiftWasm 5.5.0 is now available") 现已可用。


## 同意的提案
**SE-0328** `Structural opaque result` 类型已被[接受并进行了修改](https://forums.swift.org/t/accepted-with-modifications-se-0328-structural-opaque-result-type/53789 "[Accepted with Modifications] SE-0328: Structural opaque result type")。 

  在审核期间，主要讨论了两个方面：
    - 可选类型的拼写。 提案将其保留为 ` (some P)? `，尽管 `some P?` 更简洁，可能被作为语法糖。 核心团队更同意这种保守的方法，稍后可以在对该功能有更多经验后重新考虑。
    - 当返回函数类型即 `f() -> (some P) -> Void` 时，在“消费”而不是“生产”位置使用 `some`。 `some` 关键字的其他用途正在讨论中，并且担心与某些未来特性存在潜在冲突。 由于在消费位置使用 `opaque result` 类型不是特别有用（这种函数在所有情况下都是不可调用的），因此核心团队决定将这种使用子集化，目前仅在返回函数类型的返回值中要求 `opaque result` 类型。



## 正在审查的提案

**SE-0332**：[包管理器命令插件](https://forums.swift.org/t/se-0332-package-manager-command-plugins/53769 "Package Manager Command Plugins")正在审查中。
  
  **SE-0303** 引入了在 SwiftPM 中定义构建工具插件的能力，允许在构建过程中自动调用自定义工具。 该提案扩展了该插件支持以允许定义自定义命令插件——用户可以直接从 SwiftPM CLI 或从支持 Swift 包的 IDE 调用的插件，以便对其包执行自定义操作。 

**SE-0331**: [从不安全的指针类型中删除 `Sendable` 一致性](https://forums.swift.org/t/se-0331-remove-sendable-conformance-from-unsafe-pointer-types/53768 "Remove Sendable conformance from unsafe pointer types")正在审查中。
  
  **SE-0302** 引入了 `Sendable` 协议，包括对各种语言结构的 `Sendable` 要求，各种标准库类型对 `Sendable` 的一致性，以及非公共类型隐式符合 `Sendable` 的推理规则。

  `Sendable` 的使用经验表明，这种表述是不必要的危险，并且会对隐式一致性产生意想不到的负面影响。

**SE-0333**：正在审查 [`withMemoryRebound` 的扩展可用性](https://forums.swift.org/t/se-0333-expand-usability-of-withmemoryrebound/53799 "Expand usability of withMemoryRebound")。

  函数 `withMemoryRebound(to:capacity:_ body:)` 执行一个闭包，同时将一定范围的内存临时绑定到与被调用者绑定的类型不同的类型。 我们建议解除 `withMemoryRebound` 的一些显着限制，并允许重新绑定到更大的类型集，以及从原始内存指针和缓冲区重新绑定。

  请注意，此提案与 **SE-0334** 同时运行，这也与不安全的指针可用性有关。

**SE-0334**：正在审查[指针可用性改进](https://forums.swift.org/t/se-0334-pointer-usability-improvements/53800 "Pointer Usability Improvements")。

该提案为 `UnsafePointer` 及其 `Mutable` 和 `Raw` 变量引入了一些质的改进。
  1. 添加一个 API 以获取一个 `UnsafeRawPointer` 实例，该实例从其起点前进到给定的对齐方式。
  2. 在给定 `UnsafePointer<T>` 的情况下，添加 API 以获取指向聚合 `T` 的存储属性的指针。
  3. 添加比较任意两种类型的指针的能力。
  
请注意，此提案与 **SE-0333** 同时运行，这也与不安全的指针可用性有关。

## Swift 论坛

### I
**Ethan Kusters** 开始讨论[在静态托管环境中支持托管 DocC 档案](https://forums.swift.org/t/support-hosting-docc-archives-in-static-hosting-environments/53572 "Support hosting DocC archives in static hosting environments")。

  这篇文章讨论了 Swift-DocC 和 Swift-DocC-Render 的增强功能，这将允许开发人员构建无需自定义路由即可托管的 DocC 档案。 这是专门为使 DocC 能够在其他静态托管环境中使用而设计的，最显着的是 GitHub Pages。

  此更改旨在作为解决紧迫需求的快速解决方案，并提供普遍的好处。 但请注意，我们已经听到社区的反馈，他们希望 Swift-DocC 直接发出静态 HTML，并且此功能在优先级列表中居高不下。

### II
**Sam Deane** 提出了一个想法来[实现一个默认的可初始化协议](https://forums.swift.org/t/default-initable-protocol/53723 "Default-initable Protocol")。 

**Kristaps Grinbergs** 遇到过工厂类型的情况，最终制定了一个协议来表示“可以使用不带参数的默认 `init` 构造这种类型”。

**Kristaps Grinbergs** 发现他感到惊讶： **(a)** 这个协议是否已经存在于标准库中的某个地方，以及 **(b)** 如果 `init()` 存在，Swift 是否可以自动使任何类型符合它。

### III
一个好的[提醒](https://forums.swift.org/t/a-built-in-angle-type/53726 "A built-in Angle type")， [库 Swift Numerics](https://github.com/apple/swift-numerics) 确实存在。

**Guillaume Lessard** 提出了使缓冲区切片更有用的[提案](https://forums.swift.org/t/pitch-buffer-partial-initialization-better-buffer-slices/53795 "[Pitch] Buffer Partial Initialization / Better Buffer Slices")，尤其是在缓冲区的部分初始化方面。

  `UnsafeBufferPointer` 系列的子序列具有 `UnsafeBufferPointer` 的所有 `[Mutable]Collection` API，但没有它们特定于缓冲区的 API。 这使得缓冲区的部分初始化以及其他任务变得困难。
  
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
