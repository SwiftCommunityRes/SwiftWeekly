
## 前言

**LeetCode 算法**到目前我们已经更新了 5 期，我们会保持更新时间和进度，每期的内容不多，我们希望大家可以在上班路上阅读，长久积累会有很大提升。

[Xcode 13.2 beta](https://developer.apple.com/documentation/xcode-release-notes/xcode-13_2-release-notes#Build-System "Xcode 13.2 beta") 中有一项新功能，可以通过使用更多 CPU 内核来加快构建速度。这个新的构建系统是可选的，所以你必须启用它。

> 为了 Swift 社区周报持续稳定的发布更新，我们希望邀请 Swift 爱好者参与**周报编辑**，同时邀请赞助商对我们平台赞助支持。

## 新闻和社区

**Nicole Jacque** 向我们介绍了 [Swift 5.6 发布流程](https://forums.swift.org/t/swift-5-6-release-process/53412 "Swift 5.6 Release Process")的最新情况。

**Mishal Shah** 通知我们[更新了 swift:main 的 llvm-project 分支](https://forums.swift.org/t/updating-llvm-project-branch-for-swift-main/53438 "Updating llvm-project branch for swift:main")。

**John Sundell** 宣布了 [CollectionConcurrencyKit](https://github.com/JohnSundell/CollectionConcurrencyKit "CollectionConcurrencyKit") —— 一个轻量级的 Swift 包，他将所有符合 `Sequence` 协议的 Swift 集合添加了标准 `map`、`flatMap`、`compactMap` 和 `forEach API` 的异步和并发版本。

**Steven Van Impe** [在高等教育中引入了 Swift](https://forums.swift.org/t/introducing-swift-in-higher-education/53445 "Introducing Swift in higher education")。

**Mishal Shah** 向我们通报了 Swift 项目的[假期时间表](https://forums.swift.org/t/holiday-schedule/53507 "Holiday Schedule")。

**Leonardo Maia Pugliese** 写了一篇文章[解释使用递归链接列表](https://holyswift.app/reverse-reverse-linked-list-linked-list-using-recursion "List : Using Recursion")。

**Antoine van der Lee** 在博客文章中[解释了 Swift 中的属性包装器](https://www.avanderlee.com/swift/property-wrappers/ "Property Wrappers in Swift explained with code examples")。

## 同意的提案

SE-0326 [Multi-statement 闭包参数/结果类型推断]( https://forums.swift.org/t/accepted-se-0326-multi-statement-closure-parameter-result-type-inference/53502 "Multi-statement closure parameter/result type inference")已被接受。

## 拒绝的提案

**SE-0327** 被拒绝[重新进行修订](https://forums.swift.org/t/returned-for-revision-se-0327-on-actors-and-initialization/53447 "SE-0327: On Actors and Initialization")。

审查讨论集中在初始化模型的复杂性上，并发现了一个更简单的模型，应该更容易推理。核心团队已退回此提案进行修订，以调查此新模型。感谢所有参与的人！

## 正在审查的提案

**SE-0329：** `Clock`, `Instant`, `Date`, 和 `Duration` 正在[审查中](https://forums.swift.org/t/se-0329-clock-instant-date-and-duration/53309 "Clock, Instant, Date, and Duration")。

**时间的概念可以分为三个不同的部分：**

1. 提供现在概念的项目以及在给定时间点后醒来的方式
2. 时间点的概念
3. 时间测量的概念

这三个项目分别是一个时钟、一个瞬间和一个持续时间。时间测量可用于多种类型的 API，从高级网络连接超时概念到休眠任务的时间量。目前，测量时间类型的 API 使用 `NSTimeInterval`（又名 `TimeInterval`）、`DispatchTimeInterval`，甚至 `timespec` 等类型。

## Swift 论坛

### I

**Ilias Karim** 提议将 [notContains](https://forums.swift.org/t/pitch-not-contains/53305 "notContains") 添加到标准库。

在 Swift 中，使用 `keypath` 符号过滤可以让函数式编程变的更加简洁和可读。

然而，没有一种直观的标准库方法可以按布尔值相反的方向过滤。我之前提议 `.toggled` 或 `.isFalse`，但是被驳回了。

### II

**Karl** 提议对 [RandomNumberGenerator](https://forums.swift.org/t/filling-buffers-using-randomnumbergenerator/53324 "RandomNumberGenerator") 完善两个小功能。

1. 填充缓冲区
2. 静态成员语法

### III

**Richard Wei** 提出了一个关于[强类型正则表达式捕获](https://forums.swift.org/t/pitch-strongly-typed-regex-captures/53391 "Strongly Typed Regex Captures")的想法。

捕获组是正则表达式的常用组件，允许程序员从匹配的输入中提取信息。捕获组将多个字符收集在一起作为一个单元，可以在正则表达式中反向引用，并在成功匹配的结果中访问。

### IV

**Joseph Heck** 开始讨论术语问题 —— `behaviors`、`shell` 和 `possible reductions`。

我会回答 “Yep, these could be all implementation details”。在挖掘 `swift-distributed-actor` 的源代码后，我了解了一些信息（`basic actor concept`, `mailboxes`, 和 `messages`）。

分布式 actors 代码使用了一些我不太熟悉的术语和措辞，大部分我可以通过推断和猜测知道是什么意思和关系，但是我认为最好是弄清楚他们之间的相互关系。

### V

**Ethan Kusters** 提出了非框架文档演示的改进。

并不是所有的 `Swift-DocC` 文档都是用框架构建的。在自定义工作流程中，Swift-DocC 将提供任何符号图形输入构建文档，例如 Swift-DocC 在 Swift.org 上的用户文档。然而不管符号图形的内容是什么，Swift-DocC 都将此文档描述为最上层页面上的“框架”。

例如，当 Swift-DocC 在 Swift.org 上的用户文档是用作“工具”，而不是“框架”时，在最上层页面上被描述为“框架”。

### VI

**Tom Doron** 基于 result builders 提出了 [SwiftPM](https://forums.swift.org/t/pre-pitch-swiftpm-manifest-based-on-result-builders/53457 "SwiftPM Manifest based on Result Builders") 清单。

`Swift Package Manager`（以下简称 SwiftPM）是在 2016 年 Swift 开源时发布的。SwiftPM 使用一个名为 `Package.swift` 的文件，用户可以用它来描述包的源结构、构建工件（例如构建生成的任何可执行文件或库）以及 对其他包的任何依赖。

SwiftPM 的清单是一个 Swift 程序（各种脚本），SwiftPM 在安全沙盒中作为单独的进程构建和执行，以生成代表所需包配置的静态数据模型。 目前，静态表示基于 JSON，该 JSON 的详细内容是内部实现细节。 JSON 模型后来被反序列化并加载到父进程内存空间，从而驱动 SwiftPM 的工作流，如依赖解析、构建、测试等。

### VII

**Konrad ktoso Malawski** 分享了一个实现[分布式 actor 隔离](https://forums.swift.org/t/proposal-distributed-actor-isolation/53460 "Distributed Actor Isolation")的提议。

该提案仅侧重于支持分布式 actor 所需的隔离规则，并从大型整体分布式 actor `pitch 8` 中分离出来。我们的目的是提出这个非常大的提案的各个部分，作为单独但是又相互关联的提案，类似于去年引入 `Swift Concurrency` 的方式。通过这种方式，我们希望保持内容数量的可审查性，并且讨论也集中在手头的特定主题上。

### VIII

**Holly Borla** 提出了一项 [Introduce existential `any`](https://forums.swift.org/t/pitch-introduce-existential-any/53520 "Introduce existential any")的提案。

Swift 中的现有类型具有一个非常轻量级的拼写：类型上下文中的普通协议名称表示存在类型。多年来，这已经从引起混乱上升到**主动危害**的程度，导致程序员走上了错误的道路，一旦他们遇到值级抽象的基本限制，通常需要他们重新编写代码。该提案通过使用 any 注释这些类型，使语言中的存在类型的影响变得明确。

## 推荐博文

[LeetCode - #5 求最长的镜像字符串](https://mp.weixin.qq.com/s/XUY2DCQfRVPmt-5cXRvRag)

[Swift 编译器 Crash—Segmentation fault 解决方案](https://mp.weixin.qq.com/s/AiMkjBRg-UHEpqv5WsGyGA)

[狐友 iOS 客户端埋点的前世今生](https://mp.weixin.qq.com/s/AacxlJd315kdy9N73dRnyw)

[从野指针探测到对iOS 15 bind 的探索](https://mp.weixin.qq.com/s/OG5WQR3m-8G0617yoEGgvg)

[iOS 如何监测 FPS](https://mp.weixin.qq.com/s/O9ABm4lntZHmMaDcwNAoFQ)

## 关于我们

公众号是由 Swift 爱好者共同维护，我们会分享以 Swift 实战、SwiftUI、Swift 基础为核心的技术内容，也整理收集优秀的学习资料。欢迎关注公众号：**Swift社区**，后台点击进群，联系我们获取更多内容。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">


感谢 SwiftWeekly 与我们的合作，开启 Swift 周报中文版发布之旅。周报仓库：https://github.com/SwiftCommunityRes

后续还会翻译大量资料到我们公众号，有感兴趣的朋友，可以加入我们，扫码添加微信

<img width="300" alt="fzhanfei" src="https://files.mdnice.com/user/17787/9a7911bf-75f2-40f5-866b-3171868bb92c.jpg">
