## 前言

**本期是 Swift 编辑组自主整理周报的第十五期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

一个人真正觉悟的时候，就会去追寻内心世界真正的财富。**Swift社区**渴望走进你的内心，与你一起拥抱财富！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果高管确认，新品即将上市
> 
> 提案：围绕 `Macros` 提出多个提案
> 
> Swift 论坛：新发布 VSCode devContainers 的新功能
>
> 推荐博文：使用 `async/await` 完成后台任务管理
> 
> **话题讨论：** 
> 
> 程序员养生喝什么？

## 新闻和社区

### 苹果高管确认，新品即将上市

众所周知，苹果对待还未正式发布的产品，向来采取较为严格的保密政策。
不过，在去年 3 月举办的苹果春季发布会上，苹果对新品的一波预告，似乎成了近些年来罕有的例外。

![](https://pics0.baidu.com/feed/58ee3d6d55fbb2fbd4417ebff105eeaf4723dc94.jpeg@f_auto?token=aac9eaa5fbccbd32593233adc298b6cf)

苹果硬件工程高级副总裁 John Ternus 在发布会结尾，暗示了即将要推出新款 Mac Pro 的消息。

实际上这也并不稀奇，苹果早在 2020 年就曾宣布了一项「两年计划」，预计在两年时间内将旗下所有 Mac 产品都转向自研芯片，彻底抛弃英特尔。

而如今两年之期已到，Mac 产品线中，也仅剩 Mac Pro 一款产品还未搭载 M 系芯片。

就在许多期待这款新 Mac 的小伙伴望眼欲穿之际，另一位苹果高管为我们带来了与之相关的最新消息。

近期，苹果全球产品营销副总裁 Bob Borchers 接受了 India Today 的采访，并针对一些产品问题进行了回复。

![](https://pics0.baidu.com/feed/8435e5dde71190ef286707907054531dfcfa60b8.jpeg@f_auto?token=3c29a4745197240d1fc4ebb55a85bd89)

Bob Borchers 表示，在将大部分 Mac 产品都搭载 M 系芯片后，现阶段苹果的「两年计划」还在进行中。

也就是说，苹果的终极目标是将 Mac 产品线完成全系自研后，将自研芯片扩展至所有苹果产品中，其中自然也包括新款 Mac Pro。

从这两年的苹果的一系列动作来看，推动 Mac 全面自研化的进程已经接近收官，目前只差 Mac Pro。
### 对等组基准指标现已在“App 分析”中发布

App Store Connect 中的“App 分析”是一款实用的工具，它具备丰富的功能，可帮助你了解和改进你的 App 在 App Store 中的表现。借助与获客率、使用和盈利策略相关的指标，你可以通过“App 分析”监控客户生命周期 (从认知到转化再到留存) 中各个阶段的结果。对等组基准指标会将你 App 的表现与 App Store 中类似的 App 进行比较，从今天开始，你可以使用此功能在有效情境中衡量 App 的表现。现在，你将获得更多见解，更有效地发现业务增长机会。

对等组基准指标会在整个客户旅程中提供独到且实用的新见解，帮助你更准确地了解 App 在哪些方面表现出色，并找到改进的方向。系统会根据 App 的 App Store 类别、商业模式和下载量将 App 归入不同的对等组中，以确保比较数据的相关性。此外，对等组基准指标使用行业领先的差分隐私技术，提供相关且切实可行的见解，同时确保单个 App 表现的私密性。

查看新的基准指标数据，然后利用 App Store Connect 中的其他工具来改善转化率、收益、崩溃率和用户留存率。你可以测试产品页上的不同元素以找出最能引起用户共鸣的部分，创建出额外的产品页版本以重点推介特定功能或内容，获得有关 Beta 版 App 的反馈，提供 App 内活动以鼓励参与，等等。

## 提案

### 正在审查的提案

[SE-0382](https://github.com/apple/swift-evolution/blob/main/proposals/0382-expression-macros.md "SE-0382") **Expression Macros** 提案重新恢复审查。该提案已在 **二十期周报** 正在审查的提案模块做了详细介绍。

[SE-0388](https://github.com/apple/swift-evolution/blob/main/proposals/0388-async-stream-factory.md "SE-0388") **增加 Async[Throwing]Stream.makeStream 方法** 提案正在审查。

改天建议引入辅助方法来创建 `AsyncStream` 和 `AsyncThrowingStream` 实例，使开发者使用起来更加方便。

[SE-0389](https://github.com/apple/swift-evolution/blob/main/proposals/0389-attached-macros.md "SE-0389") **Attached Macros** 提案正在审查。

`Attached Macros` 是 Swift 中 `Macros` 愿景的一部分，该提案以 SE-0382 `Expression Macros` 的思想和动机为基础，涵盖了大量新的用例，将参考该提案以了解 `Macros` 如何集成到语言中的基本模型。

[SE-0390](https://github.com/apple/swift-evolution/blob/main/proposals/0390-noncopyable-structs-and-enums.md "SE-0390") **引入 @noncopyable ** 提案正在审查。

该提案引入了 `@noncopyable` 类型（也称为 `move-only` 类型）的概念。 `@noncopyable` 类型的实例始终具有唯一所有权，这与可以自由复制的普通 Swift 类型不同。

[SE-0391](https://github.com/apple/swift-evolution/blob/main/proposals/0391-package-registry-publish.md "SE-0391") **Package Registry 公开发布** 提案正在审查。

`Package Registry` 公开发布后，可以对外公开可用。 从 Swift 5.7 开始，SwiftPM 支持使用任何实现与 SE-0292 一起提出的服务规范的注册表的依赖项解析和包下载。

## Swift论坛

1) 提议[包管理器支持自定义宏](https://forums.swift.org/t/weburl-keyvaluepairs-api/63164 "包管理器支持自定义宏")
**介绍**
宏提供了一种通过对输入源代码执行任意句法转换来生成新代码来扩展 Swift 的方法。 一个例子是之前在[SE-0382](https://github.com/apple/swift-evolution/blob/main/proposals/0382-expression-macros.md) 中提出的表达式宏。该提案涵盖了如何定义、构建和分发自定义宏作为 Swift 包的一部分。
**动机**
[SE-0382](https://github.com/apple/swift-evolution/blob/main/proposals/0382-expression-macros.md) 和 [A Possible Vision for Macros in Swift](https://gist.github.com/DougGregor/4f3ba5f4eadac474ae62eae836328b71) 涵盖了宏本身的动机，将它们定义为包的一部分将提供一种直接的方式来重用和分发宏作为源代码。
**提议的解决方案**
在外部程序中实现的宏可以通过新的宏目标类型声明为包的一部分，定义在 CompilerPluginSupport 库：
```Swift
public extension Target {
    /// Creates a macro target.
    ///
    /// - Parameters:
    ///     - name: The name of the macro.
    ///     - dependencies: The macro's dependencies.
    ///     - path: The path of the macro, relative to the package root.
    ///     - exclude: The paths to source and resource files you want to exclude from the macro.
    ///     - sources: The source files in the macro.
    static func macro(
        name: String,
        dependencies: [Dependency] = [],
        path: String? = nil,
        exclude: [String] = [],
        sources: [String]? = nil
    ) -> Target {
}
```
类似于包插件（SE-0303“包管理器可扩展构建工具”），宏插件被构建为主机的可执行文件（即，运行编译器的地方）。 编译器从构建系统接收到这些可执行文件的路径，并将作为编译过程的一部分按需运行它们。 宏可执行文件可自动用于任何通过包清单传递依赖于它们的目标。
包含宏的实现、定义和客户端的最小包如下所示：
```Swift
import PackageDescription
import CompilerPluginSupport

let package = Package(
    name: "MacroPackage",
    targets: [
        .macro(name: "MacroImpl"),
        .target(name: "MacroDef", dependencies: ["MacroImpl"]),
        .executableTarget(name: "MacroClient", dependencies: ["MacroDef"]),
    ]
)
```
宏实现将在类似于 package plugins 的沙盒中执行，防止文件系统和网络访问。 这是一种鼓励宏不依赖于任何状态的实用方法，除了它们被赋予扩展的特定宏扩展节点及其子节点（但不是其父节点），以及宏扩展上下文专门提供的信息。 如果将来宏需要访问其他信息，这将通过扩展宏扩展上下文来实现，这也为编译器提供了一种机制来跟踪宏实际查询的信息。

2) 新发布[VSCode devContainers 的新功能](https://forums.swift.org/t/a-few-features-for-vscode-devcontainers-now-available/63485 "VSCode devContainers 的新功能")
这些新功能它们让我的生活更轻松，所以我将它们添加到可用容器的通用目录中，以支持在 Swift:5.7 及更高版本中使用 .devContainer 设置。 具有三个独立的功能：
* jemalloc - 安装 jemalloc 库（如果你正在探索使用 package-benchmark 1 会很有帮助）
* swiftpm - 安装构建 SwiftPM 所需的 sqlite 和 libsqlite 库
* foundationnetworking - 安装 libcurl-openssl 以支持基础网络

3) 提问[如何测量结构实例的实际内存占用量？](https://forums.swift.org/t/how-to-measure-the-actual-memory-footprint-of-an-instance-of-a-struct/63474 "如何测量结构实例的实际内存占用量？")
MemoryLayout.size(ofValue: theInstance) 但它只返回错误的大小（可能是指针的大小）。
将这个问题的范围缩小到仅结构体。例如：测量仅包含结构体的字典结构占用了多少内存。
回答：
一旦部分“值”没有存储在堆栈中，这个问题也变得没有意义。 如果我说 let newDict = existingDict，占用空间估计函数可能会说它们每个总共有 1024 个字节，因此您可能会得出结论，它们加起来是 2048 个字节。 但事实并非如此，因为 Dictionary 被记录为像这样的简单副本共享存储，直到一个值或另一个值发生变化； 实际总数大约是 1032 字节。 同样，您可以想象在这些字典中还嵌套了其他字典； 如果您修改其中一个顶级词典，将分配新的存储空间，但仍将共享嵌套词典。
说“这个值能保持多少内存”绝对是有价值的，但在一种具有无处不在的引用计数（或垃圾收集，就此而言）的语言中，它没有一个简单的答案。

4) 讨论[为什么有这么多“@”表达式？](https://forums.swift.org/t/why-so-many-expressions/63461 "为什么有这么多“@”表达式？")
我不是每天都使用 Swift，因为它实际上是 Apple 专用的语言。
所以当我最近回到它时，我发现了两个新问题。
使用 Swift 5 编译器编译后运行良好的代码在使用 5.9-dev 编译器构建时无法正确运行。 后者会产生以前不存在的运行时错误。
查看一些示例代码，我看到比以前更多的 @ 表达式，例如 @frozen、@State、@stateobject 等。 有没有完整的列表？ 这些都有什么用？ 文档（在其存在的范围内）含糊不清。 这些表达式不会降低代码的可读性吗？
回答：
一些“@表达式”内置于编译器中，如@available、@propertyWrapper、@dynamicMemberLookup。
大多数由 SwiftUI 等库以 Property Wrappers 的形式提供
这些表达式不会降低代码的可读性吗？相反，与手卷替代方案相比，它们大大提高了可读性。
属性包装器让您可以提取自动应用于获取或设置值的可重用行为（如 JS 2 中的处理程序方法或 Python 1 中的描述符）。
例如，每次写入标记为@Published 的属性时，您的 ObservedObject 都会自动发出一个 objectWillChange 事件。 如果 @Published 属性包装器不存在，代码中的 @ 符号就会减少，但您还需要在每次写入属性时执行类似 objectWillChangePublisher.send() 的操作。 这很费力，引入了疯狂的重复和忘记这样做的机会。 在不知不觉中，您会在论坛上看到类似以下的问题：
提问者：“为什么当我更改此属性时我的视图没有更新？”
回答者：“因为你忘记了 objectWillChangePublisher.send()。”
提问者：“为什么框架不能自动为我调用它？”
因此，出现了属性包装器。

5) 提问[SwiftUI 如何只启动一次 onApper？](https://forums.swift.org/t/how-to-launch-effect-onapper-only-once/63455 "SwiftUI 如何只启动一次 onApper？")

6) 提问[选择取消 macOS 上的自动 Foundation 链接？](https://forums.swift.org/t/opting-out-of-automatic-foundation-linking-on-macos/63430 "选择取消 macOS 上的自动 Foundation 链接？")

7) GSoC[Swift参加GSoC 2023！](https://forums.swift.org/t/swift-to-participate-in-gsoc-2023/63441 "Swift参加GSoC 2023！")
很高兴与大家分享，Swift 将再次参加 Google Summer of Code 3！ 到现在为止，也许您已经看到潜在的参与者开始了一些话题
去年，我们设法运行了 5 个很棒且成功的项目。 如果您对它们是什么感到好奇，您可以直接在 Swift 博客 10 上从他们的参与者和导师那里了解相关信息。
今年，我们已经收集了一些潜在的项目想法以及他们自愿参与 Swift 网站的导师：Swift.org - GSoC 2023 的项目想法 23。
今年我们准备了一个专门针对 GSoC 6 的新论坛类别，因为我们发现虽然有些项目有很好的空间来讨论它（比如服务器类别），但有些项目以前并没有真正的讨论空间（ 之后）他们开始了。 我们仍然鼓励使用 gsoc-2023 标签 2 来标记所有与 gsoc 相关的线程，并且并非所有线程都需要属于这个新类别。 然而，这个类别应该有助于引导讨论，否则没有一个很好的归宿。
与往常一样，我们期待听到您的项目想法，并建议在新论坛类别中打开一个主题，描述您的项目想法以及您需要帮助以使其成为现实的领域。 如果某个项目看起来很有吸引力并且有可能在 GSoC 时间框架内实现，我们将尽最大努力为其寻找导师。
我们对有助于“Swift 项目”的项目感兴趣，其中包括各个重点领域的各种项目。 以下是一些可能成为 GSoC 项目创意候选者的项目示例：
Swift 编译器 2 本身（类型检查器、前端、后端、标准库），项目可以包括改进调试、性能、添加一个小功能，
相关包，如 Collections、Async Algorithms、SwiftSyntax、SourceKit-LSP、DocC、Distributed Actor Cluster 等 1，
主要由服务器生态系统使用的包，包括为尚未支持的数据库、队列或其他 API 提议新的库，
Swift Package Manager 2、Swift 网站、文档或 Swift 的其他部分。
您可以在我们的 Swift 博客上回顾去年的成功项目 10 ，了解接受了哪些类型的项目。
今年我们还为非 Apple 员工开放了导师角色。 如果您是一位经验丰富的 Swift 贡献者，并且有兴趣作为 GSoC 导师为我们的参与者提供指导，请留意进一步的公告，或使用下面的联系方式与我联系。 这对我们来说是一个新流程，所以我们将看看它是如何运作的，但我们有兴趣向更广泛的 Swift 项目贡献者开放指导。
作为 GSoC 体验的一部分，我们也在考虑提供更多机会与其他 Swift 贡献者会面。

8) GSoC[有兴趣使用 Swift 中的脚本来改善用户体验](https://forums.swift.org/t/interested-in-improving-user-experience-with-scripting-in-swift/63478 "有兴趣使用 Swift 中的脚本来改善用户体验")

## 推荐博文

[使用 async let 在 Swift 中并行运行后台任务](https://swdevnotes.com/swift/2023/use-async-let-to-run-background-tasks-in-parallel-in-swift/ "Use async let to run background tasks in parallel in Swift")

**摘要：** 本文介绍了如何在后台执行长期运行的任务并保持 UI 响应。`async/await` 提供了执行异步任务的干净机制。允许并行执行多个后台任务。

[如何在 Swift 中取消后台任务](https://swdevnotes.com/swift/2023/how-to-cancel-a-background-task-in-swift/ "How to cancel a background task in Swift")

**摘要：** Swift 5.5 中引入的 `async/await` 语法允许以可读的方式编写异步代码。异步编程可以提高应用程序的性能，同时很重要的一点是要取消不需要的任务，以确保暂时不需要的后台任务不会干扰应用程序。本文演示了如何取消任务，并解释了如何自动取消子任务。

[如何在 Flutter 中使用 async/await](https://sarunw.com/posts/how-to-use-async-await-in-flutter/ "How to use async/await in Flutter")

**摘要：** 在本文中展示了一系列异步实现示例，并在最后给出三个组件（`Future`，`async` 和 `await`）的使用说明。

## 话题讨论

**程序员养生喝什么？**

123

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
