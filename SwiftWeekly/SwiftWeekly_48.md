## 前言

**本期是 Swift 编辑组自主整理周报的第四十八期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

倚高山之巅，方见大河奔涌。读**Swift社区**，便知书海浩瀚。渺小与博大，总是同伴己身！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果突然不造车了，雷军：非常震惊！分析师：马斯克或是最大赢家
> 
> 提案：自定义 SerialExecutor 的隔离检查
> 
> Swift 论坛：讨论在整个应用程序中共享变量
>
> 推荐博文：使用 MLX 和 Swift 进行设备端机器学习研究
>
> **话题讨论：** 
> 
> 如果 2024 年购车，你选择买那种车？
>
>**上期话题结果**

![](https://files.mdnice.com/user/17787/82e1c543-c37a-4a5a-8b65-3161c0661e4d.jpeg)

我认为应该鼓励人们在面对工作中的挑战和不如意时保持乐观和积极的态度。被裁员可能是一个人职业生涯中的一次挑战，但也是一个机会去探索新的职业道路和发展方向。因此，即使面对困难，也应该以积极的心态去应对，寻找新的机会和可能性。

## 新闻和社区

### 苹果突然不造车了，雷军：非常震惊！分析师：马斯克或是最大赢家

苹果的造车项目最终还是黄了。

于 2014 年正式启动的“泰坦计划”曾经承载着苹果的美好憧憬：分食全球近两千亿美元的电动车市场。然而，十年过去，苹果却未能让其野心开花结果，项目在高管更迭和试驾事故等波折中反复挣扎，并于 2 月 27 日走向终局。

据彭博社，放弃“泰坦计划”是由苹果首席运营官杰夫·威廉姆斯 (Jeff Williams) 和负责造车项目的副总裁凯文·林奇 (Kevin Lynch) 共同做出的。随着造车项目被叫停，相关项目小组（内部称为“特殊项目小组”或 SPG）的近 2000 名员工也面临着未知的前路。

据悉，SPG 部分人员将在高管约翰·詹南德雷亚 (John Giannandrea) 的领导下专注于生成式AI项目。而其他数百名成员（其中许多是硬件工程师和汽车设计师）要么可以在苹果内部申请另一份工作，要么将被解雇。目前尚不清楚将有多少人会被裁员。

从整个大环境看，苹果大举砍掉造车项目的背后也是电动车市场的转冷。据彭博社预测，2024 年美国电动汽车销量的增长将不超过 9%，而过去三年的复合年增长率高达 65%。苹果的这一决策公开后，特斯拉 CEO 马斯克在X上进行了回应。在竞争激烈的市场环境中，特斯拉作为行业领头羊，或许会是苹果此次抉择的最大受益者。

“泰坦计划”折戟之后，苹果能否如愿在生成式AI的天地中重塑其辉煌，外界只能拭目以待。

![](https://tmp-file-1252627319.cos.ap-shanghai.myqcloud.com/wx_article_img/CFF20LXzkOzP9RNPkLFCxvHE42MgHicib2R858blKVJZiciahvFicxniadhdAtpD5UCpmSOJoUSuHGqib49WOmcZvT2kg.jpg)

对此，正在造车的小米创始人雷军在微博发文称：看到这个新闻，非常震惊！小米战略是“人车家全生态”，我们深知造车难度，3 年前依然做了无比坚定的战略选择，认认真真为米粉造一辆好车！”

![](https://tmp-file-1252627319.cos.ap-shanghai.myqcloud.com/wx_article_img/CFF20LXzkOzP9RNPkLFCxvHE42MgHicib21wa54X6iaY0YhPkkwOjdw0b4oJnkJScJrd5SQEpQXUtQUWtsCCYlSgg.jpg)

理想汽车 CEO 李想 2 月 28 日在微博发文称，苹果放弃造车，选择聚焦人工智能是绝对正确的战略选择，时间点也合适。李想表示，战略层面，新业务能聚焦一个，就决不做两个。另外，选择那个最大的，以及距离自己核心优势最近的，知难而上大概率不是好战略。

![](https://tmp-file-1252627319.cos.ap-shanghai.myqcloud.com/wx_article_img/CFF20LXzkOzP9RNPkLFCxvHE42MgHicib2aCenHKWIy1HLmD5Mcn2JBPYXwzVht1OtfKxJicCsIf3iagsOb2eF1rIQ.png)

特斯拉首席执行官埃隆·马斯克则在社交媒体网站X上发了一个敬礼的表情符号和一支香烟。有中国网友戏称，马斯克的“香烟”表情是在给苹果汽车“上香”。

![](https://tmp-file-1252627319.cos.ap-shanghai.myqcloud.com/wx_article_img/CFF20LXzkOzP9RNPkLFCxvHE42MgHicib218MvDL7RfngK5JQRQXZ5Z9rOXAibuc3uib47BgibI9407b6N40bP1GibYA.png)

### 你会爱上的开发者活动

2024 年 2 月 14 日

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/02C54728-A44D-49AF-923D-EC54D9EBF3DC/2048.jpeg)

Apple 开发者活动正在火热进行中，让我们来看看具体都有哪些活动：

参加 App Store 专家主持的在线讲座：了解如何如何最大程度地减少用户流失并赢回订阅者。
共庆国际妇女节：参加在班加罗尔、库比蒂诺、上海、新加坡、悉尼和东京举办的特别线下活动。
参加世界各地的 Apple Vision Pro 开发者实验室 (库比蒂诺、伦敦、柏林、新加坡、悉尼和东京皆有举办)：测试和完善你的 App，让它们在无边的空间画布中提供出色的体验。
与 Apple 团队成员会面，探讨为遵守《数字市场法》而对在欧盟分发的 App 产生影响的 iOS、Safari 浏览器以及 App Store 的变更。
全年我们都将以线上和线下的形式，举办各种涵盖多种语言的活动。

## 提案

### 通过的提案

[SE-0422](https://github.com/apple/swift-evolution/blob/main/proposals/0422-caller-side-default-argument-macro-expression.md "SE-0422") **表达式宏作为调用方默认参数** 提案通过审查。该提案已在 **四十七期周报** 正在审查的提案模块做了详细介绍。

[SE-0421](https://github.com/apple/swift-evolution/blob/main/proposals/0421-generalize-async-sequence.md "SE-0421") **推广 AsyncSequence 和 AsyncIteratorProtocol 的效果多态性** 提案通过审查。该提案已在 **四十七期周报** 正在审查的提案模块做了详细介绍。

[SE-0420](https://github.com/apple/swift-evolution/blob/main/proposals/0420-inheritance-of-actor-isolation.md "SE-0420") **继承 actor 隔离性** 提案通过审查。该提案已在 **四十七期周报** 正在审查的提案模块做了详细介绍。

[SE-0419](https://github.com/apple/swift-evolution/blob/main/proposals/0419-backtrace-api.md "SE-0419") **Swift Backtrace API** 提案通过审查。该提案已在 **四十七期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0423](https://github.com/apple/swift-evolution/blob/main/proposals/0423-dynamic-actor-isolation.md "SE-0423") **非严格并发上下文中的动态 actor 隔离执行** 提案正在审查。

许多 Swift 程序需要与用 C/C++/Objective-C 编写的框架进行交互，这些框架的实现无法参与静态数据竞争安全性。同样，许多 Swift 程序依赖项尚未采用严格的并发性检查。`@preconcurrency import` 语句会降级与并发相关的错误消息，因为程序员无法解决的根本问题在其中一个依赖项中。为了在与预并发依赖项一起工作时加强 Swift 的数据竞争安全性保证，该提案在运行时为同步隔离函数添加了 actor 隔离检查。

[SE-0424](https://github.com/apple/swift-evolution/blob/main/proposals/0424-custom-isolation-checking-for-serialexecutor.md "SE-0424") **自定义 SerialExecutor 的隔离检查** 提案正在审查。

SE-0392（自定义 Actor 执行器）增加了对自定义 actor 执行器的支持，但其支持还不完整。像 `Actor.assumeIsolated` 这样的安全检查在通过任务在 actor 上运行代码时能够正常工作，但当代码被安排在 actor 的执行器上通过其他机制运行时则无法正常工作。

例如，如果一个 actor 使用串行 `DispatchQueue` 作为其执行器，那么使用 `DispatchQueue.async` 直接将函数调度到队列时，无法使用 assumeIsolated 来断言 actor 当前是否被隔离。该提案通过允许自定义 actor 执行器为这些安全检查提供自己的逻辑来解决此问题。

## Swift论坛

1) 提议[解决 DistributedActor 协议（针对服务器/客户端应用程序）](https://forums.swift.org/t/pitch-resolve-distributedactor-protocols-for-server-client-apps/69933 "解决 DistributedActor 协议（针对服务器/客户端应用程序）")

**内容大概**

讨论了解决 Swift 中服务器/客户端应用程序的 DistributedActor 协议的提案。 该提案旨在促进分布式系统之间的通信，同时仍然有效地利用参与者。 发帖人赞赏所提出的优雅解决方案，特别强调了宏的使用。 他们提出了有关在客户端实现分布式系统的简化版本、跨不同语言创建共享 API 的潜力的问题，并询问有关类似概念的现有框架或研究论文。 

这篇文章还提到了分布式 Actor 的多功能性，并引用了 Akka 和 Orleans 的例子，表明它们适合实时和耦合系统。 此外，它还提到了 2023 年 Google 研究人员发表的一篇论文，该论文倡导受参与者模型启发的分布式系统，强调了位置透明的好处。

根据这个建议，可以编写以下内容：

```Swift
// API module
import Distributed

@DistributedProtocol
public protocol Greeter: DistributedActor
    where ActorSystem: DistributedActorSystem<any Codable> {

  distributed func greet(name: String) -> String
}
```

```Swift
// Client module
import API // declared Greeter
import Distributed

let someActorSystem = // <the actor system you're using>
let remote = try $Greeter.resolve(id: id, using: someActorSystem)

let reply = try await remote.greet(name: "Caplin")
print(reply) // Dzień dobry, Caplin!
// oh, we didn't know the remote implementation is PolishGreeter!
```

这允许开发人员发布具有协议描述的 API 包，并对客户端应用程序完全隐藏服务器实现类型。

2) 提议[按位复制标记协议](https://forums.swift.org/t/pitch-bitwisecopyable-marker-protocol/69943 "按位复制标记协议")

**内容大概**

该提案建议在 Swift 中引入一种名为 BitwiseCopyable 的新标记协议，以识别可以有效复制、移动和销毁的类型。 该协议将允许通过启用直接内存操作（例如 memcpy）来优化低级代码。 通过将泛型函数限制为 BitwiseCopyable 类型，开发人员可以减少开销并提高性能，特别是对于涉及批量内存复制的操作。 

该提案概述了标准库中的基本类型和开发人员定义的类型如何符合 BitwiseCopyable，并由编译器推断某些情况下的一致性。 但是，对于其他模块中定义的类型或可能并不总是满足 BitwiseCopyable 要求的类型，需要显式一致性。 此外，讨论还深入探讨了泛型类型的 BitwiseCopyable 一致性的可确定性以及库演化的注意事项。

完整的提案可以在这里找到：[BitwiseCopyable](https://github.com/apple/swift-evolution/pull/2314/)

3) 提议[不可复制值的分段消耗](https://forums.swift.org/t/pitch-piecewise-consumption-of-noncopyable-values/70045 "不可复制值的分段消耗")

**内容大概**

该提案建议放宽对某些不可复制类型的限制，以允许它们在特定场景中分段使用，旨在促进 Swift 代码中对不可复制值的更自然的操作。 目前，处理聚合中的不可复制字段面临着挑战，例如在不可复制的 Pair 类型中交换值等函数的编写困难。 所提出的解决方案建议允许在逐个字段的基础上使用非弹性、不可复制的聚合而不使用反初始化器，从而实现诸如在 Pair 内交换值之类的操作。 然而，该提案有意保留了限制：它不支持带有反初始化器的聚合的部分消耗或已消耗字段的重新初始化，并且弹性聚合永远不能被部分消耗。 讨论还包括对源代码破坏性更改的考虑以及了解部分消耗的类型布局的必要性。

完整的提案可以在这里找到：https://github.com/apple/swift-evolution/pull/2317

4) 讨论[如何识别/关联 swiftinterface 声明与原始声明？](https://forums.swift.org/t/how-to-identify-associate-swiftinterface-declarations-with-original-declarations/70342 "如何识别/关联 swiftinterface 声明与原始声明？")

**内容大概**

讨论围绕识别 `.swiftinterface` 文件中的声明并将其与其原始声明关联起来，主要是为了提取有关 Swift 库中 `@_spi` 属性的信息。 但是，将 .swiftinterface 文件中的完整签名映射到 `lib/SymbolGraphGen` 发出的部分签名存在不确定性，因为它缺乏 `@_spi` 意识。 提出了各种建议，包括扩展 SymbolGen 以发出相关信息或使用索引存储来弥合 USR 和解析的源位置之间的差距。 对话还涉及为 Swift 包生成文档以及与工具链兼容性相关的挑战。 

此外，还考虑使用夜间工具链编译包，同时使用不同版本的工具链发出符号图 JSON。 总的来说，讨论探讨了潜在的解决方法和解决方案，以解决将 Swift 接口声明与其原始对应项关联的问题。

5) 讨论[在整个应用程序中共享变量？](https://forums.swift.org/t/sharing-variables-throughout-the-application/70352 "在整个应用程序中共享变量？")

**内容大概**

这篇文章讨论了 Swift 应用程序中全局变量的使用，特别是在多个视图之间共享数据。 用户创建一个 Global.swift 文件，在其中使用 @State 属性包装器声明一些变量。然后他们询问是否正确使用这些全局变量。 

然而，出于安全考虑，另一位用户建议不要将用户凭据等敏感信息存储在全局变量中，并建议使用用户的钥匙串。 此外，他们警告不要共享可变状态，并建议研究 @EnvironmentObject 和 @Environment 以在 SwiftUI 中的视图之间共享通用逻辑。

6) 宣布[类型安全的日历计算](https://forums.swift.org/t/announcing-time-1-0-0-type-safe-calendar-calculations/70366 "类型安全的日历计算")

**内容大概**

该公告推出了 Time 1.0.0，这是一个专为 Swift 中类型安全日历计算而设计的包。 它庆祝其前身 Time 0.9.0 一周年，并强调其已升级至 1.0.0 版本。 Time 提供了广泛的日期和时间操作功能，强调安全性和便利性。 主要功能包括获取设备时间、舍入时间值、按特定间隔提前时间、检索日历信息以及格式化时间数据。 

Time 通过 Swift 的类型系统确保正确性，并为无效操作提供错误处理。 它可在 GitHub 上获取，并具有有关 Swift 包索引的全面文档。 此外，Time 还提供高级功能，例如创建自定义时钟、监听时间变化、时区和区域设置之间的转换、计算日历值之间的差异等等。 总体而言，Time 简化了日期和时间操作，同时确保准确性和安全性。

7) 讨论[迁移 ThreadSafe 类以使用最新的并发](https://forums.swift.org/t/migrating-a-threadsafe-class-to-use-modern-concurrency/70349 "迁移 ThreadSafe 类以使用最新的并发")

**内容大概**

讨论了寻求迁移线程安全类的指导，该类利用异步写入和同步读取的同步技术，以使用现代并发技术，例如 Swift Actors。 他们提供了 A 类的代码示例，该类通过共享队列将任务发送到另一个类（缓存）来同步读取和异步写入。 他们询问在迁移到 Actor 或现代并发时如何在类之间执行类似的同步。 A 类（`ThreadSafeClassA`）包含读取和写入消息的方法，而 B 类（`ThreadSafeClassB`）则异步处理消息检索。 用户有兴趣在迁移过程中维持这种同步模式。

## 推荐博文

[使用 MLX 和 Swift 进行设备端机器学习研究](https://www.swift.org/blog/mlx-swift/ "使用 MLX 和 Swift 进行设备端机器学习研究")

**摘要：**  文章介绍了使用MLX和Swift进行设备上机器学习研究的新方法。 Swift 编程语言具有与 Python 类似的易用性和高级语法，同时又具有类似 C++ 的编译语言的速度。 MLX 是专为在苹果芯片上进行机器学习研究而设计的数组框架，提供了硬件加速和自动微分等关键功能。 

MLX Swift 将 MLX 扩展到 Swift 语言，为机器学习研究人员提供了一个全面的实验平台。该平台包括全面的 Swift API、高级神经网络和优化器包，以及文本生成和MNIST训练等示例。这一步骤标志着ML研究人员可以更轻松地在苹果设备上进行机器学习实验，并且所有组件都以MIT许可证开放源代码。通过本文，读者可以了解到如何快速开始使用 MLX Swift ，并利用其在机器学习研究中的潜力。

[Swift 字面量](https://juejin.cn/post/7340464722279907339/ "Swift 字面量")

**摘要：**  这篇博客主要讨论了 Swift 中的字面量（Literal）的概念及其在编写代码时的重要性。文章以 Franz Boas 在 1911 年的观察为引子，指出不同语言对于相同概念的命名方式可能存在差异，从而呈现出语言相对性的现象。Swift 提供了多种类型的字面量，包括标准字面量和自定义类型支持的字面量初始化方法。通过示例展示了如何自定义类型支持字面量初始化，以及如何扩展已有类型以支持不同类型的字面量初始化。

文章还介绍了未来可能出现的一些发展趋势，如原始字符串字面量和通过强制执行的字面初始化，以及它们对 Swift 语言和开发者的影响。最后，强调了编程语言中的词汇选择对开发者的思维方式和代码编写方式的影响，鼓励开发者利用 Swift 提供的特性使代码更加自然和高效。

[在 Swift 中创建服务层](https://juejin.cn/post/7340471458949644351/ "在 Swift 中创建服务层")

**摘要：**  本文介绍了在Swift中创建服务层的方法。服务层允许将与框架和 API 相关的逻辑转移到它们自己的类或结构体中，通过创建协议并实现方法和属性，可以使代码更具可重用性、可测试性和可读性。

示例项目使用了 UIKit、MVVM 设计模式和 Combine 框架的一部分。文章通过代码示例详细说明了如何创建服务层、编写单元测试以及实现模拟服务等内容。通过添加服务层，可以使代码库保持模块化，并从可重用性、单元测试覆盖率、可读性和可替换性中受益。

## 话题讨论

如果 2024 年购车，你选择买那种车？

* 油车
* 混动
* 电车

欢迎在文末留言参与讨论。


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
