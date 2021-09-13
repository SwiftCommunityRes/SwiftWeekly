
## 前言

[California streaming](https://www.apple.com/apple-events/ "California streaming"). 我们都知道这意味着什么：马上将迎来重要的一天 —— `Apple` 宣布了 **9 月 14 日**的活动！ 他们在活动邀请中隐藏了一个彩蛋 —— [一种隐藏的 AR 体验](https://9to5mac.com/2021/09/07/apple-hypes-next-weeks-iphone-13-event-with-ar-portal-experience/ "一种隐藏的 AR 体验")，看起来很酷。 这也让全球的粉丝们纷纷猜测 `Apple` 即将发布的产品。

过去两周 `Swift 社区`非常活跃。 许多提案正在 `Swift` 迭代中产生，有些已经同意或拒绝，有些仍在审查中。 这些提议有助于促进 `Swift` 保持现代语言的地位，所以让我们继续努力吧！

## 新闻和社区

[John Sundell](https://twitter.com/johnsundell "John Sundell") 写了一篇文章解释  [Swift 表达式中的条件编译](https://www.swiftbysundell.com/articles/conditional-compilation-within-swift-expressions/ "Conditional compilation within Swift expressions")。

[Gabriel Theodoropoulos](https://twitter.com/gabtheodor "Gabriel Theodoropoulos") 写了一篇博文解释了如何[在 Swift 中使用可变参数](https://serialcoder.dev/text-tutorials/swift-tutorials/using-variadic-parameters-in-swift/ "Using Variadic Parameters in Swift")。

## Commits 和 pull requests

[Doug Gregor](https://twitter.com/dgregor79 "Doug Gregor") 合并了一个 `pull request`，该请求[添加了一个选项来构建并发库以进行后端部署](https://github.com/apple/swift/pull/39051 "Add an option to build the concurrency library for back deployment")。

[FW](https://github.com/fwcd "FW") 合并了一个[为 Swift 实现语义高亮](https://github.com/apple/sourcekit-lsp/pull/414 "
Implement semantic highlighting for Swift") 的 `pull request`。

## 同意的提案

[SE-0321](https://github.com/apple/swift-evolution/blob/main/proposals/0321-package-registry-publish.md "SE-0321") Package Registry Service - Publish Endpoint 已被[接受](https://forums.swift.org/t/accepted-se-0321-package-registry-service-publish-endpoint/51660 "Package Registry Service - Publish Endpoint")。

[SE-0304](https://github.com/apple/swift-evolution/blob/main/proposals/0304-structured-concurrency.md "SE-0304") Structured Concurrency [第四次](https://forums.swift.org/t/se-0304-4th-review-structured-concurrency/50281 "SE-0304 (4th review): Structured Concurrency")审查被[接受](https://forums.swift.org/t/accepted-with-modifications-se-0304-structured-concurrency/51850 "[Accepted with modifications] SE-0304: Structured Concurrency")。

## 拒绝的提案

[SE-0320](https://github.com/apple/swift-evolution/blob/main/proposals/0320-codingkeyrepresentable.md "SE-0320") 已返回进行[修订](https://forums.swift.org/t/returned-for-revision-se-0320-coding-of-non-string-int-keyed-dictionary-into-a-keyedcontainer/51706 "[Returned for revision] SE-0320: Coding of non String / Int keyed Dictionary into a KeyedContainer")。

审查的反馈是积极的，社区成员建议作者和核心团队认为可以采用以下几项改进：

1. 在 `CodingKeyRepresentable` 中添加 `String` 和 `Int` 的一致性，这将允许在 `CodingKeyRepresentable` 用作通用约束时主动使用 `String` 和 `Int` 键。
2. 使 `CodingKeyRepresentable` 协议的初始化通用。
3. 为 `RawRepresentable` 的一致性提供默认实现（带有 `String` 和 `Int` 原始值）。
4. 使内部 `_DictionaryCodingKey` 的初始值设定项 non-failable。

## 正在审查的提案

[SE-0320](https://github.com/apple/swift-evolution/blob/main/proposals/0320-codingkeyrepresentable.md "SE-0320")：允许将非 `String` / `Int` 键值 `Dictionary` 编码到 `KeyedContainer` 中 正在[接受第二次审查](https://forums.swift.org/t/se-0320-2nd-review-coding-of-non-string-int-keyed-dictionary-into-a-keyedcontainer/51710 "SE-0320 (2nd review): Coding of non String / Int keyed Dictionary into a KeyedContainer")。

* 第二次审查的重点是社区在第一次审查期间提出的改进建议，并通过 [swift-evolution#1435](https://github.com/apple/swift-evolution/pull/1435 "swift-evolution#1435") 进行讨论。

[SE-0292](https://github.com/apple/swift-evolution/blob/main/proposals/0292-package-registry-service.md "SE-0292")：Package Registry Service 修正[正在审查中](https://github.com/apple/swift-evolution/pull/1410 "修正 SE-0292 #1410")。

[SE-0303](https://forums.swift.org/t/amendment-se-0303-package-manager-extensible-build-tools/51763 "SE-0303: Package Manager Extensible Build Tools")：包管理器可扩展构建工具修正[正在审查中](https://github.com/apple/swift-evolution/pull/1434 "Amend SE-0303 to use @main for plugin entry point and adjust API accordingly #1434 ")。

[SE-0322](https://github.com/apple/swift-evolution/blob/main/proposals/0322-temporary-buffers.md "SE-0322")：正在审查[临时未初始化缓冲区](https://forums.swift.org/t/se-0322-temporary-uninitialized-buffers/51848 "Temporary uninitialized buffers")。

* 该提案引入了新的标准库功能，用于操作临时缓冲区，这些缓冲区优先分配给堆栈，而不是堆。
* `Swift-evolution` 线程：[Pitch] [临时未初始化缓冲区](https://forums.swift.org/t/pitch-temporary-uninitialized-buffers/48954 "Temporary uninitialized buffers")

## Swift 论坛

[Michael Verges](https://github.com/maustinstar "Michael Verges") 提出了[在 Swift 中添加可选 `throws` 的提案](https://forums.swift.org/t/pitching-optional-throws-in-swift/51650 "Pitching Optional Throws in Swift")。

* 在许多情况下，错误处理的权限不明确。开发者可能会质疑是处理还是传播错误。
* 选择抛出错误可以让调用者灵活地处理问题。
* 选择不抛出错误是为用户提供了简化语法（没有 `do-try-catch`）。

[Karl](https://forums.swift.org/t/api-changes-for-0-2-0/51647 "Karl") 向社区通报了 [WebURL](https://karwa.github.io/swift-url/ "WebURL") 0.2.0 版。

* 我正准备发布 `WebURL 0.2.0` 版本 。 这将是一个非常重要的版本，包括用于与 `System.framework` 和 `swift-system` 包集成的 `WebURLSystemExtras` 模块，并使项目与 `URL` 标准的最新版本保持一致。

[Patrick Goley](https://forums.swift.org/categories "Patrick Goley") 提出了[添加结构和类的析构赋值](https://forums.swift.org/t/pitch-destructuring-assignment-of-structs-and-classes/51593 "Destructuring Assignment of Structs and Classes")的建议。

* 析构赋值是一项语言功能，允许你提取值的多个部分，并将其分配给单个赋值语句中的多个变量。

[Steve Canon](https://twitter.com/stephentyrone "Steve Canon") 宣布 [Swift Numerics](https://forums.swift.org/t/1-0-0-release-notes/51641 "Swift Numerics") 的第一个稳定版本现已发布。

Austin 开始讨论 [SwiftNIO 中的 netlink 套接字支持](https://forums.swift.org/t/netlink-socket-support-in-swiftnio/51651 "Netlink socket support in SwiftNIO")。

[Konrad ktoso Malawski](https://forums.swift.org/categories "Konrad ktoso Malawski") 提出了一项实施 [Distributed Actors](https://forums.swift.org/t/pitch-distributed-actors/51669 "Distributed Actors") 的提案。 

* 随着最近 `Swift` 并发的引入，特别是该语言的参与者，`Swift` 在表达线程安全的并发程序方面获得了强大的基础构建。该提案旨在通过引入分布式参与者和与他们相关的位置透明度，扩大 `Swift`的参与者在分布式系统方面同样出色的工作能力。

[Max Desiatov](https://twitter.com/maxdesiatov "Max Desiatov") 告诉我们 [SwiftWasm 5.4.0](https://forums.swift.org/t/swiftwasm-5-4-0-has-been-released/51753 "SwiftWasm 5.4.0 has been released") 已经发布。

* 此版本与 `upstream` `Swift 5.4` 匹配，并允许您将 `Swift` 应用程序（只要它们不使用特定于其他平台的代码）编译到 `WebAssembly`，甚至可以在浏览器中运行。

[elsh](https://forums.swift.org/categories "elsh") 提出了添加[模块别名](https://forums.swift.org/t/pitch-module-aliasing/51737 "Module Aliasing")支持的建议。

随着 `Swift` 库和软件包分布更加广泛，模块名称有时会发生冲突。由于 `Swift` 中还没有模块命名空间，在这种情况下，库经常被迫重命名或固定在旧的非冲突版本上。这使得以下用例具有挑战性：

* 添加新的依赖项或升级，因为它可能会引入冲突：一个新的（或升级的）模块可以与依赖关系图中已经存在的另一个模块具有相同的名称。模块名称 `Logging` 是一个常见示例。

* 从上游库固定的旧版本升级到软件包的更新版本：考虑这样一个场景，其中 `MyApp` 依赖于模块 `Lib`，而 `Lib` 依赖于模块 `Logging`。 `MyApp` 还依赖于 `Logging`。 如果 `Lib` 固定到 `Logging 1.0.0`，则 `MyApp` 会停留在同一版本 `1.0.0`。

2021年9月3日，服务器工作组的 `Swift` 宣布了一项[特别更新](https://forums.swift.org/t/september-3rd-2021-special-update/51766 "September 3rd, 2021 Special Update")。

[Isabel Lima](https://forums.swift.org/t/pitch-introduce-expanded-parameters/51885 "Introduce Expanded Parameters") 向我们更新了有关[添加 Property Wrappers 共享存储](https://forums.swift.org/t/add-shared-storage-to-property-wrappers/49898 "Add shared storage to property wrappers ")的状态。

* `Swift` 是一种允许我们编写富有表现力的 `API` 接口语言。通过**约束泛型**、**方法重载**、**尾随闭包**和**默认参数**等功能，您可以在实现相当灵活的 `API`的同时减少代码重复。本提案旨在使用 `@expanded`（函数参数的新属性）增加语言的这一部分。

[John Holdsworth](https://github.com/johnno1962 "John Holdsworth") 提议引入 [ Unwrap 或 Throw 运算符](https://forums.swift.org/t/introducing-an-unwrap-or-throw-operator/51905 "Introducing an “Unwrap or Throw” operator")。

* 该提议是之前 [[Pitch] Introducing the “Unwrap or Die” operator to the standard library](https://forums.swift.org/t/pitch-introducing-the-unwrap-or-die-operator-to-the-standard-library/6207 "[Pitch] Introducing the “Unwrap or Die” operator to the standard library") 以及最近 [Moving toward deprecating force unwrap from Swift?](https://forums.swift.org/t/moving-toward-deprecating-force-unwrap-from-swift/43455 "Moving toward deprecating force unwrap from Swift?") 两个有争议提议的延伸。 后一个提议除了被锁定之外没有得出结论，这个提议在前一个提议上取而代之，建议使用 “`Unwrap or Throw`” 运算符可能是解决 `Swift` 中强制解包问题的更好解决方案，这让我很疑惑，我相信当用户的应用程序崩溃时，会影响到用户使用。

* 总之，我想提出一个 `!!` 运算符，强制打开和 `nil` 并之间的交叉，如果可选是 `nil`，则抛出。

## 关于我们

公众号是由 Swift 爱好者共同维护，我们会分享以 Swift 实战、SwiftUI、Swift 基础为核心的技术内容，也整理收集优秀的学习资料。欢迎关注公众号：**Swift社区**，后台点击进群，联系我们获取更多内容。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">


感谢 SwiftWeekly 与我们的合作，开启 Swift 周报中文版发布之旅。周报仓库：https://github.com/SwiftCommunityRes

后续还会翻译大量资料到我们公众号，有感兴趣的朋友，可以加入我们，扫码添加微信

<img width="300" alt="fzhanfei" src="https://files.mdnice.com/user/17787/9a7911bf-75f2-40f5-866b-3171868bb92c.jpg">
