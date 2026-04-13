## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第九十八期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

数据可以被云端存储，但勇气必须随身携带。即使在 AI 算法的时代，你仍是自己人生的唯一开发者，代码可以复制，但你的坚韧与勇气无可粘贴。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：库克祝贺阿耳忒弥斯 2 号成功，iPhone 17 Pro Max 完成载人深空拍摄；苹果「三年计划」与折叠屏 iPhone Ultra（9 月）等传闻；工信部提醒苹果用户及时修复漏洞
> * **提案**：SE-0503、SE-0510、SE-0522、SE-0523 正式通过；SE-0524～SE-0526 正在审查；SE-0490、SE-0516 被拒
> * **Swift 论坛**：Result 异步支持、swift-tar、SE-0526 withDeadline、Task.immediate 用法、SE-0469 Task.name 修订
> * **推荐博文**：Swift 脱离 Xcode 与 LSP、Swift 从应用到服务（QCon）、defer 原理与场景

上期话题投票结果如下：

![](https://files.mdnice.com/user/38781/9fa3d4db-d710-4ba3-9b4c-1a0e477ada2b.png)

## 话题讨论

### 本期话题：**随着 AI 辅助编程普及，你觉得程序员岗位被 AI 大面积取代还有多久？**

**选项：**

1. 放心，没那么容易被取代，至少 10 年内不会。
2. 五年左右吧，岗位已经在大面积减少啦。
3. 三年左右吧，各行各业都在被取代了。
4. 兄 dei，我已经在拼命发展副业啦，一年以后必然是 AI 的天下啦。

欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### 苹果 CEO 库克祝贺阿耳忒弥斯 2 号任务成功，将 iPhone 摄影带到全新高度

*2026 年 4 月 11 日｜来源：快科技*

NASA 阿耳忒弥斯 2 号「猎户座」飞船成功溅落，美国首次载人绕月任务收官。库克发文祝贺，称宇航员用 iPhone 捕捉太空与地球景观，将 iPhone 摄影带到新高度。任务中 4 名宇航员各携带一台 iPhone 17 Pro Max（飞行模式、经飞船系统回传），完成绕月拍摄等，被视作「Shot on iPhone」的太空级里程碑；NASA 认可其便携、防抖与影像能力。

![](https://pics1.baidu.com/feed/9e3df8dcd100baa18c01c5c70ef23a03c9fc2e94.png@f_auto?token=61da563e16eb200845d83acc0d1f1b69)

### 苹果三年计划曝光：由里到外「重新定义」iPhone；首款折叠屏或定名 iPhone Ultra

*2026 年 4 月 9 日｜来源：鲁中晨报等*

据产业链与彭博社古尔曼等报道，苹果正推进一项约三年的 iPhone 路线图：**2025 年 9 月**已推出重新设计的 iPhone 17 Pro 系列与 iPhone Air；**2026 年 9 月**有望发布首款大折叠 iPhone（传闻命名 **iPhone Ultra**），横向书本式折叠、内外双屏，iOS 27 或强化分屏与类 iPad 多任务；售价或突破 2000 美元，成史上最贵 iPhone。古尔曼还称**2027 年 9 月**可能有 20 周年纪念版（无开孔全面屏等设想仍存不确定性）。另有分析称折叠机型或因厚度采用侧边 **Touch ID**、**eSIM** 等取舍。富士康试产、郭明錤与机构对定价的预测多为市场传闻，以官方发布为准。

![](https://pics4.baidu.com/feed/a5c27d1ed21b0ef449bd1bea9426d2cb80cb3e24.png@f_auto?token=4371674dd7c92a238aec52931cee3ae1)

### 工信部紧急提醒苹果用户

*2026 年 4 月 4 日｜来源：券商中国*

工信部网络安全威胁和漏洞信息共享平台（NVDB）通报，有攻击者利用针对苹果终端的漏洞利用工具实施网络攻击，可导致信息窃取、设备被远程控制等。影响范围包括 **iOS 13.0 至 17.2.1** 的 iPhone、iPad 等。攻击常通过短信、邮件或恶意网页诱导用户使用 Safari 访问恶意页面并植入木马。建议用户尽快升级系统、安装安全补丁（可参考 [苹果安全更新公告](https://support.apple.com/zh-cn/100100)），并避免点击可疑链接。

![](https://pics1.baidu.com/feed/e824b899a9014c08a00e1b8fda0178197bf4f46b.jpeg@f_auto?token=d4160fe2f2dfe66309ffcf3457f07b53)

## 提案

### 通过的提案

[SE-0503](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0503-suppressed-associated-types.md "SE-0503")
**抑制与默认值关联类型的默认一致性** 提案已通过审查。

该提案此前已在 **第九十四期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0510](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0510-dictionary-mapvalues-with-keys.md "SE-0510")
**介绍 Dictionary.mapValuesWithKeys** 提案已通过审查。

该提案此前已在 **第九十五期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0522](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0522-source-warning-control.md "SE-0522")
**源级控制编译器警告** 提案已通过审查。

该提案此前已在 **第九十七期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0523](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0523-hashable-unownedtask-executor.md "SE-0523")
**Hashable 符合 UnownedTaskExecutor** 提案已通过审查。

为 `UnownedTaskExecutor` 增加 `Hashable` 一致性，使其可作为字典键与集合元素；该类型已符合 `Equatable`，此次为自然且源码兼容的扩展。

### 正在审查的提案

[SE-0524](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0524-span-temporary-allocation.md "SE-0524")
**使用 Output(Raw)Span 添加 withTemporaryAllocation** 提案正在审查。

引入以 `OutputSpan` 或 `OutputRawSpan` 包裹临时缓冲区的顶层 API，在保留跨度类型安全保证的同时，沿用 `withUnsafeTemporaryAllocation` 的栈分配优化。

[SE-0525](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0525-rawspan-safe-loading-api.md "SE-0525")
**RawSpan 安全加载 API** 提案正在审查。

为从 `RawSpan`、`MutableSpan`、`OutputRawSpan` 表示的内存中安全加载与存储特定类型提供一组 API，便于跨进程缓冲与解析类工具。

[SE-0526](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0526-deadline.md "SE-0526")
**withDeadline** 提案正在审查。

引入 `withDeadline`，为异步操作提供基于连续时钟截止时间的可组合限制：在截止前完成则返回结果，超时则取消操作。

### 拒绝的提案

[SE-0490](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0490-environment-constrained-shared-libraries.md "SE-0490")
**环境受限的共享库** 提案被拒绝。该提案此前已在 **第八十六期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0516](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0516-borrowing-sequence.md "SE-0516")
**借用序列** 提案被拒绝。该提案此前已在 **第九十六期周报** 的「正在审查的提案」模块中做过详细介绍。

## Swift 论坛

### 1、Pitch: 为 Result 添加异步支持

作者：mattie ｜ 发布日期：2026 年 4 月 8 日
[阅读原帖](https://forums.swift.org/t/pitch-async-result-support/85888 "Pitch: Async Result Support")

**动机：**
`Result.init(catching:)` 仅支持同步 `throws` 闭包，难以直接包裹异步工作，项目中常重复手写样板代码。

**核心设计：**

* 为 `Result` 增加支持 `async throws` 的 `catching` 初始化器
* 讨论是否为 `Task` 增加 `result` 属性（`Result<Success, Failure>`）以配合 `flatMap` 等链式用法

```swift
let result = await Result {
  try await asyncWork()
}
```

**讨论亮点：**
社区对异步版 `catching init` 反响积极；对 `Task.result` 是否必要存在分歧，作者表示持开放态度。

**简要点评：**
小而实用的补全，有助于统一 `Result` 与 `async/await` 的用法，纳入标准库可减少重复工具代码。

### 2、swift-tar：纯 Swift 实现的 TAR 归档读写库

作者：kateinoigakukun ｜ 发布日期：2026 年 4 月 6 日
[阅读原帖](https://forums.swift.org/t/swift-tar-a-pure-swift-tar-archive-read-write-extract-library/85844 "Swift-tar: A pure Swift TAR archive read/write/extract library")

**动机：**
在无 Foundation、嵌入式或 WebAssembly 等环境处理 TAR 时，缺少成熟纯 Swift 方案。

**核心特性：**
无 Foundation 依赖；跨平台（含 WASM、Embedded Swift）；支持 GNU/PAX 扩展；提供内存与流式解压 API。基准测试中解压大型 tarball 速度可略快于系统 `bsdtar`。MIT 协议开源。

**讨论亮点：**
关注 API 设计与大文件场景下的内存行为。

**简要点评：**
填补了「无系统框架场景下的 TAR」空白，对工具链与跨平台 Swift 很实用。

### 3、SE-0526：withDeadline 正式审查

作者：Jumhyn ｜ 发布日期：2026 年 4 月 7 日
[阅读原帖](https://forums.swift.org/t/se-0526-withdeadline/85850 "SE-0526: withDeadline")

审查期截至 **2026 年 4 月 20 日**。提案引入 **`withDeadline`**，在绝对时间点前完成异步体则返回结果；超时则取消并待操作结束后以包装错误等形式返回。

**动机：**
为超时与取消提供可组合、与 Swift 并发模型一致的表达。

**讨论亮点：**
关于 `DeadlineError<Failure>` 与 typed throws 的配合、超时后是否等待任务结束等语义，社区有细化讨论。

**简要点评：**
并发工具箱的重要补充；错误建模方式也反映出当前类型化错误在「联合错误」上的局限。

### 4、Task.immediate 的正确使用场景探讨

作者：mattneub ｜ 发布日期：2026 年 4 月 8 日
[阅读原帖](https://forums.swift.org/t/is-this-a-good-use-of-task-immediate/85885 "Is this a good use of Task.immediate?")

作者在 UIKit `@IBAction` 中用 `Task.immediate` 调用 `@MainActor` 的 `async` 处理器，以减少普通 `Task` 的调度延迟与测试中的时序问题。

**讨论亮点：**
mattie 等指出 `Task.immediate` 与继承 Actor 上下文语义相关；若目标为独立 actor 而非 `@MainActor`，仍可能在进入 body 时挂起切换执行器，效果因隔离域而异。

**简要点评：**
有助于厘清 `Task.immediate` 的边界：不是万能「同步立即」，需结合目标隔离域理解。

### 5、修订：SE-0469 Task 命名新增实例属性

作者：John McCall ｜ 发布日期：2026 年 4 月 6 日
[阅读原帖](https://forums.swift.org/t/amended-se-0469-task-naming/85841 "Amended SE-0469: Task Naming")

SE-0469 已在 Swift 6.2 落地，但缺少从任意 `Task` 实例读取名称的公开 API。语言指导小组以轻量修订流程为 `Task` 增加只读 **`name`** 属性；若有重大异议可回到常规审查。

**简要点评：**
补全可观测性与调试场景下的常见需求，属于对既有功能的合理收尾。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[Swift 脱离 Xcode：Apple 编程语言为跨平台开发者迈出最激进的一步](https://www.webpronews.com/swift-breaks-free-from-xcode-apples-programming-language-makes-its-boldest-play-yet-for-cross-platform-developers/ "Swift 脱离 Xcode：Apple 编程语言为跨平台开发者迈出最激进的一步")

**摘要：** 报道解读 Swift 官方强化 **SourceKit-LSP** 与多编辑器体验（VS Code、Neovim 等）：补全、宏、跨模块导航及 Swift for VS Code 扩展等，意在降低对单一 IDE 的依赖，以服务服务端与多平台生态。

[从应用到服务：Swift 的演进之路](https://www.infoq.com/presentations/swift-apps-services/ "从应用到服务：Swift 的演进之路")

**摘要：** QCon London 演讲（Cory Benfield）：Swift 在 Apple 内外长期用于关键服务；无 GC、零成本抽象等与 C++ / Java 互操作、服务端采纳路径等，勾勒 Swift 作为服务端语言的定位。

[讲讲 Swift 中 defer 的实现原理和使用场景](https://juejin.cn/post/7350860141582385188/ "讲讲 swift 中 defer 的实现原理和使用场景")

**摘要：** 结合用法与实现思路介绍 `defer`，强调资源清理价值，并提醒误用（如在 `defer` 中不当使用控制流等）。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 "进群" 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
