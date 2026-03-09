## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第九十六期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

天增岁月人增寿，春满乾坤福满路。无惊无险，又是一年，愿您一路向前又向钱，无限风采添运财！！！👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：MacBook Pro 全系 M5 芯片 3 月 11 日开售；Apple TV / HomePod mini 或因 Siri 延期；iOS 26.3.1 发布，国行 AI 仍缺席
> * **提案**：SE-0504、SE-0506、SE-0508、SE-0509 正式通过；SE-0512～SE-0519 正在审查；SE-0505 被拒
> * **Swift 论坛**：Continuation 安全延续、Borrow/Inout 类型、~Sendable、FOSDEM 2026 回顾、新 Codable 原型
> * **推荐博文**：Swift 6 Actor 与严格并发、iOS 集成 YOLOv8、App Store 上架被拒案例

上期话题投票结果如下：

![](https://files.mdnice.com/user/47553/240c742c-4445-482b-a339-734be9eb664a.png)

## 话题讨论

### 本期话题：**苹果在本周集中发布了多款新产品，你最期待哪一款？**

**选项：**

1. 搭载 M5 芯片的 MacBook Pro
2. M5 版 MacBook Air
3. MacBook Neo —— 苹果推出的 $599 入门级笔记本
4. iPhone 17e
5. 新款 Studio Display / Studio Display XDR
6. 这些产品都没有让我特别兴奋

欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### 苹果新款 Apple TV 与 HomePod mini 缺席，或因 Siri 未就绪

*2026 年 3 月 5 日｜来源：IT之家*

苹果本周发布了七款产品，但全新 Apple TV 和 HomePod mini 并未登场。据 Macrumors 推测，原因很可能与 Siri 有关：新一代 Apple TV 和 HomePod mini 都将支持由 Apple Intelligence 驱动的更个性化 Siri，而该功能被推迟，两款设备因此大概率延期。古尔曼称，个性化 Siri 计划随 iOS 26.5 或 iOS 27 推出；据此推算，新款 Apple TV 和 HomePod mini 可能要到今年 4 月至 9 月才会发布。现款 Apple TV 发布于 2022 年 10 月，HomePod mini 首发于 2020 年 10 月，均已到更新周期。

![](https://pics4.baidu.com/feed/a1ec08fa513d2697268334360374e6ea4216d8ad.jpeg@f_auto?token=0f34c987cd802ab4726884b180f6485d)

### 马年首次更新！苹果 iOS 26.3.1 正式版发布：国行用户苦等的 AI 依然缺席

*2026 年 3 月 5 日｜来源：快科技*

苹果发布 iOS 26.3.1 正式版（版本号 23D8133），为农历马年以来首次正式版更新。本次主要为小幅功能完善与问题修复，外接显示器新增适配 2026 款 Studio Display 和 Studio Display XDR，并带来针对 iPhone 的错误修复。作为例行小版本，iOS 26.3.1 未带来重磅新功能，国行用户期待的 Apple Intelligence 依然缺席。古尔曼此前透露苹果原计划 2025 年中将 Apple Intelligence 引入中国市场，但因工程与模型等问题及监管审批多次延期，国行版至今未有时间表。

![](https://pics6.baidu.com/feed/0824ab18972bd407f8b27a6e5e3bcd400eb3096b.jpeg@f_auto?token=b56bd838fb96cfad9f17fad263395cee)

### 苹果最新 MacBook Pro 问世，全系配 M5 芯片，3 月 11 日开售

*2026 年 3 月 3 日｜来源：CNMO科技*

苹果正式推出全新 14 英寸和 16 英寸 MacBook Pro，搭载 M5 Pro 和 M5 Max 芯片。John Ternus 表示，新机实现高达 4 倍于前代的 AI 处理速度、8 倍于 M1 的 AI 性能；采用融合架构，配备多核 CPU、下一代 GPU 与神经加速器。SSD 读写最高约 14.5GB/s，M5 Pro 标配 1TB、M5 Max 标配 2TB；支持 Wi-Fi 7、蓝牙 6，续航约 24 小时。提供深空黑与银色，3 月 4 日起预订，3 月 11 日起发售。

![](https://pics2.baidu.com/feed/7af40ad162d9f2d3aa4520310f8fd8026227cc09.jpeg@f_auto?token=005f76106497a7bc8a5536daa354c26f)

## 提案

### 通过的提案

[SE-0504](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0504-task-cancellation-shields.md "SE-0504")
**任务取消屏蔽** 提案已通过审查。

该提案此前已在 **第九十四期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0506](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0506-advanced-observation-tracking.md "SE-0506")
**高级观察跟踪** 提案已通过审查。

该提案此前已在 **第九十五期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0508](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0508-array-expression-trailing-closures.md "SE-0508")
**数组表达式尾随闭包** 提案已通过审查。

该提案此前已在 **第九十五期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0509](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0509-swift-sboms-via-swiftpm.md "SE-0509")
**Swift 软件包管理器的软件物料清单（SBOM）生成** 提案已通过审查。

该提案此前已在 **第九十五期周报** 的「正在审查的提案」模块中做过详细介绍。

### 正在审查的提案

[SE-0512](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0512-withlockifavailable-cannot-spuriously-fail.md "SE-0512")
**记录 Mutex.withLockIfAvailable 不能虚假失败** 提案正在审查。

修改 `Mutex.withLockIfAvailable(_:)` 的文档，以明确其不会虚假失败的保证，当前实现已满足该行为。

[SE-0513](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0513-commandline-executablepath.md "SE-0513")
**API 获取当前可执行文件的路径** 提案正在审查。

在 Swift 标准库中新增用于读取当前执行二进制文件路径的接口，便于需要生成子进程或向用户展示当前程序信息的场景。

[SE-0514](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0514-hashable-conformance-for-dictionarykeys-collectionofone-emptycollection.md "SE-0514")
**Hashable 符合 Dictionary.Keys 和 EmptyCollection** 提案正在审查。

为三种标准库集合类型添加 `Hashable` 一致性：`Dictionary.Keys`、`CollectionOfOne` 和 `EmptyCollection`。

[SE-0515](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0515-noncopyable-reduce.md "SE-0515")
**允许 reduce 产生不可复制的结果** 提案正在审查。

提议对 `Sequence.reduce(_:_:)` 进行扩展：支持不可复制的初始值与结果，并以 consuming 方式接收初始值（即便其可复制）。

[SE-0516](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0516-borrowing-sequence.md "SE-0516")
**借用序列** 提案正在审查。

引入新迭代协议 `BorrowingSequence`，适用于不可复制类型，并在部分场景下为可复制类型提供更高效的迭代；Swift 编译器将支持通过现有 `for` 语法使用该协议。

[SE-0517](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0517-uniquebox.md "SE-0517")
**UniqueBox** 提案正在审查。

在标准库中引入 `UniqueBox` 类型，作为在堆上唯一持有某一值的智能指针类型。

[SE-0518](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0518-tilde-sendable.md "SE-0518")
**~Sendable 用于显式标记非 Sendable 类型** 提案正在审查。

引入 `~Sendable` 一致性语法，用于显式抑制 Sendable 推断，避免类型被自动判定为 Sendable，并可在不受继承影响的情况下表达“经审查确认为非 Sendable”的语义。

[SE-0519](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0519-borrow-inout-types.md "SE-0519")
**Borrow 和 Inout 类型，用于安全的一级引用** 提案正在审查。

引入两种标准库类型 `Borrow` 和 `Inout`，分别表示对另一值的共享（只读）与排他（可变）安全引用。

### 拒绝的提案

[SE-0505](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0505-delayed-enqueuing.md "SE-0505")
**执行者延迟排队** 提案被拒绝。该提案此前已在 **第九十四期周报** 的「正在审查的提案」模块中做过详细介绍。

## Swift 论坛

### 1、Pitch: Continuation — 安全且高性能的异步延续类型

作者：Fabian Fett, Konrad Malawski ｜ 发布日期：2026年3月5日
[阅读原帖](https://forums.swift.org/t/pitch-continuation-safe-and-performant-async-continuations/85165 "Pitch: Continuation — Safe and Performant Async Continuations")

Fabian Fett 和 Konrad Malawski 提出了一个新的 **Continuation** 类型，旨在解决现有延续类型的安全性和性能问题。目前开发者在使用延续时面临两难选择：**UnsafeContinuation** 零开销但不安全（重复恢复会导致未定义行为，忘记恢复会导致任务永久泄漏），而 **CheckedContinuation** 虽然能检测错误但需要运行时开销（包括堆分配和原子操作）。

新提案引入的 **Continuation<Success, Failure>** 是一个 **~Copyable** 类型，通过三个机制确保正确使用：

- **移动语义（~Copyable）**：延续无法被复制，从两个不同代码路径恢复在编译时就会报错
- **consuming 方法**：每个 `resume` 方法都会消费 `self`，第二次调用会产生编译错误
- **deinit 陷阱**：如果延续被丢弃而未恢复，`deinit` 会调用 `fatalError`，成功路径使用 `discard self` 避免开销

```swift
// 双重恢复 - 编译时错误
actor LegacyBridge {
    var continuation: Continuation<String, Never>?
    
    func complete(with value: String) {
        if let continuation {
            continuation.resume(returning: value) // 消费 continuation
            continuation.resume(returning: value) // 编译错误：已被消费
        }
    }
}
```

该提案还引入了统一的 `withContinuation(of:throws:)` 函数，利用 **SE-0413 类型化 throws** 特性，用单个函数替代之前的两个函数（throwing 和 non-throwing 版本）。社区讨论集中在是否应该等待 **~Discardable** 协议、文件和行号信息的权衡（增加类型大小）、以及与 **call-once 闭包**的配合等问题。

### 2、SE-0519: Borrow 和 Inout 类型 — 安全的一级引用

作者：Douglas Gregor ｜ 发布日期：2026年3月4日
[阅读原帖](https://forums.swift.org/t/se-0519-borrow-and-inout-types-for-safe-first-class-references/85151 "SE-0519: Borrow and Inout types for safe, first-class references")

SE-0519 提案进入正式审查阶段，审查期至 **2026年3月17日**。该提案引入 `Borrow<T>` 和 `Inout<T>` 两个类型，为 Swift 提供安全的一级引用能力。这些类型允许开发者创建对值的借用或可变引用，而无需使用不安全指针。

`Borrow<T>` 和 `Inout<T>` 的关键特性：

- 都是 **~Copyable** 类型，确保引用的唯一性
- 通过 `.value` 属性访问底层值
- 根据类型大小和特性选择不同的内部表示（值拷贝或指针）
- 小于等于 4 个 `Int` 大小且可按位借用的类型使用值表示，其他使用指针表示

```swift
func processData(_ data: Borrow<LargeStruct>) {
    // 通过 .value 访问底层数据
    print(data.value.field)
}
```

社区讨论非常激烈，主要争议点包括：

- **命名问题**：John McCall 建议使用 `Borrowed<T>` 和 `Mutable<T>`，与 `Span/MutableSpan` 保持一致
- **与借用访问器提案的关系**：Keith Bauer 认为两个提案不够正交，应该更深度整合
- **隐式解引用**：是否应该像 Rust 的 `Deref` 那样自动解引用访问成员
- **类型系统支持**：是否应该作为语言内置特性而非标准库类型

该提案依赖 **SE-0507 借用访问器**作为前置条件，两者共同构建 Swift 的所有权系统。

### 3、SE-0518: ~Sendable — 显式标记非 Sendable 类型

作者：Xiaodi Wu ｜ 发布日期：2026年3月4日
[阅读原帖](https://forums.swift.org/t/se-0518-sendable-for-explicitly-marking-non-sendable-types/85132 "SE-0518: ~Sendable for explicitly marking non-Sendable types")

SE-0518 提案进入审查阶段，审查期至 **2026年3月16日**。该提案引入 **~Sendable** 语法，允许开发者显式标记类型为非 Sendable，以区分"未经审查"和"经审查后确认为非 Sendable"两种情况。

在 Swift 6 的严格并发检查下，类型默认不符合 **Sendable**，但这种隐式行为无法表达"该类型已经过并发安全审查，确认不应该是 Sendable"的语义。**~Sendable** 填补了这一表达空白：

```swift
// 显式标记为非 Sendable
struct NonThreadSafeCache: ~Sendable {
    private var storage: [String: Any] = [:]
    // 该类型经过审查，确认不应跨并发域传递
}
```

**关键规则**：

- **~Sendable** 必须声明在类型定义上，不能在扩展中声明
- **actor** 类型不能标记为 **~Sendable**（actor 始终是 Sendable）
- 可以与条件 Sendable 共存，在特定平台上标记为非 Sendable

该提案对 Foundation 等框架特别重要，Jeremy Schonfeld 表示 Foundation 团队希望使用 `-require-explicit-sendable` 编译选项防止意外发布未经审查的 API，但之前无法表达"显式非 Sendable"。社区普遍支持该提案，认为这是完善 Swift 并发模型的重要一步。

### 4、FOSDEM 2026 Swift 社区活动回顾与照片

作者：Konrad Malawski ｜ 发布日期：2026年3月3日
[阅读原帖](https://forums.swift.org/t/wrapping-up-pre-fosdem-community-event-2026-and-photos/85108 "Wrapping up Pre-FOSDEM Community Event 2026, and Photos!")

Konrad Malawski 发布了 **FOSDEM 2026** Swift 社区活动的总结帖。此次活动在 FOSDEM 大会前举办，汇聚了全球 Swift 开发者。Konrad 特别感谢了项目委员会成员 Karen Chu、Steven Van Impe 和 Joannis Orlandos，以及志愿者 Mona、Theo、Sam 和 Manolo。

活动亮点：

- 所有演讲已由 Sébastien Stormacq 录制并上传至 [Swift Community Meetups YouTube 频道](https://www.youtube.com/@SwiftCommunityMeetups)
- FOSDEM 主会场的 Swift 相关演讲包括：**容器化的未来**、**将 Swift 移植到 FreeBSD**、**使用 LLDB 调试 WebAssembly**、**Swift Package Manager 的构建时 SBOM 生成**
- 现场有大量开发者佩戴 Swift 帽子，展现了社区的活力

Konrad 分享了活动的集体照和相册链接，所有照片都可以自由使用（包括用作个人头像）。Tracy Miranda 和 Karen Chu 也在帖子中表达了对活动的感谢，期待未来能再次相聚。这次活动展示了 Swift 社区的全球化和开放性，为开发者提供了面对面交流的宝贵机会。

### 5、新 Codable 原型开放反馈

作者：Kevin Perry ｜ 发布日期：2026年3月6日
[阅读原帖](https://forums.swift.org/t/new-codable-prototype-available-for-feedback/85186 "New Codable prototype available for feedback")

Kevin Perry 宣布"新 Codable"原型已在 **swift-foundation** 的 `experimental/new-codable` 分支上线，距离去年的"序列化与反序列化 API 未来"帖子已近一年。该原型引入了全新的序列化框架，旨在解决现有 **Codable** 的性能瓶颈。

**核心组件**：

- **CommonEncodable/CommonDecodable**：格式无关的协议，避免了现有 Codable 的性能限制
- **JSONEncodable/JSONDecodable**：针对 JSON 优化的协议
- **JSONParserDecoder** 和 **JSONDirectEncoder**：新的 JSON 编解码器
- **JSONElement**：JSON 元素表示类型

**性能提升**：初步基准测试显示，在解码 `twitter.json` 时，新的 **JSONDecodable** 和 **JSONParserDecoder** 相比现有 **Decodable** 和 **JSONDecoder** 提供了约 **6 倍**的吞吐量提升！

```swift
// 使用新 Codable
.package(
    url: "https://github.com/apple/swift-foundation.git",
    branch: "experimental/new-codable"
)
```

**路线图**：

1. 完善 `Common*` 协议
2. 完善 `JSON*` API
3. 支持 Embedded Swift
4. 添加 XML 和二进制 Property List 支持
5. 设计并实现 `@JSONCodable`、`@PropertyListCodable` 等宏
6. 发布库以支持其他格式的自定义宏

社区反馈积极，Simon Leeb 对 Embedded WebAssembly 场景特别感兴趣，Filip Sakel 关注性能对比和命名空间污染问题。该项目需要 **Swift 6.3**，欢迎社区通过 GitHub Issue 和 PR 参与贡献。


## 推荐博文

以下三篇文章非常值得一读，适合本周“提升技能 + 开阔思路”：

[掌握 Swift 6 中的 Actor 隔离与严格并发](https://dev.to/devin-rosario/mastering-actor-isolation-and-strict-concurrency-in-swift-6-gf5/ "掌握 Swift 6 中的 Actor 隔离与严格并发")

**摘要：** 文章深入剖析了 Actor 隔离和 Sendable 协议这两个核心机制。Actor 作为保护内部状态的引用类型，确保任何时候只有一个任务能访问其可变属性。作者对 await 关键字给出了新的解读：它并非简单的语法障碍，而是一种结构性的安全机制，用于确保获得数据的独占访问权。Sendable 协议则相当于数据的"安全传输证书"，要求类要么保证属性不可变，要么通过内部锁机制同步，要么被隔离到全局 Actor 上。

[iOS 开发之集成目标检测模型 YOLOv8 ](https://juejin.cn/post/7370876224320618535/ "iOS开发之集成目标检测模型 YOLOv8 ")

**摘要：**  这篇文章是一篇技术教程，讲解如何将YOLOv8目标检测模型集成到iOS应用中。
由于YOLO模型无法直接在iOS中使用，需要先进行转换。文章介绍了从Hugging Face或Ultralytics下载YOLOv8模型，并使用命令行训练自定义模型的方法。训练完成后，通过Python代码将模型转换为Apple官方支持的Core ML格式。
  
在iOS集成部分，文章详细说明了将Core ML模型导入项目、使用Vision框架初始化和调用模型的步骤。通过VNCoreMLRequest创建识别请求，在回调中获取检测结果（包括置信度、识别内容和位置边框）。文章还提供了摄像头实时捕获的完整代码示例，展示了如何将AVCapture输出的视频帧传递给Vision框架进行处理。

[iOS App Store 上架被拒 case](https://juejin.cn/post/7116301510887079967/ "iOS App Store 上架被拒 case")

**摘要：** 这篇文章主要记录了 App Store 上架过程中遇到的一些被拒绝的案例，以及对应的原因分析和解决策略。案例涵盖了从功能完整性、信息需要、隐私确认，到软件需求和上传被拒等不同阶段的问题。文章还详细阐述了各种问题的产生原因，如 APP 功能不全、集成未使用的库、隐私信息填写不全等，并提出相应的解决方案。通过这些案例的分享，开发者可以理解和学习如何避免类似的错误，更顺利地完成 App Store 的上架过程。


## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
