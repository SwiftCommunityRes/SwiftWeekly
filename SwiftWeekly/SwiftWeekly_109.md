## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百零九期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

心简单，世界便温柔似水，人知足，日子才幸福长久。允许一切发生，接受预期之外的喧哗，这便是人生最大的修行。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：苹果AI服务器曝光：代号Baltra、搭载自研M8 Ultra芯片
> * **提案**：
> * **Swift 论坛**：
> * **推荐博文**：

## 话题讨论

Apple 9 月发布会即将登场！据传将带来首款折叠屏 iPhone Ultra、iPhone 18 Pro 系列、Apple Watch Series 12 / Ultra 4 和 AirPods 5。

**你最期待哪款新品？**

1. 首款折叠屏 iPhone Ultra
2. iPhone 18 Pro / Pro Max
3. Apple Watch Series 12 / Ultra 4
4. AirPods 5

欢迎在评论区留下你的看法和建议。

## 新闻和社区

### 9 月 20 日消息，苹果在今年调整了沿袭多年的 iPhone 秋季发布节

*2026 年 9 月 20 日｜来源：汇通财经*

9 月 20 日消息，苹果在今年调整了沿袭多年的 iPhone 秋季发布节奏，本次秋季发布会仅推出了 iPhone 18 Pro 系列机型，以及旗下首款折叠屏产品 iPhone Duo。而标准版 iPhone 18、定位更亲民的 iPhone 18e 还有 iPhone Air 2，预计会延后到 2025 年春季正式发布。 针对这一调整，分析机构 Deepwater Asset Management 的管理合伙人兼联合创始人、前 Piper Jaffray（现在的 Piper Sandler）分析师 Gene Munster 发布观点称，苹果拆分 iPhone 18 系列发布节奏的策略已经显现成效。 他给出的相关数据显示，iPhone 18 Pro 系列开启预购后，上市首日的产品预计送达时长相较 2024 年同期拉长了约 15%。基于这一表现，Gene Munster 判断，有一部分原本打算入手基础款 iPhone 的消费者，选择了提升预算，转而选购定价更高的 iPhone 18 Pro 或者 iPhone 18 Pro Max 机型。

### 苹果 AI 服务器曝光：代号 Baltra、搭载自研 M8 Ultra 芯片

*2026 年 9 月 18 日｜来源：新浪财经*

9 月 18 日消息，据 The Information 报道，苹果已讨论在一款规划中的 AI 推理服务器上采用英伟达 NVLink Fusion 网络技术。

该服务器将搭载苹果自研芯片，意味着苹果可能重返服务器市场。知情人士向该媒体介绍了相关情况。消息传出后，苹果股价稍早一度走低，随后在盘前交易中翻红并小幅上涨。

报道称，苹果正在开发一款企业级 AI 服务器，面向 AI 开发者、企业和政府部门，可能推出搭载两颗或四颗规划中 M8 Ultra 芯片的版本。M8 Ultra 被描述为苹果性能最高的处理器，目前仍处于研发阶段，尚未正式发布。

苹果上一次销售专用服务器硬件，还要追溯到旗下 Xserve 产品线。Xserve 于 2002 年推出，采用 1U 机架式设计，预装基于 UNIX 的 Mac OS X Server 操作系统，主要面向企业级用户与数据中心场景，早期搭载 PowerPC G4 处理器，后升级至英特尔至强处理器。

但由于苹果对企业市场重视不足、客户支持薄弱，Xserve 始终未能打开局面，最终于 2011 年 1 月 31 日停止销售。此后，苹果业务重心全面转向消费电子设备。

苹果已与博通合作开发首款 AI 服务器芯片，内部代号为"Baltra"，预计采用台积电 3 纳米 N3E 工艺，基于 Chiplet 架构设计。

博通协助苹果设计各个小芯片，苹果则负责将它们组装成单一封装。这种隔离式开发方式，使苹果能够对博通等合作伙伴保密整体设计。

苹果已考虑用 NVLink Fusion 连接这款规划中 AI 服务器里的 M8 芯片。NVLink Fusion 是英伟达于 2025 年 5 月台北国际电脑展期间发布的高速互联技术，将原本主要用于自家芯片的 NVLink 开放给其他厂商，使客户的定制芯片既能彼此高速互联、组成大规模 AI 计算系统，也能与英伟达 GPU 协同工作。

据英伟达官方介绍，第五代 NVLink 支持 72 个 GPU 实现全互联通信，通信速率达 1800 GB/s，聚合总带宽高达 130 TB/s。目前，联发科、Marvell 等企业已成为该技术首批合作伙伴，富士通和高通则计划通过该技术将自家 CPU 与英伟达 GPU 进行集成。

推动苹果进军企业级 AI 服务器的因素之一是 Mac 业务的强劲增长。苹果最新财报显示，Mac 单季度营收达到 103 亿美元，同比增幅接近 29%，增速超过 iPhone 和 iPad，成为苹果硬件板块增长最快的业务线。市场将这一增长很大程度上归因于 AI 企业的批量采购需求。

![](https://pics0.baidu.com/feed/9825bc315c6034a8e0bf64b46fb31846082376dd.jpeg@f_auto?token=fa29a3072e40cefab3e3f390bfcdde46)

### 苹果自研 AI 服务器芯片：基于 M7 Ultra 款有望 2029 年登场

*2026 年 9 月 17 日｜来源：IT之家*

针对科技媒体 The Information 昨日关于苹果服务器芯片报道，彭博社的马克 · 古尔曼（Mark Gurman）表示这颗服务器芯片可能基于 M7 系列开发，预估 2029 年发布，上市后会和英伟达竞争。

昨日报道，苹果公司正筹划自研企业级服务器，采用自研 AI 芯片，产品目前考虑推出两个版本：基础版配备两颗计划中的 M8 Ultra 芯片，高配版则配备四颗。

苹果考虑用英伟达的 NVLink Fusion 连接这些 M8 芯片。NVLink Fusion 包括交换机、芯粒和软件，能够让数据中心内的多颗芯片高速协同工作。如果这一方案最终落地，也会成为苹果与英伟达关系回暖的又一迹象。

彭博社的马克 · 古尔曼今天在 X 平台转发推文并表示，认为苹果研发的自研服务器芯片可能基于 M7 Ultra，预估 2029 年发布。此外苹果还将推出一款新的 AI 服务器，预计于 2027 年初上线。

![](https://pics4.baidu.com/feed/38dbb6fd5266d01628789d0fa109841535fa3563.jpeg@f_auto?token=409a39d7860503dbc77de331f1ac7536)

## 提案


## Swift论坛

### 1、Vapor 5 首个测试版发布：拥抱结构化并发

作者：Tim（0xTim） ｜ 发布日期：2026-09-15
[阅读原帖](https://forums.swift.org/t/vapor-5-beta-1-released/89572 "Vapor 5 Beta 1 Released")

**Vapor 5 Beta 1** 在 Vapor 1.0 发布十周年当天亮相。此次重写以 **结构化并发** 和最新生态库为基础，推动框架摆脱围绕事件循环组织服务的旧模型。

作者在后续的[官方介绍](https://blog.vapor.codes/posts/whats-new-in-vapor-5-beta/ "What's New in Vapor 5 Beta")中说明：路由默认采用流式请求体，`content.decode()` 因此需要 `await`；**Request** 与 **Response** 改为结构体，服务通过显式依赖注入传递，并接入 **Swift HTTP Types**、**Swift Configuration** 和 **Swift Service Lifecycle**。

讨论中，开发者肯定通用类型和 HTTP 服务实现拆分为独立包的方向，认为这有助于扩大 Swift 后端生态。**点评：** 本次升级值得关注的是并发模型与服务组织方式的改变；测试版可用于评估迁移，部分 API 仍在调整。

### 2、提议引入 Cell、ConstCell 与 Volatile，补足共享内存抽象

作者：Alejandro Alonso ｜ 发布日期：2026-09-15
[阅读原帖](https://forums.swift.org/t/pitch-cell-constcell-and-volatile/89582 "[Pitch] Cell, ConstCell, and Volatile")

这份由 Alejandro Alonso 与 Doug Gregor 合作的提议，以可组合类型取代此前的 `AliasedSpan`／`AliasedRef` 方案，解决共享内存、C/C++ 互操作和同步原语难以满足 **独占访问规则** 的问题。

**Cell** 提供内部可变性，可与 **Span**、**Ref** 组合；**ConstCell** 禁止从 Swift 写入，但允许外部修改底层内存；**Volatile** 表达面向内存映射 I/O 等场景的易失读写语义。它们仍是拟议 API。

争议集中在 **Cell** 的条件式 **Sendable** 遵循：参与者担心它让未同步的共享状态绕过诊断，支持者强调其跨语言同步用途。此外，硬件开发者建议以显式读写方法替代属性访问，避免隐含的多次读改写。**点评：** 生命周期安全与并发正确性需要分别保证，接口必须清楚表达这条边界。

### 3、UncheckedString 提议：保留未经 Unicode 验证的字符串数据

作者：Alastair Houghton ｜ 发布日期：2026-09-15
[阅读原帖](https://forums.swift.org/t/pitch-uncheckedstring-raw-string-support-for-swift/89571 "[Pitch] `UncheckedString` (raw string support for Swift)")

作者提议新增 **UncheckedString<Element>**，容纳编码未知、非有效 UTF-8 或宽字符数据，服务于文件名、命令行参数、环境变量及 Windows 互操作等需求。

方案提供按元素宽度表示的字符串字面量，并用 `\x{...}` 写入原始单元，避免先转换为 **String** 而丢失原始数据。**swift-protobuf** 开发者指出，这也有助于替代大型数组字面量，缓解嵌入二进制数据时的编译与存储问题。

讨论焦点是应否引入整套新字符串类型与协议，还是先设计原始字面量并衔接通用字节容器；命名和 **Span** 接口也待完善。**点评：** 无损保留数据的需求明确，但它与 Unicode 文本、普通字节缓冲区的职责边界仍需收敛。

### 4、Swift 密码学生态讨论：Swift Crypto 是否应独立演进

作者：Paul Toffoloni ｜ 发布日期：2026-09-18
[阅读原帖](https://forums.swift.org/t/state-of-cryptography-in-swift/89649 "State of cryptography in Swift")

作者重新讨论 **Swift Crypto** 与 **CryptoKit** 紧密耦合带来的限制，认为服务端及非 Apple 平台需要更透明、独立的贡献和发布流程。

他以 **HMAC** 内存分配优化、**ML-DSA-44** 与 **SLH-DSA** 支持推进缓慢为例，提出在 `swiftlang` 下建立初期兼容现有 API 的密码学库，或让 Swift Crypto 逐步独立演进。这些是讨论方向，尚非确定计划。

回复支持改善治理与发布节奏，并补充 **swift-nio-ssl** 和 Swift Crypto 各自编译 **BoringSSL** 所增加的构建负担；Tim 认为需要生态指导组进一步讨论。**点评：** 关键在于如何兼顾 API 稳定性、维护能力与跨平台需求，形成社区能够持续参与的演进机制。

### 5、提议为 Hasher 增加 RawSpan 字节输入接口

作者：Jeremy Schonfeld ｜ 发布日期：2026-09-15
[阅读原帖](https://forums.swift.org/t/pitch-add-rawspan-primitive-to-hasher/89583 "[Pitch] Add RawSpan primitive to Hasher")

该提议为 **Hasher** 增加 `combine(bytes: RawSpan)` 重载，使开发者无需借助 **UnsafeRawBufferPointer** 即可将原始字节混入哈希状态，补齐标准库对安全内存视图的支持。拟议接口如下：

```swift
extension Hasher {
    public mutating func combine(bytes: RawSpan)
}
```

讨论中有人建议同时接受 **ConvertibleToBytes**。作者希望保持范围集中，认为减少转换样板应在所有接收 **RawSpan** 的 API 间统一设计。让 RawSpan 遵循 **Hashable** 也被列为未来方向，不属于本次改动。

**点评：** 这是一次范围明确的安全性补齐，保留现有按字节混入的语义；帖子发布时尚未实现，不能视为已经可用的标准库 API。


## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[Swift 6.3 中 Codable 错误终于变得可读了](https://sarunw.com/posts/readable-codable-errors/ "Swift 6.3 中 Codable 错误终于变得可读了")

**摘要：** 这篇来自Sarunw的技术博客聚焦于 Swift 6.3 中一项看似微小却极大改善开发体验的改进：DecodingError 和 EncodingError 现在会输出带有编码路径的清晰单行摘要，而不再是过去需要费力略过的大段文本。全文为长期受困于 Codable 错误信息冗长难读的开发者，提供了一个简洁实用的版本升级理由。

[我们的WWDC 26系列现已免费开放](https://www.pointfree.co/blog/posts/226-our-wwdc-26-series-is-now-free/ "我们的WWDC 26系列现已免费开放")

**摘要：** 这篇来自Point-Free的公告宣布其WWDC 26系列共10集内容现已免费。系列深入分析了SwiftUI、UIKit和SwiftData的重大更新，并与Point-Free生态中的SwiftNavigation、SQLiteData、StructuredQueries等工具进行对比。内容从Apple新的状态驱动弹窗API讲起，覆盖UIKit对Observation框架的支持、SwiftData新的查询与持久化特性，最终通过逆向工程SwiftUI的@State宏来填补其遗留缺口，为希望深入理解WWDC 26框架更新的开发者提供了一份系统性的深度解读。

[为什么某些 Swift 类型只在你导入两个模块时才会出现](https://sarunw.com/posts/swift-cross-import-overlay/ "为什么某些 Swift 类型只在你导入两个模块时才会出现")

**摘要：** 这篇来自 Sarunw 的技术博客揭示了一个许多开发者未曾留意却频繁遭遇的编译现象：单独 import SwiftUI 时 Map 视图报“cannot find in scope”，加上 import MapKit 后立即编译通过。文章指出， Map 实际上位于一个名为 _MapKit_SwiftUI 的交叉导入覆盖层（ cross-import overlay ）模块中——只有当文件中同时导入了MapKit和SwiftUI时，编译器才会自动加载这个隐藏模块。 Apple 采用这一设计的目的是避免框架间的强制依赖：若将 Map 放入 SwiftUI，则每个导入 SwiftUI 的应用都会被迫拖入 MapKit ；放入 MapKit 则反向发生。文章还提供了通过 xcrun 命令自行查看 SDK 中覆盖层定义的具体方法，并梳理了iOS 26 SDK 中常见的36组配对关系。


## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
