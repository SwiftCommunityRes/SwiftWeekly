## 前言

**本期是 Swift 编辑组自主整理周报的第九十一期**，各个模块已逐步稳定成型。如果你对内容选题、结构或呈现方式有任何建议，欢迎在文末留言反馈。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周周一发布**，也非常欢迎志同道合的朋友加入编辑组。

草木需要阳光，生活需要向往。即使风雨来袭，也要绽放自己的芬芳。平凡的日子，也可以不平凡地闪耀。

> **周报精选**
>
> 新闻和社区：苹果内部震荡加剧，产品线与人才结构同时承压
>
> 提案：HTML 覆盖率报告进入审查，SwiftPM 工作流持续完善
>
> Swift 论坛：所有权模型、C 工件生成与轻量工具的边界讨论
>
> 推荐博文：并发、构建工具与任务取消的实践总结

## 话题讨论

**在当今科技发展背景下，你认为科技创新是更难了，还是更容易了？**

1. **更容易了**：工具、算力与开源生态降低了创新门槛，个人与小团队也能快速试错并产生影响。
2. **更难了**：底层技术与系统复杂度显著上升，真正具备颠覆性的创新需要更高投入与更长周期。

欢迎在评论区留下你的看法。

## 新闻和社区

### iPhone Air 销量遇冷，苹果暂停超薄 iPhone 产品线

![](https://files.mdnice.com/user/47553/4ee7e96a-10c6-4a51-81a9-05d3c3cf050f.png)

近日，多家供应链渠道确认，苹果已暂停 **iPhone Air** 相关产线准备工作，原计划于 2026 年更新的下一代机型被无限期搁置。这意味着，苹果极有可能放弃这条以“极致轻薄”为卖点的全新 iPhone 产品线。

iPhone Air 厚度仅 **5.6mm**，是目前最薄的 iPhone 机型。但为了实现这一设计目标，苹果在电池容量、摄像头配置以及整体续航表现上做出了明显取舍。尽管外观辨识度极高，但市场反馈并不理想。

![](https://files.mdnice.com/user/47553/43831129-b3d9-4342-be40-f5015b851362.png)

供应链消息显示，负责主要代工的富士康已拆除部分相关产线，立讯精密也提前停止了后续生产准备。iPhone Air 的起售价为 **999 美元**，仅比同期 Pro 机型低 100 美元，这一价格区间进一步放大了用户对“性能与续航妥协”的不满。

这是苹果近年来第三次尝试拓展 iPhone 第四产品线但未能成功的案例。此前的 iPhone mini 与 Plus，均未能长期保留在主力产品序列中。

从结果来看，市场给出的信号相当明确：在当前阶段，用户对 iPhone 的核心诉求仍然集中在续航、性能与稳定体验，而非极端形态创新。

### 库克退休传闻再起，真正的变化发生在苹果内部结构

![](https://files.mdnice.com/user/47553/1dff8113-d022-4e21-a421-f269ebdb6e93.png)

近日有报道称，苹果 CEO 蒂姆·库克可能于明年卸任，公司正在加速寻找继任者，硬件工程高级副总裁 **John Ternus** 被视为潜在接班人。

不过，知名苹果爆料人 Mark Gurman 随后明确辟谣，表示库克在明年上半年离职的说法并不属实。如果这一传闻为真，将会令苹果内部与资本市场感到震惊。

![](https://files.mdnice.com/user/47553/15556504-d518-408f-b608-d41fb29604ae.png)

尽管如此，围绕“库克是否退休”的讨论，并未掩盖苹果正在经历的一系列深层变化。多位核心高管正处于职业生涯后期，一些关键岗位已经或正在发生交接。同时，苹果在人工智能方向的推进节奏，也持续受到外界质疑。

John Ternus 之所以被频繁提及，并不仅仅因为年龄优势。他长期负责硬件工程核心项目，在公司内部拥有较高信任度。但外界普遍认为，即便完成权力交接，新一任 CEO 的角色也更可能延续“运营与执行导向”，而非回到“产品驱动型创始人”的风格。

### OpenAI 持续挖角苹果工程师，硬件与 AI 人才流动加速

![](https://files.mdnice.com/user/47553/075593fe-6e43-4163-b266-15e929f91c82.png)

相比高管层相对平稳的表象，苹果当前面临的另一项现实挑战，是 **核心工程师的持续流失**。

最新爆料显示，仅在过去一个月内，OpenAI 的硬件相关团队就吸纳了 **40 多名**新成员，其中相当一部分来自苹果。这些人员覆盖的领域非常广泛，包括 iPhone 与 Mac 硬件、芯片设计、工业设计、制造工艺、音频系统、可穿戴设备以及 Vision Pro 相关方向。

![](https://files.mdnice.com/user/47553/740e6c92-05f5-4bcf-bf38-07c4fc823fef.png)

随着 OpenAI 加速布局自有 AI 硬件，并计划在 2026 年推出首批产品，其对成熟消费电子人才的需求正在快速放大。多位消息人士透露，苹果内部已将这种集中式挖角视为需要严肃对待的问题。

与此同时，也有苹果设计与工程领域的新生代骨干选择加入 AI 创业公司。这一趋势被认为反映出，苹果在 AI 时代对部分基层与中层技术人才的吸引力，正在面临新的竞争压力。

## 提案

### 正在审查的提案 

[SE-0501](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0501-swiftpm-html-coverage-report.md "SE-0501") **HTML 覆盖报告** 提案正在审查。 

目前，`swift test` 支持生成 JSON 覆盖报告，这非常适合摄取到各种系统中。然而，在办公桌上迭代时，JSON 不是很“人类可读”。 这建议在 `swift test` 中添加一个额外的命令行参数，允许呼叫者选择生成 HTML 覆盖报告。 

### 拒绝的提案 

[SE-0478](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0478-default-isolation-typealias.md "SE-0478") **默认 actor 隔离类型别名** 提案被拒绝。该提案已在七十六期周报 正在审查的提案模块做了详细介绍。

## Swift 论坛

### 1、提案：为关联类型支持抑制默认约束

作者：Kavon Farvardin ｜ 发布日期：2025 年12 月 10 日
[阅读原帖](https://forums.swift.org/t/pitch-suppressed-associated-types-with-defaults/83663 "Pitch: Suppressed Associated Types With Defaults")

该 pitch 关注 **协议关联类型默认引入 `Copyable` / `Escapable` 约束** 所带来的表达受限问题。在当前规则下，即便协议逻辑并不需要可复制能力，关联类型仍会被隐式约束。

**问题示例：**

```swift
protocol Queue<Element>: ~Copyable {
  associatedtype Element
  associatedtype Allocator = DefaultAllocator
}
```

在现行语义中，`Element` 会被默认要求为 `Copyable`，导致无法使用 `~Copyable` 的元素类型实现该协议。

**提案方案：**

```swift
protocol Queue<Element>: ~Copyable {
  associatedtype Element: ~Copyable
  associatedtype Allocator: ~Copyable = DefaultAllocator
}
```

通过显式抑制默认约束，协议只声明“真正需要的能力”，让非可复制、资源型数据结构也能参与协议设计。

**简要点评：**
这是一次贴合所有权模型演进的底层改进，能显著提升协议在泛型与资源管理场景下的可扩展性。

### 2、提案：放宽 SwiftPM 对插件生成 C 产物的限制

作者：Doug Schaefer ｜ 发布日期：2025 年 12 月 8 日
[查看原帖](https://forums.swift.org/t/pitch-remove-restrictions-on-generation-of-c-artifacts/83611 "Pitch: Remove restrictions on generation of C artifacts")

该提案讨论 **SwiftPM 插件在构建时生成 C/C++ 头文件、module map 等工件无法参与编译** 的现实问题。目前这些文件往往被忽略或当作资源处理，迫使项目将生成结果提交到仓库。

**核心改动方向：**

* 将插件输出目录下的 `include` 目录视为公共头文件路径
* 让生成的 C 产物像普通源码一样进入构建流程

短期方案通过固定目录名解决问题，长期目标是提供可配置路径。

**简要点评：**
这是一个偏工程层面的改进，但对依赖 C/C++ 绑定、自动代码生成的 Swift 包具有实际价值。

### 3. SE-0501：HTML 覆盖率报告（审查中）

作者：Bassam (Sam) Khouri ｜ 发布日期：2025 年 12 月 8 日
[阅读原帖](https://forums.swift.org/t/se-0501-html-coverage-report/83601 "SE-0501: HTML Coverage Report")

SE-0501 提议为 `swift test` 增加 **HTML 格式的覆盖率输出**，补足当前仅支持 JSON、不便人工阅读的问题。

**提案要点：**

* SwiftPM 自动生成静态 HTML 覆盖率页面
* 与现有 JSON 覆盖率机制并存
* 更适合本地查看和 CI 构件展示

**简要点评：**
这是一个不破坏现有工具链、但能明显改善日常体验的增强型提案，目前正处于社区审查阶段。

### 4、社区动态：Swift 社区将亮相 FOSDEM 2026

作者：Swift 社区组织者 ｜ 发布日期：2025 年 12 月 9 日
[阅读原帖](https://forums.swift.org/t/save-the-date-swift-community-event-at-fosdem-26-fri-jan-30/83620 "Save the date: Swift community event at FOSDEM 26")

Swift 社区宣布将在 **FOSDEM 2026** 期间举办线下交流活动，时间为 **2026 年 1 月 30 日**，地点在比利时布鲁塞尔。

该活动为社区主导的非官方聚会，重点围绕 Swift 在服务器、系统编程及跨平台方向的实践交流。

### 5、讨论：为 Swift Argument Parser 引入轻量级“兄弟库”

作者：Eliot Arntz ｜ 发布日期：2025 年 12 月 10 日
[阅读原帖](https://forums.swift.org/t/a-little-brother-for-swift-argument-parser/83634 "A Little Brother for Swift Argument Parser")

社区中提出一个想法：为 Swift Argument Parser 提供一个 **更轻量、低样板的参数解析库**，服务于简单 CLI 或脚本工具场景。

示意写法如下：

```swift
let args = parse(["--verbose", "-o", "file.txt"])
let verbose = args.flag("--verbose", default: false)
let output = args.option("-o", default: "out.txt")
```

该方案并非替代 Argument Parser，而是作为补充，降低小工具的使用成本。

**简要点评：**
随着 Swift 在脚本与自动化工具中的使用增加，轻量级 CLI 解析方案具备现实需求，但 API 设计仍需谨慎权衡类型安全与简洁性。

## 推荐博文

[iOS 知识点 - 多线程总结（GCD/Operation/Swift Concurrency/线程安全/线程通信）](https://juejin.cn/post/7581324171398201390/ "iOS 知识点 - 多线程总结（GCD/Operation/Swift Concurrency/线程安全/线程通信）")

系统梳理了 GCD、Operation、Swift Concurrency 等多种并发模型，适合希望全面理解线程安全与任务调度策略的开发者阅读。

[使用 Swift Package 插件将自定义字体加载到您的应用程序中](https://www.polpiella.dev/load-custom-fonts-with-no-code-using-swift-package-plugins/ "i使用 Swift Package 插件将自定义字体加载到您的应用程序中")

介绍了如何借助 Swift Package 与插件机制，在构建阶段自动生成字体加载代码，减少重复劳动并提升项目可维护性。

[在 Swift 中如何取消后台任务](https://swdevnotes.com/swift/2023/how-to-cancel-a-background-task-in-swift// "在 Swift 中如何取消后台任务")

围绕 async/await 场景，详细讲解了多种任务取消方式及其适用场景，帮助开发者避免无效后台任务对性能的影响。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
