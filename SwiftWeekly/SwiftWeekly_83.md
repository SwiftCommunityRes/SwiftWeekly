## 前言

**本期是 Swift 编辑组自主整理周报的第八十三期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

有梦想就该去追逐，哪怕遥不可及，纵然风雨雷电。人生就是敢于向前，要么第一，要么唯一。👊👊👊

> **周报精选**
>
> 新闻和社区：苹果公司宣布未来四年在美投资总额将达 6000 亿美元
> 
> 提案：改进 EncodingError 和 DecodingError 的打印描述提案通过审查
> 
> Swift 论坛：提议简化 InlineArray 类型语法糖
>
> 推荐博文：基于 OpenCV 的 iOS 图像处理
>
> **话题讨论：** 
> 
> 你怎么看待跨平台语言？
>
>**上期话题结果**

![](https://files.mdnice.com/user/47553/ca30bede-1cab-4058-ab1d-1588787ce81f.jpg)

从投票结果中可以看出，少林并不仅仅是武术发源地。

## 话题讨论

近期，Airbnb 放弃 React Native 转向原生开发，给跨平台开发提出了警示。“一次编写，随处运行”的承诺往往变成“一次编写，到处调试”，每个复杂功能都必须编写平台特定的代码。“将开发时间减半，同时保持原生性能”的承诺更像个笑话。**那么你怎么看待跨平台语言？**

1. 用户不关心你的开发栈，他们关心应用性能，性能比便利更重要。
2. 跨平台解决方案需要多个领域的专业知识，增加了开发者适配难度。
3. 跨平台语言确实能够适应快速的版本迭代，抢占项目市场。
4. 现在企业和开发者都在卷跨平台语言，即便知晓其弊端又能怎样？
5. Swift赶快适配安卓吧，这样就可以完美解决啦

欢迎在评论区交流分享。

## 新闻和社区  

### 苹果公司宣布未来四年在美投资总额将达 6000 亿美元

2025 年 8 月 7 日

8 月 7 日电，苹果公司宣布，将向美国新增 1000 亿美元投资承诺，此举大幅加快了其在美国的投资步伐，未来四年投资总额将达 6000 亿美元。今日的公告中还包括一项雄心勃勃的全新“美国制造计划”（American Manufacturing Program，简称 AMP），该计划致力于将更多苹果供应链及先进制造业务引入美国。通过实施“美国制造计划”，苹果将加大在美国各地的投资力度，并鼓励全球企业在美国生产更多关键零部件。未来四年，苹果计划在美国直接雇佣 2 万人，其中绝大多数将专注于研发、芯片工程、软件开发以及人工智能和机器学习领域。

首批“美国制造计划”合作伙伴包括康宁公司（Corning）、相干公司（Coherent）、环球晶圆美国公司（GlobalWafers America，简称GWA）、应用材料公司（Applied Materials）、德州仪器公司（Texas Instruments，简称TI）、三星公司（Samsung）、格芯公司（GlobalFoundries）、安靠公司（Amkor）和博通公司（Broadcom）。

“美国制造计划”将助力苹果公司与长期合作伙伴康宁公司深化合作，在肯塔基州哈罗兹堡的工厂打造全球最大、最先进的智能手机玻璃生产线。此次扩建意味着，不久之后，全球销售的每一部 iPhone 和 Apple Watch 都将采用肯塔基州生产的盖板玻璃。（来源：财联社）

### 苹果财报：核心业务竞争力尽显，AI 已成软肋

2025 年 8 月 2 日

苹果发布截止 2025 年 6 月 28 日 2025 财年第三财季，这是一份远超市场预期的财报，也实现了苹果自 2021 年 12 月以来最强劲的季度营收增长。
 
财报数据显示：第三财季苹果总营收达 940.4 亿美元，同比增长近 10%，远高于市场预期的 895.3 亿美元，创下近年来当季最高营收水平；净利润达 244.3 亿美元，同比增长近 9.3%。大中华区也因受益于消费补贴以及 618 等活动助推，当季实现营收 153.7 亿美元，同比增长 4.35%，一举扭转过去两个季度的下跌趋势。

![](https://files.mdnice.com/user/47553/6d30094a-ba42-4820-8465-0a4716b4b4f4.png)

核心业务竞争力尽显

拆分到具体业务：则是在 iPa d和可穿戴业务之外，苹果各大业务线均实现了超预期的增长，特别是 iPhone 和 Mac 业务表现亮眼，可谓竞争力尽显。

![](https://files.mdnice.com/user/47553/87f6fc82-65a0-458f-aacb-9c98b647cc86.png)

首先是 iPhone 业务：得益于 iPhone 16 系列的强劲竞争力，当季 iPhone 业务营收达 445.8 亿美元，同比增长 13.5%。

库克表示：iPhone 16 销量表现出色，远超去年同期的 iPhone 15，尤其是在现有用户的换机需求上，“iPhone 16 销售实现了强劲的双位数增长。”

来自 IDC 发布的《全球季度手机追踪报告》的初步数据显示：苹果第二季度全球 iPhone 出货量为 4640 万部，较 2024 年的 4570 万部增长 1.5%。

从现实来说，iPhone 在当季表现出了远超过往的营收增速表现，可能与用户在特朗普关税威胁下的恐慌性购买有着莫大关系。而在中国市场，则与苹果更为积极的销售政策、国家补贴以及618购物节活动三重叠加刺激的用户购机需求有着相当大的关系。

来自研究机构 Counterpoint Research 的就表示：凭借 iPhone 16 Pro 和 Pro Max 机型的竞争力，苹果当季预计将实现同比 8% 的销量增长。并且苹果在618前一周调整 iPhone 售价恰逢其时。

![](https://files.mdnice.com/user/47553/43d062a0-ad93-481c-82da-b50f0b2f9da6.png)

事实上，一直以来 iPhone 在中国高端市场都保持着绝对的领先地位，有统计数据显示：iPhone 16 系列在中国市场的激活量超过了 2000 万部，在 618 期间，iPhone 也在高端市场实现了销量霸榜。

其次是 Mac 业务：得益于苹果在 3 月份发布了搭载 M4 系列芯片的 Mac 业务产品线所展现出的强劲竞争力， Mac 业务在本财季实现营收 80.5 亿美元，同比增长近 14.8%。

特别是在 MacBook Air 上，苹果执行了增配降价的产品策略，在搭载 M4 芯片的前提下，其 7999 元的起售价相对于前代产品更是降价高达 1000 元，并且在国补加持、平台补贴、教育优惠等加持下，M4 芯片的 MacBook Air 最低能以 5000 多元入手，成为妥妥的真香机，也引发了用户的购买热潮，所以本季 Mac 业务的是可以预期的。

![](https://files.mdnice.com/user/47553/692d0541-8553-4781-867e-8c3606d5fff4.png)

而近年来一直作为苹果营收增速稳定器的服务业务，本季表现依旧亮眼，实现了同比高达 13.3% 的营收增长至 274.2 亿美元。成为苹果当之无愧的第二大营收来源。并且在不久之前，苹果对 App Store 进行了重大改版，在细化年龄分层和增强辅助功能的同时，更是进一步提升了游戏入口的权重，而这对于提升苹果服务营收，应该是有所裨益的。

本季度，iPad 和可穿戴业务由于缺乏新品的有效刺激，本季度这两项业务表现并不令人满意，数据显示，iPad 业务本季实现营收为 65.8 亿美元，同比下降 8%；可穿戴设备和其他硬件产品（包括 Apple Watch 和 AirPods）本季营收为 74 亿美元，同比下滑 8.6%。

所以从营收整体而言，本季度苹果的业务表现可以说是大超预期，特别是 iPhone 和 Mac 的表现，这也说明苹果现有业务线的竞争力依旧强悍乃至是无可替代。而随着 iPhone 17 系列等新品即将在 9 月份发布，苹果在硬件和服务营收上的强势或将进一步延续。

![](https://files.mdnice.com/user/47553/6e028847-406e-4567-8293-3f4af7b40026.png)

AI已成为苹果赢得资本市场青睐的软肋

但即使如此，资本市场对苹果的表现并不太满意，体现在股价上，则是苹果股价累计下跌约 17%，原本市场预期的其将成为首个突破 4 万亿美元市值的也随之被英伟达和微软夺走。

而导致资本市场对苹果不买账的核心原因则是苹果在 AI 领域进展缓慢，被市场认为落后于竞争对手。

体现在 AI 技术层面，则是苹果在 WWDC23 上就展示的 Apple Intelligence，目前仍仅能实现部分功能，Siri 更是成为延期交付者，苹果在 WWDC24 上已公开承认这一失败；而在 AI 落地层面，虽然苹果 AI 已在部分地区落地，但在竞争最为激烈的中国市场，目前仍未看到苹果AI通过审批落地的迹象。

不仅如此，在 Meta 等对手使用钞能力强势挖角的现实下，苹果还面临着 AI 核心研究人员流失的挑战，市场担忧这或将进一步削弱苹果在AI领域的竞争力与落地速度。

据报道称：Meta 在苹果挖走了包括 Ruoming Pang、Mark Lee、Tom Gunter、Bowen Zhan 在内的多名AI核心研究成员。

面对 AI 大潮对苹果构成的重大挑战，库克在财报会上也表示：苹果将“大幅增加”其人工智能（AI）投资，公司“对加速我们发展路线图的并购持开放态度”。事实上，此前业界也传出了苹果或将对 AI 搜索公司 Perplexity 发起并购，但时至今日却并未有后续动作传出。所以如何解决AI软肋已成苹果必答题！(来源：澎湃新闻)

## 提案

### 通过的提案

[SE-0483](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0483-inline-array-sugar.md "SE-0483") **InlineArray 字面语法** 提案通过审查。该提案已在 **第七十七期周报** 正在审查的提案模块做了详细介绍。

[SE-0489](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0489-codable-error-printing.md "SE-0489") **改进 EncodingError 和 DecodingError 的打印描述** 提案通过审查。该提案已在 **第八十一期周报** 正在审查的提案模块做了详细介绍。

## Swift论坛

1、讨论[为 Swift AsyncAlgorithms 开启新一轮开发：引入 share 算法](https://forums.swift.org/t/kickoff-of-a-new-season-of-development-for-asyncalgorithms-share/81447 "为 Swift AsyncAlgorithms 开启新一轮开发：引入 share 算法")

该帖开启了 Swift AsyncAlgorithms 包的新发展阶段，重点是引入一种称为 share 的新算法，以支持多个消费者并行共享同一个异步序列的值。

**背景与需求**

许多场景中，相同的数据源可能需要同时被 UI 更新、日志记录、网络传输等独立路径消费，但不能互相阻塞或丢失值。已有方案无法满足这些独立又并行的消费需求。 ￼

**提议方案**

将在 `AsyncSequence` 上新增 `share(bufferingPolicy:)` 扩展方法，允许多个迭代器并发消费相同数据流。新 API 示例：

```swift
extension AsyncSequence where Element: Sendable {
  public func share(
    bufferingPolicy: AsyncBufferSequencePolicy = .unbounded
  ) -> some AsyncSequence<Element, Failure> & Sendable
}
```

**行为亮点：**

* 共享缓冲区：维护一个共享 buffer，供所有迭代路径使用，根据 policy 决定缓冲行为（无限、旧值优先、最新值优先等）。
* 无值丢失与背压机制：当缓冲区耗尽，可让消费者等待；生产者则暂停生成新值，确保消费方不会漏值。

**社区讨论亮点**

* 关于 `.bounded(n)` 策略的作用机制：当缓冲区值少于 n 时，所有消费者将 await，维持背压而非丢失值。
* 如何检测值被丢弃：可以结合 `.enumerated()` 和 `reductions` 算法辅助判断数据缺口，为用户提供提示或日志。

**总结与展望**

这项工作是 Swift AsyncAlgorithms 向支持多消费者共享流数据能力迈出的重要一步。它为 UI、网络、日志等模块独立且并发消费数据提供了优雅解法。该 API 是对现有功能的补充，无破坏性，且具有灵活扩展的潜力。社区普遍支持这方向，并期待后续进一步完善行为控制与检测机制。

2、讨论[Valkey 的 Swift 客户端：valkey-swift](https://forums.swift.org/t/new-swift-client-for-valkey-redis/81480 "Valkey 的 Swift 客户端：valkey-swift")

Valkey-swift 是一个全新的 Swift 客户端包，专为 Valkey（一个高性能的键值存储服务，Redis 的一个分支）设计，借助现代 Swift 并发机制构建，目前已发布预览版本 v0.1.0。

核心特性一览：

* 完整命令支持

自动生成所有 Valkey（包括字符串、列表、集合、有序集合、流、哈希、地理空间、Pub/Sub、HyperLogLog、Bloom、JSON 模块）命令，保持与 Valkey 8.1.3 兼容，并将轻松适配即将发布的 9.0 版本。API 可通过 ValkeyClient 或 ValkeyConnection 调用。 ￼
示例：

```swift
try await valkeyClient.set("Key1", value: "Test")
let value = try await valkeyClient.get("Key1")
```

* 高级流水线（Pipelining）机制

提供两种流水线执行方式：

1.	使用 `execute(_:)` 一次提交多个命令并接收一个响应元组；
2.	使用 Swift 并发特性，通过同一个连接在多个并发任务中发送命令，避免等待前一个命令响应完成。

示例：
```Swift
let (lpushResult, rpopResult) = await valkeyClient.execute(
    LPUSH("Key2", elements: ["entry1", "entry2"]),
    RPOP("Key2")
)
```
* Pub/Sub 支持

提供直观的 AsyncSequence 接口处理订阅消息，并自动管理订阅与取消订阅生命周期，降低使用复杂度与潜在错误。
示例：

```swift
try await valkeyClient.withConnection { connection in
    try await connection.subscribe(channels: ["channel1"]) { subscription in
        for try await event in subscription {
            print(String(buffer: event.message))
        }
    }
}
```

* 集群支持

通过 `ValkeyClusterClient` 实现分片路由、拓扑发现、连接池管理、故障转移与熔断机制，支持横向扩展与高可用性。

* Redis 协议兼容性

基于 RESP 协议构建，因此可与 Redis 通信（兼容至 Redis v7.2.4 之前）。

社区反馈亮点：

* 社区对 valkey-swift 的现代 API 和并发整合给予高度认可：“APIs look great and fit right into modern Structured Concurrency.” 

* 开发团队计划整合 Swift Metrics 和 Swift Distributed Tracing，并继续推进至 1.0 正式版本（时间未定）。 

3、提议[简化 InlineArray 类型语法糖](https://forums.swift.org/t/accepted-se-0483-inlinearray-type-sugar/81509 "简化 InlineArray 类型语法糖")

该提案 SE-0483 已被语言指导组接受，目标是为 Swift 引入一种更简洁的语法，用以声明固定长度、内联存储的数组 —— 即 InlineArray，旨在提升高性能代码的开发 ergonomics 。语法糖采用如下形式：

```swift
[5 of Int]
```

代表 `InlineArray<5, Int>` 类型的数组，即包含 5 个 Int 元素，存储在线程栈或结构体内部，无需堆分配。

关键语法变化和设计考虑：

* 分隔符从原提案的 x 改为 of，理由是 of 更贴近 Swift 中其他介词关键词（如 in, as），且更不可能与变量名冲突。
* 虽然语法糖中没有显式标明“inline（内联）”特性，语言团队认为这与 Swift 中 `[...]` 语法表示 Array 类似，用户会自然理解其为高性能、固定大小数组。
* 针对未来可能扩展语法支持固定值字面量构造（例如 “`[5 of 0]`”），团队建议若未来加入相关特性，应使用不同语法以避免混淆。

该提案为 Swift 提供了一个简明可读的语法来使用固定容量的内联数组类型，兼顾性能与表达力，尤其适用于嵌入式系统、graphics、游戏开发等对性能敏感的场景。

4、提议[SwiftPM 自定义模板改进包创建流程](https://forums.swift.org/t/pitch-improving-package-creation-with-custom-templates-swiftpm-template-initialization/81525 "SwiftPM 自定义模板改进包创建流程")

提议内容是对现有 swift package init 命令的一项扩展，旨在让 SwiftPM 官方支持使用 自定义可复用包模板，简化复杂项目初始化的流程，从而替代目前常见的第三方脚本或工具方式。

设计目标与动机：

* 当前 SwiftPM 仅支持一些硬编码模板（如 library、executable、macro 等），无法满足复杂项目初始化需求（如 HTTP 服务、OpenAPI 项目等）。
* 本提议在 SwiftPM 内引入模板机制，使模板可以像 Swift 包一样被声明、共享并从注册表或本地引用使用。
* 模板支持可配置参数和逻辑，可通过如下方式调用：

```swift
swift package init --type PartsService --package-id author.template-example
```

接着，SwiftPM 将：

1.	创建临时工作目录
2.	初始化基础包结构
3.	提示用户进行配置选择（如是否添加数据库、是否生成 README 等）
4.	最终将生成内容复制到目标目录

核心优势：

* 与 SwiftPM 深度集成，无需跳出工具链使用外部脚本。
* 极高的可发现性与可共享性：模板本身可发布至包注册表，被团队或社区复用。
* 增强灵活性与一致性：支持各种用例的初始化流程，例如 REST API 服务、CLI 工具、模块化项目结构等。

这个提案有望大幅提升 Swift 包初始化体验，让开发者用更一致、更模块化的方式快速启动新项目

5、提议[嵌入式 Swift 的链接（linkage）模型](https://forums.swift.org/t/embedded-swift-linkage-model/81441 "嵌入式 Swift 的链接（linkage）模型")

该帖子探讨了 Embedded Swift 与 “Desktop Swift” 在链接模型方面的不同设计，并提出了一种更适合嵌入式环境下的链接策略，以改善符号生成与控制。

链接模型对比

* Desktop Swift 链接模型

在编译库时，会在目标对象文件（.o）中生成所有 public、package 和 open 声明的符号。即使某些成员可以通过 @inlinable 或跨模块优化进行内联，但其规范实现仍保留在对象文件中。

* Embedded Swift 链接模型

嵌入式模块会将所有实体定义保存在中间表示（SIL）中，存储于 `.swiftmodule` 文件内。编译时，编译器可以生成整个模块依赖的特化版本代码，也可选择生成空对象文件（适用于库）。这种方式通过泛型特化（specialization）消除类型元数据依赖，是嵌入式 Swift 的核心机制。

类比与设计启发

这种模型类似于 C/C++ 中的 inline 函数或模板实例化：定义保存在头文件中，在使用端生成对应代码，并通过链接时消除重复定义。

嵌入式模型存在的问题

* 非 Swift 客户端使用时的符号冲突

若将多个 Swift 静态库集成至非 Swift 客户端（如 C 程序），容易因重复定义相同模块符号而引发链接错误。虽可通过 -mergeable-symbols 标志指导链接器去重，但这无法保证每个符号在单个对象文件中仅被定义一次。

* 缺乏链接时多态支持

无法像传统 C 模式那样，通过链接不同实现库来选择具体行为；嵌入式 Swift 会在编译时将实现内联到客户端，从而无法动态替换实现，这种神经性通过 -mergeable-symbols 掩盖但不解决问题。
* 实现隐藏不足

因 .swiftmodule 包含所有实现定义，internal 或 `@_implementationOnly` 导入无法隐藏模块依赖，与 Desktop Swift 的链接模型相比缺少封装能力。

总结：该帖子清晰阐释了 Embedded Swift 链接模型的设计理念及其与 Desktop Swift 的区别，并点出了当前设计在静态库集成、符号管理和模块封装方面的挑战。该讨论为未来优化 Embedded Swift 在嵌入式系统和混合语言项目中的构建流程提供了有价值的参考方向。

## 推荐博文

[解密 Swift 5.5 中的 @MainActor, 深入了解其优势与误区 ](https://juejin.cn/post/7533816448919093284/ "解密 Swift 5.5 中的 @MainActor, 深入了解其优势与误区")

**摘要：**  随着 Swift 5.5 的发布，苹果引入了强大的并发编程特性，其中 `@MainActor` 作为一种全局 actor，为开发者提供了一种更优雅的方式来确保 UI 更新在主线程上执行。本文深入探讨了 `@MainActor` 的核心概念、使用场景以及需要注意的常见误区。

`@MainActor` 是一个全局唯一的 actor，它继承自 GlobalActor 协议，专门用于确保标记的代码在主线程上运行。开发者可以将其应用于类、方法、属性或闭包，从而避免手动使用 `DispatchQueue.main.async` 的繁琐操作。例如，在 MVVM 架构中，可以使用 `@MainActor`标记 ViewModel，以确保所有 UI 相关的状态更新都在主线程上执行。此外，`MainActor.run` 方法提供了一种直接在主线程上执行代码块的方式，进一步简化了并发编程。

然而，`@MainActor` 并非在所有情况下都能保证主线程执行。在非隔离上下文（如同步方法或未标记为异步的闭包）中调用 `@MainActor` 方法时，仍可能发生线程安全问题。特别是在 Swift 5 模式下，编译器不会强制检查这种潜在风险，而 Swift 6 则提供了更严格的编译时保护，能够捕获大多数线程隔离问题。

本文还对比了传统 `DispatchQueue.main` 和 `@MainActor` 的优劣，强调了后者在代码简洁性和性能优化上的优势。通过合理的 `@MainActor` 使用，开发者可以减少不必要的线程切换，提升应用性能，同时避免常见的线程安全问题。

最后，文章建议开发者尽早迁移到 Swift 6 语言模式，以充分利用编译器提供的线程安全保护机制。`@MainActor` 作为 Swift 并发模型的重要组成部分，不仅简化了主线程调度，也为未来的并发编程提供了更可靠的基础。

[基于 OpenCV 的 iOS 图像处理](https://juejin.cn/post/7140079324928933896/ "基于OpenCV的iOS图像处理")

**摘要：**  文章首先介绍了 OpenCV 的核心模块及其在 iOS 平台上的适用性，包括图像处理、视频分析、物体检测等关键功能。在集成方式上，开发者既可以通过传统方式手动导入框架，也可以使用 CocoaPods 进行便捷管理，同时需要注意必要的依赖库和编译环境设置。

在实践层面，重点展示了两个典型应用场景：图像灰度化处理和人脸识别。通过封装 UIImage 分类方法，实现了 OpenCV 的 cv::Mat 与 iOS 原生 UIImage 格式的无缝转换，并详细讲解了从图像预处理到特征提取的完整流程。特别是在人脸识别部分，不仅演示了如何加载预训练模型进行人脸检测，还分享了在图像上标记识别结果的具体实现。

针对 iOS 开发中常见的混合编程需求，文章还特别介绍了 Objective-C 与 C++ 的互操作技巧，包括数据类型转换、内存管理等实用内容。这些经验对于需要在项目中同时使用两种语言的开发者具有重要参考价值。

最后，通过实际效果展示和完整代码示例，为开发者提供了可直接复用的解决方案。这些技术不仅适用于基础的图像处理需求，也能为 AR/VR、人工智能等前沿应用提供底层支持，展现了 OpenCV 在移动开发领域的广阔应用前景。

[iOS 开发之集成目标检测模型 YOLOv8 ](https://juejin.cn/post/7370876224320618535/ "iOS 开发之集成目标检测模型 YOLOv8 ")

**摘要：**  本文详细介绍了如何在 iOS 应用中集成 YOLOv8 目标检测模型的全流程，从模型训练到 Core ML 转换，再到最终在项目中的实际应用。YOLOv8 作为一种高效的目标检测算法，凭借其轻量级和高精度的特点，成为移动端开发的理想选择。

文章首先讲解了 YOLOv8 模型的获取方式，开发者可以从 Hugging Face 或 Ultralytics 官网下载不同精度的预训练模型。随后重点介绍了自定义数据集的训练方法，通过简单的命令行即可完成模型微调，使其适应特定场景的需求。由于 YOLO 模型无法直接在 iOS 中使用，文章详细演示了如何将训练好的 .pt 模型转换为 Apple 官方支持的 Core ML 格式，这一步骤是 iOS 集成的关键。

在开发实践部分，文章提供了完整的代码示例，展示如何通过 Vision 框架加载 Core ML 模型，并利用 AVFoundation 处理实时摄像头输入。核心内容包括模型初始化、请求创建、图像处理以及检测结果解析，其中特别介绍了如何通过 `VNRecognizedObjectObservation` 获取目标的类别、置信度和位置信息。此外，文章还分享了设备方向适配等实用技巧，确保检测结果能够正确匹配屏幕显示。

本文为开发者提供了一条清晰的路径，帮助他们在 iOS 应用中快速集成高性能的目标检测功能。通过遵循文中的步骤，开发者可以避免常见的模型转换和集成问题，专注于构建更智能的移动应用体验。无论是静态图片分析还是实时视频流处理，这套方案都能提供可靠的目标检测能力。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
