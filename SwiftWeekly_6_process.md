
## 前言

译者言：周日立冬，北方多地迎来 2021 年的第一场雪，上海也降下大雨，此时你所在的城市降温了吗？记得添衣保暖，避免感冒生病影响工作和生活。

[Xcode 13.2 Beta](https://developer.apple.com/documentation/xcode-release-notes/xcode-13_2-release-notes#Swift) 版已具备并发支持，该特性将有助于解决很多 Swift 开发者的某些痛点。或许 Swift 内置的并发系统最重要的好处是，它允许以更简单的方式，并行执行多异步任务。可以想像，通过增加执行任务的速度这将节省我们更多时间。

[Kristaps Grinbergs](https://twitter.com/fassko) Swift 周报负责人在本期周报中公开自己将不再领导 Swift 周报项目，原文如下：

我非常高兴地编写这么优秀并且已经运营了三年的 Swift 新闻周报。我遇到了很多了不起的人，并且感谢你们所有人，我已经收获了很多！ 这是为什么打出下面这句话，让我感慨万千的原因。第 200 期周报将是我运营的最后一期。我已经决定不再领导这个项目，并且怀着愉悦的兴奋，我正在寻找愿意继续管理 Swift 周报的人。

> 为了 Swift 社区周报持续稳定的发布更新，我们希望邀请 Swift 爱好者参与**周报编辑**，同时邀请赞助商对我们平台赞助支持。

## 入门任务
**SR-15408** [Swift-DocC] [用含有空格的回调显示名称构建文档会产生一篇无法阅读的文章](https://bugs.swift.org/browse/SR-15408 "Building documentation with a fallback display name that includes a space produces a broken-looking article") 

译者注：如果将带有空格的回调显示名称（如 --fallback-display-name "My Display Name"）以及有效的符号图传递给 docc，DocC 会生成一篇以“我的显示名称”作为 H1 的文章标题并将其组织在顶级框架页面上的“文章”主题组下。

## 新闻和社区

新的 [Xcode 13.2 Beta](https://developer.apple.com/documentation/xcode-release-notes/xcode-13_2-release-notes#Swift) 增加了对 macOS 10.15、iOS 13、tvOS 13 和 watchOS 6 或更高版本的 Swift 并发支持。 这种支持包括`async/await`、[actor](https://developer.apple.com/documentation/swift/actor)、全局 `actor`，结构化的并发及其任务 API。

**Tim Condon** 发布了 [Vapor](https://forums.swift.org/t/async-await-has-arrived-in-vapor/53077 "Async/await has arrived in Vapor") 已经支持 `async/await`。

**Konrad ktoso Malawski** 写了一篇介绍 [Swift Distributed Actors](https://www.swift.org/blog/distributed-actors/ "Introducing Swift Distributed Actors") 的文章。

**Marc Aupont** 将加入 Diversity in Swift 工作组。

Swift 下载链接已移至新位置以提供更快的下载速度！ 工具链将托管在 [download.swift.org](https://www.swift.org/download/)，它将使用与当前 URL 类似的模式。 要使用新 URL，请将 **swift.org/builds/** 替换为 **download.swift.org/**。 从 2021 年 10 月 26 日开始，**swift.org/builds** URL 已重定向到新的子域。

**Sarun Wongpatcharapakorn** 写了一篇博文解释 Swift 中的 [KeyPath](https://sarunw.com/posts/what-is-keypath-in-swift/ "What is a KeyPath in Swift")。

## Commits 和 pull requests
**Erik Eckstein** 合并了一个 `pull request`，该请求[实现了性能注释的原型](https://github.com/apple/swift/pull/39902 "First prototype of Performance Annotations")，如 Swift 中的 `@_noLocks` 和 `@_noAllocation`。

**Slava Pestov** 合并了一个 `pull request`，该请求[改进了对“身份一致性”的处理 [P].[P] => [P]]("RequirementMachine: Improved handling of identity conformances" [P].[P] => [P]")。

**John McCall** 合并了一个 `pull request`，该请求[修复了高度对齐的结果类型的未来片段的对齐方式](https://github.com/apple/swift/pull/39829 "Fix the alignment of future fragments for highly-aligned result types")


## 同意的提案

**SE-0325** [附加包插件 API](https://forums.swift.org/t/accepted-with-modifications-se-0325-additional-package-plugin-apis/53086 "[Accepted with Modifications] SE-0325: Additional Package Plugin APIs") 提案已被修改并同意。


## 正在审查的提案

**SE-0326**: [多语句闭包参数/结果类型推断](https://forums.swift.org/t/se-0326-multi-statement-closure-parameter-result-type-inference/52964 "Multi-statement closure parameter/result type inference")正在审查中.

**Kristaps Grinbergs** 建议通过启用闭包体的参数和结果类型推断，来改进多语句闭包推断行为。 这将令类型推断更符合开发者的预期，并且移除现存的行为壁垒，即向闭包添加一个表达式或语句会导致编译失败的结果。

**SE-0327**: [On Actors and Initialization](https://forums.swift.org/t/se-0327-on-actors-and-initialization/53053 "On Actors and Initialization")正在审查中。

**Actors** 是 Swift 中相对较新的名义类型，为其可变态提供了数据竞争安全性。数据保护是通过将每个 `actor` 实例可变状态一次最多隔离一个任务来实现的。引入 `actor`（[SE-0306](https://github.com/apple/swift-evolution/blob/main/proposals/0306-actors.md "Actors")）的提案非常庞大和详细，但忽略了创建和销毁 `actor` 隔离状态的一些细微之处。 该提案旨在支持一个 `actor` 的定义，为了弄清一个 `actor` 实例的数据隔离何时开始和结束，以及在一个 `actor` 的 `init` 和 `deinit` 函数声明中能够做什么。

**SE-0328**：[Structural opaque result](https://forums.swift.org/t/se-0328-structural-opaque-result-types/53248 "SE-0328: Structural opaque result types") 类型正在审查中。

**Opaque** 结果类型可以用作函数的结果类型、变量的类型或者下标的结果类型。在所有情况下， **Opaque** 结果类型必须是整个类型。该提案建议解除该限制，并且在“结构性”的位置中允许使用 **Opaque** 结果类型。

## Swift 论坛

### I
一个来自 **@justkwin** 关于 `Foundation` 如何使用 `URL` 结束来表示 `file.paths` 的小历史[教训](https://forums.swift.org/t/get-folders-number-of-elements/ "Get Folder’s Number of Elements")。

### II
**Anders Bertelrud** 提出了添加[包管理器命令插件的提案](https://forums.swift.org/t/pitch-package-manager-command-plugins/53172 "[Pitch] Package Manager Command Plugins")。

**SE-0303** 引入了第一种 SwiftPM 插件，专注于使用自定义构建工具调用扩展构建系统的能力（特别是为了生成源代码）。 那些插件一直计划成为第一种被 SwiftPM 支持的插件。

**Kristaps Grinbergs** 想提出一个提案草案，为 SwiftPM 添加另一种更通用目的的“命令插件”。 这些类型的插件可以由用户直接调用，用于源代码格式化、文档生成、测试报告生成等。命令插件不一定与构建系统有任何关系。

这些自定义命令插件一个重要的方面是它们可以要求插件主机（SwiftPM 或支持包的 IDE）按需生成专门的信息，或着初始化构建或测试运行。 这是提案草案中最需要仔细审查的部分。 在使 API 足够丰富以令其尽可能有用，同时也使其足够通用以不仅在 SwiftPM 中而且 IDE 中支持 Swift 包，这里有一个相悖的因素。

### III
**Guillaume Lessard** 提出了一项提案，该提案将实现[指针族初始化改进](https://forums.swift.org/t/pitch-pointer-family-initialization-improvements/53168 "[Pitch] Pointer family initialization improvements")。

`UnsafeMutablePointer` 系列中的类型通常需要手动管理内存分配，包括对其初始化状态的管理。 涉及的状态是在分配后:

  1. 未绑定和未初始化时（当在 `UnsafeMutableRawPointer.allocate()` 返回）
  2. 绑定到一个类型，并且未初始化（从 `UnsafeMutablePointer<T>.allocate()` 返回）
  3. 绑定到一个类型，并且初始化

无论何时它未曾被初始化，内存都能够安全地销毁。

不幸的是，不是每一个 `UnsafeMutablePointer` 系列中的类型有这个必要功能，以用于全面管理它内存初始化的状态。 我们打算在本提案中解决这个问题，并提供在各种更广泛的情况下管理初始化状态的功能。

### IV
**Kelvin Ma** 展开了一个关于 `AsyncStream` 构造函数的[讨论](https://forums.swift.org/t/asyncstream-constructor-which-also-returns-its-continuation/53251 "`AsyncStream` constructor which also returns its Continuation")，该构造函数也返回其 `Continuation`。

有没有什么方法我们可以向 `AsyncStream` 添加一个 API，它直接返回 `Continuation`，从而我们就不必把它的闭包“调来调去”？

一般来说，我也觉得 `AsyncStream` 真的很难使用，因为迭代在创建了 `AsyncStream` 的同一个任务中发生，甚至是没有并发迭代时曾出现。 这使“订阅” `actor` 对象生成的事件变得困难，即使订阅方法被标记为 `nonisolated`。

### V

**Adam Fowler** 积极将 `MQTTNIO` 库[加入 `SSWG` 包列表中](https://forums.swift.org/t/mqttnio/53238 "Mqttnio").

MQTT 是一种通常用于与 IoT（物联网）设备进行通信的消息传递协议。 它是一种轻量级的发布/订阅消息传输，旨在具有较小的代码占用空间和网络带宽。

### VI

**Cory Benfield** 向我们[更新了](https://forums.swift.org/t/swiftnio-swift-version-support/53232 "SwiftNIO Swift version support")关于 `SwiftNIO Swift` 版本支持。

SwiftNIO 团队已将其作为我们工作流程的主要支柱，以尝试在相当长的时间内支持 Swift 版本。大多数用户没有利用这一点，更愿意继续使用最新版本的 Swift，但我们认为重要的是你要有信心，新编写的应用程序将在未来获得一些有意义的支持。

### VII

**Victoria Mitchell** [写了一篇](https://forums.swift.org/t/extending-swift-docc-to-support-objective-c-documentation/53243 "Extending Swift-DocC to support Objective-C documentation")关于扩展 `Swift-DocC` 以支持 `Objective-C` 的文档。

`DocC` 的架构目前仅支持 `Swift` 一个语言的渲染符号文档。然而，有些跨语言项目可以从将多个“语言变体”收集到同一组文档中受益，例如可以被 `Swift` 中调用的 `Objective-C` API，反之亦然。

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
