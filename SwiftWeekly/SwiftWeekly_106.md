## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百零六期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

盛夏丰盈，万物生光，让我们在滚烫的日子里撒野，奔赴那个叫做远方的诗行。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：苹果创新周期打开增量空间：折叠屏与 AI Siri 共振；果链公司双线谋增长
> * **提案**：Iterable 协议正式通过；SE-0540 默认目标设置、SE-0541 Swift/C 互操作正在审查
> * **Swift 论坛**：宏初始化 self 访问、隔离协议并发安全性、Iterable 经修改后获接受
> * **推荐博文**：SwiftData 可测试性、iOS 性能诊断方法论、协议与全局 Actor

**上期投票结果：**

![](https://files.mdnice.com/user/47553/c5ff4ff1-1ae3-4940-8180-1df90facca89.png)

**如果 OpenAI 真的推出 AI 硬件，62.5% 的读者选择等评测再决定，另有 25% 明确表示不会考虑，仅 12.5% 愿意第一时间尝鲜——消费者对 AI 新硬件的态度趋于理性务实。**

## 话题讨论

**在 AI 迅速发展的今天，为了不被 AI 替代，程序员最应该做的事情是什么？**

1、深耕业务，成为业务专家
2、提升架构和复杂系统设计能力
3、学会编写各种 Skill 文档，提升 AI 工作效率
4、趁早转行

欢迎在评论区留下你的看法和建议。

## 新闻和社区

### 苹果创新周期打开增量空间 "果链"公司双线谋增长

*2026 年 8 月 6 日｜来源：新浪财经*

北京 8 月 6 日电，苹果正迎来近年来最大规模的产品创新周期。这将是一场为期三年、覆盖手机、手表、平板、电脑、智能家居五大产品线的深度战略布局，2026 年下半年计划推出折叠屏手机、iPhone 18 系列等十几款新品。

**苹果交出史上最强劲季度成绩单** 截至 2026 年 6 月 27 日的第三财季，苹果营收达 1094 亿美元，同比增长 16%，iPhone、Mac 和服务在全球所有地区均实现两位数营收增长。

**折叠屏与 AI 成最大增量窗口** 多方消息表明，苹果首款折叠屏手机采用阔折叠形态，内屏展开后接近 4:3 比例，2026 年组装出货量预计达 700 万至 800 万台。单机零部件价值将显著高于普通 iPhone，折叠屏核心结构件供应商将率先获得实质增量。

同时，"Apple 智能"正式通过手机端侧生成式 AI 服务备案，阿里千问将作为 AI 能力集成至 Apple 智能。另有消息称，苹果计划将 AI 眼镜打造为健康健身终端。

**全行业直面存储涨价"压力测试"** 今年上半年国内多个品牌手机已进行两至三轮涨价。6 月 25 日苹果宣布对 MacBook 和 iPad 实施全球提价，涨幅约 20%。部分 1TB、2TB 固态硬盘单价可达 1000 至 2000 元，DRAM 与 SSD 合计成本占整机物料成本的 30%至 40%，行业低谷时期该占比仅 10%左右。

**"果链"寻求第二增长曲线** 工业富联预计上半年归母净利润 234 亿至 244 亿元，同比增长 93%至 101%，AI 服务器与数据中心交换机业务成为新引擎。蓝思科技布局汽车玻璃、机器人组装等业务，京东方 A 携手康宁围绕玻璃基封装载板开展合作。舜宇光学董事长王锬炯这样定义转型："让手机拍出好照片，是过去 40 年的事；让 AI 看懂物理世界，是未来几十年的事。"

### 苹果 Siri AI 即将登场：亟需高频重大更新

*2026 年 8 月 4 日｜来源：星途科讯*

随着苹果 OS 27 更新的发布，iPhone、iPad、Mac 和 Apple Watch 将预装成熟的对话式人工智能——"Siri AI"。这不再是一个基础的语音助手，而是一个拥有完整对话历史、能处理复杂提示词并从广泛知识库中提供答案的独立应用程序。用户可向其上传文档并指令执行操作，其形态酷似 ChatGPT、Gemini 或 Claude，区别在于它将预装在数亿台设备上。

新 Siri AI 在几乎所有维度上都较旧版实现了巨大飞跃。它能从信息、邮件、联系人及网络历史记录中提取上下文，提供更具个性化的回答，真正展现出"私人助理"的特质。然而，与前沿模型相比，Siri AI 在信息访问广度、复杂查询理解及输入处理深度上仍显不足。

**Siri AI 亟需高频重大更新** 苹果习惯于每年随新操作系统发布进行核心组件的重大改进，这种节奏对于 AI 领域而言过于缓慢。过去一年，主要 AI 厂商已建立起每数月进行一次重大发布的节奏：

- **Anthropic**：发布了 Claude Opus 4.1 至 Opus 5 等多个版本
- **OpenAI**：推出了 ChatGPT 5 及 GPT 5.1 至 GPT 5.6 等系列更新
- **Google**：更新了 Gemini 3 Pro、3 Deep Think、3.1 Pro、3.5 Flash 等变体

Siri AI 基于与 Google Gemini 相同的技术基础，使用苹果自有训练数据和权重，被称为苹果基础模型（AFM）3。为在 AI 竞赛中保持竞争力，苹果需对运行在设备端的 AFM 3 Core 和云端的 AFM 3 Cloud 进行每年多次的重大更新，理想的节奏可能包括 12 月发布 AFM 3.1、3 月发布 AFM 3.2、5 月发布 AFM 3.5，并最终在 OS 28 更新时推出 AFM 4。

**苹果能否适应新节奏？** 这种全年持续交付显著质量提升的开发模式，与苹果传统的秋季大更、后续小修小补的习惯截然不同。然而，变革时机或许已经成熟——一位新任 CEO 将于 9 月上任，且苹果近期已展现出打破常规的迹象，从统一操作系统命名方案，到推出入门级 MacBook，再到设计更易维修的产品。

## 提案

### 通过的提案

[SE-0478](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0478-default-isolation-typealias.md "SE-0478")
**File-level 默认值** 提案已通过审查。

该提案此前已在 **第七十六期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0516](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0516-borrowing-sequence.md "SE-0516")
**可迭代协议（Iterable）** 提案已通过审查。

该提案此前已在 **第九十六期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0526](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0526-deadline.md "SE-0526")
**withDeadline** 提案已通过审查。

该提案此前已在 **第九十八期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0535](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0535-global-mirrors-configuration-cli.md "SE-0535")
**添加用于编辑全局镜像配置的CLI** 提案已通过审查。

该提案此前已在 **第一百零四期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0536](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0536-registry-search.md "SE-0536")
**软件包注册表搜索** 提案已通过审查。

该提案此前已在 **第一百零四期周报** 的「正在审查的提案」模块中做过详细介绍。

### 正在审查的提案

[SE-0539](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0539-self-access-for-property-initializers.md "SE-0539")
**启用宏以授予属性初始化器的 self 访问权限** 提案正在审查。

为 `accessor` 宏角色声明新增一个可选 `initialization: selfAvailable`。该参数用于声明：此宏会将属性初始化表达式转移至全新上下文，在该上下文中允许访问自身 `self` 以及实例成员。

[SE-0540](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0540-default-target-settings.md "SE-0540")
**默认目标设置** 提案正在审查。

Swift 软件包在所有目标上使用相同的设置标志是很常见的。应用这些基本设置的内置机制提高了软件包清单的可读性和便利性。

[SE-0541](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0541-flexible-swift-c-interoperability-for-packages.md "SE-0541")
**软件包的灵活 Swift/C 互操作性** 提案正在审查。

Swift 对与 C、C++ 和 Objective-C 的双向互操作性有很好的支持，但历史上 SwiftPM 限制了软件包作者可用的一组互操作功能。该提案解除了其中大部分限制，为软件包提供了一套新的工具来组织其代码。

[SE-0543](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0543-inline-array-hashable.md "SE-0543")
**InlineArray: Hashable** 提案正在审查。

当 Element 满足时，InlineArray 有条件地符合 Equatable 和 Hashable。

### 拒绝的提案

[SE-0534](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0534-swiftpm-exact-literal-version-matching.md "SE-0534")
**选择与构建元数据完全匹配版本标识符** 提案被拒绝。该提案此前已在 **第一百零三期周报** 的「正在审查的提案」模块中做过详细介绍。

## Swift论坛

### 1、[SE-0539：让宏为属性初始化表达式开放 self 访问]

作者：Nils Grabenhorst ｜ 发布日期：2026 年 8 月 2 日
[阅读原帖](https://forums.swift.org/t/se-0539-enable-macros-to-grant-self-access-for-property-initializers/88713 "SE-0539: Enable Macros to Grant `self` Access for Property Initializers")

**核心内容：**
SE-0539 为 **accessor macro** 的角色声明新增可选参数 `initialization: selfAvailable`，允许宏承诺把属性初始化表达式移动到一个可以访问 `self` 的上下文。当前编译器在宏展开前会把所有属性初始化表达式都按立即执行处理，导致模拟 `lazy` 行为的宏即使最终把表达式放进 getter，也无法引用实例成员。

**动机说明：**
原生 `lazy` 属性可以在初始化表达式中访问实例成员，但实现同样语义的宏却会被提前拒绝。提案希望消除这种能力差异，同时保留宏展开前的类型检查，以便宏仍能获得推断出的属性类型。

**主要修改或代码示例：**

```swift
@attached(accessor, initialization: selfAvailable,
          names: named(get), named(set))
@attached(peer, names: prefixed(_))
public macro Lazy() = #externalMacro(...)

struct Earth {
    let mice = 21
    @Lazy var theAnswer = self.mice * 2
}
```

**简要点评：**
这是一个范围克制但实用的宏能力补全，让库作者可以构建更接近语言原生 `lazy` 的抽象，同时把正确放置初始化表达式的责任明确交给宏实现者。

### 2、[SE-0540：为 Swift Package 提供默认构建设置]

作者：Matt Massicotte ｜ 发布日期：2026 年 8 月 3 日
[阅读原帖](https://forums.swift.org/t/se-0540-default-package-settings/88748 "SE-0540: Default Package Settings")

**核心内容：**
SE-0540 提议在 **Package.swift** 的 `Package` 层统一声明 `defaultSwiftSettings`、`defaultCSettings`、`defaultCXXSettings` 和 `defaultLinkerSettings`，减少多 target 包中反复复制相同编译选项的问题。

**主要修改或代码示例：**

```swift
let package = Package(
    name: "MyPackage",
    targets: [
        .target(name: "Library"),
        .testTarget(
            name: "LibraryTests",
            swiftSettings: [.inherited()]
        )
    ],
    defaultSwiftSettings: [
        .enableUpcomingFeature("ApproachableConcurrency")
    ]
)
```

**简要点评：**
提案直击多 target 包的真实痛点，但继承顺序与覆盖规则会成为长期 API 心智负担；在接受前进一步简化退出继承和覆盖单项设置的表达方式会更稳妥。

### 3、[隔离协议一致性中的 concurrent 方法真的安全吗？]

作者：Matt Massicotte ｜ 发布日期：2026 年 8 月 6 日
[阅读原帖](https://forums.swift.org/t/are-concurrent-methods-on-isolated-conformances-actually-safe/88813 "Are concurrent methods on isolated conformances actually safe?")

**核心内容：**
讨论研究 **isolated conformance** 与 `@concurrent` 协议要求组合时的安全性。一个 `@MainActor` 类型以主 Actor 隔离方式遵循协议，但从 `nonisolated(nonsending)` 函数调用其 `@concurrent` 要求时，编译器警告该一致性可能被传入并发上下文。

**主要修改或代码示例：**

```swift
protocol AsyncRequirement {
    @concurrent func work() async
}

@MainActor
final class ConformingType: @MainActor AsyncRequirement {
    func work() async {}
}

nonisolated(nonsending) func useThem() async {
    let value: some AsyncRequirement = ConformingType()
    await value.work() // 隔离一致性警告
}
```

**简要点评：**
这场讨论很好地展示了 Swift 并发标注不能只看"是否 async"：方法实际在哪个隔离域执行，以及协议一致性何时跨域，才是判断安全性的核心。

### 4、[SE-0516 Iterable 经修改后获接受]

作者：Nate Cook、Ben Cohen ｜ 发布日期：2026 年 8 月 5 日
[阅读原帖](https://forums.swift.org/t/accepted-with-modifications-se-0516-iterable/88806 "[Accepted with modifications] SE-0516: `Iterable`")

**核心内容：**
语言指导组宣布 SE-0516 经修改后接受。新的 **Iterable** 协议为同步迭代提供统一入口，覆盖不可复制、不可逃逸元素及可抛错迭代，并通过批量返回 **Span** 降低跨模块逐元素调用的成本；常见代码仍可使用熟悉的 `for-in`。

**讨论亮点：**
最终契约规定：迭代器一旦返回空 span，后续 `nextSpan()` 也必须为空；一旦抛错，调用方不得再次调用 `nextSpan()`。需要可恢复错误的场景应使用非抛错、元素为 `Result` 的迭代器。

**简要点评：**
最终方案在命名、可预测语义和性能之间取得了务实平衡，也让 Swift 的同步迭代能力更好地衔接所有权模型。

### 5、[SE-0541：为 Swift Package 放宽 Swift/C 互操作限制]

作者：Owen Voorhees ｜ 发布日期：2026 年 8 月 5 日
[阅读原帖](https://forums.swift.org/t/se-0541-flexible-swift-c-interoperability-for-packages/88796 "SE-0541: Flexible Swift/C Interoperability for Packages")

**核心内容：**
SE-0541 计划解除 **SwiftPM** 对包内 Swift 与 C 系语言互操作的多项限制：普通、可执行、测试和宏 target 可混合 Swift、C、C++ 与 Objective-C 源码，并可配置 bridging header。插件 target 本身仍只允许 Swift 源码。

**主要修改或代码示例：**

```swift
.executableTarget(
    name: "swift-format",
    swiftSettings: [
        .bridgingHeader(
            "swift-format-bridging-header.h",
            visibility: .internal
        )
    ]
)
```

**简要点评：**
这是一项显著改善工程体验的 SwiftPM 提案，可减少 shim target 和手工模块化样板，让 Swift/C 渐进式混编更接近 Xcode 工程中的成熟能力。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[构建可测试的 SwiftData 应用](https://azamsharp.com/2026/08/02/building-testable-swiftdata-apps "构建可测试的 SwiftData 应用")

**摘要：** 这篇博客聚焦于 SwiftData 应用中测试策略的落地实践。作者深入探讨了如何通过依赖注入和自定义容器来隔离数据层，使单元测试不再受真实持久化存储的干扰。文章不仅展示了模拟数据上下文的技巧，还提供了构建可靠、可维护测试套件的具体模式，为采用 SwiftData 的开发者填补了从"能用"到"可测"之间的关键空白。

[别再浪费 Token 问"怎么修我的 iOS 应用性能"了](https://ohmyswift.com/blog/2026/08/02/stop-burning-tokens-on-fix-my-ios-app-performance/ "别再浪费 Token 问"怎么修我的 iOS 应用性能"了")

**摘要：** 这篇博客犀利地指出，与其反复向 AI 助手求助"修复性能问题"，开发者更应该掌握一套系统性的性能诊断方法论。文章从 Instruments 工具的正确使用姿势讲起，梳理了从定位 CPU 瓶颈、内存泄漏到优化渲染路径的完整工作流。全文旨在帮助开发者建立"先测量、后优化"的工程思维，将 AI 从"开药方的医生"降级为"执行处方的高级助手"。

[再探 Swift 协议与全局 Actor](https://www.massicotte.org/blog/protocols-and-global-actors/ " 再探 Swift 协议与全局 Actor")

**摘要：** 这篇博客深入剖析了协议与 Actor 隔离之间微妙的交互关系。文章清晰地区分了三种场景：整个协议被 @MainActor 标记、每个协议要求单独隔离，以及利用 Swift 6.2 新工具实现无隔离。核心观点是：在给协议打上 @MainActor 之前，先问清楚它是否真的需要——因为一旦这个约束进入代码库，就很难再移除了。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 "进群" 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
