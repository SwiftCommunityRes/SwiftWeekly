## 前言

**本期是 Swift 编辑组整理周报的第四十一期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

生活的富足并非完美无缺，适当的缺憾更能感触幸福。**Swift社区**邀你一起，保持积极向上的心！👊👊👊

> **周报精选**
>
> 新闻和社区：现推出超过 30 个新的开发者活动
> 
> 提案：全局变量的严格并发性
> 
> Swift 论坛：Swift 6 语言模式的进展
>
> 推荐博文：Swift 中的崩溃回溯

> **话题讨论：** 
> 
> 如果公司在市中心，你会选择那种方式？

**上期话题结果**

![](https://files.mdnice.com/user/17787/c606080b-63c9-439a-8f56-1baf27323195.png)

根据投票结果分析，极兔速递的 IPO 在受众中引起了相当的关注。顺丰和京东物流依然是物流行业备受看好的龙头企业，分别占据相当大的比例。菜鸟虽然有一定支持，但在此次投票中表现相对较弱。

## 新闻和社区

### 2024 年 Swift Student Challenge 公布

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/5D41BDFB-09E7-4A11-8376-C037FBF3DCF3/2048.jpeg)

Apple 很自豪能够支持和激励下一代学生开发者、创作者和企业家。挑战赛为数以千计的学生提供了机会，让他们可以展现自身的创造力和编程能力，并培养可以在职业生涯和更多地方运用的实际技能。从帮助同伴找到合适的心理健康资源，到发现在校园内支持可持续发展工作的方式，Swift Student Challenge 参赛者将发挥他们的创造力，通过开发 App 来解决他们关注的问题。

我们发布了新的编程资源、与社区合作伙伴积极合作，而且比往年更早公布了挑战赛，以便学生们能深入研究 Swift 和整个开发过程，同时教育工作者也能抢先一步为他们提供支持。

申请将在 2024 年 2 月开放三周。

2024 年挑战赛新增了一项机制，我们将在 350 名获奖者中选出 50 名杰出获奖者，并对这些提交了优秀作品的杰出获奖者予以表彰，邀请他们明年夏天前往位于库比提诺的 Apple 园区度过难忘的三天。

### 现推出超过 30 个新的开发者活动

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/E37E35FD-D28B-4204-8107-425410EF41F5/2048.jpeg)

2023 年 11 月 7 日

准备好提升你的 App 或游戏功能了吗？在整个 11 月和 12 月，欢迎参加面向全球开发者量身打造的一系列面对面或在线举办的全新实验室、咨询和讲座等活动。

你将能探索：

App Store 活动：了解关于探索、互动、App 内活动、自定产品页面、订阅推荐做法等众多精彩内容。
Apple Vision Pro 开发者实验室：申请参加位于库比提诺、伦敦、慕尼黑、纽约、上海、新加坡、悉尼或东京的实验室。

Apple Vision Pro 活动：了解如何为 visionOS 设计和构建全新的 App 和游戏世界。

设计和技术咨询：报名获取关于 App 设计、技术实施等方面的一对一指导。

探索在多个时区以多种语言进行的活动。

## 提案

### 正在审查的提案

[SE-0412](https://github.com/apple/swift-evolution/blob/main/proposals/0412-strict-concurrency-for-global-variables.md "SE-0412") **全局变量的严格并发性** 提案正在审查。

该提案定义了在不产生数据竞争的情况下使用全局变量的选项。在此提案中，全局变量涵盖任何静态持续时间的存储：在全局范围声明的 `let` 和存储 `var`，或者作为静态成员变量。

## Swift论坛

1) 讨论[Swift 6 语言模式的进展](https://forums.swift.org/t/progress-toward-the-swift-6-language-mode/68315 "Swift 6 语言模式的进展")

自上次更新为 Swift 6 语言模式 94 制定设计优先事项以来，该项目一直在稳步推进，朝着这个下一个里程碑迈进。然而，先前提出的一些目标包括尚处于开放式研究阶段的问题。在 Swift 6 的工作进展的同时，语言指导组正在将 Swift 6 剩余变更的重点缩小到默认情况下的数据竞争安全。

**数据竞争安全的准备情况**

在严格的并发检查下，Sendable 检查模型中仍存在许多错误和漏洞，允许数据竞争。同样重要的是，严格的并发检查目前会发出大量错误报告数据竞争，使得完整的检查难以进行编程。

只有当语言指导组确定编程模型是有效和可用的时，Swift 6 语言模式才会被宣布准备就绪。完成 Swift 6 语言模式的数据竞争安全所需的剩余语言工作将分为两类：

1. 填补严格并发模型中的所有漏洞，以便静态地或在静态安全无法证明的情况下动态地诊断数据竞争。
2. 缓解已被证明是安全的模式对数据竞争的虚假报告。

Swift 5.10 包含了许多与 actor 隔离和 Sendable 检查有关的重大错误修复。此外，以下语言更改目前正在进行设计和实施，以接受 Swift 演进审查过程：

1. SE-0411: 孤立的默认值表达式 23
2. 为方法和键路径文字推断 @Sendable 18
3. 全局和静态变量的严格并发检查 12
4. 改进对闭包 actor 隔离的控制 16
5. 通过孤立值区域解除对非 @Sendable 值的限制 15

这些变化共同填补了严格并发检查中的剩余主要漏洞，并通过引入更多的 `@Sendable` 推断和启用安全的方式在隔离边界传递非 `@Sendable` 值，提高了严格并发检查的可用性。语言指导组承认，并发领域的其他语言更改也很重要，但以上更改对于定义 Swift 6 语言模式是必要的。其他并发特性是附加的，可以独立探索。

**Swift 6 迁移**

即将推出的功能 16 对于迁移到 Swift 6 语言模式至关重要：可以逐个启用单个即将推出的功能，以逐步将代码库移向 Swift 6，然后再采用完整的语言模式。有许多先前接受的即将推出的功能将在 Swift 6 中默认启用：

1. SE-0274: 简洁的魔术文件名 93 (`ConciseMagicFile`)
2. SE-0286: 用于尾随闭包的正向扫描匹配 55 (`ForwardTrailingClosures`)
3. SE-0337: 增量迁移到并发检查 18 (`StrictConcurrency`)
4. SE-0354: 正则表达式文字 23 (`BareSlashRegexLiterals`)
5. SE-0383: 弃用 `@UIApplicationMain` 和 `@NSApplicationMain` 70 (`DeprecateApplicationMain`)
6. SE-0384: 导入前向声明的 Objective-C 接口和协议 31 (`ImportObjcForwardDeclarations`)
7. SE-0401: 由属性包装器引起的去除 Actor 隔离推断 22 (`DisableOutwardActorInference`)
8. SE-0409: 导入声明上的访问级别修饰符 55 (`InternalImportsByDefault`)

语言指导组已决定，先前接受的即将推出的功能 ExistentialAny 将不会在 Swift 6 中默认启用。SE-0335: 引入存在的任何 33 引入了 any 关键字以识别存在类型。该提案还规定，“裸” 协议名称将不再被允许用作类型——它们必须使用任何或一些，视情况而定——在即将推出的功能标志 ExistentialAny 下。鉴于关于向一致使用存在的任何语言迁移的担忧，以及期望会出现可能影响该迁移最终结果的其他语言改进，语言指导组正在将 SE-0335 中的源不兼容更改推迟到将来的语言修订中。

其他 Swift 6 可能包括源不兼容更改的演进提案，语言指导组将在评估这类提案是否相对于源不兼容的成本对语言的价值时逐个进行评估。例如，足够有价值的更改可能包括为完成主要功能（例如类型化抛出）而必需的轻微类型推断更改，或者为了实现数据竞争安全而进行的语义更改。

一旦为 Swift 6 准备好所有即将推出的功能，语言指导组将提供一个迁移指南，建议以一种最佳路径逐步启用项目中的严格并发检查，并提供有关如何处理某些常见代码模式中的严格并发违规的实际指导。社区对这些指南的反馈对于评估 Swift 6 迁移是至关重要的。

2) 修订[SE-0192：处理未来的枚举案例](https://forums.swift.org/t/amendment-se-0192-handling-future-enum-cases/68321 "SE-0192：处理未来的枚举案例")

自核心团队宣布对 SE-0192（处理未来枚举案例，又称为非尽事枚举）实施修改以来已经过去了五年。

换句话说，专门用于非尽事枚举的要求，即添加 @unknown 默认情况，以处理未来的枚举案例，已从 “Swift 4 中的警告/Swift 5 中的错误” 降级为 “Swift 4 中的运行时陷阱/Swift 5 中的警告”，以减轻源代码兼容性的影响。

直到今天，缺乏 `@unknown default` 情况仍然是一个警告而不是错误；忽略该警告意味着如果遇到未来的枚举案例，则会发生运行时陷阱。

语言指导组在考虑到 Swift 6 语言模式的计划时讨论了 SE-0192 的当前状态，并且我们宣布我们将修改该提案以：

1. 将 Swift 6 中的警告升级为错误
2. 为 Swift 5.x 添加一个即将推出的功能标志，以便用户可以逐步迁移其代码。
  
正如我们在关于 Swift 6 进展的最新帖子中宣布的那样，我们已经使用即将推出的功能标志合并了一些不兼容源代码的更改，计划在 Swift 6 中默认启用这些标志。当初审查 SE-0192 时，这种引入不兼容源代码更改的方法是不可用的，但今天我们认为这是完成此功能的最合适，事实上是我们唯一明智的选择。我们做出了这个决定，考虑到了几个因素，其中包括：

1. 自 Swift 5 迁移以来已经过去了很多年，而且该警告始终是无法消除的，除非实际编写 `@unknown default` 情况。

2. 忽略该警告意味着在遇到未来的枚举案例时留下了一个隐式的运行时陷阱 - 在最坏的情况下，通过编写像 `@unknown default: fatalError()` 这样的内容，这种行为在Swift 6中仍然可以轻松表达，但在明确处理时，用户可以选择上下文中有意义且不需要停止执行的其他默认行为（例如，返回nil）。

这个有限的修订与启用非扩展枚举的正交、增量工作无关，该工作适用于非弹性库。

3) 讨论[列出类型的存储属性](https://forums.swift.org/t/listing-stored-properties-of-a-type/68351 "列出类型的存储属性")

我心愿已久的一项功能是能够将类型的存储属性与计算属性分开进行分类。目前，通过生成的文档很难整理出所有实例属性，以了解类型的实际表示是什么。

我今天对这个想法进行了一些调查，发现 `lib/SymbolGraphGen` 目前将所有实例属性都分类为存储属性（vp 2）。

从发出的符号声明中也无法通过访问器的存在（`{ get }`，`{ get set }` 等）来推断这一点，因为这些也会出现在存储的公共 `private(set)` 属性中。

`lib/SymbolGraphGen` 要发出这些信息需要什么条件？

**回答**

有些相关的是，今天晚上我需要了解各种结构的实际布局 - 例如 `UnsafeMutableBufferPointer` - 最终我不得不深入挖掘 Swift stdlib 源代码中深藏的一些 gyb 模板（然后仔细阅读，以确保我找到了所有的存储属性，因为它们的声明实际上可以出现在文件的任何地方）。

如果你不知道要专门去 GitHub 并具体搜索苹果的 “Swift” 存储库，然后调整语言设置以使其实际显示这些模板文件，你永远找不到它们。搜索引擎非常努力地不显示 GitHub 源代码的结果。

如果它们只是在文档中列出，即使只是在附录或脚注中，我会感到更高兴。

请注意，在这种情况下，顺序也很重要。我需要知道完整的布局，以便将其映射到寄存器等等。

4) 讨论[没有 Reducer 协议的 NavigationStackStore](https://forums.swift.org/t/navigationstackstore-without-reducer-protocol/68359 "没有 Reducer 协议的 NavigationStackStore")

我们有一个大型项目，从 TCA 的第一个版本开始，目前我们正在使用版本 0.57.0

我们计划迁移到 TCA 的最新版本，但这需要一些时间，而我们需要使用 `NavigationStackStore`，但由于我们所有的 reducer 都是 AnyReducer 类型，我找不到一种实现的方法。

找到了在 AnyReducer 中使用 Reducer 协议的方法，但找不到一种方法在 Reducer 协议内部使用 AnyReducer 或混合它们

有什么建议吗？

**回答**

我认为你需要在 `Reduce` 中封装 `AnyReducer`。类似这样：

```swift
static let reducer: AnyReducer<State, Action, Void> = .combine(
+     AnyReducer(
        Reduce(
            .init { state, action, _ in
                return .none
            },
            environment: ()
        )
        .forEach(\State.path, action: /Action.path) {
            Path()
        }
+     )
    )
```

5) 讨论[扩展条件列表能力](https://forums.swift.org/t/extend-condition-list-abilities/68328 "扩展条件列表能力")

这只是一个小想法。如果有人愿意接手并制定正式提案和实施，随时可以着手。

在使用了相对新但规模较小的 Verse 编程语言几个月后，我开始喜欢能够在 if 语句的条件列表中创建中间常量和变量，以及执行常规函数的能力。

我开始思考为什么 Swift 没有这样相当方便的功能。与 Verse 不同，Swift 不将抛出错误视为条件。这是可以接受的，我并不打算改变这一点。

以下是我希望在 Swift 中被允许的示例。

之前：

```swift
if condition1 {
  var someVariable = ...
  // 使用 `condition1` 进行计算并改变 `someVariable`
  callSideEffect(on: &someVariable)
  callSideEffect()

  if condition2 {
    ...
  } else {
    // 执行失败分支（模拟 A）
  }
} else {
  // A: 执行失败分支
}
```

之后：

```swift
if 
  condition1,
  var someVariable = ..., // 新增（非条件）
  callSideEffect(on: &someVariable), // 新增（非条件）
  callSideEffect(), // 新增（非条件）
  condition2
{
  ...
} else {
  // A: 执行失败分支
}
```

为了简化问题，将常规的 let 和 var 视为非条件。这有点类似于我们如何在结果构建器中创建本地常量，这些常量不会立即被它消耗。

这个想法将扩展 if、guard 和 while 的条件列表。

**回答**

将条件列表重构为一个单独的函数使我们能够简化代码为单一的 if/else 分支结构。

```swift
func shouldRun() -> Bool {
    guard condition else { return false }
    var someVariable = ...
    callSideEffect(on: &someVariable)
    callSideEffect()
    return condition2
}

if shouldRun() {
  ...
} else {
  // 执行失败分支
}
```

6) 讨论[any Task 是什么类型](https://forums.swift.org/t/whats-the-type-of-any-task/68372 "any Task 是什么类型")

假设我想要将一个任意的任务记录在一个变量中，以便稍后可以取消它。这个变量的类型应该是什么？

```swift
var task: Task<Any, Never>
let foo = Task {
    return "Hello World!"
}
let bar = Task {
    return 42
}
task = foo // Cannot assign value of type 'Task<String, Never>' to type 'Task<Any, Never>'
```

**回答**

```swift
protocol Cancellable {
    func cancel()
}

extension Task: Cancellable {}

var task: Cancellable!

let foo = Task {
    "Hello World!"
}

let bar = Task {
    42
}

task = foo
task.cancel()
```

## 话题讨论

如果公司在市中心，你会选择那种方式？

* 方案一：租住公司附近，节省通勤时间，房租压力大
* 方案二：租住离公司远，通勤时间长，房租压力小
* 方案三：住自己的房子

欢迎在文末留言参与讨论。

## 推荐博文

[Swift 中的崩溃回溯](https://www.swift.org/blog/swift-5.9-backtraces/ "Swift 中的崩溃回溯")

**摘要：**  这篇博客讨论了 Swift 5.9 版本中所包含的一些新的调试代码功能，一个能在实时检查崩溃的外部互动性极强的崩溃处理器，一个可以触发调试器进行即时调试的功能，以及一个可以提升理解在一个使用结构化并发的程序中的控制流程的并发意识后退功能。

在 Swift 5.9 版本之前，一旦你的程序运行失败，你只能看到来自父进程（通常是 shell ）的消息告诉你子进程崩溃了。而现在，你得到的信息将会更具有详细性。

作者还提出了一个名为"交互式后退"的概念。在许多情况下，你可能会发现你在终端开发的程序崩溃了，但你无法复现问题。没有适当的崩溃日志，这可能会让你非常沮丧，你知道你的程序有一个 bug ，但你不知道问题出在哪里，也不知道如何复现它。这个特性的主要思想就是在程序崩溃后将其挂起，从而给你机会附加一个调试器，或对崩溃过程进行更深入的查看。

最后，后退功能支持结构化并发，并且能够正确地逆向穿过异步框架。无论你在哪个平台上，这个新功能都无需特殊要求，只需要回退追踪器能够查找到符号以确定给定框架是否是异步的。

[掌握 SwiftUI 中的 ContentUnavailableView ](https://swiftwithmajid.com/2023/10/31/mastering-contentunavailableview-in-swiftui/ "掌握 SwiftUI 中的 ContentUnavailableView ")

**摘要：**  这篇博客介绍了如何在 SwiftUI中 掌握使用 `ContentUnavailableView` 类型。`ContentUnavailableView` 类型允许我们在应用中表现空状态、错误状态或其他任何内容不可用的状态。

文章通过实例演示了 `ContentUnavailableView` 的基本用法以及如何在其中定义描述文本和操作按钮。还介绍了 SwiftUI 为我们提供的一种预制的 `ContentUnavailableView` 实例，可在搜索屏幕中使用。总的来说，我们学会了如何利用 `ContentUnavailableView` 以用户友好的方式显示空状态。

[SwiftUI 中的 visual effects](https://swiftwithmajid.com/2023/11/07/visual-effects-in-swiftui/ "SwiftUI 中的 visual effects")

**摘要：** 这篇博客介绍了 SwiftUI 在 WWDC2023 中引入的一种叫做 `visualEffect` 的新视图修饰符。 visualEffect 允许我们通过访问特定视图的布局信息来附加一组可动画的视觉效果。

通过上述示例，我们可以看到定义了一个文本视图并附加了 `visualEffect` 视图修饰符。`attach visualEffect` 视图修饰符时，你需要指定闭包以应用所需的所有效果。

闭包提供了两个参数：第一个参数是附加到视图的效果集合的初始状态，是 `EmptyVisualEffect` 类型的实例；第二个参数是 `GeometryProxy` 类型的实例，包含可能需要的视图所有布局信息，比如框架、安全区等。现在，所有这些视觉效果都遵循 `VisualEffect` 协议，可以在 `visualEffect` 闭包中使用它们。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
