## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百零一期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

也许走遍了全世界，最后才会发现，美丽的风景就在你我的脸颊，让嘴角微微上扬，便收获了最灿烂的笑容。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：iOS 27爆料：苹果“彻底重做”Siri，系统级整合AI
> * **提案**：
> * **Swift 论坛**：
> * **推荐博文**：

上期话题投票结果如下：



## 话题讨论

### 本期话题：


欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### iOS 27爆料：苹果“彻底重做”Siri，系统级整合AI

*2026 年 5 月 29 日｜来源：华尔街见闻*

苹果公司“彻底重做”Siri，将其从一款语音助手升级为具备多模态交互能力的 AI 平台。

据彭博援引知情人士透露，苹果计划在 6 月 8 日的全球开发者大会（WWDC）上发布 iOS 27。

核心内容包括：重新设计的 Siri 界面、引入谷歌 Gemini 技术的全新底层模型、AI 驱动的网页搜索功能，以及一款对标 ChatGPT 的独立 Siri 应用。

此次更新是 Siri 近 15 年历史上规模最大的一次重构，预计最早于 9 月面向消费者推出，恰逢苹果秋季 iPhone 18 Pro 系列及首款折叠屏 iPhone 发布之前。

华尔街见闻提及，本周美银证券分析师 Wamsi Mohan 将苹果目标价从 330 美元大幅上调至 380 美元，全新 Siri 到 2030 年或带来最高 650 亿美元增量收入。

此次 AI 功能的成败，将直接影响消费者对新硬件的购买意愿，以及苹果在与 OpenAI、谷歌和三星的竞争中所处的位置。

这可能是 CEO 蒂姆·库克（Tim Cook）的最后一次重大发布，

此后他将把领导权移交给 John Ternus。

Siri 全面重建，从语音助手到系统级执行层

苹果重新设计了 Siri 的交互入口，使其深度融入 iPhone 硬件架构。

新版 Siri 将以"常驻代理"的形式内嵌于灵动岛，届时全新 Siri 可随时调用设备上的个人数据、网页内容及屏幕信息完成任务。

苹果为新 Siri 设计了两种启动方式。传统方式，呼唤"Siri"或长按电源键，将触发灵动岛内的全新动画效果，适合语音查询和搜索场景。

![](https://pics7.baidu.com/feed/c2cec3fdfc0392451ae43b12d6a165d37d1e2525.jpeg@f_auto?token=b9c48dcd87001aab6c58bdfb0c13f726)

另一种全新方式则允许用户从屏幕顶部中央向下滑动，随时唤出新的"搜索或提问"界面，支持打字和语音双模操作，可直接启动应用、发送消息、查询天气、添加日历、搜索备忘录，或调用苹果新的 AI 网页搜索系统。

通知中心入口则相应调整至屏幕左上角下滑触发。

苹果还计划首次推出独立 Siri 应用，界面逻辑与 ChatGPT、Claude 等 AI 助手相似，包含对话历史列表、多轮会话界面，以及支持上传文档和图片的附件选择器。用户在 Siri 结果界面继续下滑，即可进入该应用的完整对话视图。

Gemini 技术加持，本地与云端混合推理

新版 Siri 的底层模型经过全面重建，引入谷歌 Gemini 技术，并搭载 AI 驱动的网页搜索能力，可与 Perplexity 等工具形成竞争。

据彭博社援引知情人士，苹果将利用谷歌完整 Gemini 大模型对本地运行的小模型进行蒸馏（distillation），以便在苹果设备上实现本地推理。

然而，由于谷歌完整 Gemini 模型参数规模达到万亿级别，苹果内部的 Private Cloud Compute 基础设施目前难以支撑其完整运行，部分 AI 查询仍需依托谷歌云基础设施处理。

为平衡云端处理与隐私承诺，苹果近期已批准在谷歌云环境中采用英伟达的机密计算（Confidential Compute）技术。

该技术通过加密处理中的数据与模型来保护用户隐私，代价是略微降低云端处理速度。据报道尽管如此，苹果仍可能继续沿用 Private Cloud Compute 的品牌表述。

与此同时，苹果也在积极寻求并购能够帮助其压缩模型体积、实现更充分本地推理的小型公司。据报道援引知情人士透露，专注于设备端 AI 的剑桥初创企业 Liquid AI 是苹果考虑收购的目标之一。

相机与照片应用迎 AI 升级，追赶谷歌等竞争对手

此次升级将 Siri 首次整合进相机应用，作为独立模式与照片、视频并列。

该功能将取代现有的"视觉智能"（Visual Intelligence）体验，支持对拍摄内容进行第三方 AI 分析或谷歌图片反向搜索。

苹果将该入口从现有的相机控制按钮提升至主界面，意在扩大视觉 AI 的使用覆盖面，并为未来的智能眼镜、带摄像头的 AirPods 等产品提前培育用户习惯。

相机应用本身也将迎来可定制化改造，新增"添加小组件"面板，支持用户调整顶部快捷操作栏，将景深调整、计时器、夜间模式等专业控件优先呈现。

在相册应用方面，苹果计划引入重构（Reframe）与拓展（Extend）两项AI工具。

重构（Reframe）可调整照片视角，拓展（Extend）则能借助AI生成图像延伸内容，例如补全原始画面中被截断的建筑下半部分。谷歌等竞争平台已提供类似功能多年。

![](https://pics5.baidu.com/feed/4a36acaf2edda3cc9fec0e7750dcf810213f9220.jpeg@f_auto?token=caabf4eed10e4db1beaf48268ad68483)

估值逻辑：AI 入口价值能否兑现为服务利润

苹果当前的商业模式仍以硬件为核心。

2025 财年，产品收入 3070 亿美元，占总收入约 74%；服务收入 1092 亿美元，占约 26%。但从利润结构看，服务毛利率高达 75.4%，远超产品端的 36.8%，服务业务已贡献约 42% 的总毛利。

这意味着，任何能提升用户服务使用频率与交易频率的入口，对苹果利润结构均具有高度杠杆效应。

美银证券的目标价上调将估值倍数从 32 倍提升至 37 倍 2027 年预期每股收益，依据是苹果在代理式 AI 时代有望重获服务层、交易层与入口层的定价权。

潜在增量收入来源涵盖 Apple Intelligence Pro 订阅、默认模型路由费、App Store 代理式电商抽成、Apple Pay 路由费，以及代理结果中的广告收入。

不过，美银也点明了最大的不确定性：Siri 过去已多次令市场失望，若用户任务习惯已迁移至 ChatGPT、Gemini 或 Claude，苹果虽仍掌控硬件与权限，但可获取的 AI 价值将大幅缩水。

### 苹果加码推进端侧人工智能 发力脱离云端运行模式

*2026 年 5 月 28 日｜来源：新浪财经*

![](https://pics1.baidu.com/feed/241f95cad1c8a786644e409e69aa092c71cf506a.jpeg@f_auto?token=e6d727cd9ce50984b15844051b0fc36d)

下月举行的苹果年度开发者大会上，一系列延期已久的 iPhone 人工智能功能升级将成为重头戏。与此同时，外界预计苹果还将着重亮出其追赶 AI 赛道的一大潜在优势：依托全球海量苹果设备，直接在终端设备上运行 AI 模型。

　　据了解苹果全球开发者大会相关规划的知情人士透露，苹果有望展示其十五年来为 iPhone、苹果手表、Mac 电脑自研定制芯片的技术积累。这一积淀，将成为其在终端设备本地运行 AI 模型的核心优势。而目前主流做法，是在搭载高性能 AI 芯片的大型数据中心中运行 AI 模型，这类设施建设与运营成本高昂。

　　受运算复杂度及海量网络信息调取需求所限，苹果设备发出的不少 AI 指令仍需交由云端处理。例如，根据苹果与谷歌达成的合作协议，新版部分 Siri 指令将依托谷歌云平台、调用谷歌 Gemini 大模型的授权版本运行。另有知情人士称，苹果近期已许可在该场景下使用英伟达的隐私保护技术，这意味着谷歌云内部分算力需求，苹果将采用英伟达 AI 芯片承接。

　　不过，在终端本地运行 AI 模型，既能降低用户数据泄露风险，也能杜绝广告公司利用个人信息牟利。对于企业客户而言，本地运算还能减少令牌使用量、进而降低成本——令牌是云端 AI 服务商计费所依据的文本计量单位。对苹果自身来说，将更多 AI 运算任务下放至终端设备，也得以不必像其他科技巨头那样，在数据中心领域投入巨额资金。

　　知情人士表示，按照双方合作约定，苹果正利用谷歌完整版 Gemini 大模型，通过模型蒸馏技术训练可在苹果设备本地运行的轻量化模型。此外，苹果还在物色可协助其完成 AI 模型轻量化改造、适配终端设备运行的小型企业。有相关策略知情人士透露，总部位于美国马萨诸塞州剑桥市、专注端侧 AI 技术的初创公司 Liquid AI，已进入苹果的收购考察名单。

　　苹果早在 2024 年推出苹果智能（Apple Intelligence） 系列 AI 功能时，就率先宣传过端侧 AI 在隐私保护上的优势。但此后该板块进展趋于沉寂：新 AI 功能市场反响平平，新版 Siri 又再度延期上线，接连出现的问题令苹果处境尴尬。

　　与此同时，各大科技巨头纷纷斥巨资搭建云端 AI 算力体系，苹果却基本置身事外。去年，元宇宙平台公司全年资本开支达 720 亿美元，绝大部分用于数据中心建设；微软资本开支则高达 880 亿美元。而同期苹果的资本开支仅为 127.2 亿美元。

　　苹果在 AI 领域投入保守的做法，一度遭到投资者与行业评论人士诟病。他们认为，在人工智能成为智能终端核心能力的时代，苹果或将就此掉队。如今整个科技行业的 AI 投入规模空前，仅微软今年就预计资本开支达到 1900 亿美元。部分技术从业者反而开始担忧行业盲目堆砌云端算力，也因此对苹果相对审慎的布局思路改观。

　　奥斯汀 AI 初创企业 webAI 首席执行官戴维·斯托特表示：“我认为当下的数据中心投资热潮存在误区。AI 技术正朝着轻量化方向发展，数据中心不会彻底消失，但绝大多数运算任务终将转移至边缘终端。苹果在这一点上押对了方向。”

　　如今越来越多 AI 开发者选择依托苹果硬件创业，斯托特便是其中一员。webAI 主要面向企业开发专属端侧 AI 应用，例如为航空领域打造运维工具：基于波音梦想客机发动机全套维修手册训练 AI 模型，协助工作人员开展发动机检修。

　　这类模型可直接在 iPad 或 Mac 上离线运行，无需联网。苹果设备也受到技术爱好者青睐，不少人用它运行开源工具 OpenClaw，该工具可打造能自主操控电脑的 AI 智能体。

　　阿雷特研究公司科技分析师理查德·克莱默在近期致投资者的研报中估算，全球苹果终端芯片所汇聚的算力规模，相当于一套价值 500 亿美元的算力资源，而这套算力完全由全球用户共同承载。

　　马克·苏曼曾担任苹果高级工程项目经理，2024 年离职前负责公司内部 AI 系统研发。他表示，数十亿台苹果设备整合在一起，本身就是一股强大的 AI 算力。

　　现任初创企业 Maple 联合创始人的苏曼说道：“苹果有能力搭建全球规模最大的边缘计算 AI 体系，只是时间问题，他们迟早会释放这部分潜力。”Maple 主要为用户提供可加密访问云端 AI 模型的服务。

　　当然，苹果的 AI 战略无法完全依靠端侧模型落地。谷歌完整版 Gemini 模型拥有数万亿参数（参数数量是衡量 AI 模型复杂度的重要指标），对算力要求极高。知情人士称，即便苹果自有服务器架构私有云计算（Private Cloud Compute） 采用与 Mac 同款自研芯片，也难以承载完整版 Gemini。

　　多名苹果前工程师认为，新版 Siri 的部分功能，苹果仍需借助谷歌云基础设施运行。即便如此，苹果仍在探索兼顾云端 AI 服务与高阶隐私保护的方案。据双方合作知情人士透露，苹果近期许可在谷歌云内调用英伟达机密计算系统，处理部分基于 Gemini 大模型的复杂运算，正是这类尝试之一。

　　机密计算是英伟达显卡搭载的一项安全技术，可在数据与 AI 模型运算过程中全程加密。启用该功能后，云端 AI 指令的处理速度会略有下降，但能帮助苹果兑现用户隐私保护承诺。

　　苹果最初推出苹果智能功能时曾表态：未在终端本地处理的 AI 指令，将全部交由搭载苹果自研芯片的私有云计算系统处理。如今这一安排出现调整，不过相关人士称，苹果大概率仍会保留“私有云计算”这一品牌名称。

### MacBook Neo面临更大困境：台积电据悉将连续上调3nm制程价格

*2026 年 5 月 28 日｜来源：科创板日报*

5 月 28 日消息，不断告急的芯片产能将进一步威胁到苹果平价电脑 MacBook Neo 的销售计划。有消息称，苹果公司可能正在考虑停产 MacBook Neo 售价为 599 美元的基础款。

MacBook Neo 使用的是苹果制造 iPhone 16 Pro 智能手机时筛选余留下的 A18 Pro 芯片，因此大大降低了这款笔记本电脑的物料成本，使其定价为极具吸引力的 599 美元。

然而，随着 A18 Pro 芯片的耗尽，MacBook Neo 正面临急剧升高的成本。此前消息称，苹果正在向台积电下达新订单以生产更多的 A18 Pro 芯片，但由于台积电半导体产能逼近极限，苹果不得不支付更高价格。

最新一则爆料还称，台积电将在今年下半年对 3 纳米制程的芯片提价 15%，并在明年再次提价 10%。而 A18 Pro 芯片使用的正是台积电的 3 纳米产线，这对苹果来说无疑是雪上加霜。

![](https://pics1.baidu.com/feed/738b4710b912c8fc970ddae260135254d78821c0.jpeg@f_auto?token=8f28e2b1f5785d5a68b7afee3cf01d25)

苹果的困境

据悉，业界指出，台积电 3 纳米制程涨价并非单一客户急单带动，而是整体先进制程供需结构出现根本性变化，英伟达、AMD、谷歌等多家云端服务商正全面加速应用 3 纳米芯片，推高了需求。

供应链还透露，台积电 3 纳米主力工厂 Fab 18 持续高水平运行，客户排队情况依旧严重，但产能看到爬升，从年初的月产能 13 万片上升至第二季度的 16 万至 17.5 万片，但人工智能需求成长速度仍远超市场预期。

这种情况下，苹果想要继续销售 MacBook Neo 就不得不进行提价，以防止本已微薄的利润跌入负值区间。停售基础款 MacBook Neo 相当于涨价 100 美元，这对一款售价为 599 美元的产品来说涨幅相当可观。

上周还有消息称，苹果可能将部分芯片制造业务转交给英特尔，包括下一代 MacBook Neo 使用的 A27 芯片。这可能将帮助苹果摆脱台积电的产能困境，确保即将上市的 MacBook Neo 笔记本电脑能够有充足的供应。

## 提案


## Swift论坛

### 1、`Iterable` 修订提案：从 `BorrowingSequence` 到通用借用迭代

作者：Nate Cook ｜ 发布日期：2026 年 5 月 20 日
[阅读原帖](https://forums.swift.org/t/revision-pitch-iterable-formerly-borrowingsequence/86834 "[Revision/Pitch] Iterable (formerly BorrowingSequence)")

核心内容：SE-0516 的修订版将原来的 **BorrowingSequence** 重命名为 **Iterable**，目标是为同步迭代提供一个更通用的协议基础。新协议允许类型本身、元素类型和迭代器是 **noncopyable** 或 **nonescapable**，并且支持在迭代过程中抛出具体错误类型。

动机说明：现有 **Sequence** 诞生较早，默认围绕可复制元素和 `IteratorProtocol.next() -> Element?` 建模，难以自然表达 **Span**、**InlineArray** 以及非复制元素的借用式遍历。提案希望通过按批返回 `Span<Element>`，减少复制需求，并让连续内存场景有更好的优化空间。

主要修改包括：协议名改为 **Iterable**；迭代器协议改为 **IterableIteratorProtocol**；新增 `Failure: Error = Never` 关联类型；核心入口从 `makeIterator()` 变为 `makeIterableIterator()`，迭代器通过 `nextSpan(maximumCount:)` 返回一段元素。

```swift
public protocol Iterable<Element, Failure>: ~Copyable, ~Escapable {
  associatedtype Element: ~Copyable
  associatedtype Failure: Error = Never
  associatedtype IterableIterator: IterableIteratorProtocol<Element, Failure>

  @_lifetime(borrow self)
  func makeIterableIterator() -> IterableIterator
}
```

讨论亮点集中在 **for-in** 如何对 **Iterable** 进行语法脱糖、抛错迭代是否需要 `for try`、以及泛型算法在元素生命周期受限时能否实现类似 `first(where:)`、`elementsEqual` 等操作。简要点评：这是一项面向 Swift 所有权模型长期演进的基础设施改造，短期会增加标准库协议层复杂度，但能为 **Span**、**~Copyable** 和高性能容器打开更自然的迭代接口。

### 2、用 `Disconnected` 在类型系统中表达断开隔离的值

作者：Franz Busch ｜ 发布日期：2026 年 5 月 19 日
[阅读原帖](https://forums.swift.org/t/pitch-disconnected-type-for-modeling-disconnected-values/86815 "[Pitch] Disconnected type for modeling disconnected values")

核心内容：该 pitch 提议在标准库中加入 **Disconnected<Value>**，用于把一个值标记为处于断开隔离区域，从而在容器、队列等数据结构中保存并传递这种属性。它尤其面向 **region-based isolation**、**sending** 和非 **Sendable** 值跨隔离域转移的场景。

动机说明：SE-0414 和 SE-0430 让函数边界可以要求或返回 `sending` 值，但 `sending` 是函数签名属性，无法被普通存储属性、集合或泛型容器长期保留。例如一个队列既可能存储普通非 **Sendable** 值，也可能存储可跨隔离域移动的断开值，直接把容器 API 都改成 `sending` 会限制其他合法用法。

提案中的包装类型大致如下：

```swift
@frozen
public struct Disconnected<Value: ~Copyable>: ~Copyable, Sendable {
  public init(_ value: consuming sending Value)
  public var value: Value { borrow }
  public consuming func take() -> sending Value
}
```

使用时，容器保存的是 `Disconnected<NonSendable>`，取出后通过 `take()` 消费包装并得到 `sending` 值，再把它移动到新的任务或隔离区域。

讨论亮点在于：`Disconnected` 无条件符合 **Sendable** 是否足够直观、借用访问器 `value` 如何维持断开不变量、以及它与 SE-0519 的容器借用访问器如何组合。简要点评：这个类型把并发隔离中的一个隐含状态显式建模，对编写异步算法和通用容器很有价值，但它也要求开发者更准确地区分“值可发送”和“值已断开”这两层语义。

### 3、SE-0531：Literal Expressions 进入审查

作者：Ben Cohen ｜ 发布日期：2026 年 5 月 19 日
[阅读原帖](https://forums.swift.org/t/se-0531-literal-expressions/86794 "SE-0531: Literal Expressions")

核心内容：SE-0531 进入正式审查，审查期为 2026 年 5 月 19 日至 5 月 29 日。提案引入 **Literal Expressions**，允许编译器在特定上下文中对整数文字、标准库整数运算符以及可编译期求值的整数常量引用进行常量折叠。

动机说明：当前 **enum raw values**、`@section` 变量初始化和 **integer generic arguments** 等位置往往只能写裸整数，开发者需要手工计算并维护“魔法数字”。提案希望让意图直接保留在源码中，例如页大小、位标志和 `InlineArray` 长度都可以由表达式推导。

典型示例如下：

```swift
let pageSize = 4 * 1024
let bufferSize = 16 * pageSize

enum Permissions: Int {
  case read = 1 << 0
  case write = 1 << 1
  case execute = 1 << 2
}

let buffer: InlineArray<(2 * pageSize), UInt8>
```

主要限制是：表达式结果必须是标准库整数类型；支持算术、位运算、移位和部分一元运算；用户自定义运算符不会被当作 literal expression；公开可见常量引用暂不允许参与折叠，以避免把初始化表达式变成 ABI 承诺。

讨论亮点包括 Jordan Rose 对“literal expressions”命名的质疑，认为该特性更像受限的编译期整数表达式；也有人建议称为 **Integer Literal Expressions**。简要点评：这项改动非常务实，能明显改善底层、嵌入式和泛型值参数代码的可读性；争议主要不在能力本身，而在命名和未来扩展边界。

### 4、SE-0526 第二轮审查：`withDeadline` 简化错误与取消语义

作者：Frederick Kellison-Linn ｜ 发布日期：2026 年 5 月 18 日
[阅读原帖](https://forums.swift.org/t/second-review-se-0526-withdeadline/86791 "[Second Review] SE-0526: withDeadline")

核心内容：SE-0526 **withDeadline** 开启第二轮审查，审查期至 2026 年 5 月 31 日。该 API 为异步操作提供基于绝对时间点的截止期限，过期时取消操作，并按照操作自身的返回或抛错结果继续传播。

动机说明：手写超时逻辑通常需要任务组、时钟 sleep、取消传播和竞态处理，代码冗长且难以组合。使用绝对 **deadline** 而不是相对 timeout，可以让多层调用共享同一个截止时刻，避免时间在调用链中逐层漂移。

本轮修订删除了 `Task.currentDeadline`，移除了跨时钟 deadline 组合约束，取消了包装用的 `DeadlineError`，改为直接转发 body 抛出的错误；同时 **CancellationError** 增加 `reason`，用于在 deadline 过期触发取消时携带原因。

```swift
let clock = ContinuousClock()
let deadline = clock.now.advanced(by: .seconds(5))

let result = try await withDeadline(deadline, clock: clock) {
  try await fetchDataFromServer()
}
```

讨论亮点包括：`withDeadline` 命名是否足够准确、`throws(Failure)` 与取消错误的关系、`CancellationError.reason` 的精确定义，以及 `custom(String)` 是否会带来额外成本或滥用空间。简要点评：第二轮修订明显收敛了 API 表面，错误传播更符合 Swift 的类型化错误方向；剩余关键问题是取消原因的模型需要足够严谨，否则会影响并发运行时的实现和使用预期。

### 5、Typed throws 下 `rethrows` 不能保留具体错误类型的讨论

作者：Tiago Canto ｜ 发布日期：2026 年 5 月 20 日
[阅读原帖](https://forums.swift.org/t/rethrows-does-not-seem-to-work-correctly-with-typed-throws/86843 "Rethrows does not seem to work correctly with typed throws")

核心内容：帖子讨论 **typed throws** 与 **rethrows** 的交互。发帖者发现一个 `transaction(operation:) rethrows` 包装函数虽然只调用传入闭包，但编译器并不会把闭包的具体错误类型 `DatabaseError` 保留下来。

原始示例中，`transaction` 的闭包声明为 `() throws(DatabaseError) -> Void`，但函数本身使用 `rethrows`：

```swift
struct Database {
  func transaction(operation: () throws(DatabaseError) -> Void) rethrows {
    try operation()
  }

  func saveUser() throws(DatabaseError) {
    try transaction {
      throw .connectionLost
    }
  }
}
```

讨论中指出，`rethrows` 只表达“只有当参数抛错时才抛错”，并不承诺“抛出同一种错误”。在 **typed throws** 可用后，更推荐把错误类型写成泛型参数，并让函数显式 `throws(E)`。

```swift
func transaction<E>(
  operation: () throws(E) -> Void
) throws(E) {
  try operation()
}
```

讨论亮点来自 Slava Pestov 的说明：有了 **typed throws** 后，许多 `rethrows` 场景可以改为泛型 `throws(E)`，其中 `Never` 也符合 `Error`，可表示非抛错路径。但后续回复也指出，可选闭包默认值、错误类型推断和“只有回调抛错时才改抛另一种错误”等场景仍让 `rethrows` 有残余价值。简要点评：这次讨论很好地澄清了 `rethrows` 的语义边界，也提醒库作者在迁移到 **typed throws** 时不要机械替换，而要检查错误类型推断和默认参数对调用体验的影响。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[一个偶发性测试失败，揭开了 Swift 并发调度的真相](https://www.swift.org/blog/whats-new-in-swift-january-2026/ "i一个偶发性测试失败，揭开了 Swift 并发调度的真相")

**摘要：** 这篇深度技术文章从一个令人困扰的偶发性测试失败案例入手，逐步揭示了 Swift 现代并发模型中任务、Actor 与执行器之间的微妙关系。作者指出，为支持 debounce 行为而编写一个 MockClock 看似简单，但如果忽略了执行上下文的差异，测试结果会变得难以预测。文章通过调试过程逐一拆解了多个关键概念： nonisolated async 函数会跳离调用者 Actor ； Task.yield() 只让出当前执行器而非全部； isolated 参数配合#isolation可以让工具函数“随调用者运行”而无需跳转执行器。文章的价值不在于教会读者如何实现一个测试用 Clock ，而在于它清晰地展示了 Swift 并发调度中那些容易忽略却至关重要的底层细节。全文为希望真正理解而非仅仅使用 Swift 并发的开发者提供了一份极具启发性的深度剖析。

[将300个界面迁移到 SwiftUI 后所学到的]( https://iosdevweekly.com/issues/751/ "将300个界面迁移到 SwiftUI 后所学到的")

**摘要：** 这篇来自 Artem Mirzabekian 工程团队的迁移实战复盘，记录了将一个包含300个界面的应用从 UIKit 逐步迁移到 SwiftUI 的完整历程与经验教训。文章指出，团队并没有选择“一刀切”式的彻底重写，而是采取了极为克制的分层策略：SwiftUI 只负责 UI 构建，导航依然保留在UIKit层面。这种选择并非技术妥协，而是有意为之——让团队在享受 SwiftUI 布局与组件复用优势的同时，避免在导航栈管理、深层链接和复杂流程控制上引入不必要的风险。文章详细梳理了迁移过程中反复出现的典型问题：开发者习惯了命令式思维，常把 SwiftUI 当作“语法不同的 UIKit ”来写；在 body 中夹带副作用、将 onAppear 当作v iewDidLoad 使用、嵌套ObservableObject 导致状态传播不如预期。经过持续的代码审查与内部工作坊，团队最终沉淀出一套清晰的架构方向：MVVM + 枚举驱动的状态与交互建模 + Use Case 分离业务逻辑。这篇博客为正在规划或正在进行 SwiftUI 迁移的团队提供了极具参考价值的实战指引。

[用 Swift 手写 LLM 训练内核（第一部分）：将矩阵乘法从 Gflop/s 优化到 Tflop/s ]( https://iosdevweekly.com/issues/751 "用 Swift 手写 LLM 训练内核（第一部分）：将矩阵乘法从 Gflop/s 优化到 Tflop/s ]")

**摘要：** 这篇来自 Matt Gallagher 的硬核性能探索文章，在 Swift 中从零开始手写矩阵乘法，通过一系列系统级优化将基础实现的性能从2.8 Gflop/s 一路提升至1.1 Tflop/s。文章通过一个完整的优化迭代过程，展示了高性能 Swift 的现实面貌： Swift 并非天生不够快，但当你逐渐逼近硬件极限时，将不可避免地进入 UnsafeBufferPointer、SIMD 指令、并发切片、内存布局与 GPU tile 优化等底层领域。作者详细阐述了每个优化阶段的关键技术——从编译器优化选项调整、循环展开、向量化，到利用 Swift 6.2 引入的 Span 和 InlineArray 实现零开销内存访问，再到与 Metal shader 协同利用 GPU 算力。文章同时反复强调，生产环境应优先使用Accelerate、BNNS、CoreML、MPSGraph 等成熟框架，手写优化仅适用于理解底层原理或在极端场景下突破框架限制。全文为追求极致性能的 Swift 开发者提供了一份从语言特性到硬件能力的完整优化路线图。


## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
