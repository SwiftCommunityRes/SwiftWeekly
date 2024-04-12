## 前言

**本期是 Swift 编辑组自主整理周报的第五十期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

间歇性的努力和蒙混过日子，都是对之前努力的清零。时间永不停歇，社会时刻发展，**Swift社区**也在华丽蜕变！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果被起诉！市值一夜蒸发8000亿元
> 
> 提案：`@isolated(any)` 函数类型
> 
> Swift 论坛：提议 Metatype Keypaths
>
> 推荐博文：使用 Swift 编写 GNOME 应用程序
>
> **话题讨论：** 
> 
> 讨论程序开发的终极结果
>
>**上期话题结果**

![](https://files.mdnice.com/user/17787/c9040b58-737d-4e44-b3b7-fd7f6ade70e8.jpg)

由投票结果可以看出，大部分的朋友已经开始在工作中运用 AI，但是大部分人还是选择 AI 工具作为辅助，不完全依赖。

## 新闻和社区  

### WWDC24：6 月 10 日至 14 日 (太平洋时间)

2024 年 3 月 26 日

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/7DBC4C30-A7D2-4458-8662-CF17FDB886D5/2048.jpeg)

在线加入全球开发者队伍，参与为期一周的技术和创意活动。

亲眼见证 Apple 最新平台、技术和工具的发布，了解如何创建和改进你的 App 和游戏，与 Apple 设计师和工程师互动交流，并与全球开发者社区建立联系。以上活动均免费在线举行。

### 苹果“内忧外患”，库克中国求援

![](https://imagepphcloud.thepaper.cn/pph/image/297/620/745.png)

“我很高兴再次回到中国，我们将继续投资中国市场。”上周末，苹果（Apple）CEO 蒂姆·库克（Tim Cook）现身中国发展高层论坛2024年年会，他对媒体表示，Apple Vision Pro 头显产品年内将于中国市场上市；苹果正持续加大在华研发方面的投资。

中国行五天，库克一边传递信心，一边寻找盟友。3 月 25 日，根据界面·财联社《科创板日报》报道，百度将为苹果今年发布的 iPhone16、Mac 系统和 iOS18 提供 AI 功能。

3 月 26 日，硅谷科技媒体引述消息人士称，苹果已与腾讯达成合作协议，后者将为 Vision Pro 提供多款旗下热门应用。

与此同时，苹果自家后院“起火”。就在 3 月 21 日，库克到访中国的第二天，美国政府起诉苹果公司，指控其非法垄断智能手机市场，该诉讼有可能颠覆这家科技巨头的商业模式和全球消费者使用 iPhone 的方式。

从硅谷“AI大战”，到美国司法部“重拳出击”，苹果在2024年面临多重挑战。1 月 12 日，微软（Microsoft）股价上涨 1% ，市值达到 2.88 万亿美元，再度超越苹果，重回全球第一。这意味着时代的交替，AI 正式成为新的科技生产力。

3 月 27 日凌晨，苹果宣布，将于美国太平洋时间 6 月 10 日- 6 月 14 日举行 “WWDC 2024” 全球开发者大会，今年的主题将是 AI。

开年至今，苹果市值已下跌超过 11% ，库克的压力越来越大。为加速进军 AI 赛道，库克多方求援，此次中国行也不例外。

### 苹果被起诉！市值一夜蒸发8000亿元

2024 年 3 月 22 日

当地时间 3 月 21 日，美国司法部长梅里克·加兰在当天的新闻发布会上表示，美国司法部和十几个州的总检察长对苹果公司提起反垄断诉讼，指控苹果公司利用其对苹果产品硬件和软件的控制垄断手机市场，损害了消费者、开发商和竞争对手公司的利益。

据悉，美国司法部和 16 名总检察长向新泽西州联邦法院提起的诉讼称，苹果公司的反竞争行为超出了其手机和手表正常业务范围。

加兰表示，最高法院将垄断行为定义为“控制价格或排斥竞争的行为”。司法部官员还表示，并不排除利用拆分公司的措施解决这起反垄断诉讼。

苹果公司表示，遵守监管规定会花费大量资金，可能阻止其推出新产品或服务，并可能损害客户需求。

据每日经济新闻报道，当地时间 3 月 21 日，苹果低开低走，收跌 4.09% ，报 171.37 美元，创 2023 年 8 月 4 日以来最大单日跌幅，其市值一夜蒸发超 1100 亿美元（约合人民币 8000 亿元），最新市值 2.6 万亿美元。

![](https://pics3.baidu.com/feed/0b46f21fbe096b6342fb35d07a2e3949eaf8ac7f.jpeg@f_auto?token=c4544b329bce35e1b554f0a04199d03b)

欧盟反垄断调查 4 日认定苹果公司滥用其市场主导地位，阻碍流媒体音乐市场竞争，据此向苹果公司开出逾 18 亿欧元“罚单”。

欧盟委员会当日发布公告通报这一结论。2019 年 3 月，总部设在瑞典斯德哥尔摩的声田公司向欧盟递交“诉状”，指控苹果公司与流媒体音乐应用程序开发者签订的许可协议及《苹果应用商店审核指南》影响流媒体音乐服务竞争，2020 年 6 月欧盟对此发起反垄断调查。

公告显示，欧盟委员会认定苹果公司通过其应用商店在流媒体音乐应用程序分发市场占据主导地位，流媒体音乐应用程序开发者只有进驻苹果应用商店才能吸引苹果手机和苹果平板电脑用户购买他们开发的应用程序，但苹果公司为了自身利益，对流媒体音乐应用程序开发者施加了种种限制。

公告举例，苹果公司限制流媒体音乐应用程序开发者向苹果手机和苹果平板电脑用户告知是否在苹果应用商店以外还有其它购买方式(包括不准附带流媒体音乐应用程序开发者相关网址)，是否还有更便宜的价格以及与苹果应用商店的差价，也不准应用程序开发者联系新增用户，告知苹果应用商店以外的其它购买方式和价格。

欧盟委员会的结论是，苹果公司的种种限制违反欧盟反垄断法条款，对苹果手机和苹果平板电脑用户的利益造成负面影响，对苹果公司维护自身利益“既无必要也不相称”，为此将对苹果公司处以罚款。罚金除基于苹果公司收益，还将一次性追加 18 亿欧元罚款，以确保罚金“具备足够震慑力”。

4 日欧盟公布处罚决定后，苹果公司发表声明，表示欧盟“无视流媒体音乐市场正在蓬勃发展、相互竞争和快速增长”，也未发现消费者受到损害的“可靠证据”，苹果公司将提起上诉。

目前除声田诉苹果案，苹果公司在欧盟还面临其它诉讼和调查，包括缠斗多年的欧盟诉苹果公司巨额逃税案。2016 年，欧盟委员会认定苹果公司利用与爱尔兰政府达成的税收协定大肆逃税，要求苹果公司补缴 130 亿欧元税款，双方将官司一路打到欧盟最高司法机构欧洲法院，至今仍在等待欧洲法院的终裁。(来源：中国新闻社综合报道)

## 提案

### 通过的提案

[SE-0429](https://github.com/apple/swift-evolution/blob/main/proposals/0429-partial-consumption.md "SE-0429") **不可复制值的部分消耗** 提案通过审查。该提案已在 **四十九期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0430](https://github.com/apple/swift-evolution/blob/main/proposals/0430-transferring-parameters-and-results.md "SE-0430") **transferring 参数和结果值的隔离区域** 提案正在审查。

该提案扩展了区域隔离，以启用显式 `transferring` 注释，以表示何时需要参数或结果值位于函数边界的断开区域中。这允许被调用者或被调用者分别在隔离边界上传输不可 `Sendable` 的参数或结果值，或将该值合并到 actor 隔离区域中。

[SE-0431](https://github.com/apple/swift-evolution/blob/main/proposals/0431-isolated-any-functions.md "SE-0431") **@isolated(any) 函数类型** 提案正在审查。

函数的 actor 隔离是其使用方式的重要组成部分。Swift 可以精确推断特定函数声明的隔离情况，但当函数作为值传递时，Swift 的函数类型不够表达。该提案添加了一种新的函数类型，动态携带其函数的 actor 隔离。这解决了语言中的各种表达问题。它还允许更高效地实现诸如标准库的任务创建 API 等功能，并提供更强的语义保证。

### 拒绝的提案

[SE-0426](https://github.com/apple/swift-evolution/blob/main/proposals/0426-bitwise-copyable.md "SE-0426") **BitwiseCopyable** 提案被拒绝。该提案已在 **四十九期周报** 正在审查的提案模块做了详细介绍。

## Swift论坛

1) 提议[Metatype Keypaths](https://forums.swift.org/t/pitch-metatype-keypaths/70767 "Metatype Keypaths")

**内容概括**

Metatype Keypaths

提议称为 “Metatype Keypaths” 的提议由艾米丽特·卡尔和保尔·耶斯基夫提出。该提议旨在允许键路表达式访问类型静态属性，也叫做 metatype keypaths。截至 3 月 18 日，2024 年，该提议正在等待实施。

动机

为了添加 metatype keypaths 到 Swift 语言中，该提议旨在解决挑战并改善语言语义。该提议指出，metatype keypaths 曾在提议 SE-0254 中探讨过，并被推荐作为未来方向。此外，该提议讨论了利用 metatype keypaths 来处理数据库查找以及避免冗长的破解措施的可能性。

提议解决方案

提议解决方案允许键路表达式定义静态属性的引用。该语法允许在根类型声明或键路字面量中包含 `.Type` 的键路表达式。例如，以下示例将被允许:

```Swift
let kp = ".Type" // 这将引用静态属性
```

访问语义

不可变静态属性与不可变实例属性一样，也形成只读的键路。然而，与实例成员不同，可变静态属性的键路将遵守 `ReferenceWritableKeyPath` 协议，因为 metatype 是引用类型。

源代码兼容性影响

该特性将破坏键路表达式引用静态属性之后的源代码兼容性，因为它无法区分 subscript 键路组件的返回类型，如下所示:

```Swift
let kp = ".[42]" // 这将引用subscript
```

采用影响

metatype keypaths 不可逆地添加到旧版本的应用中，并且需要在 Swift 标准库和运行时中进行更改才能充分利用它们。旧版本编译器将支持，但对比操作符(比如 Equatable或 Hashable)对于引用静态属性的键路的正确性将无法保证。

未来方向

该提议提到，未来可能会提出支持只读键路对枚举案例的支持。这个特性将允许键路包含引用 metatypes，使 Swift 语言更接近采用对枚举案例的键路支持。

讨论

该提议引发了一些讨论，开发者分享了他们的想法和建议。有些开发者提出了采用 metatype keypaths 对源代码兼容性的影响，而另一些开发者提出了对 Equatable对metatype keypaths 的行为。

总而言之，提议旨在为 Swift 编程语言提出 metatype keypaths，旨在允许键路表达式访问类型静态属性，解决挑战并改善语言语义。该提议引发了一些讨论，开发者分享了他们的想法和建议。截至 3 月 18 日，2024年该提议正在等待实施。

2) 提议[全局参与者隔离类型的可用性](https://forums.swift.org/t/pitch-usability-of-global-actor-isolated-types/70799 "全局参与者隔离类型的可用性")

**内容概括**

讨论围绕全局参与者隔离类型的可用性展开，特别关注涉及静态属性的场景。值得注意的是，属性的全局参与者隔离不仅仅取决于它是否是常量（“let”）以及是否符合 “Sendable”。相反，需要强调的是静态变量的初始值设定项也不能是全局参与者隔离的。 该提案引起了人们对公共 API 上全球参与者隔离的隐含推论的担忧，并提倡显式声明。

关于协议，需要澄清的是，协议上的全局参与者隔离并不一定意味着符合类型会改进 “Sendable”。协议的隔离适用于其所有要求，但不强制将一致性类型与该全局参与者隔离。 如果需要 `Sendable`，建议在协议中明确写入。

该提案还讨论了如果初始值为 “Sendable”，则抑制与不安全静态变量相关的警告。然而，它是作为对现有提案的单独修订而提议的，而不是当前讨论的一部分。

此外，对话还涉及将全局参与者隔离类型的实例传递给泛型函数及其对子类化模式的影响。有人反对改变限制这种使用的规则，以支持更多的子类化模式。

最后，讨论简要讨论了对隔离检查不健全的担忧，并邀请了示例（如果有）。总的来说，对话的重点是完善 Swift 中全局参与者隔离的规则和含义，强调声明的清晰度和明确性。

3) 提议[Hummingbird](https://forums.swift.org/t/pitch-hummingbird/70700 "Hummingbird")

**内容概括**

Hummingbird 轻量级，可扩展的，灵活的 HTTP 服务器框架，编写于 Swift 语言。它提供了一个用于构建轻量级服务器的服务器框架，但它可以被扩展以支持你需要的任何复杂的服务。如果你不需要 TLS、HTTP2、WebSockets 等功能，那么就不要包含它们。但如果你需要它们，那么也可以使用它们。

目前正在开发的版本 2.0 的 Hummingbird 包括完整的 Swift 并发解决方案基于 SwiftNIO 的 NIOAsyncChannel，它带来了结构化并发所带来的所有优势，包括取消任务，任务本地变量和本地推理等。此外，它利用苹果最近发布的 HTTP 类型，并与最近发布的结构化并发基于 ServiceLifecycle 的版本集成。

一个简单的 Hummingbird 应用程序可以通过创建路由器，添加路由到其中以及创建一个使用该路由的应用来实现。Hummingbird 支持路由中间件 TLS、HTTP2、指标、跟踪、文件服务等功能。还有一些相关包可以提供身份验证框架，与 Fluent 和 Redis 集成以及 WebSockets 支持。你可以查看 Hummingbird 的文档了解支持的详细信息。

目前已经在一个小服务中使用过 Hummingbird，并且已经很好地工作了。另一个明显的候选人是另一个小服务。简单而强大的框架，已经在我们的小服务中使用了版本 2，迄今为止没有任何问题。

4) xx[扩展 Any](https://forums.swift.org/t/extending-any/70762 "扩展 Any")

**内容概括**

讨论的重点是扩展 Swift 中的“Any”类型以及由于其动态特性而遇到的挑战，特别是在使用桥接到 Swift 的 Objective-C 框架时。一种建议的解决方法是创建一个空协议并在需要时添加一致性。但是，此解决方法不能解决直接遇到 “Any” 的情况。

由于 Objective-C 桥接而导致实际类型未知的场景，需要扩展 “Any”，从而导致允许哪些操作的不确定性。讨论强调了此类扩展对于提供有关错误消息或其他上下文中的类型的描述性信息的重要性。

人们对允许 “任何” 扩展的潜在影响表示担忧，包括意识形态辩论和构建时间等实际考虑因素。尽管之前对此主题进行了讨论，但当前的讨论中没有找到明确的解决方案或巧妙的解决方法。

**结论：**

论坛讨论显示，在Swift中扩展 `Any` 是一个有争议的话题。有些开发者认为应该允许，而有些开发者认为有办法可以解决这个问题。最终决定允许扩展 `Any` 取决于苹果的决定和诸如构建时间这样的考虑。

5) 讨论[严格并发与苹果框架相互不兼容，尤其是针对 var 静态成员](https://forums.swift.org/t/strict-concurrency-incompatible-with-apple-frameworks-re-var-static-members/70764 "严格并发与苹果框架相互不兼容，尤其是针对 var 静态成员")

**内容概括**

严格并发与苹果框架不兼容

Swift 6 引入了严格并发模式，但却引起了与苹果框架兼容性问题。有些苹果框架声明静态成员使用了 `var` 而不是 `let` 或者 `const` 这样使得静态成员变化，与Swift并发模式不兼容，这导致了当访问这些成员时产生警告，称为“不兼容并发模式”。

Wade Tregaskis 是一个开发者，他正在尝试使用苹果框架，比如 CoreImage，但却遇到了兼容性问题。他试图访问某些常量，但是却遭遇警告称为 “不兼容并发模式”。 Tregaskis 寻找办法来绕过这个问题，比如忽略警告或者使用一个C封装把变量声明为常量。

开发者社区也给出了建议，比如希望苹果能审计他们的SDK并在即将到来的 Swift 6、Xcode 16 及 2024 OS 版本中修复这些警告。另一个开发者叫做 Jon Shier 建议苹果可以添加类型或者标记来禁用并发检查这些值。

Tregaskis 担心到即将到来的六月份 Swift 6 发布，因为苹果尚未完成他们框架的工作，而另一个开发者叫做 Thomas Goyne 则表示很难判断苹果框架的状态直到首次测试版发布。

总之，这个问题给了很多开发者带来很多烦恼，希望苹果能在即将到来的版本中解决这个问题。

6) 讨论[Swift 并发：将已完成的任务保留为缓存对象？](https://forums.swift.org/t/swift-concurrency-keeping-completed-tasks-as-cache-objects/70796 "Swift 并发：将已完成的任务保留为缓存对象？")

**内容概括**

讨论围绕在 Swift 并发中缓存已完成的 “Task” 对象，特别是从远程文件生成 “CGImage” 对象的任务。 所提出的方法涉及将 “Task” 对象直接存储在缓存中，而不是提取并存储生成的 “CGImage” 对象。

提供的代码片段演示了 “Task” 对象如何存储在 Actor 内的 “activeTasks” 字典中。 当发出图像请求时，系统会检查相应 URL 的任务是否已处于活动状态。 如果是，它立即返回任务的值。否则，它会创建一个新任务来生成图像。

人们担心将已完成的 “任务” 对象保留在内存中的效率和开销。 虽然我们承认保留 “Task” 对象并不会无限期地保留闭包，但一旦任务完成，是否会释放所有执行上下文开销是不确定的。

讨论承认结构化并发是首选，但指出在这种情况下它不是一个选项。 尽管缺乏明确的确认，但值得注意的是，Swift 文档表明保留任务对象并不会无限期地保留闭包，这可能使缓存已完成任务的方法变得可行。 然而，对于 “Task” 对象在完成后保留的任何其他引用仍然存在担忧。

总的来说，虽然所提出的缓存 “Task” 对象的方法似乎是合理的，但关于其效率和潜在开销的讨论和不确定性仍在继续。

7) 讨论["隔离与异步let"](https://forums.swift.org/t/isolation-and-async-let/70745 "隔离与异步let")

**内容概括**

讨论围绕 Swift 中 “async let” 的行为，特别是它目前无法强制执行隔离控制。 发帖者对通过 Closure 隔离控制和“@isolated(any)”函数类型等提案不断改进 Swift 隔离控制的努力表示赞赏。 他们强调了启用 “async let” 来推断隔离的重要性，并且其行为与建议的任务 API 类似，因为它将与 Swift 并发模型的方向保持一致。

讨论表明，修复 “async let” 的行为不一定需要单独的进化提案，因为它可以被视为对现有行为的改进。 他们引用了之前讨论中的一句话，表明不需要新的语言机制就可以实现这样的修复。

虽然讨论承认将 “async let” 与建议的任务 API 保持一致的重要性，但值得注意的是 “async let” 的修复并不严重依赖这些建议，并且可以独立实现。 然而，有人提到，将 “async let” 的更改时间与其他并发相关的增强功能保持一致将是有益的，尽管对于调度决策没有做出任何保证。

## 推荐博文

[使用 Swift 编写 GNOME 应用程序](https://www.swift.org/blog/adwaita-swift/ "使用 Swift 编写 GNOME 应用程序")

**摘要：**  这篇博客介绍了使用 Swift 编写 GNOME 应用程序的方法，并重点介绍了 Adwaita for Swift 这一工具。 Swift 由于其清晰的语法、静态类型和特殊功能而非常适合创建用户界面。 Adwaita for Swift 利用 Swift 的特性为开发 GNOME 平台应用程序提供直观的界面。

文章展示了使用 Adwaita for Swift 的代码示例，并探讨了其优点，如声明性、易用性和可读性。此外，还介绍了 Adwaita for Swift 在跨平台应用开发和应用发布方面的优势，以及如何参与该项目。

[Swift  AttributedString 常见使用方法](https://juejin.cn/post/7347947619744743451/ "Swift AttributedString 常见使用方法")

**摘要：**  这篇博客介绍了在 swift 开发中常见的 `AttributedString` 的使用方法。通过示例代码展示了如何设置文本的字体大小、颜色、背景颜色，以及如何添加下划线等样式。此外，还介绍了如何拼接不同样式的文本，并提供了一个整合常用文本属性的类，使得使用 `AttributedString` 更加便捷。通过这些方法，可以轻松实现丰富的文本样式效果。

[在 SwiftUI 中如何构建异步 Button ](https://swiftwithmajid.com/2024/03/26/building-async-button-in-swiftui/ "在 SwiftUI 中如何构建异步 Button ")

**摘要：**  文章介绍了如何在 SwiftUI 中使用 Swift Concurrency 的异步功能来创建异步按钮。作者展示了如何通过简单的示例来创建一个按钮，该按钮在每次按下时都会启动一个异步任务。讲解了如何对按钮进行改进，以在任务执行期间禁用按钮，以及如何将按钮的逻辑提取到一个专用的视图中。

文章的最后讲解了如何在简单的示例中使用触发值模式来取消任务。本文深入探讨了 SwiftUI 中异步任务的处理方式，为开发人员提供了有关使用 Swift Concurrency 构建交互式用户界面的宝贵指导。

## 话题讨论

iOS 开发经历了从 OC 到 Swift，安卓开发经历了从 java 到 Kotlin，移动端从原生到跨平台，后端的各种 IDE 开发工具到如今的 IntelliJ IDEA 统一，前端的各种 IDE开发工具也统一使用了 VSCode。不难发现，所有的变化都在朝着更简单，更快捷，更兼容，更统一的方向发展。**不妨大胆猜测一下，你认为将来哪一项会实现统一呢？**

1. 编程语言统一，终有一天会诞生一种语言能够胜任所有开发工作。
2. IDE开发工具统一，终有一天会诞生一款开发工具能够胜任所有开发语言。
3. 程序员统一，终有一天程序员会等于全栈开发。
4. 以上选项均可实现。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。