## 前言

**本期是 Swift 编辑组整理周报的第四十二期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

最热烈的火焰，封锁在最沉默的火山深处。最朴实纯真的智慧，就浅藏在**Swift社区**里！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果 CEO 库克透露接班计划，希望继任者来自公司内部
> 
> 提案：Typed throws 提案正在审查
> 
> Swift 论坛：讨论 MainActor 上的上下文切换和线程数
>
> 推荐博文：SwiftUI 中的作用域动画
>
> **话题讨论：** 
> 
> 那个活在记忆中的帅气少年，已慢慢变成了大叔模样。岁月无情，那么各位程序猿和攻城狮们，你们心中最担心的容貌变化是哪一个呢？

**上期话题结果**

![](https://files.mdnice.com/user/17787/14af3e92-0eee-4ed1-8bd1-06d37adf3ca9.jpg)

这个结果反映了员工在工作和生活平衡方面的个体差异。一些人更注重通勤时间的利用效率，而另一些人则更注重在自己的房子中获得更大的舒适感和生活空间。这对公司提供灵活的工作安排和住房福利可能有一定的启示。

## 新闻和社区

### 苹果 CEO 库克透露接班计划，希望继任者来自公司内部

11 月 21 日消息，63 岁的苹果公司首席执行官蒂姆库克近日透露，苹果已经为他的继任者做好了 " 非常详细 " 的接班计划，但他也表示，他目前还没有离开苹果的打算。

![](https://zkres2.myzaker.com/202311/655cd4718e9f0911b077b37a_1024.jpg)

在 BBC Sounds 播客《Dua Lipa: At Your Service》的一次 45 分钟的采访中，库克向歌手 Dua Lipa 坦承，他不知道自己还会在苹果待多久。" 我爱这里，" 他说，回顾了自己在苹果的 25 年，" 我无法想象没有苹果的生活，所以我还会在这里一段时间。"
但是，当被问及苹果是否有任何 CEO 接班计划时，库克称：" 我们是一家相信制定接班计划的公司，所以我们有非常详细的接班计划。因为总会发生一些不可预测的事情。我明天可能会走错路边，希望不会发生这种事，我祈祷不会。"

Dua Lipa 问道：" 你能说出谁是接班人吗？" 库克回答称，" 我不能说，但我想说的是，我的工作是找到几个有能力接班的人，我真的希望下一任首席执行官是来自苹果内部的人。所以这是我的角色：让董事会有几个人可以选择。"

在这次采访中，库克讲述了自己作为苹果 CEO 的一天，分享了他在阿拉巴马州一个蓝领家庭长大的经历，以及最终成为苹果 CEO。(文章来源：IT 之家)

### 消息称苹果自研 5G 调制解调器开发再“难产”，将推迟到 2026 年

IT之家 11 月 17 日消息，彭博社的马克・古尔曼（Mark Gurman）发布最新一期 Power On 时事通讯，表示苹果的自研 5G 调制解调器计划遇到麻烦。

IT之家注：苹果公司于 2019 年收购了英特尔大部分智能手机业务，并开始认真开发自己的调制解调器硬件，但开发过程并不顺利。

![](https://pics6.baidu.com/feed/64380cd7912397dd18a035baa6f4a9bad1a28733.jpeg@f_auto?token=fab61a6b05898db7419af695da5bd6d5)

苹果公司原本计划 2024 年推出自研 5G 调制解调器芯片，并率先装备在 iPhone SE 机型上，但随后有消息称延后到 2025 年。

古尔曼在最新时事通讯中表示，苹果计划再次延后推出自研 5G 调制解调器芯片时间，目前已经推迟到 2025 年年底或者 2026 年年初。

古尔曼在文章中透露，苹果的自研 5G 调制解调器芯片目前还处于早期阶段，可能落后竞争对手“数年”时间。

消息称苹果目前自研的 5G 调制解调器芯片并不支持 mmWave 技术，目前主要存在 2 个难题：第一是英特尔遗留代码，需要苹果重写，而添加新功能可能会中断现有功能；第二是开发芯片过程中，要小心绕过不侵犯高通的专利。

一位苹果员工表示：“我们接手了英特尔的一个失败项目，我们盲目自信地认为可以成功”。据说苹果的硬件技术部门在众多项目中“捉襟见肘”，各项资源没有向其倾斜，导致难以解决错误。

## 提案

### 正在审查的提案

[SE-0413](https://github.com/apple/swift-evolution/blob/main/proposals/0413-typed-throws.md "SE-0413") **Typed throws** 提案正在审查。

Swift 的错误处理模型允许标记为 throws 的函数和闭包指示它们可以通过引发错误来退出。错误值本身始终被类型擦除为 `any Error`。这种方法鼓励以通用方式处理错误，并且对于大多数代码来说仍然是一个很好的默认选项。然而，有一些情况下类型擦除是不幸的，因为它不允许在可能且有必要处理所有错误的狭窄位置进行更精确的错误类型化，或者在类型擦除的成本很高的情况下。

该提案引入了指定函数和闭包只能引发特定具体类型错误的能力。

## Swift论坛

1) 提议[多语句 if/switch/do 表达式](https://forums.swift.org/t/pitch-multi-statement-if-switch-do-expressions/68443 "多语句 if/switch/do 表达式")

**内容概括**

该提案基于 SE-0380，引入了“then”关键字来处理 if 或 switch 表达式中的多个语句，从而促进更清晰的语法并提高可读性。 “then”关键字允许这些表达式每个分支有多个语句，从而简化了以前需要立即执行闭包或显式键入的场景。 此外，它还引入了“do”表达式，使代码结构更加清晰，并处理 API 需要价值创建和后续突变的情况。

该提案概述了详细设计，引入“then”作为上下文关键字，指定其在 if、switch 和 do 表达式中的用法。 它强调了解析歧义和可能的替代方案，探索诸如在 Swift 中使用最后一个表达式或受 Rust 启发的分号终止等变体，同时讨论它们对代码可读性和语言设计的影响。

总体而言，该提案旨在增强 Swift 的表达能力而不影响 ABI 稳定性，并邀请讨论引入的“then”关键字的替代方案和潜在的解析复杂性。

**介绍**

该提案引入了 then 关键字，用于确定单个分支中包含多个语句的 if 或 switch 表达式的值。 它还介绍了 do 表达式。

**动机**

SE-0380 引入了使用 if 和 switch 语句作为表达式的功能。 正如该提案所述，这可以大大改进语法，例如在初始化变量时：

```Swift
let width = switch scalar.value {
    case 0..<0x80: 1
    case 0x80..<0x0800: 2
    case 0x0800..<0x1_0000: 3
    default: 4
}
```

否则需要诸如立即执行闭包或显式类型确定初始化之类的技术。
然而，该提案将让 switch 分支包含多个语句的能力作为未来的方向：

```Swift
let width = switch scalar.value {
    case 0..<0x80: 1
    case 0x80..<0x0800: 2
    case 0x0800..<0x1_0000: 3
    default: 
      log("this is unexpected, investigate this")
      4  // error: Non-expression branch of 'switch' expression may only end with a 'throw'
}
```

当需要这样的分支时，当前用户必须退回到旧技术。
该提案引入了一个新的上下文关键字，它允许 switch 保留为表达式：

```Swift
let width = switch scalar.value {
    case 0..<0x80: 1
    case 0x80..<0x0800: 2
    case 0x0800..<0x1_0000: 3
    default: 
      log("this is unexpected, investigate this")
      then 4
}
```

then 可以类似地用于允许 if 表达式中的多语句分支。
该关键字的引入还使得独立的 do 表达式更加可行。 它们有两个用例：

1. 要从 do/catch 块的成功路径和失败路径生成值：

```Swift
let foo: String = do {
    try bar()
} catch {
    "Error \(error)"
}
```

2. 当使用单个表达式无法轻松完成变量初始化时，能够初始化变量：

```Swift
let icon: IconImage = do {
    let image = NSImage(
                    systemSymbolName: "something", 
                    accessibilityDescription: nil)!
    let preferredColor = NSColor(named: "AccentColor")!
    then IconImage(
            image, 
            isSymbol: true, 
            isBackgroundSupressed: true, 
            preferredColor: preferredColor.cgColor)
}
```

虽然上面的内容可以组成一个表达式，但声明单独的变量然后使用它们会更清晰。

在其他情况下，这是无法完成的，因为 API 的结构要求您首先创建一个值，然后更改其中的一部分：

```Swift
let motionManager: CMMotionManager = {
    let manager = CMMotionManager()
    manager.deviceMotionUpdateInterval = 0.05
    return manager
}()
```

这种立即执行的闭包模式在 Swift 代码中很常见。 以至于在某些情况下，用户认为即使是单个表达式也必须包含在闭包中。 do 表达式将提供更清晰的习惯用法来对这些进行分组。

2) 讨论[借用和输入输出模式匹配的设计问题](https://forums.swift.org/t/design-concerns-for-borrowing-and-inout-pattern-matching/68396 "借用和输入输出模式匹配的设计问题")

**内容概括**

讨论围绕着通过启用借用和输入输出模式匹配来增强 Swift 的模式匹配、允许在不复制或消耗值的情况下进行值匹配以及在模式匹配期间启用枚举的就地突变来增强 Swift 的模式匹配。 主要设计问题包括：

1. 新的绑定模式：引入“借用 x”和“inout x”分别作为借用和变异模式绑定的语法。 这些将允许借用或改变部分匹配值而不消耗它。
2. 模式的所有权行为：分析 Swift 中的各种模式类型以了解其所有权含义。 诸如绑定、通配符、元组、枚举、可选展开、布尔值、动态转换和表达式模式之类的模式将根据其所有权行为进行评估。
3. 确定模式匹配所有权：探索确定模式匹配的所有权行为的方法。 聚合模式（元组和枚举）遵循其组件之间最严格的所有权行为：借用、变异或消费。
4. 确定开关的效果：讨论如何通过句法标记或从应用模式推断所有权来确定开关对其主题的总体效果。 有人建议使用“&”标记来改变模式匹配。
5. 条件中的所有权控制：考虑“if let”和“if case”构造中借用和 inout 模式绑定的含义。 这些新的绑定形式可用于可选展开，并且其行为类似于根据其所有权要求切换主题。

总体而言，我们的目标是在 Swift 中引入更细致的模式匹配，允许在不消耗值的情况下进行借用和变异，并探索这些增强功能在各种语言结构（如 switch 语句和条件）中的含义。

3) 讨论[如何依赖 SwiftPM 作为一个库？](https://forums.swift.org/t/how-do-you-depend-on-swiftpm-as-a-library/68574 "如何依赖 SwiftPM 作为一个库？")

**问题**

理论上，SPM 是一个普通的 swift 包，您可以将其（使用工具链附带的 SPM）构建为普通的 swift 包。但 swift-package-manager 存储库没有最新的 semver 标签，它使用“工具链”标记方案（swift-5.9.1-RELEASE）。
如何依赖 SPM 作为library？

**回答**

截至目前，libSwiftPM 尚未维护可以遵循语义版本控制的稳定 API。 您使用自己的 libSwiftPM 构建的软件包将从当前的 Swift 安装中提取 PackageDescription 模块，这可能与您使用的 libSwiftPM 版本不兼容。 这种不兼容性将表现为用于传递包清单和插件信息的不同序列化格式（本身是私有 API），这将导致模糊且难以诊断的错误。

作为以前维护过基于 libSwiftPM 构建的 CLI 工具，现在维护 SwiftPM 本身的人，我建议不要将其添加为依赖项。 它不适合在一起版本化并随 Swift 工具链分发的工具集之外使用。

如果您需要一个可以在包上操作的 CLI 界面，请改用 SwiftPM 命令插件，它们确实提供了稳定的 API。

4) 讨论[MainActor 上的上下文切换和线程数](https://forums.swift.org/t/context-switch-on-mainactor-and-number-of-threads/68386 "MainActor 上的上下文切换和线程数")

**提问**

我正在观看 [Swift 并发：幕后](https://developer.apple.com/videos/play/wwdc2021/10254/ "Swift 并发：幕后")我了解到，作为使用 Swift 并发的开发人员，我们不应该违反不阻塞线程的运行时契约。 看来 Swift 的目标是运行与设备中 CPU 核心数量一样多的线程。 然而，会议结束时提出的一个观点引起了一些混乱。 演讲者提到，当我们调用 MainActor 的方法时，会发生上下文切换，因为主线程与协作池中的线程是分开的。 这引发了几个问题：

1、协作池中有多少个线程？ 

2、如果不包括主线程，这是否意味着实际的协作线程数是 numberOfCoresInDevice - 1？

3、为什么主线程不是协作池的一部分？ 

我的假设是，这可能是出于优化目的，允许主线程专注于 UI 任务； 否则，任何线程的任何继续都可以在挂起后在主线程上恢复。

4、这里是否违反了运行时契约：当我们将上下文切换到主线程时，我们当前的线程应该被阻塞？ 

5、或者这个合约只针对我们，开发者，系统可以随意违反吗？ 

无论如何，看起来在这种情况下我们有一个线程被阻塞。

也许，这个问题将作为前三个问题的答案得到回答，但无论如何：为什么主线程不能像协作池中的线程一样工作？ 只是接收必须在主线程上执行的延续？ 这将解决上下文切换问题。

**回答**

主线程主要通过 NSRunLoop 进行管理，因为它的存在时间比 Swift 存在的时间要长得多，更不用说 Swift 并发了。 当在默认模式下不可重入运行时，主调度队列由主运行循环提供服务。 在 Swift Concurrency 中，主要参与者的执行者负责将工作分派到该队列上，就像常规参与者的执行者（默认执行者）将工作分派到协作队列上一样，如您链接的文章中所述

但并非所有进程都有主线程； 它主要是一个与 UI 相关的概念，像守护进程这样的非 UI 进程不需要它。

5) 讨论[枚举案例关键路径：更新](https://forums.swift.org/t/enum-case-key-paths-an-update/68436 "枚举案例关键路径：更新")

**内容概述**

讨论围绕使用 Swift 宏增强对枚举的关键路径支持，特别是引入“案例关键路径”以更好地处理枚举案例。

1. `@CasePathable` 宏：该宏为枚举案例生成实际的关键路径，称为“案例关键路径”。 这些关键路径提供动态案例查找功能，并且可以与常规关键路径类似地使用。
2. 使用示例：`@CasePathable` 宏允许实现各种功能：
 * 通过下标访问枚举案例。
 * 使用 `callAsFunction` 嵌入新的有效负载。
 * 简化枚举案例检查和有效负载提取。
 * 利用 SwiftUI 绑定的大小写键路径，启用基于枚举大小写的导航和表单控件使用。
 * 使用大小写键路径组合应用程序功能，在构建和组合不同的应用程序功能时特别有用。
3. 对库的影响：`SwiftUINavigation` 和 `Composable Architecture` 等库已更新，以合并案例键路径，使用 Swift 键路径语法增强其功能、结构和可组合性。

提供的示例和案例研究旨在展示案例关键路径的多功能性和实用性，强调它们在简化代码、增强 SwiftUI 绑定、组合应用程序功能等方面的潜力。 希望展示这些用例将鼓励将案例关键路径纳入语言中，并激发进一步的创新应用程序。

**案例研究：SwiftUI Bindings**

大小写键路径使从枚举而不是一堆独立选项驱动 SwiftUI 导航成为可能。 例如，如果一个视图可以导航到两个不同的、互斥的功能，那么最好像这样建模：

```Swift
struct FeatureView: View {
  @State var destination: Destination?

  enum Destination {
    case activity(ActivityModel)
    case settings(SettingsModel)
  }

  …
}
```

但构建对 Destination 枚举的每种情况的绑定可能很困难，以便您可以使用 `sheet(item:)`、`popover(item:)`（以及更多）视图修饰符。
但是如果你的枚举用 `@CasePathable` 注释

```Swift
@CasePathable
enum Destination {
	// ...
}
```

然后我们可以利用绑定上的“动态大小写查找”，允许它们通过点链语法转换为 SwiftUI 现有视图修饰符所期望的形状：

```Swift
.sheet(item: self.$destination.activity) { model in 
  ActivityView(model: model)
}
.popover(item: self.$destination.settings) { model in 
  SettingsView(model: model)
}
```

还可以使用 String 或 Bool 来驱动表单控件，例如 TextFields 和 Toggles，否则这些控件将被困在枚举案例中：

```Swift
@CasePathable
enum Status {
  case inStock(quantity: Int)
  case outOfStock(isOnBackOrder: Bool)
}

@Binding var status: Status

switch self.item.status {
case .inStock:
  $status.inStock.map { $quantity in
    Section {
      Stepper("Quantity: \(quantity)", value: $quantity)
      Button("Mark as sold out") {
        status = .outOfStock(isOnBackOrder: false)
      }
    } header: { Text("In stock") }
  }
case .outOfStock:
  $status.outOfStock.map { $isOnBackOrder in
    Section {
      Toggle("Is on back order?", isOn: $isOnBackOrder)
      Button("Is back in stock!") {
        status = .inStock(quantity: 1)
      }
    } header: { Text("Out of stock") }
  }
}
```

如果您想尝试其中任何一个，我们的 `SwiftUINavigation` 库已更新，可以在使用 `CaseKeyPath` 进行绑定时定义动态成员查找。

**案例研究：Composing App Features**

近 4 年前我们开发案例路径的主要推动力是我们的可组合架构库，它提供了一种定义功能并将它们组合在一起的结构化方法。 功能使用枚举来枚举应用程序中所有可能的用户操作，并且这些枚举嵌套在父/子域层中，并且需要案例路径来编写可以将这些功能抽象地粘合在一起的代码。

我们还更新了该库以使用案例键路径，这允许人们通过使用简单且熟悉的键路径语法隔离子状态和操作来将功能组合在一起：

```Swift
Reduce { state, action in 
   // ...
 }
-.ifLet(\.child, action: /Action.child) {
+.ifLet(\.child, action: \.child) {
   ChildFeature()
  }
```

这使我们能够利用本机键路径给我们带来的所有好处，例如 Xcode 自动完成和类型推断。

## 推荐博文

[基于 UI 交互意图理解的异常检测方法](https://juejin.cn/post/7304831120710156340/ "基于 UI 交互意图理解的异常检测方法")

**摘要：**  本文介绍了利用页面多模态信息在UI测试领域的探索与实践经验。针对意图信息识别问题，我们利用图像+文本+渲染布局属性信息探索出了一种交互意图簇识别模型，验证了基于自注意力的多模态方向可行性。

此模型可以识别出渲染树元素多维度的意图属性信息，同时利用聚类算法将节点聚成交互意图簇，可以为后续的任务提供结构化决策信息。在标注数据较少的情况下仍体现了较好的准确率以及泛化能力。后续计划通过扩大数据集、加强预训练等方式继续提升模型识别的精度。

[SwiftUI 中的作用域动画](https://swiftwithmajid.com/2023/11/21/scoped-animations-in-swiftui/ "SwiftUI 中的作用域动画")

**摘要：**  文章介绍了在 SwiftUI 中使用作用域动画的新方法。首先，我们回顾了以前在 SwiftUI 中处理动画的方式，并指出了其中的一些缺点。随后，我们展示了如何使用带有 value 参数的 animation 视图修饰符来限定动画范围，以及如何处理多个可动画属性的情况。

接着，我们介绍了 SwiftUI 中引入的 animation 视图修饰符的新变体，允许我们使用 ViewBuilder 闭包来限定动画范围。最后，我们还提到了在视图层次结构中维护作用域事务的方法。这些新方法为我们在 SwiftUI 中创建精确且有限范围的动画提供了更灵活的选择。

[线程调度和 Actors 的执行方式](https://www.avanderlee.com/concurrency/thread-dispatching-actor-execution/ "线程调度和 Actors 的执行方式")

**摘要：**  本文讨论了在 Swift 中使用线程调度和 Actors 时的执行机制。Actors 可以确保代码在特定线程上执行，如主线程或后台线程，并帮助同步访问可变状态以防止数据竞争。

然而，开发人员常常误解 Actors 在非异步上下文中的线程调度，这是为了避免意外崩溃而至关重要的。作者建议在深入研究调度的具体细节之前，先阅读他的两篇文章：《Actors in Swift: how to use and prevent data races》和《MainActor usage in Swift explained to dispatch to the main thread》，因为它们会向您介绍 Actors 的概念。在本文中，探讨了调用带有任何 actor 属性标记的方法的影响。

在异步上下文中，文章讨论了使用 Actors 时的线程调度。通常情况下，您可能会在异步环境中使用 Actors 。如果您的调用代码访问带有 actor 属性的方法，您必须使用任务（task）或采用相同的全局 actor 。文章提供了相关的示例代码，并说明了编译器如何防止在非异步上下文中调度到 actor 线程。

## 话题讨论

那个活在记忆中的帅气少年，已慢慢变成了大叔模样。岁月无情，那么各位程序猿和攻城狮们，你们心中最担心的容貌变化是哪一个呢？

1. 最害怕越吃越肥胖，横向发展。
2. 最害怕逐渐变厚的高度镜片。
3. 最害怕青丝若雪，白发横生。
4. 最害怕秀发稀疏，日渐秃然。

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
