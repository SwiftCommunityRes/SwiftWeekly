## 前言

**本期是 Swift 编辑组自主整理周报的第七十八期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

人生没有太晚的开始，只要你勇敢的迈步，不断的向前，无论目标有多大，都比站在原地更接近成功，加油👊👊👊

> **周报精选**
>
> 新闻和社区：苹果 CEO 库克松了一口气！特朗普关税被美法院叫停
> 
> 提案：Swift 功能的迁移工具提案正在审查。
> 
> Swift 论坛：提议让 UUID 遵循 `LosslessStringConvertible` 协议
>
> 推荐博文：在 iOS 中调用 GPU 算力：加速你的应用性能
>
> **话题讨论：** 
> 
> 高考还有意义吗？知识改变命运的时代还存在吗？
>
>**上期话题结果**

![](https://files.mdnice.com/user/47553/89c09c86-167f-4645-bc27-a3587e47d10f.jpg)

## 话题讨论

一年一度的全国大高考再次来临，高考人数再创新高。然而，中国大学毕业生的就业问题依然严峻，学历贬值问题日趋明显，那么你们认为：**高考还有意义吗？知识改变命运的时代还存在吗？**

1. 高考仍是最公平的选拔机制之一，尽管各地难度不同，但它至少提供了改变命运的可能。
2. 大学学历虽然不能直接提升阶层，但它能为人生带来更多可能性和选择机会。
3. 高校教育与企业需求脱节，很多毕业生拿着文凭却找不到对口工作，就业难是现实问题。
4. 与其投入时间和金钱拿一个就业无保障的文凭，不如早些学手艺、积累经验，现实点更实在。
5. 不管有没有用，我还是想上大学——人生只有一次高考，重要的是经历和过程。

## 新闻和社区  

### 苹果Siri升级搁浅：轻资产路线受阻，缺自研芯、数据中心、训练数据

2025 年 5 月 29 日

5 月 29 日消息，据外媒 Business Insider 昨天报道，正值谷歌上周高调发布AI视频工具 Flow 之际，苹果被迫推迟生成式 AI 版 Siri 的核心升级计划。这一突发状况暴露苹果存在致命技术短板：缺乏自研 AI 芯片、数据中心依赖谷歌设施、训练数据困于隐私枷锁。

与谷歌 25 年构建的 12 层技术栈（含 Transformer 架构、TPU 芯片及 YouTube 数据资产）相比，苹果自研 AI 芯片进度落后 7 年，年资本支出不足谷歌 75 亿美元（折合人民币约为 539.30 亿元）的零头。

为挽救困局，苹果正与 OpenAI 紧急谈判引入 ChatGPT 替代 Siri，但后者已联合苹果前设计总监乔尼·艾维（Jony Ive）开发竞品硬件。科技博主本·汤普森（Ben Thompson）警告：“轻资产路线已然失效，苹果要么每年豪掷百亿美元自建 AI 基建，要么吞下并购苦果。”

一、谷歌 25 年筑就 AI 帝国：YouTube 数据+自研 TPU 构筑护城河，从数据到算力的全栈掌控

外媒 Business Insider 披露，谷歌已构建起覆盖数据、算法、算力的完整 AI 生态体系，其依托全球最大视频平台 YouTube 以及长达25年的网页索引历史，积累了海量训练数据，为第三代视频生成模型 Veo 3 和第四代图像模型 Imagen 4等技术提供了充足的动力。

谷歌在 2013 年花费 4400 万美元（折合人民币约为 27240.08 万元）收购了多伦多大学亚历克斯·克里泽夫斯基（Alex Krizhevsky）、伊利亚·苏茨克韦尔（Ilya Sutskever）与杰弗里·辛顿（Geoffrey Hinton）的初创公司 DNNResearch，从而获得了 AlexNet 技术（AlexNet 是一种卷积神经网络，它在 2012 年的 ImageNet 竞赛中表现出色，大幅降低了图像识别的错误率）。

在 2014 年，谷歌收购德米斯·哈萨比斯（Demis Habassis）领导的 DeepMind 实验室。

在算力层面，谷歌于 2016 年推出自研 TPU 芯片以应对英伟达的技术垄断，并通过 TensorFlow 开发框架构建起支撑全球开发者的生态体系。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2025%2F0529%2Fad393f4aj00sx0olu00erd000rs015vg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

谷歌 CEO 桑达尔·皮查伊（Sundar Pichai）在 2016 年谷歌 I/O 大会时曾向多家媒体透露谷歌进入“AI 优先”时代。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2025%2F0529%2Fb298babdj00sx0olu00vzd000rs00img.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

此外，为保障谷歌的数据中心能耗需求，谷歌不仅斥资开发三座核电站，其可再生能源采购量更位居全球企业首位，从能源端完成战略布局。

据外媒 Business Insider 透露，谷歌今年计划投入 750 亿美元（折合人民币约为 5393.02 亿元）资本支出建设 AI 数据中心，通过三座核电站与可再生能源支撑算力需求。

苹果算力、数据、人才、基建断层落后，数据中心靠租借、芯片研发迟 7 年

在 AI 发展进程中，苹果面临多重结构性挑战。

在算力层面，苹果 2023 年才启动数据中心 AI 芯片研发，较谷歌 TPU 晚了七年，苹果在训练“Apple Intelligence”时更需紧急租用谷歌 TPU 集群。

在数据开发层面，苹果受隐私政策桎梏，10 亿用户数据难以充分用于模型训练，苹果依赖设备端算力处理复杂任务，数据价值挖掘严重受限。

在人才机制层面，苹果长期禁止 AI 团队公开发表论文的政策，使其错失顶尖人才招募窗口，即便苹果在 2018 年挖角谷歌 AI 掌门约翰·詹南德雷亚（John Giannandrea），仍未能扭转人才储备的颓势。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2025%2F0529%2Fe4355988j00sx0olu00l0d000rs00jwg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

在基建布局层面，苹果的 iCloud 服务长期依赖谷歌数据中心托管，自建算力规模不足谷歌 1/10，基础设施实力差距显著。

苹果 AI 突围困局：ChatGPT 替代 Siri 遇反垄断狙击，合作并购与百亿收购成艰难抉择

苹果在 AI 领域的合作布局正遭遇战略级冲突与结构性困境，苹果努力突围 AI 困局。

苹果与 OpenAI 在去年 5 月谷歌 I/O 大会后一周就引入 ChatGPT 替代 Siri 进行谈判，但 OpenAI 近期联合苹果前设计总监乔尼·艾维（Jony Ive）开发新型 AI 硬件设备，直接威胁 iPhone 市场地位，或导致合作可行性骤降。

在外媒看来，若苹果转向谷歌寻求算力支持，可能触发美国及欧盟反垄断机构审查，而潜在合作伙伴 Meta 因首席执行官马克·扎克伯格（Mark Zuckerberg）与苹果 CEO 蒂姆·库克（Tim Cook）长期交恶，已被排除在合作名单之外。

在并购领域，科技分析师本·汤普森（Ben Thompson）提出的方案同样危机四伏。其建议苹果收购的初创公司 SSI 由 OpenAI 创始元老伊利亚·苏茨克韦尔（Ilya Sutskever）创立，至今尚未推出成熟产品，估值却已达百亿美元级别。

苹果的另一选项是埃隆·马斯克（Elon Musk）的xAI公司，则因创始人反复无常的技术路线与苹果封闭生态理念相悖，被业内视为荒诞提案。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2025%2F0529%2F827a0076j00sx0olu00l4d000rs00grg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

更现实的压力来自资本层面。若选择自建 AI 基础设施，苹果需每年追加 750 亿美元（折合人民币约为 5434.73 亿元）资本支出，该金额相当于其 2023 年研发总投入的 45%。这迫使库克团队在技术自主权与财务可持续性间寻找危险平衡。

谷歌用 25 年构筑从 TPU 芯片、Transformer 架构到核电站的 12 层技术栈。苹果移动生态优势在 AI 时代转化为算力枷锁，设备端处理能力在百亿参数模型前捉襟见肘。当科技巨头年投入百亿级资金夯实 AI 地基时，轻资产路线宣告失效。而苹果在移动生态的优势未能转化为 AI 时代的护城河，设备端算力在百亿参数大模型前捉襟见肘，隐私保护理念反成数据开发枷锁。

苹果的被动局面可能也揭示了行业新规则：AI 竞争本质是数据中心规模、能源掌控力、学术人才储备的复合较量。这场基于数据中心规模、能源掌控力与学术储备的马拉松竞赛，正迫使后来者付出多倍代价填补技术代沟。(来源：Business Insider)

### 苹果 CEO 库克松了一口气！特朗普关税被美法院叫停

2025 年 5 月 29 日

据媒体报道，美国联邦法院裁定，特朗普试图对进口商品（包括苹果产品）全面加征关税的行为超越行政权限。

就在上周，特朗普威胁苹果 CEO 库克，称如果不在美国生产 iPhone，就要对苹果公司征收至少 25% 的关税，不止是苹果公司，这条规则也适用于三星和其它智能手机制造商。

如今美国法院认定，美国法律并未授权特朗普在未经国会批准的情况下单方面对外国商品加征关税，受此影响，全球股票市场应声大涨，标普 500 指数期货上涨 1.4%，道琼斯指数期货上涨 1.1%。

据分析师测算，如果加征关税，顶配版 1TB iPhone 16 Pro Max 零售价可能从 1599 美元暴涨至 4300 美元以上；基础款 128 GB 的 iPhone 16 e也可能飙升至 1617 美元。

另外，即便是苹果公司现金充裕，在美国从头开始制造 iPhone 也是非常困难的，短期内根本不可能实现。
 
美国投行 Wedbush 知名分析师 Dan Ives 在一份报告中表示，将 iPhone 生产转移到美国将需要 5 到 10 年的时间，最终每部 iPhone 的售价可能高达 3500 美元。(来源： 快科技)

![](https://n.sinaimg.cn/spider20250529/199/w600h399/20250529/c803-947a83b107ece801a2db0d0adba08888.jpg)

### 消息称苹果重塑六大系统：iOS 26 领衔，命名向年份看齐

2025 年 5 月 29 日

5 月 29 日消息，彭博社的马克・古尔曼（Mark Gurman）今天（5 月 29 日）发布博文，报道称苹果公司正重塑其六大系统（iOS、iPadOS、macOS、watchOS、tvOS 和 visionOS），不再使用传统版本号，而是以年份为后缀命名。

例如，苹果计划在 2025 年全球开发者大会（WWDC）上宣布下一代 iOS 系统，不再叫做 iOS 19，而是叫做 iOS 26。IT之家注：该命名策略类似汽车行业的命名规则，虽然系统是在 2025 年发布，但会以 26 后缀命名。

古尔曼表示苹果此次命名调整，是协调苹果不同系统之间的版本号。目前的操作系统版本号因初始发布时间不同而各异，例如 iOS 18、watchOS 12、macOS 15 和 visionOS 2，这种不统一容易让用户和开发者感到困惑，而通过年份后缀，可以很好统一版本号。

在用户界面方面，古尔曼再次强调今年会是苹果史上最大规模界面改版，代号为 Solarium，主打 visionOS 的玻璃质感风格，影响范围将远超 2013 年的 iOS 7 改版。

“Solarium”玻璃质感界面调整将成为重头戏，新设计被描述为“更流畅、更现代”，目标为苹果的各操作系统注入统一的视觉语言。

新设计将覆盖 tvOS、watchOS 及部分 visionOS，力求让用户在不同设备间切换时获得更连贯的体验。(来源： IT之家)

## 提案

### 通过的提案

[SE-0472](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0472-task-start-synchronously-on-caller-context.md "SE-0472") **从调用者上下文同步启动任务** 提案通过审查。该提案已在 **第七十四期周报** 正在审查的提案模块做了详细介绍。

[SE-0482](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0482-swiftpm-static-library-binary-target-non-apple-platforms.md "SE-0482") **二进制静态库依赖项** 提案通过审查。该提案已在 **第七十七期周报** 正在审查的提案模块做了详细介绍。

[SE-0484](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0484-allow-additional-args-to-dynamicmemberlookup-subscripts.md "SE-0484") **允许对 @dynamicMemberLookup 下标的附加参数** 提案通过审查。该提案已在 **第七十七期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0485](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0485-outputspan.md "SE-0485") **OutputSpan：委托连续内存的初始化** 提案正在审查。

在引入 `Span` 和 `MutableSpan` 之后，该提案增加了一个通用设施，用于使用 `OutputSpan` 和 `OutputRawSpan` 类型初始化专用借用内存。`OutputSpan` 表示的内存由许多初始化元素组成，然后是未初始化的内存。`OutputSpan` 的操作可以更改内存中初始化元素的数量，这与 `MutableSpan` 不同，`MutableSpan` 总是代表代表固定数量元素的初始化内存。

[SE-0478](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0478-default-isolation-typealias.md "SE-0478") **Swift 功能的迁移工具** 提案正在审查。

Swift 5.8 引入了即将推出的功能，这些功能能够逐步采用语言模式中包含的单个源不兼容的更改。许多即将推出的功能都有机械迁移，这意味着编译器可以确定必要的确切源更改，以允许代码在即将推出的功能下编译，同时保留代码的行为。本提案旨在通过提供自动生成这些源代码修改的集成机制来改善启用单个 Swift 功能的体验。

### 拒绝的提案

[SE-0480](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0480-swiftpm-warning-control.md "SE-0480") **SwiftPM的警告控制设置** 提案被拒绝。该提案已在七十六期周报 正在审查的提案模块做了详细介绍。

## Swift论坛

1) 提议[可扩展枚举](https://forums.swift.org/t/se-0487-extensible-enums/80114 "可扩展枚举")

该提议旨在引入“可扩展枚举（extensible enums）”这一新特性，使枚举能够在定义后通过扩展添加新的 case。当前 Swift 中的枚举是封闭的，所有 case 必须在原始定义中列出，这限制了某些 API 的灵活性，尤其是在跨模块或插件架构中。

SE-0487 提出，通过标记为 `@extensible` 的枚举可以允许在其他模块中添加新的 case，从而提升库的可扩展性和未来兼容性。

为了支持这一能力，提议还引入了新语法和运行时行为的变化，例如新的 switch 匹配策略。讨论中关注的点包括语义清晰性、编译器处理、ABI 影响以及如何保证已编写代码的兼容性。该提议目前正处于积极讨论阶段，社区对其潜力表现出浓厚兴趣。

2) 提议[让 UUID 遵循 LosslessStringConvertible 协议](https://forums.swift.org/t/pitch-conform-uuid-to-losslessstringconvertible/80084 "让 UUID 遵循 LosslessStringConvertible 协议")

该提议建议将标准库中的 UUID 类型添加对 `LosslessStringConvertible` 协议的遵循。该协议的要求是类型能够从其 description 文本精确还原自身实例。由于 UUID 本身已经具有 `uuidString` 属性来表示其标准化字符串形式，并且可以通过该字符串重新初始化，因此完全符合该协议的语义。

```swift
extension UUID: LosslessStringConvertible {
  public init?(_ description: String) {
    self.init(uuidString: description)
  }

  public var description: String {
    uuidString
  }
}
```

这项更改将带来更好的泛型兼容性，例如可用于基于 `LosslessStringConvertible` 构建的 API（如 `String.init<T: LosslessStringConvertible>(_ description: String)`）。该提议受到社区普遍支持，被认为是一个小而有益的改进，且没有 ABI 或源兼容性问题。

3) 讨论[提升对“追溯一致性”支持的易用性](https://forums.swift.org/t/basic-quality-of-life-improvements-for-retroactive/80180 "提升对“追溯一致性”支持的易用性")

该提议讨论了 Swift 中“追溯一致性（retroactive conformance）”的使用体验问题，并提出了几项基础但实用的改进措施。当前，当一个类型在扩展中添加协议一致性后，往往需要显式声明相关成员函数，这在已满足协议要求的情况下会显得冗余。

提议的主要目标是：
* 允许使用现有成员自动满足协议一致性，而无需重复声明。
* 提升错误信息的清晰度，帮助开发者识别为什么协议一致性失败。
* 改善与泛型约束交互的体验，避免开发者在追溯一致性中遇到不必要的限制。

例如，目前开发者可能需要重复声明成员以使扩展符合协议：

```swift
extension MyType: Equatable {
  static func == (lhs: MyType, rhs: MyType) -> Bool {
    lhs.id == rhs.id
  }
}
```

若 `==` 已定义，未来希望可简化为：

```swift
extension MyType: Equatable {}
```

该 pitch 尚未包含完整的语法提案或实现细节，当前处于早期讨论阶段。社区反馈强调其方向合理，尤其适合提升大型项目和多模块代码的可维护性。开发者普遍支持改善追溯一致性的可用性，并建议优先关注诊断质量和语义推导能力的提升。

4) 讨论[预览 Swift 宏开发用 SwiftSyntax 预构建包](https://forums.swift.org/t/preview-swift-syntax-prebuilts-for-macros/80202 "预览 Swift 宏开发用 SwiftSyntax 预构建包")

该帖宣布了一个供宏开发者使用的新预览功能：SwiftSyntax 的预构建二进制包。Swift 宏的实现依赖 SwiftSyntax 和相关组件，这些库频繁变动，版本匹配问题常给开发者带来困扰。

为简化体验，Swift 项目团队推出了官方构建的 SwiftSyntax 预编译版本，并托管在 swift-macro-prebuilts GitHub 仓库。

开发者现在可以在 Swift 宏项目中通过添加如下依赖，快速集成正确版本的 SwiftSyntax：

```swift
.package(url: "https://github.com/apple/swift-macro-prebuilts", from: "0.50900.1")
```

优点包括：
* 省去手动同步 SwiftSyntax 与 Swift 工具链版本的工作量
* 加快构建速度
* 避免源码依赖的编译开销

预构建包以与特定 Swift 工具链兼容为目标，版本号与 Swift 版本一致（例如 0.50900.1 对应 Swift 5.9）。未来计划是让该机制成为宏开发的推荐方式，简化整个宏生态工具链。社区反馈积极，许多宏作者表示这将极大提升开发体验和版本稳定性。

5) 讨论[关于 type(of: s.foo) 的陷阱](https://forums.swift.org/t/type-of-s-foo-gotcha/80156 "关于 type(of: s.foo) 的陷阱")

该帖子指出一个关于 `type(of:)` 函数在访问实例属性时可能引发误解的语义陷阱。开发者可能直觉地认为 `type(of: s.foo)` 会返回属性 foo 的运行时类型，尤其当 foo 是协议类型或有类型擦除时。但实际上，它返回的是编译时静态类型，这可能导致结果与预期不符。

示例代码：

```swift
protocol P {}
struct S: P {}

struct Wrapper {
  var value: P
}

let s = Wrapper(value: S())
print(type(of: s.value))  // 输出 P，而不是 S
```

虽然 `s.value` 在运行时中实际保存的是 S 类型的实例，但 `type(of:)` 返回的是 P，即属性声明时的静态类型。这是因为 Swift 中 `type(of:)` 是泛型函数，它的类型参数是在编译时推导的。

讨论指出该行为虽符合语言设计，但易误导开发者。若想获取实际底层类型，应显式使用 `Swift.type(of:)` 和 any 关键字或结合类型转换，例如：

```swift
print(type(of: s.value as Any))  // 输出 S
```

社区讨论建议可能通过改进文档或静态警告提升此类易错用法的可发现性，避免初学者或跨语言用户踩坑。

## 推荐博文

[在 iOS 中调用 GPU 算力：加速你的应用性能](https://blog.csdn.net/Myqijiahai/article/details/145828195/ "在 iOS 中调用 GPU 算力：加速你的应用性能")

**摘要：** 随着移动设备性能的不断提升，GPU 不再只是图形渲染的工具，它在 iOS 应用中的角色也越来越重要。通过调用 GPU 的强大并行计算能力，开发者可以显著提升应用在图像处理、机器学习和科学计算等场景中的性能与效率。

本文系统介绍了在 iOS 中调用 GPU 算力的可行路径，包括底层的 Metal 框架以及更高层的 Core ML 集成方式。Metal 允许开发者直接操作 GPU，灵活实现高性能的通用计算任务，而 Core ML 则提供了更为简洁的方式，将 GPU 加速无缝应用于机器学习模型的推理过程。借助这些工具，开发者不仅能缩短计算时间，还能有效提升应用响应速度，改善用户体验，甚至优化设备的能耗表现。

文章还结合图像处理、模型推理和数值计算等实际应用场景，展示了 GPU 加速在移动开发中的巨大潜力。总体而言，掌握 GPU 调用技术正成为 iOS 开发者提升应用性能的重要途径。

[音视频基础能力之 iOS 视频篇（一）：视频采集](https://juejin.cn/post/7437456956077654055/ "音视频基础能力之 iOS 视频篇（一）：视频采集")

**摘要：** 本文是“音视频基础能力”系列文章的第一篇，聚焦于 iOS 平台下的视频采集实现。视频采集作为音视频处理流程的起点，其核心任务是从摄像头获取原始图像数据，为后续的编码、渲染、传输等操作奠定基础。

文章首先介绍了媒体数据在 iOS 中的封装方式，即 `CMSampleBuffer` 的结构与用途，并从权限申请、设备初始化、参数配置、数据输出等方面详细解析了使用 AVCaptureSession 进行视频采集的完整流程。文中还涵盖了如分辨率与帧率设置、数据格式选择、输出代理回调的处理方式，以及如何从采集到的图像缓冲中提取有效数据。

整体内容深入浅出，既体现出 iOS 音视频开发的工程实践细节，也为后续实现视频编码、渲染等更复杂模块打下了坚实的基础。

[SwiftUI 之 frame 详解](https://juejin.cn/post/6844904201588490253/ "SwiftUI 之 frame 详解")

**摘要：** 这篇文章深入探讨深入探讨了 SwiftUI 中 frame 的实际意义，帮助我们跳脱出 UIKit 思维，重新理解视图布局的本质。在 SwiftUI 中，frame 不再是直接设置视图尺寸的位置参数，而是作为一种“建议”参与布局计算。每个视图会根据父视图提供的建议尺寸，自行决定所需空间，并反馈给父视图，形成一种自下而上的布局机制。

文章通过一系列嵌套 frame 和 background 的例子，展示了 SwiftUI 中布局的灵活性和声明式特点。我们看到不同类型的视图——如只占内容尺寸的 Text、依赖子视图的 VStack、根据父视图扩展的 Shape 等——在布局时会有不同的行为方式，而 Spacer 和 layoutPriority 则提供了对剩余空间和布局冲突的更精细控制。

文中还重点讲解了 fixedSize 和带有 minWidth、idealWidth、maxWidth 的 frame，它们让开发者能更明确地表达视图对尺寸的期望和限制，避免自动布局带来的意外效果。这种方式鼓励我们从“告诉视图该多大”转向“表达视图希望多大”，是 SwiftUI 宣言式编程思想的核心体现。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
