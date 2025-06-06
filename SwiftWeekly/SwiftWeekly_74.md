## 前言

**本期是 Swift 编辑组自主整理周报的第七十四期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

以前我一直在躲、在藏，直到无路可走，我才明白该如何面对这个世界。**Swift社区**，真的勇士，敢于直面惨淡的人生，敢于正视淋漓的鲜血。👊👊👊

> **周报精选**
>
> 新闻和社区：库克：苹果将持续加大在华投入！他还称是《哪吒2》忠实观众
> 
> 提案：Clock Epochs 提案正在审查。
> 
> Swift 论坛：讨论序列化和反序列化 API 的未来
>
> 推荐博文：苹果设备端与服务器基础模型介绍
>
> **话题讨论：** 
> 
> AI 的迅速发展，曾经的科幻电影离我们已不再遥远，今天我们来聊一下人类世界的未来，你认为以下哪种结果更会最先降临地球？
>
>**上期话题结果**

![](https://files.mdnice.com/user/47553/a5d7420c-1a42-4bf2-926f-a5db7bc0ac8e.jpg)

投票结果与我私下与朋友沟通的反馈结果一致，看来大多数朋友的想法都是相同的。

## 新闻和社区  

### 消息称苹果未来两年无推出小屏iPhone计划 专注6英寸以上机型

2025 年 3 月 29 日

相关爆料称苹果公司目前没有计划推出屏幕尺寸小于 6 英寸的 iPhone 新机型。苹果公司已于 2023 年 9 月停产了 5.4 英寸的 iPhone 13 mini，这款手机成为了苹果旗下最后一款小屏旗舰。此后，苹果的产品策略发生了明显转变，专注于 6 英寸以上的大屏手机。

![](https://zkres1.myzaker.com/202503/67e6cc508e9f094f9e52b151_1024.jpg)

此外，第三代 iPhone SE 也于 2025 年 2 月正式下架，这标志着苹果公司彻底停止销售小屏新机。内部消息人士表示，未来两年内，苹果将不会推出任何 mini 机型。

小屏 iPhone 市场表现不佳是苹果作出这一决策的主要原因。iPhone 12 mini和 iPhone 13 mini 两款机型尽管硬件配置与其他机型相同，但由于续航能力较差且不支持双卡功能，导致销量不佳。

鉴于 mini 机型的市场反馈，苹果从 iPhone 14 系列开始，用 Plus 机型替代了原有的 mini 产品线。据悉，今年苹果还将推出全新的 Air 机型，以取代 Plus 机型，进一步丰富产品线。(来源：太平洋电脑网)

### 消息称欧盟拟对苹果和Meta处以最低罚款，避免与美国加剧紧张关系

2025 年 3 月 28 日

3 月 28 日消息，据英国金融时报报道，欧盟计划下周根据《数字市场法》对苹果和脸书母公司 Meta 处以最低限度的罚款，以避免与美国总统特朗普加剧紧张关系。

![](https://pics7.baidu.com/feed/d058ccbf6c81800a8a65652d15f9a8f5838b4769.jpeg@f_auto?token=b1f6ac13bc8a4711062990f8b1c9ff40)

据知情人士透露，苹果公司预计将因 App Store 规则问题被罚款，并被要求修改相关规则。此前，欧盟曾调查这些规则是否限制了应用程序开发者将消费者引导至其平台之外进行购买或获取优惠。此外，欧盟还将结束另一项针对苹果的调查，该调查聚焦于苹果网络浏览器选择界面的设计，且不会再对苹果施加进一步的制裁。

Meta 也将面临罚款，并被要求改变其“付费或同意”的模式，该模式要求用户要么同意数据追踪，要么支付订阅费以获得无广告的产品体验。

根据《数字市场法》，相关公司可能面临高达其全球营业额 10% 的罚款，这意味着苹果和 Meta 可能面临数十亿美元的罚款。然而，据三位官员表示，欧盟委员会计划将罚款金额控制在远低于这一上限的水平，因为欧盟的数字法规相对较新，且相关决定仍可能在法庭上受到挑战。

欧盟委员会的这一举措旨在执行《数字市场法》，该法案旨在遏制科技巨头在数字市场的主导地位，同时避免与美国政府发生直接冲突。新上任的委员会自去年 12 月开始工作，其重点更多地放在确保大型科技公司遵守法律，而不是处以巨额罚款。

此外，欧盟监管机构计划撤销一项关于苹果操作系统是否阻碍用户更换浏览器或搜索引擎的案件，因为苹果已做出一系列调整，以符合欧盟的相关规则。

然而，对美国科技公司处以任何形式的罚款都可能引发反弹。特朗普曾直接抨击欧盟对美国公司的罚款，称其为“一种税收”，并将对科技公司的罚款比作“海外敲诈”。

此前，特朗普曾警告称，将对征收数字服务税的国家实施关税。根据上个月发布的一份备忘录，特朗普表示，他将审视那些“阻碍”美国公司海外业务增长的税收、法规或政策。

Meta 此前曾表示，其做出的调整“满足了欧盟监管机构的要求，并且超出了欧盟法律所要求的范围”。

据官员透露，这些计划中的决定在公布前仍有可能发生变化，预计将于周五提交给欧盟 27 个成员国的代表审议，而罚款的正式公告预计将在下周发布，不过这一时间表也仍有可能调整。（来源：IT之家）

### 稳链、培新、逐绿——苹果公司坚定“深耕中国”

2025 年 3 月 28 日

![](https://pics1.baidu.com/feed/cb8065380cd79123fec0d1265bf0c28db3b78090.jpeg@f_auto?token=01312659f5d897471658a2b13fd2d458)

2024 年，在第二届链博会数字科技链展区，美国苹果公司精选 4 家中国供应商携手亮相展台。

新华社北京 3 月 26 日电 题：稳链、培新、逐绿——苹果公司坚定“深耕中国”

新华社记者
“中国供应商正推动智能制造和绿色制造取得世界级进步。”苹果公司首席运营官杰夫·威廉姆斯日前在参观位于山东省潍坊市的歌尔股份有限公司时说，这里高度自动化的生产线和精密制造水平令其印象深刻。

歌尔潍坊光电园二期厂区内，公司自主研发的音圈绕线机正火热运转，该机器能够把线径接近人的头发丝的漆包线在高温高速下缠绕成音圈，形成紧密的分层叠加结构。这是最新的 iPhone 16e 扬声器自动化生产线。

“中国企业自动化生产以及在产线上使用AI的能力取得了非常大的进步。”杰夫·威廉姆斯说。

![](https://pics1.baidu.com/feed/8694a4c27d1ed21b3e16083b58aa46cb53da3f60.jpeg@f_auto?token=716ddf14e0b2bb4601ed2a2640ffc682)

3 月 25 日，苹果公司首席运营官杰夫·威廉姆斯（右）与立讯精密董事长王来春参观立讯精密位于江苏常熟的精密零组件工厂。
随着中国发展高层论坛2025年年会在北京举行，大量美国企业家现身中国，其中就包括苹果公司的高管团队。苹果首席执行官蒂姆·库克在北京三里屯零售店与顾客交流，参访浙江大学并捐赠3000万元人民币；杰夫·威廉姆斯则造访了山东、江苏等地多家供应链企业。

自 1993 年开展在华业务以来，苹果公司在全世界最主要的 200 家供应商中，超过八成在中国设有工厂从事相关业务。过去 5 年，苹果公司在中国投资智能和绿色制造的资本支出达到 200 亿美元。
歌尔公司从 2010 年开始与苹果公司合作，先后参与了苹果数十款产品的生产与制造；立讯精密与苹果公司的合作始于 2011 年，产品几乎覆盖了苹果几乎所有的产品线；杰士德集团从 2008 年开始成为苹果公司的自动化设备供应商，累计为苹果公司提供了近 6.5 万台设备……

![](https://pics3.baidu.com/feed/7e3e6709c93d70cf76877de30d184a0fbba12b37.jpeg@f_auto?token=b842d65c6e27b8ed2b11c948248d057a)

3 月 25 日在立讯精密常熟工厂音圈马达生产线拍摄的自动化功能测试机器。

杰士德集团董事长景余祥说：“在与苹果的合作中，我们意识到提高垂直整合能力的重要性。中国制造正处于转型发展期，希望与外资合作的优秀经验能够沉淀下来，帮助我们在世界供应链舞台上更好地发展。”

26 日，蒂姆·库克在浙江大学举办的第十届移动应用创新赛上宣布，向浙江大学捐赠 3000 万元人民币，深化其对中国下一代开发者的支持。

据介绍，苹果公司将与浙江大学共同设立 Apple 移动应用孵化基金，提供最前沿的技术培训，包括 App 开发、产品设计、市场营销和商业运营等专业课程。此前十年，苹果公司共向浙江大学捐赠 5000 万元人民币，用于开展移动应用创新赛。
“大赛已经超越了我们的期望。”蒂姆·库克说，年轻的创新者设计出了令人惊叹的应用。在中国蓬勃发展的应用经济中，每天都有数以百万计的开发者与世界各地的客户建立联系。

![](https://pics2.baidu.com/feed/a6efce1b9d16fdfa7ec2def2424b175b95ee7b50.jpeg@f_auto?token=dab7e67e2af4e768bea7aef55e9f7061)

3 月 24 日，参加苹果公司的线组长培训项目的学员（左一）向苹果公司首席运营官杰夫·威廉姆斯（右一）、歌尔股份有限公司董事长姜滨（左二）等，分享参加培训对自身和职业发展的改变。

近年来，苹果与中国供应商在清洁能源领域的合作持续深化。24 日，苹果公司宣布发起 7.2 亿元人民币的投资基金，计划扩大在中国的清洁能源产能，助力其在 2030 年实现供应链 100% 使用可再生能源。

苹果公司介绍，公司正在和供应商们密切合作，努力完成相关目标。目前，苹果公司在中国约三分之二的生产由可再生能源驱动，100 多家中国供应商为这一进展作出了贡献。

在歌尔公司的厂区，厂房、办公楼的屋顶都安装了一排排蓝色的光伏电板，将太阳能转化为绿色电能。“自 2023 年以来，歌尔在中国为苹果生产的产品已实现 100% 使用可再生能源。”歌尔股份有限公司董事长姜滨说。

2018 年，苹果公司及其供应商曾推出首个中国清洁能源基金，该基金发展已经超过既定目标，在中国 14 个省份新建超过 1 千兆瓦的风能和太阳能项目。

今年的政府工作报告中，将“扩大高水平对外开放，积极稳外贸稳外资”作为 2025 年中国政府工作十大任务之一。从扩大电信、医疗、教育等领域开放试点，到鼓励外国投资者扩大再投资、切实保障外资企业在诸多领域的国民待遇，再到近期发布的《2025年稳外资行动方案》，中国在降低“进”的门槛、对接“高”的标准、提升“促”的水平、营造“优”的环境等方面不断进步。

“到中国去”正成为越来越多外企的共识。2024 年，中国新设立外商投资企业 5.9 万家，同比增长 9.9%。近 5 年，外商在华直接投资收益率约 9%，位居全球前列。

“我们将坚定在华投资发展。”杰夫·威廉姆斯说。(来源：新华网)

### 库克：苹果将持续加大在华投入！他还称是《哪吒2》忠实观众

2025 年 3 月 27 日

苹果 CEO 蒂姆·库克近两年来持续加强与中国市场的联系。自上周末到访中国以来，库克就进入了“夸夸模式”，从北京到杭州，他一路表达着对中国创新的赞誉。

据中国日报 3 月 27 日报道，库克在接受专访时表示，近年来中国软件开发者取得的突破有目共睹，他们的创造力“无与伦比”，未来成功的案例只会越来越多。他认为，中国软件开发者的国际影响力正在与日俱增，“他们展现出的激情让我深受震撼”。同时，库克还表示自己是电影《哪吒之魔童闹海》（《哪吒2》）的忠实观众。

![](https://pics7.baidu.com/feed/aa64034f78f0f736740e1e9610e32816e9c413fe.jpeg@f_auto?token=a5631c0d92443075cbd460e4c6975ff9)

谈及《黑神话悟空》火遍海外，库克表示，看到有人不仅在国内取得成功，更能走向世界舞台，真是太棒了。

库克访华之际，正值苹果 iPhone 销量增长乏力之时。他重申了苹果将持续加大在华投入的承诺。

库克：将持续加大在华投入,支持中国高质量发展

苹果 CEO 库克于本周访华。此次中国之行，库克到访北京、杭州等地。

3 月 24 日，商务部部长王文涛在北京会见美国苹果公司首席执行官库克。双方就苹果公司在华业务发展、中美经贸关系等议题进行了交流。

![](https://pics2.baidu.com/feed/c83d70cf3bc79f3d95a671eca317561e708b29e8.jpeg@f_auto?token=65ef0427d3f08040dcaee7fd37f8973c)

王文涛表示，中国经济展现了强大的韧性和活力，已经成为创新发展的热土。中国坚定不移扩大对外开放，向外资企业提供公平竞争环境，支持外资企业产品公平参与以旧换新等扩消费政策。欢迎苹果公司扩大在华投资，深度融入中国市场，共享发展机遇。

王文涛强调，贸易战没有赢家，保护主义没有出路。作为全球最大的两个经济体，中美加强经贸合作符合经济规律，脱钩断链将损及各方利益。美方采取的单边加征关税等限制措施干扰企业经营预期，为世界经济带来不确定性。中方愿与美方一道，通过平等对话为企业创造更稳定的政策环境。

库克表示，苹果公司在华发展是两国经贸合作互利共赢的典范，将持续加大在华供应链、研发、社会公益等领域的投入，支持中国高质量发展。工商界是两国沟通的天然桥梁，苹果公司愿为中美经贸关系稳定健康发展发挥积极作用。

此外，库克还去了苹果北京三里屯店。

![](https://pics3.baidu.com/feed/cefc1e178a82b901ca4b39ea6a3b32783b12ef4f.jpeg@f_auto?token=c8b367951781d3c76bb5e7255aad0c2d)

夸 DeepSeek、给浙大捐钱、玩《燕云十六声》

在西湖喝龙井茶、听白娘子故事……

随后，库克在参加了中国发展高层论坛后到访杭州，杭州因诞生了 DeepSeek 而备受瞩目。库克此前谈及 DeepSeek 时表示，自己使用过该应用，并称赞“太棒了”。

此外，库克还现身浙江大学紫金港校区，参加移动应用创新赛十周年活动，并在看到历年创新赛优秀项目后直呼 “unbelievable”（不可思议）。

![](https://pics6.baidu.com/feed/a08b87d6277f9e2f338706640586722bb999f375.jpeg@f_auto?token=4e4c7d50b2ac5ccf39016be87f6e7922)

当天苹果宣布向浙江大学捐赠 3000 万元，深化其对中国下一代开发者的支持。该合作基于其对移动应用创新赛十年的支持，继续加强苹果在大中华区长期开展的学生和开发者的教育支持。

此外，3 月 26 日，网易《燕云十六声》举办了新版本河西区域的线下前瞻体验活动。网易公司 CEO 丁磊现身现场，苹果公司 CEO 蒂姆·库克也作为活动嘉宾闪现，共同体验《燕云十六声》的新版本内容和诸多新技术适配。

当天，库克与丁磊一起感受了《燕云十六声》在新 iPad 上的硬件光线追踪技术。在看到游戏在 iPad 上的水体反射后，库克夸赞了场景的光追实机效果。

3 月 28 日上午，库克还转发了知名博主何同学的微博，两人在西湖边品龙井茶。库克还听何同学讲了白娘子的故事。(来源：每日经济新闻)

## 提案

### 通过的提案

[SE-0459](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0459-enumerated-collection.md "SE-0459") **添加 Collection 一致性 enumerated()** 提案通过审查。该提案已在 **第七十一期周报** 正在审查的提案模块做了详细介绍。

[SE-0460](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0460-specialized.md "SE-0460") **Explicit Specialization** 提案通过审查。该提案已在 **第七十一期周报** 正在审查的提案模块做了详细介绍。

[SE-0465](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0465-nonescapable-stdlib-primitives.md "SE-0465") **不可可调配类型的标准库原语** 提案通过审查。该提案已在 **第七十三期周报** 正在审查的提案模块做了详细介绍。

[SE-0466](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0466-control-default-actor-isolation.md "SE-0466") **控制默认演员隔离推断** 提案通过审查。该提案已在 **第七十三期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0470](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0470-isolated-conformances.md "SE-0470") **全局行为者隔离一致性** 提案正在审查。

隔离到全局行为者（如 `@MainActor`）的类型对于表示只能从单个并发上下文中使用的数据很有用。它们既发生在所有代码都应在主行为者上运行的单线程程序中，也发生在与用户界面交互通过主行为者发生的更大应用程序中。不幸的是，由于隔离不匹配，这些类型无法符合大多数协议：

```swift
@MainActor
class MyModelType: Equatable {
  var name: String

  init(name: String) {
    self.name = name
  }

  // error: main-actor-isolated static function '==' cannot satisfy non-isolated requirement 'Equatable.=='
  static func ==(lhs: MyModelType, rhs: MyModelType) -> Bool { 
    lhs.name == rhs.name
  }
}
```

该提案引入了隔离一致性的概念，这是一种只能在类型的隔离域内使用的一致性。对于上述代码，`Equatable` 的一致性可以指定为与主要行为者隔离，如下所示：

```swift
@MainActor
class MyModelType: @MainActor Equatable {
  // unchanged from the above ...
}
```

这允许 `MyModelType` 提供与 `Equatable` 的一致性，该一致性与所有其他一致性一样，除了它只能从主要行为者使用。

[SE-0471](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0471-SerialExecutor-isIsolated.md "SE-0471") **改进了并发运行时的自定义 SerialExecutor 隔离检查** 提案正在审查。

该提案扩展了这些功能，允许自定义执行者不仅“检查和崩溃假设是否错误”，还检查并根据检查结果采取行动。

[SE-0472](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0472-task-start-synchronously-on-caller-context.md "SE-0472") **从调用者上下文同步启动任务** 提案正在审查。

Swift Concurrency 进入异步上下文的主要手段是创建任务（结构化或非结构化），从那里开始可以调用异步函数，当前工作的执行可能会暂停。

今天进入异步上下文需要创建和安排任务，以便稍后执行。对于执行最少或没有执行（!）的任务来说，这种初始延迟可能是浪费的根本不工作。

在某些情况下，这种初始延迟也可能有问题，因为已知我们正在执行“正确的行为者”，但不是在异步函数中，因此，为了调用一些不同的异步函数，我们必须创建一个新任务，并引入微妙的时序差异，与仅能够立即调用目标函数相比——目标函数可能被隔离到我们正在调用的同一行为者。

[SE-0473](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0473-clock-epochs.md "SE-0473") **Clock Epochs** 提案正在审查。

**SE-0329：时钟、即时和持续时间** 引入了三种具体的时钟类型：`SuspendingClock`、`ContinuousClock` 和 `UTCClock`。虽然并非所有时钟都有有意义的参考或零瞬时概念，但 `SuspendingClock` 和 `ContinuousClock` 确实有，并且可以访问它是有用的。

## Swift论坛

1) 讨论[序列化和反序列化 API 的未来](https://forums.swift.org/t/the-future-of-serialization-deserialization-apis/78585 "序列化和反序列化 API 的未来")

在 Swift 论坛的讨论中，Kevin Perry 提出了对现有 Codable API 的改进建议，旨在提升序列化和反序列化的性能。现有的 Codable API 存在一些性能瓶颈，例如使用存在类型（existentials）导致的运行时和内存开销，以及动态类型转换带来的性能影响。

为了解决这些问题，Kevin Perry 借鉴了 Rust 的 Serde 设计，提出了以下核心原则：

1. 设计新的 API 以突破 Codable 的性能限制：通过避免使用存在类型和动态类型转换，减少运行时和内存开销。 
2. 借鉴 Rust Serde 的设计：采用访问者模式（Visitor Pattern），让解析器驱动反序列化过程，从而避免构建临时的中间表示，提升性能。
3. 深度依赖宏以减少手动实现：利用 Swift 的宏功能，自动生成序列化和反序列化的代码，减少开发者的手动编码量。

此外，为了兼容现有的 Codable，建议新的编码器和解码器不仅支持新的协议，还应支持现有的 Encodable 和 Decodable 类型。同时，新的设计应专注于 Swift 生态中常用的序列化格式，避免引入需要外部工具或代码生成的复杂方案。

这一讨论旨在收集社区的反馈，以确保新的序列化和反序列化 API 能够满足开发者的需求，并在性能和易用性之间取得平衡。

2) 讨论[Swift 6.2 及更高版本对生命周期依赖项的实验性支持](https://forums.swift.org/t/experimental-support-for-lifetime-dependencies-in-swift-6-2-and-beyond/78638 "Swift 6.2 及更高版本对生命周期依赖项的实验性支持")

在讨论中，语言指导组（LSG）提议在 Swift 6.2 中引入 `@lifetime` 作为受支持的实验性特性，旨在为非逃逸类型（如 Span）提供生命周期依赖的支持。此前，SE-0446 为 Swift 增加了对非逃逸类型的基本语言支持，但有意省略了函数和属性返回这些类型值的能力，等待未来的提案来添加生命周期依赖。然而，SE-0456 已在标准库中添加了多个返回 Span 的属性，这些属性使用了尚未正式纳入语言的 `@lifetime` 特性。

LSG 对于将 `@lifetime` 正式作为定义生命周期依赖的方式持谨慎态度，因此尚未将其作为正式特性提出。然而，考虑到开发正式特性可能需要数个版本，LSG 希望开发者能够在此期间利用 Span 等非逃逸类型，并反馈使用中的问题和需求。因此，LSG 提议将 `@lifetime` 作为受支持的实验性特性引入，具体承诺包括：

1. 为该实验性特性发布设计文档，可能比正常的演进提案文档更为简略，但会阐述开发者可以使用的功能。该特性将通过适当的 `-enable-experimental-feature` 标志在官方 Swift 版本中可用。 ￼
2. 在官方特性能够表达实验性特性的所有功能之前，不会弃用该实验性特性。弃用的发布版本将包括自动迁移工具，并至少在实验性特性本身的支持周期内可用。
3. 如果未来弃用该实验性特性，它将在官方 Swift 版本中继续可用至少三个版本。例如，假设在 Swift 6.2 中引入了该实验性特性，而在 Swift 6.4 中添加了替代它的官方特性。LSG 将在 6.4 版本中宣布该实验性特性被视为弃用，但它仍将在 6.2、6.3、6.4、6.5 和 6.6 版本中可用，为采用该实验性特性的开发者提供足够的迁移时间。
4. 官方特性的部署限制不会比它们所替代的实验性特性更严格，除非绝对必要。

LSG 认为这是一个允许程序员提前利用仍在开发中的特性的良好框架，特别是当一个正式特性被另一个可能复杂得多的特性“解锁”时。对于不确定是否能够在支持窗口内迁移出受支持的实验性特性的程序员，通常应等待官方特性的发布。

LSG 将在未来几周内创建一个单独的讨论线程，专门讨论 @lifetime 特性。请将任何反馈集中在受支持的实验性特性的概念上。

3) 提议[SwiftPM 对二进制静态库依赖项的支持](https://forums.swift.org/t/pitch-swiftpm-support-for-binary-static-library-dependencies/78619 "SwiftPM 对二进制静态库依赖项的支持")

在 Swift 论坛的提议中，Daniel Grumberg 提出了一个关于 Swift 包管理器（SwiftPM）支持二进制静态库依赖的提案。目前，SwiftPM 对二进制依赖的支持主要局限于 Apple 平台，使用 XCFramework 格式的库。该提案旨在扩展 SwiftPM 的功能，使其在非 Apple 平台上也能支持暴露 C 接口的静态库依赖。

动机：

Swift 作为跨平台语言，应用范围广泛，但 SwiftPM 对二进制依赖的支持存在局限。现有的二进制目标支持：

* 在 Apple 平台上使用 XCFramework 格式的库。
* 通过工件包（artifact bundles）支持可执行文件。

该提案旨在以安全的方式将 XCFramework 的部分功能引入非 Apple 平台。

提议的解决方案：

提案建议扩展工件包，引入新的工件类型 staticLibrary，以表示二进制静态库依赖。工件清单（artifact manifest）将为每个变体编码以下信息：

* 链接器使用的静态库文件路径。
* 用于在包的源代码中使用该库的 API 的信息，例如头文件路径和模块映射（module map）。

此外，提案还建议增加一个审计工具，以验证库工件在 Linux 平台上的安全使用，确保分发的工件在各个部署平台上满足依赖要求。

详细设计：

工件清单的 JSON 格式将包含：

* type 字段：指定为 `staticLibrary`，表示这是一个静态库。
* `headerPaths` 字段：相对于工件包根目录的头文件目录路径数组，这些路径将作为搜索路径传递给编译器。
* `moduleMapPath` 字段：可选字段，指定自定义模块映射的路径。

通过这些扩展，SwiftPM 将能够在非 Apple 平台上支持二进制静态库依赖，进一步增强其跨平台能力。

4) 提议[退出测试](https://forums.swift.org/t/st-0008-exit-tests/78692 "退出测试")

在论坛的提议中，Maarten Engels 宣布了对提案 ST-0008 “Exit Tests” 的审查期，该提案旨在为 Swift 测试引入新的功能，允许开发者验证代码是否以特定的退出状态终止。审查期从 2025 年 3 月 20 日开始，持续至 2025 年 4 月 8 日。

提案概述：

ST-0008 提议在 Swift 的测试框架中添加新的宏，允许开发者编写测试，期望被测代码以特定的方式退出，例如成功、失败或抛出特定的错误。这对于需要验证进程终止行为的应用程序测试尤为重要。

社区反馈：

社区成员对该提案进行了讨论，主要集中在 API 的命名和可读性上。例如，有人建议将 `#expect(exitsWith: .failure)` 修改为 `#expect(exit: .failure)`，认为这样更符合 Swift 的命名惯例，提高了可读性。 此外，还有讨论涉及如何更好地表达测试期望，以及与现有测试宏（如 `#expect(throws:)`）的一致性。 ￼ ￼

如何试用：

要尝试该特性，开发者需要将 swift-testing 的 main 分支作为依赖项添加到项目中，并在测试目标中引入相应的产品。然后，使用 `@_spi(Experimental) import Testing` 导入 Swift Testing。详细的设置和示例可参考提供的示例仓库。  ￼

审查参与：

社区鼓励开发者参与审查过程，提供关于提案的反馈和建议。审查的目标是通过建设性的批评改进提案，并最终确定 Swift 的发展方向。更多关于 Swift 演进过程的信息可在相关文档中找到。

5) 提议[使数组和朋友符合 Comparable](https://forums.swift.org/t/pitch-making-array-and-friends-conform-to-comparable/78634 "使数组和朋友符合 Comparable")

在 Swift 社区的讨论中，Paul Hudson 提出了一个建议：让 Array 等序列类型符合 Comparable 协议。目前，元组可以直接进行比较，例如 (1, 2, 3) < (4, 5, 6) 是有效的，但对数组进行类似的比较（如 [1, 2, 3] < [4, 5, 6]）却会导致编译错误。为了解决这一问题，Paul 提议为 Sequence 添加一个扩展，利用已有的 `lexicographicallyPrecedes()` 方法，实现序列的比较功能。 ￼

具体实现如下：

```swift
extension Sequence where Element: Comparable {
    public static func <(lhs: Self, rhs: Self) -> Bool {
        lhs.lexicographicallyPrecedes(rhs)
    }
}

extension Array: Comparable where Element: Comparable { }
```

此提案的动机在于，Swift 已经支持元组、字符串和 IndexPath 的比较操作，引入数组的比较符合语言的一致性。此外，其他编程语言（如 Rust、Python、Ruby 等）也支持类似功能。

然而，社区成员对该提案表达了不同的看法。有人指出，数组的比较可能导致性能问题，特别是在处理大型数组时。此外，数组的比较顺序可能存在多种解释，例如前缀顺序和短词典序，可能导致混淆。

总体而言，该提案引发了关于数组比较的实用性、性能影响和潜在歧义的讨论。社区正在积极探讨如何在保持语言一致性的同时，平衡这些因素。

## 推荐博文

[苹果设备端与服务器基础模型介绍](https://machinelearning.apple.com/research/introducing-apple-foundation-models "苹果设备端与服务器基础模型介绍")

**摘要：** 苹果在 2024 年推出了全新 AI 系统 Apple Intelligence，包含两个核心部分：一个能在 iPhone 上快速运行的小模型（30 亿参数），和一个更强大的云端大模型。这两个模型都特别注重保护用户隐私。

小模型经过特殊优化，在 iPhone 15 Pro 上反应极快，处理文字速度达到每秒 30 个词。大模型则放在苹果自己的服务器上运行，通过特殊技术确保用户数据安全。

这些 AI 模型很聪明，可以帮用户改文章、总结通知、甚至生成图片。苹果特别强调，训练这些模型时绝对不会用用户的私人数据。测试显示，它们的表现比很多更大的开源AI模型更好，特别是在理解指令和内容安全方面。

现在，这些 AI 功能已经用在 iPhone、iPad 和 Mac 的很多地方，比如帮助写代码、制作聊天表情等，既实用又保护隐私。

[苹果开源 Swift Build](https://mp.weixin.qq.com/s/i9uYsUdJ0NK4gmLsI8Zg7w "苹果开源 Swift Build")

**摘要：** 苹果宣布开源其核心开发工具 Swift Build，这是 Xcode 的底层构建引擎，已为数百万 iOS 应用提供支持。这一举措标志着苹果在跨平台开发领域迈出重要一步，未来将支持 Linux、Windows 等更多操作系统。

此次开源意味着开发者能够获得更统一的跨平台构建体验，解决长期以来 Xcode 与 Swift 包管理器在构建行为上的差异问题。虽然 iOS 开发中的核心流程如代码签名等仍依赖 Xcode 专有功能，但开源 Swift Build 为开发者提供了更大的灵活性和控制权，也为 Swift 语言的跨平台发展奠定了基础。

这一决定被视为苹果对开源社区的积极回应，有望推动 Swift 突破苹果生态的限制，向更通用的编程语言方向发展。开发者社区可以更深入地参与工具改进，共同提升 Swift 在各平台的表现。不过，如何在保持苹果商业利益与促进开源生态发展之间取得平衡，仍是未来需要面对的挑战。

[苹果开发者性能优化指南](https://developer.apple.com/documentation/Xcode/improving-your-app-s-performance/ "苹果开发者性能优化指南")

**摘要：** 这篇苹果文档讲的是如何提升 App 性能。核心思路就是：先测量问题，再改进代码，最后验证效果，不断循环这个过程。

具体操作分四步：

1. 先用 Xcode 自带的工具检查 App 的启动速度、卡顿情况、耗电量等数据
2. 找到最影响用户体验的问题（比如某个页面特别卡）
3. 用 Instruments 工具深入分析原因（比如是内存泄漏还是网络请求太慢）
4. 修改代码后，再测试看是否真的变快了。

文档特别提醒：即使现在 App 运行良好，也要定期做这些检查，防止新版本变慢。优化时要重点看真实用户的数据，因为模拟器测试的结果可能不准确。
简单来说就是：测量→找问题→改代码→验证，循环做这几步就能让App越来越流畅。

## 话题讨论

**AI 的迅速发展，让我逐渐意识到：** 人类种群的集体思想需求是无法阻止的，曾经的科幻电影离我们已不再遥远，今天我们来聊一下人类世界的未来，你认为以下哪种结果更会最先降临地球？

1. AI 智能机器人迅速发展且产生自我意识，机器人取代人类统治地球。
2. 能够使人类丧失人性意识的传染性T病毒出现并迅速传播，生化危机蚕食全球。
3. 地球环境极速巨变，地表环境不再适宜人类居住，流浪地球计划被迫启动。

> ps: 我把这个问题问了一下 AI，AI 给的排序：‌1. 地球环境巨变（选项3） → 2. AI危机（选项1） → 3. 生化危机（选项2）‌😂

有点怀疑：有没有可能 AI 为了防止人们怀疑，故意把自己排在第二。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
