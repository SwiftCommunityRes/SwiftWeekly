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
> * **提案**：
> * **Swift 论坛**：
> * **推荐博文**：CompilationTesting 测试框架预览、SwiftUI 里的 layoutMarginsGuide、嵌套 NSHostingView 的生命周期陷阱

## 话题讨论

欢迎在评论区留下你的看法和建议。

## 新闻和社区

### 400 多岗位被裁！苹果收缩传统业务，新任 CEO 剑指 AI

*2026 年 10 月 28 日｜来源：雷科技*

互联网大厂动不动就甩出个几千上万人的裁员计划，仿佛降本增效已经成了行业标配。

但在这群“裁员大户”里，苹果一直是股清流。它几乎从没搞过全公司声势浩大的裁员新闻。

可最近一波消息出来，不少人都愣了。苹果居然也开始悄悄裁员了？

前后算下来有 400 多个岗位被撤销，AI、混合现实、硬件管理、销售四大板块全被波及。

先给大伙补个关键背景。今年 9 月 1 日，苹果正式完成了权力交接。执掌公司十几年的蒂姆・库克退居二线，转任执行董事长，原先负责硬件工程的核心高管约翰・特努斯接棒，成为苹果新一任 CEO。这次横跨数月的人员调整，基本就是特努斯上任后烧的“第一把火”。

![](https://pics2.baidu.com/feed/c9fcc3cec3fdfc037c16618076530286a4c2261f.jpeg@f_auto?token=04be5ff633cb8f14b66485b414c71f55)

最早的一波调整，从今年 8 月就已经悄悄启动了。根据《海湾新闻》和《经济时报》的相关报道，当时苹果一口气砍掉了约 200 个岗位，主要集中在两个部门，一个是负责 Vision Pro 等产品的视觉产品组，另一个就是 Siri 及相关软件团队。

这波人员收缩，多多少少也能看出苹果对这两块业务的优先级，已经有了新的判断。

10 月份，官方文件也实锤了一部分裁员信息。《水星新闻》扒出了苹果提交的加州 WARN（工人调整与再培训通知）备案，上面白纸黑字记录了 147 个永久离职岗位。其中 79 个岗位在库比蒂诺的苹果总部 Apple Park，剩下 68 个分布在森尼韦尔的两处办公地点，员工正式离职日期为 2026 年 10 月 19 日和 20 日。

说到这里必须划个重点，现在网上传的 400 多个岗位被裁，其实是多家媒体综合各方信息估算出来的数字，并不是苹果官方公布的准确数据。目前有政府正式文件实锤的，只有加州 WARN 备案里的 147 个岗位。

![](https://pics5.baidu.com/feed/359b033b5bb5c9ead6655815745533123bf3b335.jpeg@f_auto?token=de6ce41e1c77d36876fdfdc79c7cce07)

据雅虎财经的报道，苹果之前其实打过一个更大的算盘，想用 AI 智能客服代理，替换掉约 5000 名 AppleCare 技术支持员工。5000 人是什么概念？是目前这波裁员人数的十多倍，真要落地绝对是苹果历史上数得着的人力大变动。但戏剧性的是，这个计划据说已经被无限期搁置了。

当然，苹果也不是完全没碰 AI 客服。现在美国和加拿大的部分用户拨打苹果支持热线，其实已经能体验到 AI 辅助的客服服务了。但真正用 AI 大规模取代人工客服的动作，苹果至今也没敢公开官宣。

为啥好好的计划说搁置就搁置？可能是 AI 客服的处理能力还达不到苹果的高标准，怕砸了自己服务口碑的招牌；也可能是怕引发舆论和员工的双重反弹，毕竟几千人的岗位说没就没，社会影响实在太大。

现在业内对苹果这波整体调整，其实有两种完全不同的解读。

一种观点认为，新 CEO 特努斯这是在给公司管理层瘦身，先把冗余的中间层级压平，裁掉一部分管理岗，再把人力和预算全面往 AI 赛道集中。

![](https://pics4.baidu.com/feed/a50f4bfbfbedab641121c3a4555a2ad178311e85.jpeg@f_auto?token=3e0758bf5b904a45d1d7636e064a07f3)

另一种观点则认为，Vision 和 Siri 团队的人员收缩，本质上是项目优先级的调整，和降本增效没太大关系。说白了就是，部分进展慢、方向不符合新战略的项目被砍掉。

就目前曝光的信息来看，两种说法都能自圆其说，也没法断定哪个就是标准答案。

但话又说回来，这波调整很可能只是个开始。真正决定苹果未来人力走向的，还是那个被暂时搁置的 AppleCare AI 替代计划。

如果未来这个计划重新启动，那就说明苹果是真的铁了心要用 AI 重构内部人力体系。因为在 AI 浪潮面前，没有哪家大厂能真正置身事外。

接下来苹果的 AI 路到底怎么走，是抱着稳妥的步子慢慢迭代，还是大刀阔斧搞全面变革？咱们先走着瞧吧。

### M6 芯片加持！新款苹果 iMac AI 性能直接翻 5 倍，起售价 12499 元

*2026 年 10 月 28 日｜来源：华尔街见闻*

苹果公司本周密集发布新品，在触控屏 MacBook Pro 亮相前夕，率先推出搭载 M6 芯片的 24 英寸 iMac 与 14 英寸入门级 MacBook Pro。

两款新机将于 10 月 29 日凌晨 1 点 10 分接受预购，11 月 6 日正式发货。新款 iMac 起售价 12499 元人民币，MacBook Pro 起售价 15999 元。

![](https://pics5.baidu.com/feed/11385343fbf2b211757903868d46e12a0ed78ef8.jpeg@f_auto?token=8fc519ef6b3c9bd8e33b6872c0f89f70)

苹果表示，M6 芯片赋予新款 iMac 在人工智能任务上较上代机型五倍的性能提升，入门级 MacBook Pro 的图形处理速度则较前代提升 30%。

此次发布是苹果本周新品攻势的第二波，周一该公司刚更新了 iPad mini，新增屏幕升级与防水功能。华尔街见闻提及，苹果将于周三以其史上首款触控屏 MacBook Pro 为本周产品发布收尾。
据彭博社报道，该款触屏 Mac 将成为该公司最贵的笔记本，已经探讨将新款 14 英寸 Mac 售价定在 2899 美元，16 英寸机型至少 3399 美元。

M6 芯片成核心升级，外观延续前代设计
新款 iMac 与 MacBook Pro 在外观上与前代产品高度相似，主要变化集中于内部硬件。两款机型均搭载 M6 芯片——该芯片于今年 9 月随 Mac mini 首次亮相。

![](https://pics0.baidu.com/feed/d62a6059252dd42aec1ff6f64bfddfa7c8eab8b6.jpeg@f_auto?token=9190c45efb229f052cf3138c28a27e25)

此次更新中，iMac 从 M4 芯片跨代升级至 M6，而 MacBook Pro 去年刚搭载了 M5 芯片，本次迭代周期相对更短。

在连接性方面，两款新机均支持蓝牙 6 与 WiFi 7，新款 MacBook Pro 还获得更快的充电速度。

苹果目前仍继续销售搭载 M5 Pro 与 M5 Max 芯片的高端 MacBook Pro 机型，后者在主处理器与图形核心规格上均高于本次发布的入门级 M6 机型。

苹果本周三将发布史上首款配备触控屏的 MacBook Pro，终结该公司对触控屏笔记本长达二十余年的抵制立场。

新款触控屏 MacBook Pro 将采用更轻薄的机身设计、更窄的屏幕边框，并引入 OLED 显示技术。

苹果电脑产品线换代路线图延伸至 2028 年
此轮密集更新是苹果更宏观产品规划的一部分。

据彭博新闻报道，除触控屏 MacBook Pro 外，苹果还计划于明年上半年推出焕新版 MacBook Neo 与 MacBook Air。

在芯片路线图方面，苹果预计于 2027 年发布 M7、M7 Pro 与 M7 Max 芯片，并推出经过重新设计的入门级 MacBook Pro；M7 Ultra 芯片与新款 Mac Studio 则被安排在 2028 年推出。

苹果正持续推进电脑产品线的全面革新，以满足日益增长的人工智能应用需求，此次发布的两款新品是这一进程中的阶段性节点，而非终点。

### 苹果 Siri AI 即日起支持法语、日语、韩语等语言，繁体中文得等到年底前

*2026 年 10 月 27 日｜来源：IT 之家*

苹果今天（27 日）通过新闻稿宣布，今天发布的 27.2 版本软件更新，进一步扩大新一代 Siri AI 的使用范围，新增支持法语、日语、韩语、葡萄牙语和西班牙语。

Siri AI 是全面升级的 Siri，不仅功能更强大，对话也更加自然，还能提供更个性化的服务。根据介绍，其基于 Apple 智能打造，在保护用户隐私的同时，大幅提升了 Siri 的能力。新版本能够理解用户的个人情况，从信息、邮件、照片等内容中查找所需资料，还可以执行更多系统级应用操作。借助屏幕感知能力，Siri AI 可以理解屏幕上显示的内容，回答用户的问题或完成相应操作。此外，Siri AI 还能利用广泛的知识获取“几乎任何话题”的最新信息。

新闻稿提到，苹果计划继续增加 Siri AI 支持的语言，繁体中文、挪威语、土耳其语和越南语将在年底前加入。

![](https://pics7.baidu.com/feed/e1fe9925bc315c60c8fa0b3d4a1148014854772c.jpeg@f_auto?token=5a48dfd21d5e5f3be298795e0a4e7521)

目前，Siri AI 测试版支持 iOS 27.2、iPadOS 27.2、macOS 27.2、watchOS 27.2 和 visionOS 27.2。IT 之家提醒：用户需要使用兼容 Apple 智能的设备，并将设备语言设为 Siri AI 支持的英语、法语、日语、韩语、葡萄牙语或西班牙语。部分功能可能存在地区或语言限制。

此外，部分需要调用服务器端模型的 Apple 智能功能设有每日使用限额，包括不限于 Siri AI、智能照片编辑工具、图乐园，以及快捷指令中的 AFM 3 Cloud 模型，具体限额或因功能类型、请求复杂程度、系统负载、系统政策等因素而异。

## 提案


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
