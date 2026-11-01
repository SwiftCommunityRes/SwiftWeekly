## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百一十一期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

想赢才会兴奋，怕输才会紧张。朝目标往前冲的心跳加速，远比怕出错的原地踏步更加耀眼。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：400多岗位被裁！苹果收缩传统业务，新任CEO剑指AI
> * **提案**：将 bidiClass 添加到 Unicode.Scalar.Properties
> * **Swift 论坛**：Swift 6.4.2 发布：修复编译、构建与运行时问题
> * **推荐博文**：CompilationTesting 测试框架预览、SwiftUI 里的 layoutMarginsGuide、嵌套 NSHostingView 的生命周期陷阱

## 话题讨论

苹果推出了首款触屏 MacBook Pro，配备 OLED 显示屏，14 英寸版本起售价为 $2,899。**你认为触屏功能会显著提升 MacBook 的使用体验吗？**

1. 当然！早就应该推出了！
2. 锦上添花，但不是必需的
3. 不需要，我更喜欢键盘和触控板
4. 不值得为触屏功能多花钱

欢迎在评论区留下你的看法和建议。

## 新闻和社区

### 400 多岗位被裁！苹果收缩传统业务，新任 CEO 剑指 AI

*2026 年 10 月 28 日｜来源：雷科技*

今年 9 月 1 日苹果完成权力交接，库克转任执行董事长，原硬件工程负责人约翰·特努斯接任 CEO。这轮横跨数月的人员调整，是特努斯上任后烧的“第一把火”，波及 AI、混合现实、硬件管理与销售四大板块。

![](https://files.mdnice.com/user/38782/3fb00452-be87-46d5-97ff-5bb205476f78.png)

**调整时间线**

- **8 月**：据《海湾新闻》与《经济时报》报道，苹果砍掉约 200 个岗位，集中在负责 Vision Pro 的视觉产品组，以及 Siri 及相关软件团队
- **10 月**：《水星新闻》查到苹果提交的加州 WARN（工人调整与再培训通知）备案，记录 147 个永久离职岗位——79 个在库比蒂诺的 Apple Park，68 个在森尼韦尔两处办公地点，离职日期为 10 月 19 日和 20 日

需要说明的是，网传“400 多个岗位”是多家媒体综合各方信息的估算，并非苹果官方数据；目前有政府文件实锤的只有 WARN 备案里的 147 个。

![](https://files.mdnice.com/user/38782/0bd4d30c-f48e-4fc7-af6c-b3b1ee7293d2.png)

**被搁置的更大计划**

据雅虎财经报道，苹果曾计划用 AI 智能客服代理替换约 5000 名 AppleCare 技术支持员工，规模是本轮裁员的十多倍，但该计划已无限期搁置。目前美国和加拿大的部分用户拨打支持热线已能体验 AI 辅助客服，苹果却始终未官宣大规模替代人工。

**两种解读**

一种观点认为，特努斯在给管理层瘦身，压平冗余的中间层级后，把人力与预算全面集中到 AI 赛道；另一种观点认为，Vision 与 Siri 团队的收缩本质是项目优先级调整——进展慢、方向不符合新战略的项目被砍掉。两种说法目前都能自圆其说，而真正决定苹果人力走向的，仍是那个被搁置的 AppleCare AI 替代计划会不会重启。

### M6 芯片加持！新款苹果 iMac AI 性能直接翻 5 倍，起售价 12499 元

*2026 年 10 月 28 日｜来源：华尔街见闻*

苹果本周密集发布新品，在触控屏 MacBook Pro 亮相前夕，率先推出搭载 M6 芯片的 24 英寸 iMac 与 14 英寸入门级 MacBook Pro：10 月 29 日凌晨 1 点 10 分接受预购，11 月 6 日正式发货。iMac 起售价 12499 元，MacBook Pro 起售价 15999 元。

![](https://files.mdnice.com/user/38782/671d9780-897c-4e62-bc60-780eb0016af0.png)

**M6 是核心升级，外观延续前代**

两款机型外观与前代高度相似，变化集中在内部硬件。iMac 从 M4 跨代升级至 M6（该芯片今年 9 月随 Mac mini 首次亮相），MacBook Pro 去年才搭载 M5，迭代周期相对更短。官方称 M6 让新款 iMac 的 AI 任务性能较上代提升 5 倍，入门级 MacBook Pro 图形处理速度提升 30%。两者均支持蓝牙 6 与 WiFi 7，新款 MacBook Pro 充电更快。搭载 M5 Pro 与 M5 Max 的高端 MacBook Pro 仍在售，规格高于本次入门机型。

![](https://files.mdnice.com/user/38782/853fe748-5ef9-4890-8edc-b7a882507a22.png)

**首款触屏 MacBook Pro 收尾，路线图延伸至 2028 年**

苹果将于周三发布史上首款配备触控屏的 MacBook Pro，终结其对触控屏笔记本长达二十余年的抵制：采用更轻薄机身、更窄边框，并引入 OLED 显示技术。据彭博社报道，14 英寸定价约 2899 美元、16 英寸至少 3399 美元，将是苹果最贵的笔记本。

据彭博社的路线图，苹果还计划明年上半年推出焕新版 MacBook Neo 与 MacBook Air；2027 年发布 M7、M7 Pro 与 M7 Max，并推出重新设计的入门级 MacBook Pro；2028 年推出 M7 Ultra 与新 Mac Studio。

### 苹果 Siri AI 即日起支持法语、日语、韩语等语言，繁体中文得等到年底前

*2026 年 10 月 27 日｜来源：IT 之家

苹果通过新闻稿宣布，随 27.2 版本软件更新，新一代 Siri AI 新增支持法语、日语、韩语、葡萄牙语和西班牙语；繁体中文、挪威语、土耳其语和越南语将在年底前加入。

![](https://files.mdnice.com/user/38782/fb43ba59-b3ad-4cc0-b6cf-a5bea10e8320.png)

Siri AI 基于 Apple 智能打造，能理解用户个人情况、从信息、邮件、照片中查找所需资料，并执行更多系统级应用操作；借助屏幕感知能力，它可以理解屏幕上的内容并作出回答或操作，还能利用广泛知识获取“几乎任何话题”的最新信息。

目前 Siri AI 测试版覆盖 iOS 27.2、iPadOS 27.2、macOS 27.2、watchOS 27.2 与 visionOS 27.2，需使用兼容 Apple 智能的设备并将语言设为受支持的语种，部分功能存在地区或语言限制。此外，调用服务器端模型的 Apple 智能功能设有每日使用限额，包括 Siri AI、智能照片编辑工具、图乐园，以及快捷指令中的 AFM 3 Cloud 模型。

## 提案

### 通过的提案

[SE-0550](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0550-nosanitize-attribute.md "SE-0550")
**功能的 @noSanitize 属性** 提案已通过审查。

该提案此前已在 **第一百零九期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0555](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0555-iterable-inout-skip.md "SE-0555")
**inout 重载 BorrowingIteratorProtocol.skip(by:)** 提案已通过审查。

该提案此前已在 **第一百一十期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0557](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0557-hasher-rawspan-primitive.md "SE-0557")
**添加 RawSpan 原语到 Hasher** 提案已通过审查。

该提案此前已在 **第一百一十期周报** 的「正在审查的提案」模块中做过详细介绍。

### 正在审查的提案

[SE-0559](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0559-unicode-bidi-class.md "SE-0559")
**将 bidiClass 添加到 Unicode.Scalar.Properties** 提案正在审查。

向 `Unicode.Scalar.Properties` 添加一个 `bidiClass` 属性，该属性返回标量的 Unicode `Bidi_Class`，以及一个新的 `Unicode.BidiClass` 类型来表示其值。

[SE-0560](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0560-swiftpm-build-configuration-conditional-target-dependencies.md "SE-0560")
**为目标依赖项构建配置条件** 提案正在审查。

本提案介绍了 Swift 软件包作者对构建配置的目标依赖性进行条件化的能力。它完成了 SE-0273 的未实施部分。

## Swift论坛

### 1、使用 send 与 @oneway 表达单向 Actor 调用

作者：Konrad Malawski ｜ 发布日期：2026-10-27
[阅读原帖](https://forums.swift.org/t/pitch-2-send-and-oneway-method-calls/90305 "[Pitch#2] send and @oneway method calls")

这份第二轮提议将单向调用从分布式场景扩展至普通 **Actor**：通过 **send** 从同步上下文提交调用，无需等待完成，以减少 `Task { await ... }` 包装的开销，并让分布式传输利用单向消息机制。可选的 **@oneway** 标记用于表达 API 的调用意图。

```swift
// 提议中的语法：从同步上下文提交 Actor 调用
actor Collector {
    @oneway func collect(_ value: Int) { }
}

func notify(_ collector: Collector) {
    send collector.collect(1)
    send collector.collect(2)
}
```

同一任务向同一 Actor 连续发送的调用按顺序入队；异步方法内部仍需考虑挂起与重入。讨论集中于是否会鼓励滥用非结构化并发，以及能否用库 API 替代语法。作者在回复中同意暂时移除对 `@discardableResult` 的支持，将目标限制为不抛错、返回 `Void` 的方法。**点评：** 同步回调通知 Actor 的意图会更清晰，但它仍属于非结构化并发，不能替代需要等待结果的调用。

### 2、单次 yield 函数：让借用与资源清理走出闭包

作者：Meghana Gupta ｜ 发布日期：2026-10-28
[阅读原帖](https://forums.swift.org/t/pitch-single-yield-functions/90319 "Pitch: Single-yield functions")

提议引入 **单次 yield 函数**：函数执行到 `yield` 时交出值并暂停，调用方结束访问后再恢复执行、完成清理。这为借用值与可变访问提供函数级表达，也有望减少部分 `with*` API 的闭包嵌套。

```swift
// 提议中的声明形式
func ownedValue() -> yield T
func borrowedValue() -> yield borrow T
func mutableValue() -> yield inout T
```

社区讨论了 `yield`、`yielding` 与 `yields` 的命名、`defer` 的行为及恢复执行的时机。**Swift Testing** 的潜在用例是借出安全的 **RawSpan** 附件缓冲区；但 `withTaskGroup` 等 API 涉及异步清理与错误传播，不能直接迁移。多次 yield 的生成器及 `async` 支持也不在本轮范围内。**点评：** 这为资源访问提供了更直接的表达，实际适用范围仍取决于生命周期和清理语义的完善。

### 3、Swift Testing 预览对 Embedded Swift 的支持

作者：Jonathan Grynspan ｜ 发布日期：2026-10-26
[阅读原帖](https://forums.swift.org/t/preview-embedded-swift-support-in-swift-testing/90281 "[Preview] Embedded Swift support in Swift Testing")

借助 Swift 6.4 对 **Embedded Swift** 的改进，**Swift Testing** 已提供实验支持，并在 WASI、Raspberry Pi Pico 2 等环境演示运行。目标是让嵌入式开发沿用熟悉的测试 API；目前已覆盖 **@Test**、**#expect**、自定义测试作用域 trait 和 JSON Lines 输出。

试用需依赖 `swift-testing` 的 `main` 分支、适配目标平台的 **PAL** 扩展，并由入口调用 `swift_testing_embeddedMain()`。构建时设置 `SWT_EMBEDDED=1`，暂时使用可执行目标，尚不支持 SwiftPM 测试目标。

当前测试串行执行，但受目标支持的异步测试仍可使用；`.timeLimit` 不可用，类型扩展内的测试与运行时值描述也存在限制。社区反馈积极，并计划尝试更多微控制器；团队希望未来将其随嵌入式工具链分发，理想目标为 Swift 6.5。**点评：** 测试能力已迈出实用一步，接入时仍需处理平台适配与构建流程。

### 4、允许 SwiftPM 在依赖图中并存多个主版本

作者：Bri Peticca ｜ 发布日期：2026-10-29
[阅读原帖](https://forums.swift.org/t/pitch-allowing-multiple-major-versions-of-a-package/90326 "[Pitch] Allowing Multiple Major Versions of a Package")

这份提议希望解除 **Swift Package Manager** 对每个包仅解析一个版本的限制。当直接依赖需要某包的 1.x、传递依赖需要其 2.x 时，可以分别解析并构建，避免菱形依赖冲突迫使整个生态同步升级。

方案包括用 **PURL** 表达包来源与版本、调整 **PubGrub** 按主版本分桶、重连依赖图，以及自动生成模块别名来隔离同名 Swift 模块。初稿采用显式开启的方式，已有原型验证多版本构建与链接，但解析器等工作尚未完成。

讨论聚焦于是否应默认开启、清单如何控制此行为，以及 C 模块符号冲突。作者澄清，包含 C 目标的包不应简单地被禁止，但其符号隔离仍需进一步设计。多版本也会增加体积、下载量和旧版本审计成本。**点评：** 它能缓解依赖升级阻塞，但成功构建并不意味着不同版本的类型与共享资源可以自动互通。

### 5、Swift 6.4.2 发布：修复编译、构建与运行时问题

作者：Mishal Shah ｜ 发布日期：2026-10-30
[阅读原帖](https://forums.swift.org/t/announcing-swift-6-4-2/90337 "Announcing Swift 6.4.2")

**Swift 6.4.2** 正式发布，本次以正确性和稳定性修复为主。可通过 `swiftly install 6.4.2` 安装，公告确认 Xcode 27.2 包含该版本；Docker 与 WinGet 渠道在发帖时仍待上线。

编译器修复了带尾部填充的 C 结构体数组在优化构建中的误编译、涉及 `deinit` 的误报独占访问冲突，以及部分带大型 SIMD 参数的异步函数在调试构建中的崩溃。标准库对数组未初始化容量接口中的非法 `initializedCount` 改为触发陷阱，避免未定义行为。

**SwiftPM** 修复条件 trait、跨注册表缓存验证和动态库共享静态库等问题；**Foundation** 补上 `Data.resetBytes(in:)` 的下界检查，并修复部分 Linux 文件系统上的原子写入失败。公告帖尚无后续问答，发布说明还覆盖 LLDB、Swift Build 和测试输出修复。**点评：** 使用 Swift 6.4 的项目可重点回归 C 互操作、并发与依赖构建路径，评估此次补丁带来的收益。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[Point-Free 预告：CompilationTesting](https://www.pointfree.co/blog/posts/234-beta-preview-compilationtesting "Point-Free 预告：CompilationTesting")

**摘要：** 这篇来自 Point-Free 的公告预告了 Beta Preview 阶段的 CompilationTesting 库，用于为“本不该编译通过”的 Swift 代码编写单元测试。库会直接调用 Swift 编译器，把编译诊断（error、warning、fix-it、note）以 inline snapshot 的形式记录在测试文件中，从而锁住库对外承诺的那些编译期保证——例如某个重载不可用、某个隔离标注阻止了对共享状态的非法访问、某个宏生成的代码确实受到类型检查器的约束。文章还演示了如何用 flags 控制 Swift 语言模式（.languageMode(.v5)）、默认 actor 隔离与实验特性，以及用 .compilation trait 为整个测试套件统一配置编译环境。

[SwiftUI 中的 layoutMarginsGuide 用法详解](https://sarunw.com/posts/swiftui-content-margin-guide/ "SwiftUI 中的 layoutMarginsGuide 用法详解")

**摘要：** 这篇来自 Sarunw 的技术博客指出，SwiftUI 开发者习以为常的 .padding(.horizontal, 16) 其实只是一种“猜测”——系统边距随设备型号和方向变化，在 iPhone Duo 上甚至会出现一侧 20、另一侧 0 的非对称情况。文章详细讲解了 iOS 27.1 新增的 contentMargins(for: .container) 如何让系统自动选择容器边距、如何通过 GeometryProxy 的同名方法读取具体数值（该值不包含安全区，与 UIKit 的 layoutMargins 存在差异），并提醒它与 iOS 17 引入的 contentMargins(_:_:for:) 属于两个不同的类型体系，同时给出了兼容 iOS 27.0 的降级写法。

[被拆掉的 NSHostingView 还会再建一次 View](https://onevcat.com/2026/10/nested-hosting-view/ "被拆掉的 NSHostingView 还会再建一次 View")

**摘要：** 这篇来自王巍 (onevcat) 的博客记录了一次颇为曲折的排查经历：在 Prowl 项目中，切换到 Canvas 视图时某个终端卡片会变成一片空白。作者通过日志、二分查找与变体实验逐步缩小范围，最终定位到两个叠加的原因——其一是 SwiftUI 与 AppKit 混用时的生命周期问题，嵌套在 NSViewRepresentable 内部的 NSHostingView 在外层已经调用过 dismantleNSView 之后，只要自身仍留在 window 中，就会照常 flush 事务并对一棵已退场的视图树再次调用 makeNSView；其二是宿主在 init 中无条件接管共享 surface 的实现放大了这一副作用。文章附有独立的最小复现项目，并给出了在 dismantleNSView 中主动拆除内层 hosting view、以及让所有权规则能自行恢复的两段修复方案。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
