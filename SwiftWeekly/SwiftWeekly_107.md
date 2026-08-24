## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百零七期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

时光不停走，岁月慢慢老。人生起落皆是常态，烟火清闲只为舒心！👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：ChatGPT 接入 iMessage 与 Siri AI 直接竞争；苹果首次承认反垄断已开始冲击服务业务
> * **提案**：SE-0543 InlineArray: Hashable、SE-0537 函数部分放置控制正式通过；SE-0544 不可 Copyable typedeinits 突变正在审查
> * **Swift 论坛**：`@called(once)` 标注提议、Swift 6.4 Embedded Swift 改进、SwiftTUI 终端框架
> * **推荐博文**：Swift 6.4 Embedded Swift 进化、用 Swift 重构 Electron 会议录制引擎、Swift 社区 7 月动态

**上期投票结果：**

![](https://files.mdnice.com/user/47553/a298da6b-a19a-4129-81d5-3899fe7a36d4.jpg)

**在"如何应对 AI 替代"的话题中，39.13% 的读者选择了"科学养生"——看来比起焦虑 AI，年轻人更愿意选择保温杯里泡枸杞的务实路线。**

## 话题讨论

**"边熬夜边养生，这届年轻人到底是死是活？"——朋克养生是真有效还是自我安慰？**

从"熬最晚的夜敷最贵的面膜"到"可乐泡枸杞"，从"护肝片配烧烤"到"褪黑素配手机"。一边是身体发出警告信号，一边是"道理都懂就是改不了"。你觉得这种一边作死一边自救的生活方式，是年轻人的生存智慧还是自欺欺人？

1、心理安慰大于实际：吃了护肝片，烧烤就能多吃两串，主打一个心安？
2、真没办法：上班那么累，晚上那点时间不熬一下就感觉今天白过了？
3、科学养生：保温杯里泡枸杞，该补的补该睡的睡，谁说年轻人不懂养生？

欢迎在评论区留下你的看法和建议。

## 新闻和社区

### ChatGPT 接入 iMessage 与 Siri AI 直接竞争

*2026 年 8 月 21 日｜来源：财联社*

8 月 21 日讯，OpenAI 于当地时间周四推出新功能，允许用户通过 Mac 电脑端的 ChatGPT 操控苹果 iMessage 信息服务，执行读取、撰写与发送短信等操作，并能检索信息及生成对话摘要。

此举可让 ChatGPT 对接苹果开发工具 Xcode、备忘录和终端等 Mac 本地应用，并支持在获得专门授权后读取 iOS 系统健康 APP 相关数据。然而，周四推出的新功能涉及私密通信领域，对苹果而言更为敏感。

**隐私与竞争双重挑战** 苹果一向严格保护用户通信数据，若第三方 AI 工具涉及将通信数据上传至云端服务器，势必面临隐私质疑。据悉，苹果此前曾多次限制类似尝试，例如曾关停第三方通信软件开发商 Beeper 的跨平台应用 Beeper Mini。

业内指出，该功能还将直接对苹果下月即将推出的新版 Siri 形成竞争——新版 Siri 具备检索本地短信和内容的能力，本被视作苹果原生 AI 对抗第三方工具的核心优势之一。

**OpenAI 回应** 针对隐私方面的关切，OpenAI 回应称该功能必须经过用户主动授权，且不会对用户的全部短信建立索引。该功能在 Mac 本地运行，主要依托系统自带的 AppleScript 和辅助功能等原生接口与信息应用交互。

两家公司的关系近期正趋于紧张——苹果上月刚刚起诉 OpenAI，指控其涉嫌窃取未发布产品的商业机密。

### 苹果首次承认：反垄断已开始冲击服务业务

*2026 年 8 月 18 日｜来源：IT 之家*

据英国《金融时报》报道，苹果首次承认，各地监管机构迫使其放松 App Store 控制权，已经开始冲击其规模超过 1,000 亿美元的服务业务。这是苹果罕见承认反垄断措施已经开始影响核心利润来源。

**服务业务未达预期** 苹果 6 月季度服务业务收入为 307 亿美元，低于分析师预期的 314 亿美元。服务业务毛利率为 75.6%，同样未达到预期。财报公布后的数日内，苹果股价累计下跌约 9%。

**App Store 增速放缓** Sensor Tower 数据显示，美国消费者第二季度通过 App Store 的支出同比下降 6%，去年同期则增长 9%。Appfigures 估计，苹果今年以来在美国获得的 App Store 佣金收入已经下降 18%。

瑞银分析师戴维·福格特认为，App Store 增长放缓已经成为一个"令人担忧的问题"。

**全球监管压力** 欧盟去年因苹果涉嫌违反《数字市场法》对其罚款 5 亿欧元，苹果目前正在上诉。Epic Games 去年在美国赢得法院禁令后，苹果被迫允许开发者免费将用户引导至 App Store 之外的支付渠道。

华盛顿分析公司法律研究主管尼古拉斯·罗德利说："苹果的估值溢价建立在服务业务之上，而 App Store 正是服务业务的皇冠明珠。市场将重新评估苹果服务业务的抽成比例究竟还能维持多久。"

### 苹果 Siri AI 集体诉讼和解案"最终批准听证会"定于明年 2 月

*2026 年 8 月 18 日｜来源：IT 之家*

苹果于今年 5 月在美国市场同意支付 2.5 亿美元，以和解因 Siri AI 功能延迟推出而引发的集体诉讼。符合条件的 iPhone 用户最高可获得 95 美元赔偿。

负责审理此案的法官上周将最终批准听证会定于 2027 年 2 月 24 日。即使届时获得最终批准，赔偿款也要在此后数月才能开始发放。

**符合条件的消费者** 包括"在 2024 年 6 月 10 日至 2025 年 3 月 29 日期间购买 iPhone 16 系列或部分 iPhone 15 机型的美国消费者"。每台符合条件的设备预计可获得至少 25 美元，最终金额最高可达 95 美元，具体取决于有效索赔数量等因素。

## 提案

### 通过的提案

[SE-0543](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0543-inline-array-hashable.md "SE-0543")
**InlineArray: Hashable** 提案已通过审查。

该提案此前已在 **第一百零六期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0537](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0537-function-sections.md "SE-0537")
**功能的部分放置控制** 提案已通过审查。

该提案此前已在 **第一百零五期周报** 的「正在审查的提案」模块中做过详细介绍。

### 正在审查的提案

[SE-0544](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0544-mutate-or-consume-in-deinit.md "SE-0544")
**不可 Copyable 的 typedeinits 中的突变和消耗** 提案正在审查。

不可 `Copyable` 类型可以定义 `deinit`，以在其生命周期结束时清理拥有的资源；然而，在此提案之前，`self` 被限制为不可变的，只能在 `deinit` 主体内借用。我们建议允许 `deinit` 变异和/或消耗 `self` 领域，但仍然防止 `self` 作为整体价值的突变或消耗，以避免价值复活的问题。

[SE-0545](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0545-build-debugging-options.md "SE-0545")
**SwiftPM 构建性能调试选项** 提案正在审查。

本提案引入了两个新的 SwiftPM CLI 选项，`--trace-events-file` 和 `--enable-task-backtraces`，可用于分析干净和增量构建的性能，并识别常见问题。

[SE-0546](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0546-memberwise-init-extensions.md "SE-0546")
**同一文件成员初始化器扩展** 提案正在审查。

该提案允许在同一文件扩展中定义结构的成员初始化器。

## Swift论坛

### 1、[提议引入"至多调用一次"的函数标注]

作者：Pavel Yaskevich ｜ 发布日期：2026 年 8 月 20 日
[阅读原帖](https://forums.swift.org/t/pitch-introduce-a-way-to-annotate-functions-that-are-called-at-most-once/89088 "[Pitch] Introduce a way to annotate functions that are called at most once")

**核心内容：**
该提案引入 **`@called(once)`** 属性，用于向编译器声明一个函数值最多只会被调用一次。其核心动机是让编译器既能诊断违反调用次数约束的代码，也能更准确地分析闭包捕获值的生命周期，从而改善闭包与 **不可复制类型（non-Copyable types）** 的协作。

这一能力尤其适合 **`Task`**、任务组及各类只消费一次回调的 API。

**简要点评：**
这是一项底层但影响广泛的所有权能力，真正价值取决于标准库和生态 API 的完整采纳。社区讨论主要聚焦于属性名是否应改为更精确的 **`@called(atMostOnce)`**、现有 API 如何兼顾 ABI 与回部署，以及标准库能否及时完成广泛适配。核心团队成员表示并发库将积极采用该属性。

### 2、[Swift 6.4 即将带来的 Embedded Swift 改进]

作者：Douglas Gregor ｜ 发布日期：2026 年 8 月 20 日
[阅读原帖](https://forums.swift.org/t/embedded-swift-improvements-coming-in-swift-6-4/89085 "Embedded Swift Improvements Coming in Swift 6.4")

**核心内容：**
Swift 6.4 继续扩大 **Embedded Swift** 可用的语言子集，使受限设备上的代码更接近完整 Swift。本次语言层面的主要变化包括：全面支持 **存在类型 `any`**（含 `Any`）、支持非类型化 **`throws`**，以及完整支持元类型。

```swift
protocol DefaultInitializable {
    init()
}

extension Int: DefaultInitializable {}

let factory: any DefaultInitializable.Type = Int.self
let value: any DefaultInitializable = factory.init()
```

**简要点评：**
Swift 6.4 在保持"按需付费"的代码体积与性能原则下，明显降低了现有 Swift 代码迁移到嵌入式环境的门槛。库层面新增了字符串到浮点数的解析能力，并让并发库支持会抛错的 **`Task`** 与 **`TaskGroup`** 操作。

### 3、[SwiftTUI：面向 Swift 的终端界面框架]

作者：Adam Zethraeus ｜ 发布日期：2026 年 8 月 18 日
[阅读原帖](https://forums.swift.org/t/swifttui-a-terminal-ui-framework-for-swift/89032 "SwiftTUI — a Terminal UI framework for Swift")

**核心内容：**
**SwiftTUI** 是一个以"将 SwiftUI 语义绘制到终端单元格"为目标的开源 TUI 框架。开发者只需创建 Swift Package、添加依赖并声明遵循 **`App`** 的入口类型，即可沿用熟悉的声明式开发方式构建终端应用。

框架已实现 **`@State`**、**`@Binding`**、**`@Observable`**、堆栈布局、滚动视图、手势、键盘命令、动画与过渡等大量 SwiftUI 风格 API。它基于 Swift 6.3、启用严格并发，支持 macOS 和 Linux。

**简要点评：**
项目尚年轻，但熟悉 SwiftUI 的开发者几乎无需切换心智模型，值得 CLI 工具作者关注和试用。

### 4、[GSoC 2026：为 Swift 并发跟踪 Task 与 TaskGroup]

作者：Ege Kaya ｜ 发布日期：2026 年 8 月 20 日
[阅读原帖](https://forums.swift.org/t/gsoc-2026-task-and-taskgroup-tracking-for-swift-concurrency/89084 "[GSoC 2026] Task and TaskGroup tracking for Swift Concurrency")

**核心内容：**
该 GSoC 项目为 Swift 并发运行时加入 **TaskRegistry**，解决任务未在线程上执行时无法从回溯中看到、进而难以排查停滞与死锁的问题。实现没有采用争用严重的全局链表，而是把任务按 64 位 Task ID 哈希到 64 个缓存行对齐的 **TaskRegistryShard**；每个分片维护独立的侵入式双向链表与 **LazyMutex**，插入和删除均为 O(1)。

模拟高吞吐 Web 服务器的测试创建了超过 60 万个任务，耗时从 0.3715 秒增至 0.3860 秒。

**简要点评：**
这是对并发可观测性的关键基础设施补强，以很低的运行时成本（约 0.01 微秒单次注册）换取更强的调试能力。核心运行时支持已经合并，崩溃回溯与 LLDB 宏仍是后续目标。

### 5、[`async let` 中的捕获列表为何仍触发数据竞争诊断]

作者：Dan ｜ 发布日期：2026 年 8 月 18 日
[阅读原帖](https://forums.swift.org/t/async-let-capture-list/89043 "Async let capture list")

**核心内容：**
发帖者发现，相同的捕获列表用于 **`Task`** 时可以通过编译，直接写在 **`async let`** 右侧却会提示发送 `nonSendables` 可能造成数据竞争。

```swift
let asyncWork = { [sendables = nonSendables.map(\.description)] in
    for item in sendables {
        // 使用已转换为 String 的值
    }
}

async let result = asyncWork()
nonSendables = []
```

原因在于 `async let` 会把等号右侧的整个表达式放进立即创建的子任务中求值，而 `Task` 示例中的闭包会先在当前上下文同步创建，再传给 `Task.init`。

**简要点评：**
当前行为符合 **SE-0317** 的模型，但确实暴露了结构化并发中"表达式在哪里求值"容易被忽略的问题。将闭包或捕获结果提前保存即可消除诊断。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[Swift 6.4 中 Embedded Swift 的持续进化](https://www.swift.org/blog/embedded-swift-improvements-coming-in-swift-6.4/ "Swift 6.4 中 Embedded Swift 的持续进化")

**摘要：** 这篇官方博客详细介绍了 Swift 6.4 中 Embedded Swift 的改进内容，包括全面支持存在类型 `any`（含 `Any`）、支持非类型化 throws、完整支持元类型，以及库层面新增的字符串到浮点数解析能力和并发库改进。

[用 Swift 重构 Electron 会议录制引擎](https://ohmyswift.com/blog/2026/08/02/stop-burning-tokens-on-fix-my-ios-app-performance/ "用 Swift 重构 Electron 会议录制引擎")

**摘要：** 这篇实战博客记录了将 Electron 应用中的实时音视频捕获引擎从 JavaScript 迁移到 Swift 的全过程。团队借助 ScreenCaptureKit（macOS）和 OBSKit（Windows）实现原生方案，开发了内部工具 Atomic——借助 Swift 宏在编译时自动生成原生代码与 React 前端之间的类型安全桥接。全文呈现了一场从 Web 技术栈向原生 Swift 迁移的完整实践。

[Swift 社区动态：2026年7月版](https://www.swift.org/blog/whats-new-in-swift-july-2026/ "Swift 社区动态：2026年7月版")

**摘要：** 这篇官方月度动态汇聚了 Swift 项目在 7 月的多项进展。视频资源方面，John McCall 在 PLDI 2026 上的演讲深入探讨了为 Swift 引入显式所有权和生命周期特性时所面临的挑战；社区贡献方面，Google Summer of Code 的参与者正在为 Swift 并发运行时构建 Task Registry。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 "进群" 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
