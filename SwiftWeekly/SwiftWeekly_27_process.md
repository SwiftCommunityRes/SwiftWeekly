## 前言

**本期是 Swift 编辑组自主整理周报的第十八期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

再暗的黑夜也会迎来黎明，再长的坎坷也会连接平川。怀抱**Swift社区**，一颗永不放弃的希望之心，明天将会是温暖的阳光雨露！👊👊👊

> **周报精选**
>
> 新闻和社区：因增速放缓 苹果公司将开启大规模收购
> 
> 提案：
> 
> Swift 论坛：
>
> 推荐博文：
> 
> **话题讨论：** 
> 
> 

## 新闻和社区

### 苹果公司向“恢复基金”再投2亿美元，推进碳移除项目

![](https://jg-app.obs.cn-north-4.myhuaweicloud.com/prod/upload/jpg/0a52d53f56fb4270855286d10f80f239.jpg)

据界面新闻消息，苹果公司 4 月 12 日宣布，在最初 2 亿美元的投资基础上，将向 2021 年设立的“恢复基金”（Restore Fund）再投多达 2 亿美元。该基金旨在为高质量的自然碳移除项目提供资金，激励全球投资保护和恢复“关键生态系统”。苹果公司还希望帮助无法通过现有技术避免或减少碳排放的企业，推广可行的碳移除解决方案。

加码后的基金将由汇丰资产管理部门和 Polliation 合资成立的 Climate Asset Management 管理，额外投资预计将使苹果此前提出的每年从大气中清除 100 万公吨二氧化碳目标翻倍，同时为投资者带来经济回报。

该基金期望把重点放在面向自然的农业项目以及保护和恢复关键生态系统的项目上，前者将帮助公司从可持续管理的农业实践中获得收入，后者则能从大气中移除并储存二氧化碳。苹果公司表示，“恢复基金”的投资将遵循“严格的社会和环境标准”。

### 因增速放缓 苹果公司将开启大规模收购

【环球网科技综合报道】4 月 7 日消息，据外媒报道称，苹果公司目前拥有超过 1650 亿美元的现金储备，鉴于苹果公司当前增速放缓，这家公司未来会开启大规模的收购。
 
不过，和微软、亚马逊等大手笔收购类型不同，苹果公司更倾向于收购小型初创公司。
 
外媒称，苹果喜欢以培养、孵化的方式开展收购，并耐心等待这些初创公司成长，来撬动新的市场。
 
据此前报道，今年 2 月，苹果收购了位于加州的 AI 算法公司 WaveOne 。今年 3 月，苹果公司已经收购了英国开放银行初创公司 CreditKudos 。
 
据了解，苹果经常收购小型企业，以加强其技术和专业知识，但显然没有或立即将其推广到产品或服务中。另一方面，许多收购确实成为苹果生态系统的关键部分。近年来，苹果已经收购了音乐识别服务 Shazam 和自动驾驶汽车公司 Drive.ai 等企业。

### Swift Student Challenge 现已开放申请

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/1FFB9751-9FB2-4171-B6E2-14CF821F6887/2048.jpeg)

我们很高兴能一如既往地为世界各地热爱编程的学生提供长期支持。欢迎使用 Swift Playgrounds 或 Xcode 编写 App Playground (主题自选) 并提交你的杰作，向我们展现你对于编程的热爱。优胜者将获得奖项和表彰，以及额外奖励。

## 提案


## Swift论坛
1) 提议[可变泛型类型抽象包](https://forums.swift.org/t/pitch-variadic-generic-types-abstracting-over-packs/64377 "可变泛型类型抽象包")
**介绍**
之前的 SE-0393 引入了类型参数包和几个相关概念，允许泛型函数声明抽象出可变数量的类型。 该提案将这些想法概括为泛型类型声明。

**动机**
当试图在集合上概括通用算法时，自然会出现对可变数量的类型进行抽象的通用类型声明。 例如，惰性 ZipSequence 可能在两个序列上是通用的。 可以声明一个 ZipSequence 类型，它将固定序列列表的元素表示为元组序列：
```Swift
struct ZipSequence<each S: Sequence>: Sequence {
  typealias Element = (repeat each S.Element)

  let seq: (repeat each S)

  func makeIterator() -> Iterator {
    return Iterator(iter: (repeat (each seq).makeIterator()))
  }

  struct Iterator: IteratorProtocol {
    typealias Element = (repeat each S.Element)

    var iter: (repeat each S.Iterator)

    mutating func next() -> Element? {
      return ...
    }
  }
}
```
**建议的解决方案**
在泛型类型的泛型参数列表中，each 关键字声明了一个泛型参数包，就像它在泛型函数的泛型参数列表中所做的那样。 存储属性的类型可以包含包扩展类型，如上面的 let seq 和 var iter。

2) 讨论[点前缀被认为是丑陋的](https://forums.swift.org/t/dot-prefixing-considered-ugly/64376 "点前缀被认为是丑陋的")
虽然我们已经习惯了，但在静态成员和枚举常量前加上点会引入视觉噪音，看起来太聪明了，总是让我的其他语言背景的同事感到惊讶：
```Swift
func foo(_ v: Color) {...}
object.foo(.red) // 🤔
```
在声明中缺少点前缀之间也存在这种令人不安的不对称性：
```Swift
enum Color {
    case red
    case green
    static var blue = ...
}
```
并在其他地方使用这些前缀：
```Swift
switch color {
    case .red: break
    case .green: break
}
foo(.red)
foo(.blue)
```
有趣的是，我已经可以在某些上下文中使用“object.foo(red)”（例如，在 Color 的静态方法中），但不能在其他上下文中使用。
我很欣赏这将是一个突破性的变化，我们不可能在现阶段迅速适应这一变化。 暂时忘记这一点，你认为 Swift 通过以下更改会变得更好还是更糟？
```Swift
func foo(_ v: Color) {...}
...
object.foo(Color.red) // ok
object.foo(.red)      // 🛑 prohibited
object.foo(red)       // ✅

switch color {
    case .red: break  // 🛑 prohibited
    case red: break   // ✅
}
dispatchPrecondition(condition: .onQueue(.main)) // 🛑
dispatchPrecondition(condition: onQueue(main))   // ✅
bar(.init()) // 🛑
bar(init())  // ✅

// While choosing what "red" to use – follow these new resolution rules:
// - use local variable if exists
// - or use instance variable if exists (in which case self should be captured strongly explicitly or implicitly)
// - or use static variable if exists (in case of enum could be an enumeration constant)
// - or use global variable if exists
// - otherwise emit an error
```

3) 讨论[非 Sendable 类型可以在 Tasks 中捕获吗？](https://forums.swift.org/t/can-non-sendable-types-be-captured-in-tasks/64372 "非 Sendable 类型可以在 Tasks 中捕获吗？")
现在，我猜想下面的代码应该会出现任何错误。
```Swift
class SomeClass {
    var count: Int
    init(count: Int) {
        self.count = count
    }
}

let someClass = SomeClass(count: 0)

//public init(priority: TaskPriority? = nil, operation: @escaping @Sendable () async -> Success)
Task {
    someClass.count += 1
}

//public init(priority: TaskPriority? = nil, operation: @escaping @Sendable () async -> Success)
Task {
    someClass.count += 1
}
```
但是，在 Swift（5.8 版）中，此代码片段可以编译。 在Swift6中，这段代码有没有出现错误？

回答：

在 Swift v.Future 中，全局 someClass 必须与全局 actor 隔离，因此行 someClass.count += 1 将需要：
整个 Task 闭包被隔离到同一个global actor，或者您为该操作切换到适当的global actor
（例如：await MainActor.run { someClass.count += 1 }）
很难准确地说出在 Swift 6 中什么会/不会是错误。您可以使用一些编译器标志来尝试一些事情，但它们是不一致的。

4) 讨论[为什么 didSet 观察者在使用集合中已有的值调用插入后会触发 Set 类型的属性？](https://forums.swift.org/t/why-does-didset-observer-fire-for-property-of-type-set-after-calling-insert-with-value-already-in-the-set/64350 "为什么 didSet 观察者在使用集合中已有的值调用插入后会触发 Set 类型的属性？")
Xcode Playground 中的以下代码片段：
```Swift
import UIKit

var collection = Set<String>() {
    didSet {
        print("didSet")
    }
}

collection.insert("Test1")
collection.insert("Test2")
collection.insert("Test1")
collection.insert("Test3")

print("Done")
```
为什么是输出：
```Swift
didSet
didSet
didSet
didSet
Done
```
而不是:
```Swift
didSet
didSet
didSet
Done
```
为什么当集合未更改时它会触发，因为该值已经在集合中？

回答：
每个mutating函数都会像这样。
没有特殊的机制可以让属性知道 Set 没有在内部被修改。

5) 讨论[可变参数泛型的同时简单但可能致命复杂的使用](https://forums.swift.org/t/a-simultaneously-simple-yet-probably-fatally-complex-use-of-variadic-generics/64347 "可变参数泛型的同时简单但可能致命复杂的使用")
我很好奇即将到来的可变参数泛型特性是否能让我们实现像 transform(_:_:) 这样的函数，你可以在下面看到它的使用：
```Swift
extension String {
    var hasPrimeNumberOfCharacters: Bool {
        transform(
            self,
            { $0.count },
            { $0.isPrime }
        )
    }
}
```
该函数采用一个强制性的第一个参数，即要转换的值，然后是一个可变的转换闭包列表，每个闭包都对它之前的闭包的输出类型进行操作，第一个对初始值进行操作。 在上面的例子中，参数是：String, (String)->Int, (Int)->Bool。

我已经阅读了大量的可变参数泛型文档，如果我现在必须给出我最好的猜测，我会说我的 transform(_:_:) 函数在可变参数泛型的第一次迭代中是不可能的。

下面是一个非常粗略的草图，它是我能想象到的最接近如何编写这样一个函数签名的草图。 我发现有必要发明许多新的语法，这支持了我的猜测，即这是不可能的，至少在最初是不可能的。
```Swift
func transform
    <InitialValue,
     each (T, U)>
    (_ initialValue: InitialValue,
     _ transform: repeat each (T)->U)
-> last U or InitialValue
where first T == InitialValue {
    // How would one even implement this if the above syntax were valid?
}
```

6) 讨论[为 Debian/Ubuntu 构建发行版？](https://forums.swift.org/t/building-distros-for-debian-ubuntu/64367 "为 Debian/Ubuntu 构建发行版？")
现在我希望在 Jetson Nano（它有一个 ARM Cortex-A57 CPU）上用 Swift 做一个机器人项目，它只能使用 Ubuntu 18.04。 18.04 没有预构建的 5.8 .deb 包，这有点痛苦，因为这意味着我必须从源代码构建，并且一些构建依赖项（例如 cmake）必须从源代码构建才能获得最新的 足够的版本。 我以前构建过工具链，现在我正在 Jetson Nano 上构建它，但它花费了很长时间，尽管构建在连接的 SSD 上（操作系统运行在 SD 卡上）。
我想知道在我的 M1 Max MacBook Pro 上的 Ubuntu 18.04 Docker 容器（或者可能是 Parallels VM）中构建工具链是否有意义，然后构建将正确安装在任何 18.04 ARM 机器上的工具链的 .deb。
你认为那会建造得更快吗？
是否存在对构建 .deb 包的支持？ 20.04 和 22.04 包是如何构建的？

回答：
另一种选择是构建 MacOS -> 18.04 交叉编译工具链。 不久前，我将 x-compiler 配置移到了 focus，但要翻转回 bionic 配置应该很容易。

7) 发布[Swift 5.8 发布！](https://forums.swift.org/t/swift-5-8-released/64346 "Swift 5.8 发布！")
链接：https://www.swift.org/blog/swift-5.8-released/
您可能已经看到，Swift 5.8 现已正式发布！ :tada: 此版本包括对语言和标准库的主要补充，包括支持逐步采用即将推出的功能的 hasFeature、改进的开发人员体验、改进 Swift 生态系统中的工具，包括 Swift-DocC、Swift Package Manager 和 SwiftSyntax，经过改进 Windows 支持等。


## 推荐博文

[在 SwiftUI 中掌握 Canvas 的使用](https://swiftwithmajid.com/2023/04/11/mastering-canvas-in-swiftui/ "在 SwiftUI 中掌握 Canvas 的使用")

**摘要：** 文章介绍了如何使用 Canvas 视图在 SwiftUI 中绘制 2D 图形，而无需使用 Shape API 。在 Canvas 视图中，我们可以使用 GraphicsContext 实例进行绘图，调整透明度、缩放和混合模式等参数，并添加不同的滤镜。 Canvas 还提供了 stroke、 fill 和 clip 函数，允许我们绘制任何我们需要的路径，同时也提供了draw函数，允许我们绘制文本和图像。我们可以使用 Canvas 类型绘制任何 SwiftUI 视图，但需要在创建 Canvas 时使用 symbols 闭包中注册它们。虽然 Canvas 视图不支持动画，但可以通过将其嵌入到带有动画调度程序的 TimelineView 中来实现动画效果。 Canvas 视图没有辅助功能树，但可以附加一组辅助视图修饰符，以使每个人都可以访问其内容。

[监听 SwiftUI ScrollView 的内容偏移量](https://www.swiftbysundell.com/articles/observing-swiftui-scrollview-content-offset/#resolving-frames-using-geometryreader "监听 SwiftUI ScrollView 的内容偏移量")

**摘要：** 文章介绍了如何监听 SwiftUI ScrollView 的内容偏移量。在构建可滚动的 UI 时，通常需要观察当前滚动位置以便进行操作，但目前（在撰写本文时）SwiftUI 的 ScrollView 没有内置的方式来执行此类滚动观察。作者提供了一种利用 GeometryReader 解析器并使用 PreferenceKey 类型来实现的方法，使我们能够观察当前的内容偏移。最终作者实现了一个名为 OffsetObservingScrollView 的自定义滚动视图，可以实现监听当前内容偏移量的功能。

[Swift 中如何将不透明返回类型与主要关联类型相结合](https://www.swiftbysundell.com/articles/opaque-return-types-primary-associated-types/ "Swift 中如何将不透明返回类型与主要关联类型相结合")

**摘要：**  文章介绍了 Swift 5.7 引入的主关联类型和不透明返回类型相结合的使用方式。通过声明主关联类型，我们可以在使用 some 关键字时避免类型擦除，并使代码更加类型安全。该功能不仅适用于 Combine 框架，还可以在处理自己的泛型协议时使用。


## 话题讨论

**4月11日，央行公布了2023年一季度的金融数据，居民超额存款三年10.8万亿：北京人均存款已接近27万，上海人均超21万。你存钱了吗？你存钱的目的是什么呢？**

1. 有安全感：为了应对失业、突发疾病等，避免因意外事件而出现经济困难。
2. 实现个人目标：买房、买车、旅行等，通过积累资金来实现自己的愿望。
3. 投资理财：通过投资股票、基金、房地产等资产来增加财富，实现长期的财务目标。
4. 应对退休生活：通过积累养老金和退休金来保障自己的生活质量和经济安全。


欢迎在文末留言参与讨论。


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
