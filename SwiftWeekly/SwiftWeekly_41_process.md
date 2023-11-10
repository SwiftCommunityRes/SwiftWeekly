## 前言

**本期是 Swift 编辑组整理周报的第四十一期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

生活的富足并非完美无缺，适当的缺憾更能感触幸福。**Swift社区**邀你一起，保持积极向上的心！👊👊👊

> **周报精选**
>
> 新闻和社区：
> 
> 提案：
> 
> Swift 论坛：
>
> 推荐博文：

> **话题讨论：** 
> 
> 

**上期话题结果**



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


## Swift论坛

1) 讨论[Swift 6 语言模式的进展](https://forums.swift.org/t/progress-toward-the-swift-6-language-mode/68315 "Swift 6 语言模式的进展")
自从上次更新列出 Swift 6 语言模式的设计优先级以来，该项目一直在朝着下一个里程碑稳步前进。 然而，之前提出的一些目标包括仍处于发展早期阶段的开放式研究问题。 语言指导小组并没有随着这项工作的进展而推迟 Swift 6，而是将 Swift 6 剩余更改的重点缩小到默认情况下的数据争用安全性。

默认情况下数据竞争安全准备就绪

Sendable 检查模型中仍然存在许多错误和漏洞，这些错误和漏洞在严格的并发检查下承认数据竞争。 同样重要的是，严格的并发检查目前会发出大量数据争用的误报报告，使得完整的检查很难通过编程来应对。

只有在语言指导小组确定编程模型有效且可用后，Swift 6 语言模式才会被宣布准备就绪。 完成 Swift 6 语言模式数据竞争安全的剩余语言工作将分为两类：

填补严格并发模型中的所有漏洞，以便静态诊断数据竞争，或者在无法证明静态安全的情况下动态诊断数据竞争。
减少对已证明安全的模式的数据竞争的虚假报告。
Swift 5.10 在 actor 隔离和 Sendable 检查方面包含许多重要的错误修复。 此外，目前正在设计和实施以下语言更改，以接受 Swift 进化审核流程：

SE-0411：独立的默认值表达式
为方法和键路径文字推断@Sendable
对全局变量和静态变量进行严格的并发检查
改进了对关闭参与者隔离的控制
通过隔离值区域解除对不可发送值的限制
总之，这些更改填补了严格并发检查中剩余的主要漏洞，并通过引入更多可发送推理并支持跨隔离边界传输不可发送值的安全方法来提高严格并发检查的可用性。 语言指导小组承认并发领域的其他语言更改很重要，但上述更改对于定义 Swift 6 语言模式是必要的。 其他并发功能是附加的，可以独立探索。

**Swift 6 迁移**

即将推出的功能对于迁移到 Swift 6 语言模式至关重要：在采用完整语言模式之前，可以一次启用一项即将推出的功能，以逐步将代码库迁移到 Swift 6。 有许多之前接受的即将推出的功能将在 Swift 6 中默认启用：

SE-0274：简洁的魔法文件名（ConciseMagicFile）
SE-0286：尾随闭包的前向扫描匹配（ForwardTrailingClosures）
SE-0337：增量迁移到并发检查（StrictConcurrency）
SE-0354：正则表达式文字 16 (BareSlashRegexLiterals)
SE-0383：弃用 @UIApplicationMain 和 @NSApplicationMain (DeprecateApplicationMain)
SE-0384：导入前向声明的 Objective-C 接口和协议 (ImportObjcForwardDeclarations)
SE-0401：删除由 Property Wrappers 引起的 Actor 隔离推断（DisableOutwardActorInference）
SE-0409：导入声明的访问级别修饰符 (InternalImportsByDefault)
语言指导组已决定，在 Swift 6 中默认不会启用一项先前接受的即将推出的功能 ExistentialAny。 SE-0335：引入存在性 any 引入了 any 关键字来标识存在性类型。 该提案还规定，在即将推出的功能标志 ExistentialAny 下，将不再允许“裸”协议名称作为类型，它们必须根据需要使用任何或一些。 考虑到对迁移到语言中存在性 any 的一致使用的担忧，以及预计将会出现的其他语言改进可能会影响迁移的最终结果，语言指导小组正在推迟 SE-0335 中与源代码不兼容的更改 到未来的语言修订。

其他演变提案可能包括 Swift 6 的源不兼容更改，语言指导小组将根据具体情况评估此类提案，以相对于源不兼容的成本为语言带来高价值。 例如，足够高的值更改可能包括完成主要功能所需的次要类型推断更改，例如类型抛出或追求数据竞争安全的语义更改。

一旦 Swift 6 即将推出的所有功能就位，语言指导小组将提供迁移指南，该指南建议在项目中逐步启用严格并发检查的最佳路径，以及如何解决某些类型的严格并发的实用指南 违反常见代码模式。 社区对这些指南的反馈对于评估 Swift 6 迁移的易用性至关重要。

2) 修订[SE-0192：处理未来的枚举案例](https://forums.swift.org/t/amendment-se-0192-handling-future-enum-cases/68321 "SE-0192：处理未来的枚举案例")
自核心团队宣布修改 SE-0192：处理未来枚举案例（又名非详尽枚举）的实施以来，已经过去五年多了。

也就是说，添加 @unknown 默认情况以处理未来专门针对非详尽枚举的枚举情况的要求已从“Swift 4 中的警告/Swift 5 中的错误”降级为“Swift 4 中的运行时陷阱/Swift 中的警告” 5”以减轻源兼容性影响。

直到今天，缺少 @unknown 默认情况仍然是警告而不是错误； 忽略该警告意味着如果将来遇到枚举情况，则会发生运行时陷阱。

语言指导小组根据我们的 Swift 6 语言模式计划讨论了 SE-0192 的当前状态，我们宣布将修改该提案：

对于 Swift 6，将警告升级为错误； 和
为 Swift 5.x 添加即将推出的功能标志，以便用户可以增量迁移其代码。
正如我们在最近关于 Swift 6 进展的文章中所宣布的那样，我们使用即将推出的功能标志合并了许多与源代码不兼容的更改，并计划在 Swift 6 中默认启用这些标志。这种暂存源代码不兼容更改的方法 在审查 SE-0192 时，该功能尚不可用，但今天我们认为这是完成此功能的最合适途径（实际上，也是我们唯一明智的途径）。 我们做出这个决定是考虑了几个因素； 他们之中：

Swift 5 迁移已经过去很多年了，除非实际编写 @unknown 默认情况，否则警告始终无法消除。

忽略警告意味着如果将来遇到枚举情况，就会留下隐式运行时陷阱 - 在最坏的情况下，这种行为在 Swift 6 中仍然可以通过编写类似 @unknown default: fatalError() 的内容来简单地表达，但是当显式处理时，用户 可以选择其他在上下文中有意义且不需要停止执行的默认行为（例如，返回 nil）。

此有限的修改独立于任何正交的附加工作，以便为非弹性库启用不可扩展的枚举。

3) 讨论[列出类型的存储属性](https://forums.swift.org/t/listing-stored-properties-of-a-type/68351 "列出类型的存储属性")
我的愿望清单上有一段时间的功能是能够将类型的存储属性与计算属性分开进行分类。 目前很难从生成的文档中对所有实例属性进行排序以了解类型的实际表示是什么。

我今天对这个想法做了一些调查，发现 lib/SymbolGraphGen 目前将所有实例属性分类为存储属性 (vp 2)。

也不可能从发出的符号声明中存在访问器（{ get }、{ get set } 等）来推断这一点，因为这些访问器也出现在存储的 public private(set) 属性中。

lib/SymbolGraphGen 需要什么才能发出此信息？

**回答**

有点相关的是，我需要知道今晚早些时候各种结构的实际布局 - 例如 UnsafeMutableBufferPointer - 我最终不得不挖掘一些深埋在 Swift stdlib 源代码中的 gyb 模板（然后非常仔细地阅读以确保我找到了所有存储的属性，因为它们的声明几乎可以出现在文件中的任何位置）。 如果您不知道专门去 GitHub 并专门搜索 Apple 的“Swift”存储库并修改语言设置以使其实际显示这些模板文件，那么您将永远找不到它们。 搜索引擎非常努力地不显示 GitHub 源代码结果。

如果它们只是简单地列在文档中，即使只是在某些附录或脚注中，我也会更高兴。

请注意，在这种情况下，顺序也很重要。 我需要知道完整的布局，以便将其映射到寄存器等。
4) 讨论[没有Reducer协议的NavigationStackStore](https://forums.swift.org/t/navigationstackstore-without-reducer-protocol/68359 "没有Reducer协议的NavigationStackStore")
我们有一个大项目，从 TCA 的第一个版本开始，目前我们正在使用 0.57.0 版本

我们计划迁移到 TCA 的最新版本，但这需要一些时间，我们需要使用 NavigationStackStore，但由于我们所有的减速器都是 AnyReducer 类型，我找不到实现它的方法。

找到了一种在 AnyReducer 中使用Reducer Protocol的方法，但找不到方法
在 sideReducer 协议中使用 AnyReducer
或混合它们

有什么建议么？

**回答**

我认为您需要将Reducer转换回AnyReducer：
```Swift
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

5) 讨论[扩展“条件列表”能力](https://forums.swift.org/t/extend-condition-list-abilities/68328 "扩展“条件列表”能力")
这只是一个很小的间距。 如果有人愿意接受它并进行正式的提案和实施，请随意去做。

使用相当新但相当小的 Verse 编程语言几个月后，我开始喜欢能够创建中间常量和变量以及在 if 语句的条件列表中执行常规函数的能力。

我开始想知道为什么 Swift 没有这么方便的功能。 与 Verse 不同，Swift 不将抛出错误视为条件。 这没关系，我不会试图改变这一点。

以下是我希望 Swift 允许的示例。

以前：
```Swift
if condition1 {
  var someVariable = ...
  // do computation using `condition1` and mutate `someVariable`
  callSideEffect(on: &someVariable)
  callSideEffect()

  if condition2 {
    ...
  } else {
    // execute failure branch (mimic A again)
  }
} else {
  // A: execute failure branch
}
```
之后：
```Swift
if 
  condition1,
  var someVariable = ..., // NEW (non-condition)
  callSideEffect(on: &someVariable), // NEW (non-condition)
  callSideEffect(), // NEW (non-condition)
  condition2
{
  ...
} else {
  // A: execute failure branch
}
```
为了简化事情，请将常规 let 和 vars 视为非条件。 这有点类似于我们在结果生成器中创建本地常量的方式，这些常量不会立即被它消耗。

这个想法将扩展 if、guard 和 while 的条件列表。

**回答**

将条件列表重构为单独的函数使我们能够将代码简化为单个 if/else 分支结构。
```Swift
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
  // execute failure branch
}
```

6) 讨论[any Task是什么类型](https://forums.swift.org/t/whats-the-type-of-any-task/68372 "any Task是什么类型")
假设我想在变量中记录任意任务，以便以后可以取消它。 这个变量的类型应该是什么？
```Swift
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

```Swift
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

## 推荐博文

[ Swift 中的崩溃回溯](https://www.swift.org/blog/swift-5.9-backtraces/ " Swift 中的崩溃回溯")

**摘要：**  这篇博客讨论了 Swift 5.9 版本中所包含的一些新的调试代码功能，一个能在实时检查崩溃的外部互动性极强的崩溃处理器，一个可以触发调试器进行即时调试的功能，以及一个可以提升理解在一个使用结构化并发的程序中的控制流程的并发意识后退功能。
在 Swift 5.9 版本之前，一旦你的程序运行失败，你只能看到来自父进程（通常是 shell ）的消息告诉你子进程崩溃了。而现在，你得到的信息将会更具有详细性。
作者还提出了一个名为"交互式后退"的概念。在许多情况下，你可能会发现你在终端开发的程序崩溃了，但你无法复现问题。没有适当的崩溃日志，这可能会让你非常沮丧，你知道你的程序有一个 bug ，但你不知道问题出在哪里，也不知道如何复现它。这个特性的主要思想就是在程序崩溃后将其挂起，从而给你机会附加一个调试器，或对崩溃过程进行更深入的查看。
最后，后退功能支持结构化并发，并且能够正确地逆向穿过异步框架。无论你在哪个平台上，这个新功能都无需特殊要求，只需要回退追踪器能够查找到符号以确定给定框架是否是异步的。

[掌握 SwiftUI 中的 ContentUnavailableView ](https://swiftwithmajid.com/2023/10/31/mastering-contentunavailableview-in-swiftui/ "掌握 SwiftUI 中的 ContentUnavailableView ")

**摘要：**  这篇博客介绍了如何在 SwiftUI中 掌握使用 ContentUnavailableView 类型。 ContentUnavailableView 类型允许我们在应用中表现空状态、错误状态或其他任何内容不可用的状态。文章通过实例演示了ContentUnavailableView 的基本用法以及如何在其中定义描述文本和操作按钮。还介绍了 SwiftUI 为我们提供的一种预制的 ContentUnavailableView 实例，可在搜索屏幕中使用。总的来说，我们学会了如何利用 ContentUnavailableView 以用户友好的方式显示空状态。

[ SwiftUI 中的 visual effects ](https://swiftwithmajid.com/2023/11/07/visual-effects-in-swiftui/ " SwiftUI 中的 visual effects ")

**摘要：** 这篇博客介绍了 SwiftUI 在 WWDC2023 中引入的一种叫做 visualEffect 的新视图修饰符。 visualEffect 允许我们通过访问特定视图的布局信息来附加一组可动画的视觉效果。
通过上述示例，我们可以看到定义了一个文本视图并附加了 visualEffect 视图修饰符。attach visualEffect 视图修饰符时，你需要指定闭包以应用所需的所有效果。闭包提供了两个参数：第一个参数是附加到视图的效果集合的初始状态，是 EmptyVisualEffect 类型的实例；第二个参数是 GeometryProxy 类型的实例，包含可能需要的视图所有布局信息，比如框架、安全区等。现在，所有这些视觉效果都遵循 VisualEffect 协议，可以在 visualEffect 闭包中使用它们。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
