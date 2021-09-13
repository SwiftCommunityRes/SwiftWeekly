## 前言

从本周开始，我们 Swift 社区公众号将开始与 SwiftWeekly 合作更新关于 Swift 社区最新的进展与动向。让我们乘着社区的风帆，一起荡起双桨，让 Swift 成为世界上最好的语言。

## 播客

在 Swift by Sundell 播客的[第 103 期](https://www.swiftbysundell.com/podcast/103/ "Swift by Sundell 第 103 期")中，SwiftLee 的创建者 [Antoine van der Lee](https://twitter.com/twannl "Antoine van der Lee") 加入了 [John Sundell](https://twitter.com/johnsundell "John Sundell")。

他们从新的 concurrency 系统到 convenience 特性以及各种改进等方向讨论了 Swift 5.5 新引入的一部分功能。

## 新闻和社区

Xcode 各版本的 [最低要求和支持的 SDK](https://developer.apple.com/cn/support/xcode/ "最低要求和支持的 SDK")

[Antoine van der Lee](https://twitter.com/twannl "Antoine van der Lee") 写了一篇博文，[探讨在 Swift 中解包或 throw 的解决方案](https://www.avanderlee.com/swift/unwrap-or-throw/ "Unwrap or throw: Exploring solutions in Swift")。

[Leonardo Maia Pugliese](https://twitter.com/Leo_Pugliese "Leonardo Maia Pugliese") 写了一篇关于[如何在 Swift 中使用 @available 进行 API 约束](https://holyswift.app/how-to-do-apis-constraints-with-available-in-swift "How to do APIs constraints with @Available in Swift")的博客文章。

[John Sundell](https://twitter.com/johnsundell "John Sundell") 写了一篇文章解释了如何[在 switch 语句中使用 @unknown default](https://www.swiftbysundell.com/articles/using-an-unknown-default-case-within-a-switch-statement/ "Using ‘@unknown default’ within switch statements")。

[Bas Broek](https://twitter.com/basthomas "Bas Broek") 写了一篇博文，探讨如何在 Swift 中[弃用 Workarounds](https://www.basbroek.nl/deprecating-workarounds "Deprecating Workarounds")。

## 正在审查的提案

[SE-0321](https://github.com/apple/swift-evolution/blob/main/proposals/0321-package-registry-publish.md "SE-0321"): Package Registry Service - Publish Endpoint 正在[审查中](https://forums.swift.org/t/se-0321-package-registry-service-publish-endpoint/51286 "Package Registry Service - Publish Endpoint")

软件包注册表负责确定哪些软件包版本可提供给消费者使用。

目前，软件包版本的可用性由 `out-of-band` 流程决定。例如，注册表可以查询公共 Swift 软件包的索引，并为每个标签提供具有有效版本号的版本。

拥有发布新版本到软件包注册表的标准端点将增强维护者分发其软件的能力，并促进服务提供商之间的互操作性。

## Swift 论坛

[Dimitri Racordon](https://forums.swift.org/categories "Dimitri Racordon") 提出了一个[用私有字段实现协议的想法](https://forums.swift.org/t/pitch-protocols-with-private-fields/51209 "Protocols with private fields")。

在协议中，所有字段（`properties` 和 `methods`）都将获得符合条件类型的访问可见性。例如，符合具有公共类型的协议将提示其所有要求都是公共的。

[Evan Wilde](https://forums.swift.org/categories "Evan Wilde") 提出了一项[重新审视 async main 语义](https://forums.swift.org/t/pitch-revisit-the-semantics-of-async-main/51254 "Revisit the semantics of async main")的提案。

* main 函数应该同步运行到第一个暂停点
* main 函数应该在 `main actor` 上运行
* MainActor 应该为默认的 `runloop` 行为提供用户指定的替代方案。
* main 任务应该从 `getCurrentThreadPriority` 拉取优先级，而不是 `hard-coded` 默认优先级

[Anders Bertelrud](https://forums.swift.org/u/abertelrud "Anders Bertelrud") 提议修改 SE-0303：插件 API，使用 @main 作为插件入口点。

我想提议修改 `SE-0303`，`SwiftPM` 插件使用 `@main` 作为入口点，而不是 `top-level` 作为入口点。 虽然这样做有点冗长，但是可以为每种插件定制入口点，并且还可以更加清楚地说明每个插件的输入和预期输出是什么。

[Jeremy Saklad](https://forums.swift.org/u/saklad5 "Jeremy Saklad") 提出了一项提案，该提案将[允许使用具体的相关协议类型](https://forums.swift.org/t/allow-use-of-concrete-associated-type-of-protocols/51277 "Allow use of concrete associated type of protocols")。

[Karoy Lorentey](https://twitter.com/lorentey "Karoy Lorentey") 发布了 [Swift Collections 1.0 版](https://forums.swift.org/t/announcement-planning-for-swift-collections-v1-0/51321 "Planning for Swift Collections v1.0")。

[Konrad ktoso Malawski](https://forums.swift.org/u/ktoso "Konrad ktoso Malawski") 发布了 Swift Server Workgroup [2021 年 8 月 4 日的会议记录](https://forums.swift.org/t/august-4th-2021/51315 "August 4th 2021")。

[Doug Gregor](https://twitter.com/dgregor79 "Doug Gregor") 提出了 [在 Sendable 检查中实施 Staging](https://forums.swift.org/t/pitch-staging-in-sendable-checking/51341 "Staging in Sendable checking") 的提案。

`SE-0302` 引入了 Sendable 协议，该协议明确地指出哪些类型的值可以安全地跨过 `actors` 进行复制。通俗的讲，就是拷贝的值和原始值可以同时在上下文使用。

Sendable 检查在所有 Swift 代码中应用，消除了由 `shared mutable state` 引起的大量数据竞争。Swift 5.5 没有完全实现 Sendable 检查，因为这样做会导致太多的编译器 `errors` 和 `diagnostics`，从而导致该功能不可用。

我认为可以逐步采用 Sendable 检查来提高数据竞争的安全性。我们提出了两个想法分段完成 Sendable 检查:

* 增量采用并发并且引入更多的 Sendable 检查。
* 不能让用户模块之外的 Sendable 问题阻挡进度，防止过度的注释

[Aura Lily Vulcano](https://forums.swift.org/categories "Aura Lily Vulcano") 推荐了一个 [Swift 默认提供的新模块](https://forums.swift.org/t/pitch-the-cstdlib-module/51373 "The CStdlib module")。

该模块将重新导出包含当前平台的 `POSIX` 或类似 `POSIX` 的 C 标准库的正确模块（如果有的话）。

默认情况该模块不会被导入，但是允许 “reasonably cross-platform” 代码，以避免使用冗长的 `#if canImport(…)` 链来访问所有的标准库，因为它们在不同的操作系统上有不同的名称。

例如，模块可以命名为 CStdlib。

Robert Widmann（[@CodaFi_](https://twitter.com/CodaFi_ "CodaFi_")）提出了一个关于[开始可变参数泛型](https://forums.swift.org/t/pitching-the-start-of-variadic-generics/51467 "The Start of Variadic Generics")的想法。

作为改进泛型系统的人体工程学的一部分，以及为使用 tuples 抽象提供更好的支持，我想用 surface syntax 和 preliminary semantics 来实现这个想法。 由于这是一个很大的主题领域，对语言和后续提案的方向都有很大影响，因此你的反馈在此阶段对于塑造此功能集的方向至关重要。

我要感谢 **Alejandro Alonso**, **Doug Gregor** 和 **Slava Pestov**，感谢他们为我在这个问题上的思考奠定了基础。

可以在这里看到原文的链接 [TypeSequences.md · GitHub](https://gist.github.com/CodaFi/a461aca155b16cd4d05a2635e7d7a361 "TypeSequences.md · GitHub")

## 关于我们

公众号是由 Swift 爱好者共同维护，我们会分享以 Swift 实战、SwiftUI、Swift 基础为核心的技术内容，也整理收集优秀的学习资料。欢迎关注公众号：**Swift社区**，后台点击进群，联系我们获取更多内容。

<img width="500" alt="Swift社区" src="https://files.mdnice.com/user/17787/feeae00d-c91a-42d1-891f-111552cd57a1.png">


感谢 SwiftWeekly 与我们的合作，开启 Swift 周报中文版发布之旅。周报仓库：https://github.com/SwiftCommunityRes

后续还会翻译大量资料到我们公众号，有感兴趣的朋友，可以加入我们，扫码添加微信

<img width="300" alt="fzhanfei" src="https://files.mdnice.com/user/17787/9a7911bf-75f2-40f5-866b-3171868bb92c.jpg">
