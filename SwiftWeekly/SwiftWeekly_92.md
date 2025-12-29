## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第九十二期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

喜欢蝴蝶，不应该把它捏在手中，直到蝴蝶动弹不得。不妨试试低头种花，直到花儿绽放盛开，漫天蝴蝶纷至沓来。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：苹果重组并扩大 AI 团队，Apple Intelligence 明年初迎来关键更新
> * **提案**：SE-0499 正式通过，Swift 所有权模型继续演进
> * **Swift 论坛**：ArrayBuilder、SwiftPM 遥测、async 重试框架等多项讨论
> * **推荐博文**：并发、集合操作、SwiftUI Markdown 全覆盖

上期话题投票结果如下：

![](https://files.mdnice.com/user/47553/adce6981-8d62-4f39-bd3b-15e7581ee3ad.jpg)

在上期投票中，**近 7 成读者认为科技创新“更难了”**，但同时也有不少朋友认为，智能化正在加速技术演进的节奏。

欢迎大家继续在评论区分享你的判断依据。

## 话题讨论

### 本期话题：**当前最具影响力的科技趋势是什么？**

你认为，正在深刻影响未来 5～10 年的技术力量是哪一个？

1. AI 存储与半导体的爆发式增长
2. 自动驾驶出租车（Robotaxi）走向主流
3. AI 芯片之战（如 Nvidia vs Groq）
4. 下一代消费级显示技术（OLED / 新型电视技术）
5. 加密货币与区块链相关科技股票的市场情绪

欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### iPhone 18 Pro 系列或迎新配色，外观与硬件同步重构

![](https://files.mdnice.com/user/47553/9b4b4d98-4714-4fca-9d65-1b4eb101ac33.png)

在 iPhone 17 Pro 系列大幅收缩配色后，苹果并未在 Pro 产品线上“保守应对”。
最新消息显示，**iPhone 18 Pro / Pro Max** 正在评估 **酒红色、棕色、紫色** 等新配色方案。

更重要的是，外观设计可能迎来关键变化：

* Face ID 或完全移入屏幕下方
* 灵动岛形态可能消失
* 前置摄像头改为左上角单孔设计

硬件层面还包括：

* **A20 Pro（台积电 2nm）**
* 新一代自研蜂窝基带
* 升级版无线芯片

从节奏上看，iPhone 18 Pro 更像是一次 **外观语言 + 底层架构的同步重构节点**。

### 苹果重组并扩大 AI 团队，Apple Intelligence 明年初迎来关键更新

尽管外界一度唱衰苹果 AI，但最新信息显示，苹果正在 **系统性重组并扩大 AI 团队规模**，并继续坚持“设备端 AI + 可控云端协作”的路线。

一个重要信号是：
**苹果已允许 AI 研究人员公开发表论文**，外界统计显示，仅公开论文中就涉及近 **200 位研究人员**。

Apple Intelligence 的下一阶段更新预计随 **iOS 26.4（2026 年初）** 发布，重点包括：

* 基于大模型的新一代 Siri
* 更深度的 App Intents 执行能力
* 设备端 Foundation Models 与云端模型协作

从整体策略来看，苹果并未放弃 AI，而是在以其一贯“慢但可控”的方式推进。

### 苹果强烈建议升级 iOS 26，应对已被利用的高危漏洞

![](https://files.mdnice.com/user/47553/075593fe-6e43-4163-b266-15e929f91c82.png)

苹果近期明确调整安全策略：
**iPhone 11 及之后机型，如需获得完整安全修复，必须升级至 iOS 26。**

目前至少 **50% 的兼容设备仍未升级**，但安全公司指出，大量漏洞已被真实利用。
系统升级，正在成为苹果推动安全防线的核心手段。

## 提案

### 通过的提案

[SE-0499](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0499-support-non-copyable-simple-protocols.md "SE-0499")
**在简易标准库协议中支持 ~Copyable 与 ~Escapable** 提案已通过审查。

该提案此前已在 **第九十期周报** 的「正在审查的提案」模块中做过详细介绍。本次通过，标志着 Swift 在 **所有权模型与资源管理能力** 上又向前迈进了一步。

## Swift 论坛

### 1、提案：将 ArrayBuilder 引入标准库

作者：Filip Zavolokov ｜ 发布日期：2025 年 12 月 18 日
[阅读原帖](https://forums.swift.org/t/add-arraybuilder-to-the-standard-library/83811 "Pitch: Add @ArrayBuilder to the standard library" "提案：将 ArrayBuilder 引入标准库")

该 pitch 建议将 **ArrayBuilder** 这一声明式数组构造工具纳入 Swift 标准库，允许开发者像使用 `@ResultBuilder` 一样，通过控制流组合数组元素。

示例写法如下：

```swift
let nums = ArrayBuilder {
    if condition {
        1
    }
    for i in 0..<3 {
        i
    }
    10
}
```

支持者认为，这种方式能显著减少条件拼接数组时的样板代码，使集合构造更直观、可读。

讨论中的主要关注点包括：

* 是否应同步为 `Set` 等其他集合提供类似构造器
* 构建器语法对调试体验与类型推断的影响
* 是否应以附加模块形式提供，避免标准库膨胀

**简要点评：**
这是一个明显改善“日常体验”的提案方向，但其适用边界和标准库定位仍需谨慎权衡。

### 2、提案：为 swift build 集成可选的外部遥测服务

作者：Aleksandar Prokopec ｜ 发布日期：2025 年 12 月 18 日
[阅读原帖](https://forums.swift.org/t/proposal-external-telemetry-service-integration-for-swift-build/83806 "提案：为 swift build 集成可选的外部遥测服务")

该提案希望为 SwiftPM 构建流程引入 **可选的遥测集成机制**，用于收集构建时间、缓存命中率、依赖解析行为等指标。

设计重点包括：

* 遥测完全 **非强制启用**
* 仅上报结构化、非敏感数据
* 允许对接第三方或组织自建遥测后端

社区的主要分歧集中在隐私与复杂性：

* 支持者认为这有助于发现真实构建瓶颈
* 反对者担心构建系统承担过多职责

**简要点评：**
这是一个偏工程治理层面的提案，若设计得当，对大型项目和 CI 场景具备实际价值。

### 3、社区动态：我的第一个 PR 被合并进 Swift

作者：Paavo ｜ 发布日期：2025 年 12 月 18 日
[阅读原帖](https://forums.swift.org/t/a-christmas-milestone-my-first-pr-merged-into-swift/83840 "社区动态：我的第一个 PR 被合并进 Swift")

这是一篇典型的社区里程碑分享帖。作者记录了自己从零开始理解 Swift 编译器、提交修复、通过 CI 并最终合并 PR 的完整过程。

**简要点评：**
这类帖子虽非技术提案，但对社区健康度极其重要，能有效降低“参与门槛”的心理压力。

### 4、介绍 Typhoon：一个轻量级 async/await 重试框架

作者：R-Mo ｜ 发布日期：2025 年 12 月 17 日
[阅读原帖](https://forums.swift.org/t/introducing-typhoon-a-lightweight-async-await-retry-framework-for-swift/83797 "介绍 Typhoon：一个轻量级 async/await 重试框架")

Typhoon 提供了一套 **可组合、声明式的重试策略 API**，专为 Swift 并发模型设计，适用于网络请求和易失败的异步操作。

```swift
let result = try await retry(
    .limit(3).backoff(exponential: .seconds(1))
) {
    try await fetchData()
}
```

**简要点评：**
这是一个贴合 async/await 使用习惯的实用工具，值得在存在大量重试逻辑的项目中关注。

### 5、讨论：在 Swift 生态中更好支持 zlib

作者：Douglas Gregor ｜ 发布日期：2025 年 12 月 17 日
[阅读原帖](https://forums.swift.org/t/zlib-support-in-the-swift-ecosystem/83792 "讨论：在 Swift 生态中更好支持 zlib")

讨论围绕 **如何在 SwiftPM 和工具链层面降低 zlib 集成成本** 展开，而非直接将其引入标准库。

**简要点评：**
这是一个典型的“生态基础设施”问题，若在 SwiftPM 层得到改善，将对跨平台与系统级项目带来长期收益。

## 推荐博文

以下三篇文章非常值得一读，适合本周“提升技能 + 开阔思路”：

[Swift 新并发框架之 async/await ](https://juejin.cn/post/7587349016221810729/ "iOS 知识点 - 多线程总结（Swift 新并发框架之 async/await ")

**摘要：** Swift async/await 是新并发框架的核心，它从根本上重塑了异步代码的写法。它将原本分散嵌套的回调逻辑，转变为直观、线性的同步风格，让代码更易读、更易维护。

其核心在于，用 async 声明可能暂停的函数，用 await 标记调用时的潜在挂起点。关键在于，挂起的是函数而非线程——函数在等待时会释放当前线程，待结果就绪后恢复执行，这避免了阻塞，但也意味着要避免在持锁时跨越 await。

在实际使用中，通过 Task 进入异步上下文，并用 MainActor 确保 UI 更新回到主线程。同时，可以利用续体（Continuation）将现有回调 API 桥接到新的 async/await 世界，实现渐进式迁移。

总的来说，async/await 以更清晰、更安全的方式解决了并发编程的典型痛点，是现代 Swift 开发中提升代码质量和开发效率的关键特性。

[Swift 中 map、compactMap、flatMap 三者的核心区别](https://juejin.cn/post/7583226204033679401/ "Swift 中 map、compactMap、flatMap 三者的核心区别")

**摘要：**  在 Swift 中，map、compactMap 和 flatMap 都是用于对集合进行变换的高阶函数，它们各自承担着不同的数据处理职责。map 专注于一对一的元素转换，保持原有结构不变；compactMap 在转换的基础上，自动过滤掉空值，确保了数据的有效性；而 flatMap 则擅长处理嵌套结构，将多维数据展平为一维序列，简化复杂数据的处理逻辑。

这三者虽功能相似，却各有侧重，共同构成了 Swift 中强大而优雅的数据转换体系。在金融、数据聚合或多层嵌套的业务场景中，合理选择使用它们，可以让代码既安全又清晰，同时保持函数式编程的简洁风格。

[SwiftUI-Markdown 渲染](https://juejin.cn/post/7511299182264958986/ "SwiftUI-Markdown 渲染")

**摘要：**  这篇文章介绍了 SwiftUI 在 iOS 15 及更高版本中原生支持 Markdown 渲染的功能，使开发者能够轻松在应用中展示格式化的文本。文章详细说明了 SwiftUI 所支持的内联 Markdown 语法，包括加粗、斜体、删除线、内联代码和链接，并提供了具体的代码示例展示如何直接在 Text 视图中使用这些语法。

此外，还介绍了通过 String 和 LocalizedStringKey 来渲染 Markdown 文本的灵活方式。虽然当前功能有一定局限，但对于大多数应用场景已足够实用，有助于开发者更专注于内容与用户体验，而无需依赖额外的富文本库。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
