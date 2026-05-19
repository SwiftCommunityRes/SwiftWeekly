## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第九十九期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

生活给予我们百般苦难，但伤痕使我们愈发强壮。当穿过暴风雨幕，你就不再是原来的自己，坚韧会触发蜕变，勇气将收获新生！👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：苹果官宣库克 9 月卸任 CEO、任执行董事长，硬件工程高级副总裁 **约翰·特努斯（John Ternus）** 接任；古尔曼爆料 6 大新品方向（AI AirPods、智能眼镜、HomePad、桌面机器人等）
> * **提案**：SE-0511、SE-0520、SE-0521、SE-0524 正式通过；SE-0527～SE-0529 正在审查
> * **Swift 论坛**：SE-0529 `FilePath` 进标准库、`@Reasync` 宏 pitch、值类型 `init` 与 `private let` 缺陷、Calendar 时区初始化、SE-0521 接受（含修改）
> * **推荐博文**：Electron 录音引擎 Swift 重写、Swift 并发运行时追踪、Swift 6.3 与 Android SDK

上期话题投票结果如下：

![](https://files.mdnice.com/user/38781/39364096-24a4-4731-b9f9-b3cce78db317.jpg)

## 话题讨论

### 本期话题：**苹果 CEO 交接之际，你最关注哪一方面？**

**选项：**

1. 硬件与自研芯片路线能否延续
2. 软件、AI 与开发者体验
3. 中国市场与供应链
4. 先观望，以后续产品为准
5. 其他（欢迎留言说明）

欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### 苹果官宣 CEO 库克即将卸任，硬件高管约翰·特努斯将接任

*2026 年 4 月 21 日｜来源：TechWeb*

苹果宣布：现任 CEO **蒂姆·库克**拟于 **2026 年 9 月 1 日**卸任首席执行官，转任董事会**执行主席**；**约翰·特努斯（John Ternus）**接任 CEO。库克 1998 年加入苹果，2011 年起任 CEO 近 15 年，公司市值与营收大幅提升。特努斯 2001 年加入苹果，长期负责硬件工程，被认为是自研芯片与多款主力产品线的关键推动者。

库克发布致用户公开信，回顾与全球用户通过邮件建立的联结，表达对团队与用户的感谢，并强调特努斯对苹果价值观与产品文化的认同；**完整原文以苹果官方与权威媒体发布为准**，此处从略以控制篇幅。

![](https://upload.techweb.com.cn/s/1080/imgs/2026/0421/1776732745695.jpg)

![](https://upload.techweb.com.cn/s/1080/imgs/2026/0421/1776732762481.jpg)

### 苹果将开发 6 大新产品，涉机器人、安防摄像头等

*2026 年 4 月 24 日｜来源：TechWeb*

马克·古尔曼在播客中爆料，苹果正探索约 **6 类**新品方向，涵盖 **AI AirPods**、**智能眼镜**、挂饰类设备、**带屏智能音箱（HomePad）**、**桌面机器人**、**安防摄像头** 等，多数为苹果此前较少涉足的形态。报道称 **智能眼镜** 或于 2026 年底至 2027 年初有节点，**HomePad** 或于 2026 年秋季，**桌面机器人** 或指向 2027 年（亦可能延期）。具体节奏以官方为准，市场亦关注苹果能否在智能家居与可穿戴红海中做出差异化体验。

## 提案

### 通过的提案

[SE-0511](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0511-swiftpm-add-target-plugin.md "SE-0511")
**SwiftPM 添加目标插件命令** 提案已通过审查。

该提案此前已在 **第九十五期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0520](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0520-discardableresult-task-initializers.md "SE-0520")
**在任务初始化器中使用可丢弃的结果** 提案已通过审查。

该提案此前已在 **第九十七期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0521](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0521-improved-optional-opaque-and-any.md "SE-0521")
**改进了不透明和存在类型可选的语法** 提案已通过审查。

该提案此前已在 **第九十七期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0524](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0524-span-temporary-allocation.md "SE-0524")
**使用 Output(Raw)Span 添加 withTemporaryAllocation** 提案已通过审查。

该提案此前已在 **第九十八期周报** 的「正在审查的提案」模块中做过详细介绍。

### 正在审查的提案

[SE-0527](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0527-rigidarray-uniquearray.md "SE-0527")
**RigidArray 和 UniqueArray** 提案正在审查。

建议在标准库引入 `RigidArray` 与 `UniqueArray`，用于存储**不可复制（`~Copyable`）** 元素的数组场景（与既有 `Array` 的 CoW 模型区分）。

[SE-0528](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0528-noncopyable-continuation.md "SE-0528")
**Continuation：安全且高性能的异步延续** 提案正在审查。

提出 `Continuation<Success, Failure>` 等设计，以 **~Copyable** 与 **consuming** 语义缩小 `UnsafeContinuation` 与 `CheckedContinuation` 之间的安全与性能差距。

[SE-0529](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0529-filepath-in-stdlib.md "SE-0529")
**将 FilePath 添加到标准库** 提案正在审查。

将代表平台路径的 `FilePath` 及其基础操作纳入标准库，作为文件系统相关 API 的「货币类型」基础；更细致的便利 API 可后续迭代。

## Swift 论坛

### 1、SE-0529：将 FilePath 加入标准库

作者：John McCall ｜ 发布日期：2026 年 4 月 23 日
[阅读原帖](https://forums.swift.org/t/se-0529-add-filepath-to-the-standard-library/86194 "SE-0529: Add FilePath to the Standard Library")

审查期截至 **2026 年 5 月 4 日**。提案拟将 **`FilePath`** 提升为 Swift 标准库类型，统一跨平台（POSIX / Windows）路径表示与基础操作，并讨论与 **`swift-system`** 既有实现的迁移关系。

**动机：**
在标准库中缺少专用路径类型时，开发者往往过度依赖 `URL` 或额外依赖，路径语义与文件系统交互不够清晰。

**讨论亮点：**
围绕命名（如 `nullTerminated` 相关）、路径规范化与符号链接、是否 `Codable` 等讨论较多；有建议将平台差异与最佳实践写进标准库文档。

**简要点评：**
面向文件系统路径的「正名」型提案，有利于减少 `URL` 滥用与提升跨平台基础层一致性。

### 2、Pitch: @Reasync 与 @ReasyncMembers 宏

作者：broken-circle ｜ 发布日期：2026 年 4 月 22 日
[阅读原帖](https://forums.swift.org/t/pitch-reasync-and-reasyncmembers-macros/86180 "Pitch: @Reasync and @ReasyncMembers macros")

提议通过 **`@Reasync`** / **`@ReasyncMembers`** 在编译期为 `async` API 生成同步重载，减轻双份维护与漂移问题；作为语言级 `reasync` 未落地前的工程化补充。

**简要点评：**
适合测试、断言库等需要同步/异步成对 API 的场景，可展开关注与实现细节对函数体变换的覆盖范围。

### 3、带默认值私有 `let` 字段的 `init` 值语义问题

作者：taylorswift ｜ 发布日期：2026 年 4 月 22 日
[阅读原帖](https://forums.swift.org/t/value-semantics-of-init-with-defaulted-private-let-fields-does-not-make-sense/86193 "Value semantics of init with defaulted private-let fields does not make sense")

示例表明：含带默认值 **`private let`** 字段的结构体在扩展中写 `self = .init(...)` 会误报「只能初始化一次」。讨论中 **Joe Groff** 认为更像**编译器缺陷**，应把整体赋值视为值替换而非逐字段赋初值。

**简要点评：**
影响用 padding / 预置字段等模式封装值类型的实际写法，若修复将减少意外编译错误。

### 4、为特定时区的 Calendar 提供更具表达力的初始化方式

作者：Kiel Gillard ｜ 发布日期：2026 年 4 月 21 日
[阅读原帖](https://forums.swift.org/t/expressively-initialising-calendars-for-specific-time-zones/86139 "Expressively initialising calendars for specific time zones")

提议 **`Calendar(identifier:timeZone:)`** 等一次性构造方式；社区亦讨论 **流式/链式** API 作为替代或补充，以支撑后续更多配置项而保持可读性。

**简要点评：**
小改进型讨论，与 Foundation API 演进的 ABI/扩展性需要一并权衡。

### 5、［已接受（含修改）］SE-0521：改进 Opaque 与 Existential 类型的 Optional 语法

作者：Jumhyn (Frederick Kellison-Linn) ｜ 发布日期：2026 年 4 月 19 日
[阅读原帖](https://forums.swift.org/t/accepted-with-modifications-se-0521-improved-syntax-for-optionals-of-opaque-and-existential-types/86115 "Accepted with modifications: SE-0521")

**SE-0521** 已由 LSG **接受（含修改）**：除允许 `any P?` / `some P?` 的写法外，对 **抑制约束（如 `~Copyable`）** 的 optional 形式亦做了对齐说明；`.swiftinterface` 中可仍保留带括号形式以便工具消费。

**简要点评：**
语法层「少写一层括号」的改进，配合约束抑制场景，有利于并发与存在类型相关代码的可读性。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[我们如何用 Swift 重写 Electron 录音引擎](https://circleback.ai/blog/how-we-rebuilt-our-electron-recording-engine-in-swift/ "我们如何用 Swift 重写 Electron 录音引擎")

**摘要：** Circleback 团队将实时音视频采集从渲染进程中的 JS 迁出，在 macOS 使用 ScreenCaptureKit、在 Windows 结合自研与原生层，并以 Swift 搭建共享逻辑；同时介绍内部工具在编译期生成与前端类型安全桥接的实践，可借鉴实时媒体类桌面应用架构。

[Swift 并发：一个 await、两个 Actor 的运行时追踪](https://adjoe.io/company/engineer/blog/swift-concurrency-await-runtime-trace-executor-hops/ "Swift 并发：一个 await、两个 Actor 的运行时追踪")

**摘要：** 从一次跨 Actor 的 `await` 出发，结合运行时路径解释任务挂起/恢复、延续状态与执行器切换等，帮助在复杂并发场景下建立可预测的心智模型。

[Swift 6.3 稳定版：正式支持 Android SDK，扩展 C 互操作](https://www.infoq.com/news/2026/04/swift-6-3-android-c-interop/ "Swift 6.3 稳定版：正式支持 Android SDK，扩展 C 互操作")

**摘要：** 梳理 Swift 6.3 要点：Android SDK、**@c** / **@implementation** 等 C/C++ 互操作进展，以及 **weak `let`**、模块选择器、嵌入式等相关增强，呈现 Swift 跨平台与系统层互操作的一幅快照。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 "进群" 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
