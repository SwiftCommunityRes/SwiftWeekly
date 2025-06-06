## 前言

**本期是 Swift 编辑组自主整理周报的第七十五期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

美好的人生，便是朴素和简单，褪去繁华，回归宁静。**Swift社区**，一种适合自己的方式，与生活缠绵，与岁月偕老。👊👊👊

> **周报精选**
>
> 新闻和社区：应对美国关税政策，消息称苹果紧急从印度包机空运 600 吨 iPhone
> 
> 提案：新增 Yielding 访问器提案正在审查
> 
> Swift 论坛：提议简化 Swift 中抛出和异步函数的影响
>
> 推荐博文：如何突破动态化容器的天花板？
>
> **话题讨论：** 
> 
> 明明没搬砖，为何总像被掏空？

## 新闻和社区  

### 应对美国关税政策，消息称苹果紧急从印度包机空运 600 吨 iPhone

2025 年 4 月 11 日

4 月 11 日消息，路透社昨日援引知情人士消息称，苹果在关税生效前包机从印度空运了约 600 吨 iPhone，折合约 150 万部，以赶在美国加征关税前完成调货。苹果近期加快了在印度的生产步伐，试图在新关税生效前建立库存，从而暂时缓解美国市场可能面临的价格压力。

这次行动揭示了苹果应对美国关税政策的私下策略。在美国这个关键市场，苹果正试图分散供应链、提前备货，以避免新品 iPhone 涨价。

一名熟悉苹果物流安排的消息人士表示，苹果“是为了赶在关税生效前出货”。为了加快清关速度，苹果曾向印度金奈机场的相关部门施压，要求将通关时间从原本的 30 小时缩短到 6 小时。该消息人士还称，这项“绿色通道”安排借鉴了苹果在中国部分机场使用的模式。

该人士与一位印度政府官员透露，自 3 月以来已有六架、每架可载重 100 吨的货运飞机从印度起飞，其中一架就在新关税生效当天完成起飞。以 iPhone 14 和充电线合计每部约 350 克计算（含包装），这批 600 吨的货物大致相当于 150 万部设备。

市场研究机构 Counterpoint Research 估计，美国目前约有五分之一的 iPhone 进口自印度，其余仍来自中国。苹果每年全球销量超过 2.2 亿部。

据 Rosenblatt Securities 的预测模型显示，若以 54% 的税率计算，美国市场售价为 1599 美元的 iPhone 16 Pro Max 将上涨至 2300 美元（注：现汇率约合 16919 元人民币）—— 新关税下的溢价可能更为惊人。

为实现产能提升 20% 的目标，苹果在印度加强了空运出货，增加工人数量，并指示富士康在当地的最大工厂周日加班生产。一名知情人士透露，该厂目前已改为每周七天运营。

另有两名知情人士证实，富士康位于金奈的工厂已取消周日休假，这一工厂去年共生产了 2000 万部 iPhone，包括最新的 iPhone 15 与 16 机型。(来源：IT之家)

### 苹果 5 月 2 日发布第二财季财报 营收有望达到 941 亿美元

2025 年 4 月 10 日

4 月 9 日消息，据外媒报道，在一季度落下帷幕之后，各大科技巨头也将财报提上了日程，台积电、特斯拉、三星电子等，均已在官网公布了一季度财报的发布时间。

而从外媒最新的报道来看，苹果公司也已在官网宣布，他们将在当地时间 5 月 1 日美国股市收盘后，也就是北京时间 5 月 2 日凌晨，发布 2025 财年第二财季的财报。

苹果公司的 2025 财年第二财季，截至 3 月底，这一财季通常是苹果营收第二高的财季，仅次于秋季新推出的 iPhone 大量上市的第一财季。

对于苹果公司的第二财季，有报道称华尔街的分析师是平均预计营收 941 亿美元，高于上一财年同期的 907.53 亿美元，同比将增长 3.5%。

但同此前多年第二财季的营收环比明显下滑一样，分析师预计的苹果 2025 财年第二财季 941 亿美元的营收，环比也会有明显下滑，他们第一财季的营收高达 1243 亿美元。

在第二财季期间，苹果公司推出了 iPhone 16 家族的新成员 iPhone 16e，也推出搭载 M3 芯片的新一代 iPad Air 和搭载 A16 芯片的第十一代 iPad，这些新品在上市后的表现，也将是外界关注的，在财报分析师电话会议上预计会被提及。

从苹果在官网公布的消息来看，他们第二财季的财报分析师电话会议，将在太平洋时间 5 月 1 日下午 2 点，也就是北京时间 5 月 2 日凌晨 6 点开始，包括 CEO 库克、CFO Kevan Parekh 在内的多位高管将会出席，简要介绍他们的业绩，并回答分析师提出的问题。

而除了业绩，近期苹果的动向预计也将是分析师们所关注的，苹果在美国销售的产品全部依赖进口，如果关税压力持续他们就面临成本升高的挑战，后需是否会提高在美国的售价，预计也将被提及。(来源：新浪财经)

### 美加征关税让 iPhone 成本增加 50%，苹果公司年损失或达 330 亿美元

2025 年 4 月 8 日

近日，美国对全球多国加征“对等关税”的政策引发轩然大波，苹果公司成为受冲击的“重灾区”。

据央视新闻，根据美国媒体计算的数据，苹果公司制作一部手机，成本大约 580 美元。但在美国宣布对华加征 34% 的所谓“对等关税”后，加上已有的 20% 关税，增加的税额将达到 296.86 美元。一部手机成本上升到 876.79 美元，涨幅超过 50%。据摩根士丹利预测，这一轮关税成本给苹果公司带来的损失可能高达每年 330 亿美元。

根据关于“美国元件 20% 豁免”的条例，如果进口产品中有 20% 以上的美国原材料、零部件或技术，则美国只对产品“非美国”的部分征税。

根据日本经济新闻的拆机调查，999 美元的 iPhone 16 Pro 硬件成本大约 568 美元，其中成本最高的依次是台积电代工的 A18 Pro 芯片（135 美元）和三星电子提供的 OLED 屏幕（110 美元）。

据《印度时报》报道，3 月 27 日至 29 日期间，5 架满载 iPhone 和其他产品的货机从印度起飞，直抵美国。这是苹果为规避美国 4 月 5 日生效的 10% “对等关税”而进行的紧急行动。

苹果公司高度依赖全球供应链，除了中国、越南等国家的代工生产。去年 8 月，据外媒 gsmarena 报道，苹果公司宣布，即将推出的 iPhone 16 Pro 和 16 Pro Max 系列将在印度制造，预计将推动印度在全球 iPhone 产量中的占比从 14% 增长至 25%。

苹果公司还考量在巴西扩大 iPhone 的生产线。富士康位于圣保罗州 Jundiai 的工厂，此前已组装过 iPhone 13、14 和 15 型号，近期开始组装 iPhone 16。

另外，在特朗普第一个任期内，苹果公司就将部分手机和耳机生产转移至印度，将部分耳机、手表和电脑生产转移至越南，并在马来西亚和泰国增设电脑产品生产线。

此次关税政策使得苹果的进口成本大幅增加，进而影响其利润预期。

面对成本压力，苹果公司面临艰难抉择。若将关税成本全额转嫁给消费者，iPhone 16系列价格将上涨30%—40%，iPhone 16 Pro Max（1TB版本）售价或逼近2300美元，几乎与一台中端笔记本电脑相当。这无疑将影响消费者的购买意愿，进而冲击苹果的市场份额。

苹果也可能通过“砍价”降低零部件采购成本，例如要求台积电、富士康等供应商让利，但这将加剧供应链企业的利润危机。此外，苹果还可以与电信运营商合作降低换购补贴、缩减以旧换新折扣，或取消部分赠品来隐性涨价。然而，这些策略都可能引发消费者的不满，影响品牌形象。

尽管如此，据4月7日消息，专注苹果的科技记者马克・古尔曼发文认为，苹果公司仍然不会在这几年内将 iPhone手机生产转移到美国本土，主要是因为成本太高。

而关税政策的冲击，已在资本市场引发连锁反应。自特朗普政府宣布实施所谓“对等关税”以来，苹果公司已连续三个交易日遭遇重挫，累计跌幅超过19%，公司市值缩水6380亿美元。（来源：界面新闻）

### "史上最颠覆 iOS"流出！手势操作全面安卓化？

2025 年 4 月 6 日

苹果年度开发者盛会 WWDC 2025 官宣定档 6 月 9 日，毫无悬念，iOS 19 即将上演重头戏。这个被业界誉为"十年最强系统"的新版本究竟暗藏哪些玄机？作为数码老饕，我连夜整理了全网最全爆料清单，带你一睹为快。

![](https://files.mdnice.com/user/47553/63e61d5e-e0d7-4935-b532-cc932dbf3905.png)

一、视觉革命：Vision Pro 美学下放

这次系统改版堪称 iOS 7 以来最颠覆的设计革新。多方消息指出，苹果正将 Vision Pro 的 visionOS 设计语言全盘移植到手机端。主屏幕图标集体"整容"，圆角弧度更加柔和，系统级应用全面换上磨砂玻璃质感外衣。最惊艳的要数悬浮式交互面板，通知中心像魔法卡片般漂浮在壁纸之上，配合动态高斯模糊效果，每次亮屏都是视觉享受。

![](https://files.mdnice.com/user/47553/034ee4ab-8434-40dd-a0e7-7b5d26075697.png)

开发者内部文件显示，锁屏界面将迎来重大调整。时钟字体支持智能环境适配，通知栏透明度支持手动调节，甚至能根据壁纸色系自动生成渐变效果。不过也有小道消息说，这套新 UI 对 A15 及以上芯片有性能要求，老机型可能只能体验"青春版"视觉效果。

![](https://files.mdnice.com/user/47553/d7da0323-74dc-42bb-ba0a-6b72a1ba5b41.png)

二、专业模式破茧 AI 生态遇冷
相机应用这次要动真格了。据富士康内部流出的工程机演示视频，全新相机界面将专业模式与快捷操作合二为一。手动调节轮盘采用触感反馈设计，ISO、快门速度等参数支持滑动微调。更绝的是，拍摄界面能实时显示直方图和焦段信息，果粉们心心念念的"相机仪表盘"终于要来了。

![](https://files.mdnice.com/user/47553/364e84f1-16d4-4f17-811b-314f51f9dc56.png)

反观 AI 赛道却有些雷声大雨点小。原本承诺的对话式 Siri 跳票至 iOS 20，当前版本仅优化了相册智能分类和文本预测功能。更扎心的是，Apple Intelligence 套件大概率会成为 iPhone 17 专属配置。想起去年此时库克在发布会上大谈 AI 战略，如今这番操作着实让人唏嘘。

![](https://files.mdnice.com/user/47553/374569be-0459-48e2-bff3-44f678e63170.png)

三、七年之痒：三款经典机谢幕

适配名单总能让老用户心头一紧。供应链可靠消息源确认，iPhone XR/XS 系列将止步 iOS 18，这意味着 2018 年发布的机型正式步入历史。作为二手市场常青树，这三款机型其实早已显露疲态：A12 芯片应对 4K 视频剪辑明显吃力，电池续航也难敌如今动辄 5000mAh 的安卓阵营。

![](https://files.mdnice.com/user/47553/7dc4a5ef-5aef-4a06-b749-6e4e631d5da9.png)

不过库克这次还算厚道，iPhone 11 及以上机型都能吃上新系统。但要注意，A13 芯片用户可能无缘部分需要神经网络引擎加持的功能。建议手持老设备的用户升级前做好备份，毕竟新版系统对存储空间的要求又上了一个台阶。

![](https://files.mdnice.com/user/47553/8d801191-5db7-4e61-ba71-886e0d6d05f2.png)

四、尝鲜指南：时间线全掌握

按照惯例，开发者预览版将在主题演讲结束后即刻推送，公测版预计 7 月中旬开放。正式版大概率会随 iPhone 17 系列在 9 月亮相。需要提醒的是，今年测试版存在两个隐藏彩蛋：锁屏动态天气组件和 Safari 分屏模式，不过这些功能最终能否保留还要看后续测试反馈。(来源：来电公社)

![](https://files.mdnice.com/user/47553/993bdb02-636b-40b1-a792-7ea01ee4a29a.png)

## 提案

### 通过的提案

[SE-0461](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0461-async-function-isolation.md "SE-0461") **默认情况下，在呼叫者的演员上运行非隔离异步函数** 提案通过审查。该提案已在 **第七十二期周报** 正在审查的提案模块做了详细介绍。

[SE-0464](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0464-utf8span-safe-utf8-processing.md "SE-0464") **UTF8Span：在连续字节上进行安全UTF-8处理** 提案通过审查。该提案已在 **第七十三期周报** 正在审查的提案模块做了详细介绍。

[SE-0467](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0467-MutableSpan.md "SE-0467") **MutableSpan 和 MutableRawSpan：委托连续记忆的突变** 提案通过审查。该提案已在 **第七十三期周报** 正在审查的提案模块做了详细介绍。

[SE-0468](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0468-async-stream-continuation-hashable-conformance.md "SE-0468") **Hashable 符合 Async(Throwing)Stream.Continuation** 提案通过审查。该提案已在 **第七十三期周报** 正在审查的提案模块做了详细介绍。

[SE-0470](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0470-isolated-conformances.md "SE-0470") **全局行为者隔离一致性** 提案通过审查。该提案已在 **第七十四期周报** 正在审查的提案模块做了详细介绍。

[SE-0473](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0473-clock-epochs.md "SE-0473") **Clock Epochs** 提案通过审查。该提案已在 **第七十四期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0474](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0474-yielding-accessors.md "SE-0474") **Yielding 访问器** 提案正在审查。

我们建议引入两个新的访问器，即 `yielding mutate` 和 `yielding borrow`，以实现计算属性和下标以及当前 get 和 set。

与 get 和 set 相反，其主体的行为类似于传统方法，yielding 访问器的主体将是一个 coroutine，使用新的上下文关键字 yield 来暂停 coroutine 并向调用者提供值的访问权限。当调用者终止对贷款值的访问时，協例的执行将在 yield 后继续。

这些 yielding 访问器使值无需副本即可访问和修改。这对于不可复制的类型来说是必不可少的，即使使用可复制的类型，也通常对性能是可取的。

自 Swift 5.0 以来，此功能一直通过 `_modify` 和 `_read` 关键字提供（但不支持）。此外，该功能可以通过使用标志 `-enable-experimental-feature CoroutineAccessors` 从编译器 main 分支的最新构建中 read 和 modify。

[SE-0475](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0475-observed.md "SE-0475") **值的事务观察** 提案正在审查。

该提案提出了一种新的方式来观察模型的变化：这种方式是 安全的（safe）、符合人体工学的（ergonomic），而且具有良好的 可组合性（composable）。它通过 `AsyncSequence` 来实现观察，配合 Swift Concurrency 的能力，在第一次触发 `willSet` 时启动一个“事务”，在这个事务结束并达到一致性状态时，再通过异步序列发出一个值（事件）。

[SE-0476](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0476-abi-attr.md "SE-0476") **控制函数、初始化式、属性或下标的 ABI** 提案正在审查。

建议引入 `@abi` 属性，它提供了用于名称修改的声明的替代版本。该特性将允许 abi 稳定库的开发人员进行微小的更改，例如更改参数的可发送性或重命名声明（只要以向后部署的方式保留源代码兼容性），而不需要深入了解编译器实现细节。

## Swift论坛

1) 提议[Swift 对 WebAssembly 支持的愿景](https://forums.swift.org/t/pitch-a-vision-for-webassembly-support-in-swift/79060 "Swift 对 WebAssembly 支持的愿景")

该提案由 Swift 团队成员提出，旨在描绘 Swift 支持 WebAssembly（Wasm）的一种长远蓝图，并鼓励社区就 Swift 在这一新兴生态系统中的角色展开讨论。

背景与动机：

WebAssembly 是一种为可移植性、高性能和安全性而设计的中间语言，已经从仅限于浏览器的运行环境扩展到服务器端、边缘计算、插件系统等领域。Swift 作为一种强大、安全的编程语言，其扩展到 WebAssembly 平台将带来以下优势：

- 实现真正的跨平台支持（包括网页、嵌入式、服务器）
- 拓展 Swift 在插件和工具链开发中的适用性
- 为 Swift 提供在现代模块化系统（如组件模型）中的定位

愿景目标概述：

- 支持WASI（WebAssembly System Interface）：这是一个标准化的系统接口，使 Wasm 模块可以安全地访问文件系统、环境变量等资源。Swift 需要在编译器、标准库等层面支持 WASI ABI。
- 优化Swift编译器以生成高效的Wasm代码：例如处理内存布局、优化函数调用、错误处理等。
- 实现“组件模型”支持：组件模型是 Wasm 的新兴标准，它支持模块组合、语言间互操作、强类型接口等。Swift 若能导出/导入组件，将极大提高其在多语言系统中的整合能力。
- 支持Swift包管理器（SwiftPM）构建Wasm目标：使开发者可以像为其他平台构建 Swift 包一样，为 Wasm 构建目标，简化开发流程。
- 开发者体验的提升：例如提供更好的错误信息、调试支持、工具链集成（如Xcode、LLDB调试器）等。

潜在应用场景：

- 将 Swift 代码编译为 Web 应用中的 WebAssembly 模块
- 使用 Swift 编写插件，在宿主应用（如使用 Wasm 的文本编辑器、IDE 等）中加载执行
- 在构建工具或 DevOps 工具中使用 Swift 写任务脚本，并部署在 Wasm 虚拟环境中执行（确保隔离性与安全性）

现有工作基础：

- Swift 已能通过 SwiftWasm 项目编译为 Wasm，并有早期 WASI 支持；
- SwiftPM 和标准库的模块化为组件模型的未来集成奠定了基础；
- Swift 编译器的多目标架构已为添加 Wasm 后端提供技术可能。

呼吁与未来方向：
作者呼吁社区参与进来，共同推动 Swift 对 Wasm 的支持，例如贡献提案、工具、反馈使用场景。官方团队计划逐步完善底层支持，并探索 Swift 在 Wasm 组件生态中的角色。

2) 提议[简化 Swift 中抛出和异步函数的影响](https://forums.swift.org/t/pitch-simplifying-effects-of-throwing-and-asynchronous-functions/78996 "简化 Swift 中抛出和异步函数的影响")

提出了在 Swift 中引入新的关键字，以简化同时具有抛出（throws）和异步（async）效果的函数的声明和调用。具体而言，建议引入以下关键字：

- trawait：作为 `try await` 的简写，用于调用可能抛出错误的异步函数。
- thrasync：作为 `async throws` 的简写，用于声明既异步又可能抛出错误的函数。
- rethrasync：作为 `async rethrows` 的简写，用于声明异步函数，其错误由调用者处理。

这些新关键字旨在提高代码的可读性和一致性，减少开发者在编写和阅读代码时的认知负担。此外，提案还建议在未来的语言模式中，通过启用 `SimplifiedFunctionEffects` 特性标志，逐步弃用现有的 `try await` 和 `async throws` 语法，以推动社区采用更简洁的表达方式。

3) 提议[Swift 中的多生产者单消费者异步通道提案](https://forums.swift.org/t/pitch-multiproducersingleconsumerasyncchannel/78932 "Swift 中的多生产者单消费者异步通道提案")

提出了一个新类型 `MultiProducerSingleConsumerAsyncChannel<Element>`（简称 MPSC 通道），旨在提供一种强大、灵活且类型安全的异步通信机制，用于多个生产者发送数据到单个消费者，支持背压控制、资源管理以及高并发。

提案背景

目前 Swift 的 AsyncStream 和 AsyncChannel 等类型虽然支持异步流处理，但：

- AsyncStream 的生产者接口 (AsyncStream.Continuation) 通常只允许一个生产者；
- 缺乏清晰的“所有权”语义（谁负责关闭流、处理终止等）；
- 不支持精细控制的缓冲机制或背压策略；
- 不利于构建多个生产者协同向同一消费者发送数据的场景。

因此，提出一种 支持多个生产者、单个消费者、具备完整生命周期管理和缓冲控制的异步通道 类型，类似于 Rust 中的 mpsc、Kotlin 的 Channel 或 Swift Concurrency 未来规划的 AsyncChannel。

核心结构与功能

声明方式：

```swift
let (consumer, producer) = MultiProducerSingleConsumerAsyncChannel.makeChannel(
    Element.self,
    buffering: .bounded(max: 10)
)
```
支持三种缓冲方式：

- `.bounded(max: N)`：固定大小缓冲；
- `.unbounded(initial: N)`：初始容量后自动增长；
- `.byEstimatedBytes(max: N)`：根据估算内存字节数控制背压。

Producer 接口

```swift
await producer.send("value") // 异步发送一个值
await producer.finish()      // 终止发送
```

支持并发使用、取消时抛出错误。

Consumer 接口

```swift
for await value in consumer {
  print("received:", value)
}
```

支持迭代、手动消费、提前终止。

示例代码

多个生产者：

```swift
let (consumer, producer) = MultiProducerSingleConsumerAsyncChannel.makeChannel(Int.self)

Task {
  for i in 0..<10 {
    await producer.send(i)
  }
}

Task {
  for i in 100..<110 {
    await producer.send(i)
  }
}

Task {
  for await val in consumer {
    print("Got value:", val)
  }
}
```

带缓冲控制：

```swift
let (consumer, producer) = MultiProducerSingleConsumerAsyncChannel.makeChannel(
    Int.self,
    buffering: .byEstimatedBytes(max: 1024 * 1024)
)
```

**生命周期管理**

- 消费者取消时生产者会收到 `CancellationError`；
- 所有生产者关闭后消费者自动完成；
- 支持作用域自动清理。


**应用场景**

- UI 多源事件整合；
- 网络数据流合并；
- 多任务数据采集系统；
- Actor 模型消息管道。


**总结**

这个提案为 Swift 并发系统引入了关键的通信构建块，能够以类型安全、可控的方式连接多个生产者与一个消费者，具备丰富的缓冲策略与生命周期管理能力。

4) 讨论[Xcode 16.3 中无法在异步函数中使用 FileManager 的 enumerator(at:) 的 makeIterator 方法](https://forums.swift.org/t/xcode-16-3-cant-use-makeiterator-via-filemanagers-enumerator-at-in-async-function/78976 "Xcode 16.3 中无法在异步函数中使用 FileManager 的 enumerator(at:) 的 makeIterator 方法")

在 Xcode 16.3 中，开发者发现无法在异步函数中使用 FileManager 的 `enumerator(at:)` 方法返回的 `DirectoryEnumerator` 的 `makeIterator` 方法。这是由于 `NSEnumerator` 的 `Sequence` 遵循在 Swift Concurrency 中被标记为不兼容，导致在异步上下文中使用时编译器报错。

**问题背景**

开发者在使用自定义执行器的 Actor 中调用 FileManager 的 `enumerator(at:)` 方法，并在异步函数中使用其返回的 DirectoryEnumerator 进行目录遍历。然而，升级到 Xcode 16.3 后，编译器报错，提示无法在异步上下文中使用 makeIterator 方法。

**技术分析**

在 Swift 5.10 中，NSEnumerator 的 Sequence 遵循被标记为 `@available(*, noasync)`，意味着其 makeIterator 方法在异步上下文中不可用。此外，NSEnumerator 也被标记为 `@unchecked Sendable`，进一步限制了其在并发环境中的使用。这导致在异步函数中直接使用 `DirectoryEnumerator` 的 `makeIterator` 方法会导致编译错误。

解决方案

为了绕过这一限制，开发者可以创建一个自定义的 Sequence 类型，手动包装 `DirectoryEnumerator`，并实现自己的迭代器，从而避免直接调用被标记为 noasync 的 makeIterator 方法。

示例代码：自定义迭代器

```swift
struct DirectoryIterator: Sequence {
    let enumerator: FileManager.DirectoryEnumerator

    func makeIterator() -> AnyIterator<Any> {
        AnyIterator {
            enumerator.nextObject()
        }
    }
}

await Task {
    guard let enumerator = FileManager.default
        .enumerator(at: .applicationDirectory,
                    includingPropertiesForKeys: [.pathKey],
                    options: .skipsSubdirectoryDescendants) else { return }

    for case let path as URL in DirectoryIterator(enumerator: enumerator) {
        print(path)
    }
}.value
```

通过这种方式，编译器不再将 makeIterator 识别为异步上下文中的调用，从而避免了编译错误。

简化方法：使用类型擦除

另一种更简洁的方法是利用类型擦除，将 enumerator 包装为 AnySequence，从而避免直接调用 makeIterator：

```swift
for case let path as URL in AnySequence(enumerator) {
    print(path)
}
```

这种方法同样可以绕过编译器的限制，且代码更为简洁。

**注意事项**

虽然上述方法可以绕过编译器的限制，但需要注意的是，这些方法并未解决 NSEnumerator 在并发环境中的潜在线程安全问题。因此，在使用这些方法时，仍需确保在适当的线程或队列中执行，以避免潜在的并发问题。

**总结**

在 Xcode 16.3 中，NSEnumerator 的 Sequence 遵循被标记为不兼容 Swift Concurrency，导致在异步函数中使用 FileManager 的 `enumerator(at:)` 方法时出现编译错误。通过自定义迭代器或使用类型擦除的方式，可以绕过这一限制，实现目录的异步遍历。然而，开发者仍需注意潜在的线程安全问题，确保在适当的上下文中使用这些方法

5) 讨论[泛型函数中的 Typed throws 不推断错误类型](https://forums.swift.org/t/typed-throws-do-not-infer-type-in-generic-type-throwing-functions/79036 "泛型函数中的 Typed throws 不推断错误类型")

在 Swift 中，开发者发现当使用泛型函数并指定 throws 的错误类型时，编译器并不会自动推断闭包中抛出的错误类型，导致类型不匹配的编译错误。

**问题背景**

开发者尝试定义一个泛型函数 `withSingleTaskInThrowingTaskGroup`，该函数接受一个抛出特定错误类型的异步闭包，并期望整个函数只抛出该特定错误类型。然而，在使用该函数时，编译器报错，提示抛出的表达式类型为 any Error，无法转换为指定的错误类型。

**技术分析**

在 Swift 6 模式下，编译器不会自动推断闭包中抛出的错误类型，除非在闭包签名中显式指定 throws(特定错误类型)。这意味着，如果在闭包中使用 throw 抛出错误，但未在闭包签名中指定错误类型，编译器会将其视为抛出 any Error，从而导致类型不匹配的编译错误。 

**解决方案**

为了避免编译错误，开发者需要在闭包签名中显式指定抛出的错误类型。例如：

```swift
struct E: Error {}

func f() async throws(E) {
    try await withSingleTaskInThrowingTaskGroup(cancellationError: E()) {
        () throws(E) in
        throw E()
    }
}
```

在上述代码中，通过在闭包签名中指定 throws(E)，编译器能够正确推断闭包中抛出的错误类型，从而避免类型不匹配的编译错误。

**注意事项**

需要注意的是，即使在函数签名中指定了抛出的错误类型，如果在闭包中未显式指定错误类型，编译器仍然无法推断出正确的错误类型。因此，建议在使用泛型函数并指定 throws 的错误类型时，始终在闭包签名中显式指定错误类型，以确保类型一致性。

**总结**

在 Swift 中，使用泛型函数并指定 throws 的错误类型时，编译器不会自动推断闭包中抛出的错误类型。为了避免类型不匹配的编译错误，开发者应在闭包签名中显式指定抛出的错误类型。

## 推荐博文

[与“神”对话：Swift 语言在 2025 中的云霓之望](https://blog.csdn.net/mydo/article/details/145218947 "与“神”对话：Swift 语言在 2025 中的云霓之望")

**摘要：** 本文以与“神”（乔布斯）的灵魂对话为背景，探讨了 Swift 语言在 2025 年的发展前景。首先指出 Swift 虽为苹果生态明珠，但存在编译器不稳定、学习曲线高、生态不完善等不足。接着从核心语言进化、核心框架发展、与人工智能深度结合、生态融合四个方面阐述其未来突破方向。

核心语言将在性能优化、语法友好性、跨平台能力上提升；SwiftUI 和 SwiftData 会更智能；Swift 与 AI 结合将带来更智能开发体验、框架 AI 化及推动边缘计算；生态融合方面会与新硬件更好结合、无缝连接云服务并提升学习与社区支持。最后强调 Swift 未来在于让开发者专注创造，承载通往新科技时代的希望。

[Swift 与 Objective-C 的桥梁：深入解析类型桥接机制](https://juejin.cn/post/7485647396867178515?searchId=202504131651504CB8E7FFB901B839FA9C "Swift 与 Objective-C 的桥梁：深入解析类型桥接机制")

**摘要：** 本文深入解析 Swift 与 Objective - C 的类型桥接机制。首先阐述桥接核心原理，包括类型兼容性设计，基于 Swift 标准库部分类型实现的 `_ObjectiveCBridgeable` 协议，以及编译器自动插入桥接代码，介绍桥接的自动、手动、强制三种形态。接着讲述桥接具体实现，涵盖 Swift 与 Objective - C 间 Array 与 NSArray、String 与 NSString、Dictionary 与 NSDictionary 的转换方式。还提及桥接背后的编译器与运行时作用，如编译器通过 `_ObjectiveCBridgeable` 协议插入代码，运行时进行双向翻译。在底层机制方面，探讨内存管理（值类型桥接生成不可变对象，引用类型桥接可能深拷贝）和性能优化（零开销桥接、延迟拷贝、桥接缓存）。

同时指出桥接存在类型兼容性限制（元素类型需可桥接、泛型不兼容）和可变性差异（不可变桥接、可变对象需显式转换）。最后通过全景图对比 Swift 与 Objective - C 桥接在转换方式、内存影响、性能损耗、类型安全和典型应用场景等维度的差异，总结强调开发者虽无需手动处理桥接，但要留意相关要点以避免运行时错误。

[大前端：如何突破动态化容器的天花板？](https://tech.meituan.com/2024/10/18/recce-in-meituan.html "大前端：如何突破动态化容器的天花板？")

**摘要：** 本文源自美团技术沙龙第 83 期《前端新动向》，探讨如何突破动态化容器的性能天花板。首先介绍动态化容器虽解决研发成本和部署效率问题，但存在页面成功率低、牺牲用户体验等弊端，且性能受限于逻辑解释器执行与通信效率。美团金服大前端团队打造的 Recce 容器取得性能提升成果。接着阐述容器分类及前期思考，包括按绘制方式分类和结构分解。

然后详细介绍 Recce 的选型与搭建，涵盖解释器&编程语言、UI 框架、渲染层和整体架构的选择。之后说明 Recce 的一些细节问题，如属性转换、跨语言调用等解决方案。最后总结 Recce 是高性能、安全的动态化容器，回望其围绕渲染管线优化，展望未来将改善开发体验、进一步优化性能、自研渲染层等，并解答了关于 Recce 性能、JS 作用、命名由来及追求原生级性能原因等常见问题。


## 话题讨论

**“明明没搬砖，为何总像被掏空？”——现在的年轻人为什么总是喊累？**  

根据你的生活感受，你觉得以下哪种原因最能解释这种疲惫感？  

1. 工作压力太大：加班多、工资低，越努力越焦虑？
2. 休息方式不对：熬夜刷手机，越玩越累？
3. 社交消耗太多：朋友圈点赞、微信群回复，人情世故成负担？
4. 生活没目标：卷不动又躺不平，干啥都没劲？ 

欢迎在评论区留言讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
