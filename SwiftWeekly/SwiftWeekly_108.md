## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百零八期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

请记住，健身房里只会嘲笑第二天不来的人，没有人会嘲笑你的梦想，他们只会嘲笑你原地踏步的实力。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：苹果市值一夜大涨 8000 亿元，新任 CEO 特努斯年薪曝光、任期规划揭晓
> * **提案**：SE-0544 不可 Copyable deinit 突变、SE-0541 Swift/C 互操作、SE-0538 Disconnected 正式通过；SE-0548 分布式 resignRemoteID 正在审查
> * **Swift 论坛**：语言提案实现进度更新、命令行信号状态查询、条件编译、集合协议陷阱
> * **推荐博文**：Swift 社区 8 月动态、ContentBuilder 类型检查加速、iOS AI 安全编码

## 话题讨论

Apple 9 月发布会即将登场！据传将带来首款折叠屏 iPhone Ultra、iPhone 18 Pro 系列、Apple Watch Series 12 / Ultra 4 和 AirPods 5。

**你最期待哪款新品？**

1. 首款折叠屏 iPhone Ultra
2. iPhone 18 Pro / Pro Max
3. Apple Watch Series 12 / Ultra 4
4. AirPods 5

欢迎在评论区留下你的看法和建议。

## 新闻和社区

### 苹果市值一夜大涨 8000 亿元，新任 CEO 特努斯年薪曝光

*2026 年 9 月 2 日｜来源：九派财经*

当地时间 9 月 1 日，蒂姆·库克（Tim Cook）卸任苹果 CEO 一职，转任董事会执行主席，CEO 由约翰·特努斯（John Ternus）接任。持续 15 年的苹果"库克时代"结束，迎来了"特努斯时代"。

苹果收盘涨 2.61%，报 325.13 美元/股，市值大增 1200 亿美元（折合约 8000 亿元人民币）。

**特努斯薪酬曝光** 苹果最新提交给美国证券交易委员会（SEC）的文件显示，新任 CEO 特努斯基础年薪为 300 万美元，并将在 2027 财年获得目标价值 5500 万美元的年度股权奖励，其中 75% 为与苹果相对标普 500 股东总回报挂钩的绩效型限制性股票。转任执行董事长的库克降薪至 200 万美元，并将在 2027 财年获得目标价值 4500 万美元的股权奖励。

![](https://files.mdnice.com/user/38782/9953bfa7-358d-43a7-8776-dfd0e111f33b.png)

约翰・特努斯（左）与蒂姆・库克（右），图片来源：央视财经

**特努斯首封内部备忘录** 特努斯在上任首日向全体员工发送内部备忘录，称苹果是"世界上最伟大的公司"，并对未来产品管线表示"同样兴奋"。信中明确提到："我们下周将有一场巨大的发布，它必将惊艳四座（phenomenal）。"

![](https://files.mdnice.com/user/38782/b35d710b-4ec9-463f-9f72-c5bd7d0fbd2e.png)

值得注意的是，北京时间 9 月 1 日深夜，苹果新任 CEO 约翰·特努斯入驻中国社交平台微博，并用中英文发动态说"你好"。截至 2 日 8 时许，该账号粉丝数量破 2 万。

**特努斯履历** 特努斯于 2001 年加入苹果产品设计团队。2013 年晋升为硬件工程副总裁，负责 AirPods、Mac 和 iPad 的开发。2020 年接管 iPhone 硬件工程部门。2021 年 1 月被提升为硬件工程高级副总裁，负责领导苹果全部硬件工程团队。

本文转载自界面新闻、财联社、橙柿互动、苹果公告

### 库克执掌 15 年苹果市值增 13 倍，特努斯将迎来 AI 新考验

*2026 年 9 月 2 日｜来源：CNMO科技*

9 月 2 日，"日经中文网"在题为《苹果新 CEO 特努斯还看不清未来 15 年》的报道中指出，前任蒂姆·库克在任 15 年，苹果市值增长 13 倍。面对 AI 的全面普及，特努斯能否进一步扩大苹果的生态体系，将考验其经营能力。

![](https://files.mdnice.com/user/38782/a6fe058b-6f45-4a13-a388-1b7d5f13b5ba.png)

约翰·特努斯（左）与蒂姆·库克（右）

**折叠屏 iPhone 售价或达 1.68 万元** 有报道称，今年推出的新产品可能仅限于高端机型，主角预计是苹果首款折叠屏手机。目前折叠屏手机在全球智能手机市场占比仅为 2%，部分产品售价已达 30 万日元（约人民币 1.26 万元）以上；考虑到 iPhone 的品牌溢价，苹果折叠屏 iPhone 售价可能达到 40 万日元（约人民币 1.68 万元）左右。

**15 年业绩回顾** 根据市场预测，苹果 2026 财年销售额将达约 4773 亿美元，约为库克就任时的 4 倍；公司市值约 4.6 万亿美元，约为当时的 13 倍。包括 iPad、Apple Watch 在内，目前全球正在使用的苹果设备已超过 25 亿台。

![](https://files.mdnice.com/user/38782/3e00b012-6aae-480c-b268-a343c347372d.png)

**AI 新考验** 苹果正在开发耳机型、眼镜型等 AI 终端。出身工程师的特努斯此前负责 iPhone、Mac 等核心终端产品的开发，他能否在库克打造的庞大 iPhone 用户基础之上，通过 AI 终端建立新的生态体系，将成为关键问题。

卸任 CEO 的库克将转任董事会主席，他在 8 月 31 日发给员工的邮件中表示："几乎没有人能像特努斯一样，真正理解创造改变世界的产品需要什么。"借此强调了对特努斯的信任。

## 提案

### 通过的提案

[SE-0544](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0544-mutate-or-consume-in-deinit.md "SE-0544")
**不可 Copyable 的 typedeinits 中的突变和消耗** 提案已通过审查。

该提案此前已在 **第一百零七期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0541](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0541-flexible-swift-c-interoperability-for-packages.md "SE-0541")
**软件包的灵活 Swift/C 互操作性** 提案已通过审查。

该提案此前已在 **第一百零六期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0538](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0538-disconnected.md "SE-0538")
**Disconnected** 提案已通过审查。

该提案此前已在 **第一百零五期周报** 的「正在审查的提案」模块中做过详细介绍。

### 正在审查的提案

[SE-0548](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0548-resign-remote-id.md "SE-0548")
**为远程分布式参与者引用添加 resignRemoteID** 提案正在审查。

分布式参与者由其关联的 `DistributedActorSystem` 管理身份标识。目前，该系统通过 `assignID(_:)` / `resignID(_:)` 这对方法来观测本地分布式参与者实例的生命周期，并通过 `resolve(id:as:)` 参与远程引用的创建。但系统目前无法观测远程引用何时被反初始化。

我们建议新增一个协议要求 `resignRemoteID(_:)`，在远程分布式参与者代理被反初始化时调用。

[SE-0547](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0547-swiftpm-compilation-caching.md "SE-0547")
**SwiftPM 对编译缓存的支持** 提案正在审查。

Swift 和 Clang 编译器已支持利用 CAS（内容可寻址存储）来缓存编译输出，并在后续构建中重放这些输出。本提案介绍了在 SwiftPM 中按单次构建、按包或全局配置编译缓存的支持。

[SE-0542](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0542-package-manager-conditional-plugin.md "SE-0542")
**包管理器的条件化插件** 提案正在审查。

本提案扩展了 SwiftPM 目标声明中的 `plugins` 参数，以支持条件化地应用插件。新增的 `PluginUsageCondition` 类型允许包作者基于宿主平台、目标平台以及构建时启用的特性来门控插件的使用。

### 拒绝的提案

[SE-0539](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0539-self-access-for-property-initializers.md "SE-0539")
**启用宏以授予属性初始化器的 self 访问权限** 提案被拒绝。

该提案此前已在 **第一百零六期周报** 的「正在审查的提案」模块中做过详细介绍。

## Swift论坛

### 1、近期语言与标准库提案实现进度更新

作者：John McCall ｜ 发布日期：2026 年 8 月 31 日
[阅读原帖](https://forums.swift.org/t/implementation-status-update-for-recent-language-and-library-proposals/89295 "Implementation status update for recent language and library proposals")

**核心内容：**
随着 **Swift 6.4** 实现工作基本收尾，语言指导组整理了此前已获接受、尚未标记为实现的提案，帮助开发者确认功能落地版本。

6.4 已实现的功能包括 **UniqueArray**、**UniqueBox**、**Ref / MutableRef**、**Iterable**、`borrow` / `mutate` 访问器及任务取消屏蔽等。

**Swift 6.5** 预计实现 **FilePath**、`withDeadline`、不可复制结果的 `reduce` 等；其中获取当前可执行文件路径的 API 已实现，仍需等待 `FilePath` 以调整返回类型。较早的 yielding accessors 已恢复开发，正则后行断言等停滞提案则可能需要重新评审。

**简要点评：**
这份公告适合用于升级规划，但应区分"已实现"与"预计实现"，避免把获批提案直接视为当前可用功能。

### 2、为命令行工具提供信号触发的运行状态查询

作者：Jonathan Grynspan ｜ 发布日期：2026 年 9 月 1 日
[阅读原帖](https://forums.swift.org/t/pitch-siginfo-et-al-support/89330 "[Pitch] SIGINFO (et al.) support")

**核心内容：**
作者提议在 **Swift Argument Parser** 中增加 **InfoProvidingParsableCommand**，让根命令通过 `static func provideInfo() async` 报告运行状态，方便用户在长任务执行期间查询进度。触发方式包括 Apple 等平台的 **SIGINFO / Ctrl+T**、Linux 的 **SIGUSR1**，以及 Windows 的 **Ctrl+Break**。

```swift
static func provideInfo() async -> CommandInfo {
    let completed = await progressTracker.completedCount
    let remaining = await progressTracker.remainingCount
    return CommandInfo("Files: \(completed) completed, \(remaining) remaining")
}
```

**简要点评：**
统一状态查询能改善命令行体验；目前仍是提议，API 命名、输出职责与包边界尚待确定。

### 3、根据最低部署版本进行条件编译

作者：JiaxuLi ｜ 发布日期：2026 年 8 月 31 日
[阅读原帖](https://forums.swift.org/t/pitch-conditional-compilation-for-the-deployment-target/89282 "[Pitch] Conditional compilation for the deployment target")

**核心内容：**
作者希望根据当前模块的**最低部署版本**选择声明和存储类型，解决 **if #available** 无法切换类型布局的问题，例如在 **Mutex** 与旧系统锁实现之间取舍。

```swift
#if deploymentTargetAtLeast(macOS 15, iOS 18, *)
// 使用面向较新部署版本的实现
#else
// 使用兼容旧部署版本的实现
#endif
```

原型需启用 `-enable-experimental-feature DeploymentTargetCondition`。

**简要点评：**
该方向有望减少兼容层的运行时分支，但仍处于原型阶段，不能视为正式 Swift 语法。

### 4、引用类型实现集合协议时的拼接陷阱

作者：Nicolas（nickasd） ｜ 发布日期：2026 年 8 月 31 日
[阅读原帖](https://forums.swift.org/t/unexpected-behaviour-when-implementing-rangereplaceablecollection-in-a-class/89286 "Unexpected behaviour when implementing RangeReplaceableCollection in a class")

**核心内容：**
作者用类实现带撤销功能的 **UndoableArray**，遵循 **RangeReplaceableCollection** 后发现：执行 `a + b` 会修改左侧集合。原因是默认 `+` 实现复制变量后追加元素，对引用类型而言仍指向同一实例；标准库源码也已有相关问题注释。

讨论纠正了"自行覆盖即可解决"的说法：这些 `+` 方法是**静态派发的协议扩展方法**，并非可动态覆盖的协议要求，自定义重载无法全面替换泛型上下文中的行为。

**简要点评：**
自定义集合不仅要满足方法签名，还应检查默认实现的值语义假设；该主题尚未给出通用修复方案。

### 5、DocC 静态托管转换子命令是否应退役

作者：David Rönnqvist ｜ 发布日期：2026 年 9 月 1 日
[阅读原帖](https://forums.swift.org/t/future-of-the-transform-for-static-hosting-subcommand/89304 "Future of the transform-for-static-hosting subcommand?")

**核心内容：**
作者征集 **docc process-archive transform-for-static-hosting** 的实际用途，并探讨废弃可能。**docc convert** 自 2022 年起默认生成适合静态托管的文件；事后转换子命令只复制页面模板，会丢失自定义页眉、页脚及已有的页面静态内容。

作者列出维持现状、改造为逐页合并、提前废弃三种方向，尚无最终决定。

**简要点评：**
可据此检查文档流水线中的重复转换步骤；支持静态托管与未来的完整静态 HTML 输出，也属于不同能力。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[Swift 社区动态：2026年8月版](https://www.swift.org/blog/whats-new-in-swift-august-2026/ "Swift 社区动态：2026年8月版")

**摘要：** 这篇官方月度动态由特邀作者 Simon Leeb（elementary-swift 项目创始人）主笔，重点聚焦 Swift 在 Web 场景中的最新进展。文章介绍了 ElementaryUI——一个运行在浏览器中、基于 Embedded Swift 构建的轻量级 Web UI 框架，能够生成极小的 WebAssembly 二进制文件。此外还涵盖了 Swift on Windows 的进展、内存安全编程实践、以及 Embedded Swift 在 Raspberry Pi Pico 上的运行演示。全文呈现了 Swift 正从服务端向 Web 前端乃至嵌入式领域全面渗透的技术图景。

[ContentBuilder 详解：SwiftUI 类型检查加速背后的秘密](https://fatbobman.com/en/posts/contentbuilder-explained/ "ContentBuilder 详解：SwiftUI 类型检查加速背后的秘密")

**摘要：** 这篇技术深度解析文章，聚焦于 WWDC 2026 上 SwiftUI 引入的新特性——ContentBuilder。从表面看，它只是一个作用范围更广的 ViewBuilder；但 Apple 工程师声称这一调整能显著提升类型检查性能。文章深入剖析了 ContentBuilder 的本质，揭示了其加速类型检查背后的实现原理。全文为深受"编译器无法在合理时间内类型检查此表达式"之苦的 SwiftUI 开发者，提供了一份从现象到原理的完整解读。

[iOS 安全（第五部分）：AI 辅助编码时不泄露数据的正确姿势](https://slekens.dev/en// "iOS 安全（第五部分）：AI 辅助编码时不泄露数据的正确姿势")

**摘要：** 这篇来自 Slekens 技术博客的文章，是 iOS 安全基础系列的收官之作。文章聚焦于一个日益紧迫的现实问题：在使用 Claude、ChatGPT 等 AI 编程助手时，什么可以分享、什么绝对不能分享。作者明确指出，密钥永远不该出现在提示词中，并系统阐述了如何在享受 AI 辅助编程效率的同时，保护好代码和数据的安全边界。全文为日常依赖 AI 工具进行开发的 iOS 工程师提供了一份极具实操价值的安全守则。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 "进群" 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
