## 前言

**本期是 Swift 编辑组自主整理周报的第七十一期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

心中若有光芒，脚下自有轨道。如若前方无路，**Swift社区**与你并肩携手，踏出一条路来！👊👊👊

> **周报精选**
>
> 新闻和社区：消息称苹果首款大折叠手机目前打样外屏 5.49“±、内屏 7.74”±
> 
> 提案：添加 `Collection` 一致性 `enumerated()`
> 
> Swift 论坛：讨论使用 Swift Build 改进 SwiftPM 构建
>
> 推荐博文：揭开 iOS 中 weak 指针的神秘面纱：从原理到实践
>
> **话题讨论：** 
> 
> 苹果为何选择阿里巴巴作为中国市场的本地化合作伙伴？
>
>**上期话题结果**

![](https://files.mdnice.com/user/47553/36fbdd68-b2e2-4262-9be2-2a0a6aef3ee7.jpeg)

都说现在年味淡了，其实是曾经期待过年的那一批人，现在成为了制造年味的人。

## 新闻和社区  

### TikTok能否摆脱争议重返苹果App Store？最新消息来了！

2025 年 2 月 14 日

TikTok 能否摆脱争议重返苹果 App Store？最新消息来了！

在过去的几个月里，社交媒体巨头 TikTok 一直处于争议的风口浪尖。随着美国司法部对其采取的行动，这个年轻的平台面临着巨大的压力。然而，随着时间的推移，TikTok 似乎正在逐渐摆脱这些争议，并重新获得其在苹果 App Store 中的地位。

首先，我们回顾一下这场争议的背景。在去年 1 月，美国政府以国家安全为由，对 TikTok 采取了一系列限制措施。其中包括禁止政府机构与 TikTok 进行交易，以及要求苹果和谷歌下架该应用。然而，这些限制措施并未阻止 TikTok 的用户基础和增长势头。

近期，彭博社报道称，苹果公司将在当地时间周四根据美国司法部长的信件，恢复字节跳动公司的 TikTok 在美国 App Store 的运营。这一消息令人振奋，因为它表明 TikTok 在法律层面已经得到了美国政府的认可。

然而，尽管法律问题得到了解决，但 TikTok 仍面临许多挑战，尤其是在苹果 App Store 和谷歌 Google Play 美国区市场。尽管 TikTok 的应用程序已经下架，但苹果和谷歌尚未提供下载链接。因此，用户仍无法直接从应用商店中获取该应用。

为了解决这个问题，TikTok 在官网支持中心发布公告，称由于该应用暂时无法在美国区应用商店中下载，因此官方为用户推出了安卓 APK 安装包，以供用户在自己的安卓设备上安装相应软件。此外，对于 iOS 用户，他们可以将网页版 TikTok 添加到手机主屏幕上。这是一个积极的步骤，因为它为 TikTok 的用户提供了实际的解决方案。

然而，TikTok 的未来仍然存在不确定性。尽管它已经获得了在美国 App Store 重新上架的许可，但这个过程可能需要时间。此外，苹果和谷歌的政策可能会在未来发生变化，再次导致 TikTok 的应用被下架。因此，TikTok 需要持续关注这些情况的发展，并做好应对准备。

至于 TikTok 是否能够彻底摆脱争议并重返苹果 App Store，这取决于许多因素。首先，它需要证明其能够保护用户数据和安全。这可能涉及到与政府机构合作，以确保应用符合所有相关法规。其次，TikTok 需要与苹果和谷歌建立良好的关系，以避免未来出现任何冲突。

最后，我们需要考虑到公众舆论的影响。尽管法律允许 TikTok 在美国重新上架，但公众对其的态度仍然不确定。因此，TikTok 需要积极与公众沟通，解释其立场和计划，以建立公众对其的信任和支持。

总的来说，TikTok 正在努力摆脱争议并重返苹果 App Store。虽然这个过程可能会很艰难，但随着时间的推移，我们相信 TikTok 将能够克服所有障碍，继续发展壮大。（来源：极客网）

### 消息称苹果首款大折叠手机目前打样外屏 5.49“±、内屏 7.74”±

2025 年 2 月 14 日

博主 @数码闲聊站 透露，苹果公司的首款折叠屏 iPhone 是大折叠，目前打样外屏 5.49"±，内屏 7.74"±。

![](https://files.mdnice.com/user/47553/d9c55830-84a9-4d24-aaa2-4563243776e7.png)

此前有消息称苹果公司开始加快其首款折叠屏 iPhone 的研发步伐，公司已开始与超薄玻璃（UTG）供应商展开合作，对此蓝思科技表示“涉及保密协议公司不方便回应”。

此外，韩国企业 Dowoo Insys 和 UTI 可能成为苹果的次级供应商。IT之家获悉，Dowoo Insys 在 2024 年 10 月获得了两项 UTG 中央减薄技术的专利，其中一项与苹果同期申请的专利存在相似之处。

先前多家外媒或业内人士，包括郭明錤、Jeff Pu、《The Information》和《华尔街日报》均预测，该设备最早可能在 2026 年（明年）底或 2027 年（后年）初上市。（来源：IT之家）

### 终于确认了！阿里拿下苹果公司大生意！

2025 年 2 月 13 日

2 月 11 日晚，一则“阿里巴巴成为苹果中国 AI 合作方”的消息，引发业内高度关注。业界普遍认为，这一合作不仅关乎两大巨头的发展，更可能重塑全球智能手机 AI 应用的格局。

![](https://pic.rmb.bdstatic.com/bjh/news/926bf6fb7abad288bb04f1ce59903850.jpeg)

据第一财经，2 月 13 日，在阿联酋迪拜举办的 World Governments Summit 2025 峰会上，阿里巴巴联合创始人、董事局主席蔡崇信回应阿里与苹果合作传闻，他表示，苹果在中国需要一个本地化的合作伙伴，为他们的手机服务。苹果一直非常挑剔，他们与中国的多家公司进行了交谈。最终，他们选择与我们做生意。我们非常幸运，也非常荣幸能够与苹果这样的伟大公司做生意。

据科创板日报，AI 化是苹果手机的明确发展方向，外接大模型是关键。知情人士表示，苹果自 2023 年起开始测试来自知名中国人工智能开发者的不同人工智能模型，并在去年选择了百度作为主要合作伙伴，但由于百度在为苹果智能开发模型方面的进展未达到美国公司的标准，因此该合作后来被取消。

知情人士还称，苹果在最近几个月开始考虑其他选项，评估腾讯、字节跳动、阿里巴巴以及 Deepseek 开发的模型。报道提到，苹果最终放弃了最近呼声很高的 DeepSeek，因为 DeepSeek 团队缺乏支持像苹果这样的大客户所需的人力和经验。

据了解，阿里的通义千问 Qwen 系列大模型在开源领域和性能评测中均表现出色，处于行业第一梯队。2 月 4 日凌晨，Chatbot Arena LLM Leaderboard 更新了最新一期的榜单，不久前发布的 Qwen2.5-Max 直接冲进前十，超越 DeepSeek V3, o1-mini 和 Claude-3.5-Sonnet 等模型，以 1332 分位列全球第七名。同时，Qwen2.5-Max 在数学和编程上排名第一，在 Hard prompts 方面排名第二。（注：Qwen-Max 是阿里云通义团队对MoE模型的最新探索成果）

市场对于苹果手机在中国大陆上线 AI 功能已有预期。2 月 9 日，苹果向开发者发送邮件，宣布将于北京时间 3 月 25 日 10:00-12:00 在上海举行“利用 Apple 智能的力量”开发者活动，活动主题将围绕苹果智能和机器学习两个方面。

另据 iOS 果粉，iOS18.4 或将于 2025 年 4 月正式发布，同时中文版的 Apple Intelligence 也将于该版本中正式亮相。

目前，苹果在中国大陆的市场份额正不断被国产手机品牌蚕食。据 Canalys 数据，24Q4 中国大陆智能手机出货量达到 7740 万台，同比增长 5%。其中，苹果出货量达到 1310 万台，市场份额为 17%，排名第一。但由于国产旗舰设备竞争加剧，苹果出货量同比大幅下滑 25%。

据证券时报援引外媒报道，苹果此举正是为了应对在中国销售下滑，旨在提供更具吸引力的软件功能。消息人士补充说，苹果和阿里巴巴已将共同开发的中国 AI 功能提交给中国的网络监管机构审批，表明该合作伙伴关系已取得显著进展。

受此消息影响。阿里巴巴港股、美股近日都迎来大涨。盘面上，阿里巴巴港股今日一度大涨超 9%，盘中股价一度创下自 2022 年以来新高，且年内涨幅已超 40%。截至收盘，阿里巴巴港股涨 2.55%，报 116.7 港元/股，总市值 2.2 万亿港元。(来源： 每日经济新闻)

### 时隔一年多，苹果重新在马斯克的 X 平台投放广告

2025 年 2 月 13 日

苹果公司本月开始首次重新在 X 平台上投放广告，距离其上次在该平台投放广告已有一年多的时间。苹果曾在 2023 年 11 月暂停在 X 平台的广告投放，原因是该平台所有者埃隆・马斯克发表了一些有争议的言论。

![](https://zkres1.myzaker.com/202502/67ad26978e9f0959902346f3_1024.jpg)

据观察，苹果的官方账号 @Apple 目前投放了一则广告，宣传 Safari 浏览器的隐私功能。此外，苹果的 @AppleTV 账号也在为 Apple TV + 的剧集《Severance》投放广告。

上个月有报道称苹果正在考虑重新在 X 平台上投放广告，如今看来，苹果已经做出了这一决定，至少目前是如此。

IT 之家注意到，苹果并非唯一一家曾在 X 平台上暂停广告投放的大品牌。此前，包括迪士尼、可口可乐、索尼、IBM、康卡斯特等众多知名品牌都曾暂停过在 X 平台的广告投放。不过，迪士尼等品牌已经重新在该平台投放广告。

马斯克于 2022 年收购了 Twitter，并在 2023 年将其更名为 X。在他的掌控下，X 平台对内容审核采取了较为宽松的态度，导致一些极端观点在平台上大量传播。

尽管如此，苹果公司首席执行官蒂姆・库克以及其他高管，如营销主管格雷格・乔斯维亚克，自马斯克收购该平台以来，一直保持着在 Twitter（现 X 平台）上的活跃。不过，苹果前营销主管菲尔・席勒选择离开了 X 平台，转而使用 Mastodon 和 Bluesky 等其他平台。（来源：IT之家）

## 提案

### 通过的提案

[SE-0452](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0452-integer-generic-parameters.md "SE-0452") **整数通用参数** 提案通过审查。该提案已在 **第六十六期周报** 正在审查的提案模块做了详细介绍。

[SE-0454](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0454-memory-allocator.md "SE-0454") **工具链的自定义分配器** 提案通过审查。该提案已在 **第七十期周报** 正在审查的提案模块做了详细介绍。

[SE-0455](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0455-swiftpm-testable-build-setting.md "SE-0455") **SwiftPM @testable 构建设置** 提案通过审查。该提案已在 **第七十期周报** 正在审查的提案模块做了详细介绍。

[SE-0457](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0457-duration-attosecond-represenation.md "SE-0457") **公开秒表 Duration** 提案通过审查。该提案已在 **第七十期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0459](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0459-enumerated-collection.md "SE-0459") **添加 Collection 一致性 enumerated()** 提案正在审查。

本提案旨在解决 `enumerated()` 返回的序列缺乏 `Collection` 一致性的问题，防止它在需要 `Collection` 的上下文中使用。

[SE-0460](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0460-specialized.md "SE-0460") **Explicit Specialization** 提案正在审查。

本提案引入了一个新属性 `@specialized`，它允许泛型函数的作者为特定类型生成该函数的预专业版本。当函数的非专业版本使用这些类型之一调用时，编译器将生成代码，如果可用，该代码将重新分发到这些预专业版本。

## Swift论坛

1) 讨论[使用 Swift Build 改进 SwiftPM 构建](https://forums.swift.org/t/evolving-swiftpm-builds-with-swift-build/77596 "使用 Swift Build 改进 SwiftPM 构建")

Swift 论坛于 2025 年 2 月 1 日宣布了一个名为 Swift Build 的新开源项目，该项目将成为 Swift 工具链的一部分，并用于优化 Swift 包管理器（SwiftPM）的构建系统。该项目的目标是在所有受支持的平台上统一构建体验，并提供更强大、灵活的构建功能。

Swift Build 主要特性:

1.	基于 SwiftDriver 的构建
* Swift Build 将采用 SwiftDriver（Swift 编译器驱动的库实现），以提高构建任务的调度效率，并优化构建依赖图。
* 这将使 SwiftPM 的构建系统更可扩展，并更容易适应未来的改进。
2.	增强的构建配置
* Swift Build 将引入更强大的 构建配置系统，使开发者能够在 Package.swift 文件中定义更灵活的构建规则。
* 目前 SwiftPM 仅支持基本的构建配置（如 debug/release），未来将允许更细粒度的配置，如 针对特定平台、架构或环境的自定义设置。
3.	显式模块构建（Explicit Module Builds）
* 传统的 SwiftPM 构建过程依赖于隐式模块，可能导致 并行构建效率低下 以及 模块依赖解析问题。
* Swift Build 将采用 显式模块构建，减少模块间的争用，提高并行构建性能，并确保模块依赖解析的正确性。
4.	支持更多产品类型
* 目前 SwiftPM 主要用于构建库和命令行工具，但 Swift Build 未来将支持 GUI 应用程序、Web 服务 等更多类型的产品。
* 这将使 SwiftPM 在 iOS、macOS 和 Server-Side Swift 领域的应用更加广泛。
5.	跨平台一致性
* Swift Build 的架构设计将确保在不同平台（macOS、Linux、Windows）上提供一致的构建体验。
* 这对于 跨平台开发 和 Swift 生态系统的标准化 具有重要意义。

未来发展方向

Swift Build 的推出是 SwiftPM 发展中的一个重要里程碑，它将大幅提升 Swift 生态系统的构建能力，使其更加现代化和可扩展。未来，该项目可能会进一步优化增量编译、缓存机制，以及支持更复杂的构建系统集成，如与 C++ 交互等。

Swift 社区鼓励开发者关注该项目的进展，并参与讨论，共同推动 SwiftPM 的演进。

2) 提议[[经修改后接受] SE-0453：InlineArray（以前称为：Vector，固定大小的数组）](https://forums.swift.org/t/accepted-with-modifications-se-0453-inlinearray-formerly-vector-a-fixed-size-array/77678 "[经修改后接受] SE-0453：InlineArray（以前称为：Vector，固定大小的数组）")

2025年2月5日，Swift 论坛宣布接受了提案 SE-0453，但进行了若干修改。 该提案引入了一个名为 InlineArray 的新类型，旨在提供固定大小的数组功能。

* 原提议的初始化方法：

```Swift
public init<E: Error>(with next: (Index) throws(E) -> Element) throws(E)
```
将去掉参数标签，改为：`init(_:)`。

* 在审查过程中，有人指出 InlineArray 的下标操作与 Span 类型不同。 语言指导小组决定让 InlineArray 采用 Span 中缺失的下标操作。

关于命名：

语言指导小组对该类型的命名进行了深入讨论，考虑了审查线程中的意见和私人反馈。 最终决定采用 InlineArray 这一名称，原因如下：

* 关于 Vector 名称： 小组同意，Swift 与其他语言（如 C++ 和 Rust）对“vector”一词的不同理解可能导致混淆。 此外，Vector 与数学向量的关联性不足，难以仅凭此理由采用该名称。
* 关于 FixedSizeArray 名称： 虽然该名称准确描述了类型的行为，但未能体现该类型在复制时的性能特征。 InlineArray 通过 Inline 前缀，强调了其存储方式和性能特性。

综上，InlineArray 这一名称既传达了类型的固定大小特性，又强调了其内联存储和复制行为。 语言指导小组认为，这一命名能够有效避免潜在的性能误解。

感谢所有参与审查的人士，您的贡献使 Swift 语言更加完善。

3) 提议[非弹性模块的可扩展枚举](https://forums.swift.org/t/pitch-extensible-enums-for-non-resilient-modules/77649 "非弹性模块的可扩展枚举")

2025年2月4日，Swift 论坛成员 Franz Busch 和 Pavel Yaskevich 提出了一个名为“为非弹性模块引入可扩展枚举”的新提案。 该提案旨在解决非弹性（non-resilient）模块中枚举类型在 API 演进过程中遇到的问题。目前，Swift 包中的公共 API 避免使用枚举类型，因为在不破坏现有代码的情况下，无法向公共枚举添加新案例。该提案建议对非弹性模块中的枚举行为进行调整，使其与弹性模块中的行为保持一致。具体而言，未标记为 @frozen 的枚举将被视为可扩展的，这意味着在未来可以添加新案例，而不会破坏现有代码。对于从其他模块（不在同一包内）导入的此类枚举，开发者在使用 switch 语句时，需要添加 `@unknown default:` 分支，以处理可能的新增案例。然而，对于同一包内的模块之间的枚举使用，switch 语句仍要求穷尽所有已知案例，无需添加 `@unknown default:` 分支。该提案的目标是统一 Swift 语言中弹性和非弹性模式下的枚举行为，简化库维护，并鼓励在公共 API 中更广泛地使用枚举。

4) 提议[可替换的库插件](https://forums.swift.org/t/pitch-replaceable-library-plugins/77605 "可替换的库插件")

2025年2月2日，Swift 论坛成员提出了一个名为“可替换库插件”（Replaceable Library Plugins，简称 RLP）的新提案。 该提案旨在为 Swift 包管理器（SwiftPM）引入对动态库的支持，特别是在 Linux 环境中。目前，SwiftPM 在 Linux 上缺乏对非系统二进制库依赖项的支持，这意味着每当应用程序的某个组件发生变化时，开发者需要重新编译并部署整个应用程序。RLP 的引入将允许开发者将这些变化频繁的组件打包为动态库，并在不重新编译整个应用程序的情况下进行替换和升级。这些动态库将通过现有的 `.artifactbundle` 格式进行分发。需要注意的是，RLP 主要面向组织内部或特定客户的内部使用，组织需要定义自己的“组织定义平台”（Organization-Defined Platforms，ODP），以确保二进制兼容性。要创建 RLP，开发者需要使用 `-enable-library-evolution` 标志构建一个普通的 SwiftPM 库产品，并将其打包为 `.artifactbundle`。该提案的目标是为 SwiftPM 引入动态库支持，特别是在 Linux 环境中，以提高应用程序的模块化和可维护性。

5) 讨[在 Swift 中使用 C 库：思考](https://forums.swift.org/t/using-the-c-library-from-swift-thoughts/77648 "在 Swift 中使用 C 库：思考")

2025年2月4日，Swift 社区成员 Alastair Houghton 在 Swift 论坛上发起了关于在 Swift 中使用 C 标准库的讨论。 讨论的起因是为 FreeBSD 添加支持的拉取请求中，当前的实现滥用了 Glibc 模块，而 FreeBSD 并不使用 Glibc。这引发了关于创建统一的 C 标准库模块的想法，以简化跨平台开发者在不同操作系统上导入 C 标准库的过程。

当前问题：

* 导入差异： 开发者需要根据操作系统条件导入不同的 C 标准库模块，例如：

```swift
    #if os(Linux)
    import Glibc
    #elseif os(macOS) || os(iOS) || ...
    import Darwin
    #elseif os(Windows)
    import CRT
    #else
    #error We need a C library!
    #endif
```

这种方式增加了代码的复杂性和维护成本。

* 类型不一致： 同一 C 类型在不同平台上的导入方式可能不同，例如 FILE * 可能被导入为 `OpaquePointer`、`UnsafeMutablePointer<FILE>` 或 `UnsafeMutablePointer<FILE>?`，这取决于 C 库的定义方式，导致在 Swift 中使用这些类型时缺乏一致性。

建议的解决方案：

讨论中提出了创建统一的 C 标准库模块的想法，例如：

* 标准库模块： 允许开发者通过以下方式导入特定的 C 标准库：

```swift
import C99 // 或 C11、C23 等
```

* 扩展库模块： 提供一个模块，包含常见的 C 扩展函数，并统一命名，例如：

```swift
import CExtensions
```

在该模块中，函数 `strcasecmp` 可以在 Windows 上使用，即使在 Windows 上该函数名为 `_stricmp`。

实现挑战：

然而，实现上述方案并非易事，主要挑战包括：

* 模块化限制： Clang 模块要求每个 C 类型只能由一个模块定义。例如，FILE 类型必须由定义它的 C 库模块唯一提供。如果在其他地方重新定义该类型，可能会导致编译错误。
* 头文件问题： 特别是 Glibc 的头文件，存在难以模块化的问题，导致 Glibc 模块存在缺陷，修复这些问题也相当困难。

Alastair Houghton 表示，虽然他个人希望能够通过导入统一的 C 标准库模块来简化跨平台开发，但实现这一目标需要仔细考虑，远非简单地编写一些新的头文件和模块映射那么简单。

他还提到，平台指导小组（Platform Steering Group）对该问题表示兴趣，但目前尚未直接开展相关工作。

## 推荐博文

[【Swift 底层】Swift 底层探索方法介绍](https://juejin.cn/post/7291301474322137146 "【Swift 底层】Swift 底层探索方法介绍")

**摘要：** 本文聚焦 Swift 底层探索方法，指出在探究 Swift 底层原理时常遇无从下手的困境，进而分享多种可行途径。先阐述 Swift 底层探索基础，包括 Swift 源码定义基本功能及通过研究标准库学习底层实现，介绍 Swift 经 LLVM 编译，由 swiftc 完成从 Code 到机器码的系列步骤，且 swiftc 生成可执行文件多生成 SIL 文件这一步骤。接着说明探索方案，如 swiftc 的常用指令，强调常选 SIL 文件分析，并介绍 IR 基本语法、SIL 文件常见指令及 SIL 文件中寄存器的特点。通过创建main.swift文件实例，详细展示利用 SIL 文件探索代码底层操作的过程。还给出 Swift 源码仓库地址、目录结构及常用索引。最后总结，SIL 文件助力探究方法调用与部分数据结构底层实现，Swift 源码有助于理解设计原理，建议二者结合使用。

[iOS Protobuf 的使用](https://juejin.cn/post/7470734300346974262/ "iOS Protobuf 的使用")

**摘要：** 文章围绕 iOS 中 Protobuf 的使用展开，Protobuf 是谷歌推出的语言、平台无关且扩展性好的数据封装格式协议，支持 C++、Python、Java 等语言。首先介绍安装方式，可通过 brew 安装 protobuf 和 swift - protobuf 并检查版本确认安装成功。接着阐述创建 .proto 文件，以示例展示 V3 语法及相关配置。随后说明将 proto 文件转化为 objc 文件的步骤，包括建立文件夹、执行特定终端命令。在 iOS 工程使用部分，强调添加 Protobuf 和 SwiftProtobuf 依赖，导入生成文件并设置编译参数，分别以 OC 和 Swift 代码示例展示构建请求、发送数据、处理响应及对比 Protobuf 与 JSON 数据长度的过程，同时提及确保服务器端支持 Protobuf 并正确配置服务接口。

[揭开 iOS 中 weak 指针的神秘面纱：从原理到实践](https://juejin.cn/post/7470394526323671092/ "揭开 iOS 中 weak 指针的神秘面纱：从原理到实践")

**摘要：** 本文深入探讨 iOS 开发里的 weak 指针，从编译期和运行时讲解它的原理和使用。编译期初始化 `__weak typeof(obj) weakObj = obj;` 时，会转为 `objc_initWeak((void *)&weakObj, obj);`。运行时，`objc_initWeak` 等 4 个初始化函数都调用 storeWeak，`objc_initWeak` 用于初始化新的 weak 指针，`objc_storeWeak` 在 weak 指针赋值时调用。storeWeak 会先解除与旧对象的关联，再和新对象建立关联。关联操作通过 weak_table 这个类似哈希表的数据结构，SideTable 则是获取 weak_table 的入口。对象释放时，`weak_clear_no_lock` 函数会遍历其对应的弱引用表，把 weak 指针赋值为 nil。此外，文章还解答了如不能给 Category  添加 weak 属性、block 中 weak 指针访问成员变量报错、无弱引用时仍执行 `weak_clear_no_lock` 等疑问。

## 话题讨论

**苹果为何选择阿里巴巴作为中国市场的本地化合作伙伴？**

1. 深厚的技术积累：阿里在人工智能领域有着深厚的技术积累。
2. 强大的本地化市场理解：阿里对中国市场的理解和洞察非常深刻，能够在本地化服务上提供更好的体验。
3. 丰富的数据资源：阿里的数据资源涵盖了各个领域的用户行为，这些数据可以用来优化苹果的各项服务，提高用户体验。
4. 全球化经验：阿里在全球范围内都有广泛的业务布局，具备丰富的跨国合作经验。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
