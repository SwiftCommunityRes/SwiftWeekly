## 前言

**本期是 Swift 编辑组整理周报的第三十四期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

恰似烈日灼身，清风缕缕慰我清静。恰似无边心海，**Swift社区**渡我心安！👊👊👊

> **周报精选**
>
> 新闻和社区：iPhone Pro 要提价！新款 iPhone 或会使用 USB-C 充电器，边框更薄
> 
> 提案：允许在非泛型上下文中嵌套协议
> 
> Swift 论坛：提议 DocC 中的数学排版
>
> 推荐博文：Swift HTTP Types 的介绍
>
> **话题讨论：** 
> 
> 苹果公司正在考虑在今年秋季推出新款 iPhone Pro 时提高其高端手机的价格，那么如果到时候新款 iPhone Pro 在国内的价格超过了一万元，你还会买吗？

**上期话题结果**

![](https://files.mdnice.com/user/17787/9206a50e-e85e-4b70-bcff-5396ed536173.jpg)

这只是一个简单的投票结果，虽然不能完全反映实际的社会情况，但是也能帮助大家了解目前的生活状态（仅作参考）。

## 新闻和社区

### iPhone Pro 要提价！新款 iPhone 或会使用 USB-C 充电器，边框更薄

据彭博社当地时间 7 月 24 日报道，苹果公司正在考虑在今年秋季推出新款 iPhone Pro 时提高其高端手机的价格。
 
苹果公司通常在 9 月份发布新款 iPhone 。自 2019 年以来，苹果公司一直在销售高端的 iPhone Pro ，其起售价在美国为 999 美元，而屏幕更大的 Max 型号至少为 1099 美元。据报道，苹果公司最新的高端型号可能会涨价，这将通过提高新 iPhone 的平均售价来增加苹果公司的总收入。

![图片来源：苹果官网](https://pics0.baidu.com/feed/34fae6cd7b899e51482ccff515245e3fca950dc4.jpeg@f_auto?token=8eb543197d27f0d69f5479a7a2299a2b)

在疫情期间，苹果公司没有提高美国新款 iPhone 的价格，尽管该公司面临零部件短缺，并表示通货膨胀导致了一些服务（如运输和零部件）的成本上升。

然而，苹果公司经常根据汇率波动调整其在全球各地的产品价格，包括去年推出的 iPhone 14 设备。

苹果公司没有回应置评请求。

新款 iPhone 可能会使用 USB-C 充电器，而不是专有的 Lightning 充电器，这是去年欧洲通过新规定后的结果。据供应链分析师郭明錤称，新款 Pro 型号可能会采用钛合金外壳和更薄的边框。

价格上涨也可能有助于苹果公司利用智能手机行业近期的趋势。总体而言，智能手机出货量下降并已持续一年，但消费者仍然对最好和最贵的设备有需求，分析师们说。

“尽管全球智能手机需求复苏低于预期，但看起来高端市场（因此也是苹果）受到的影响较小。”德意志银行分析师何思迪（Sidney Ho）周一在一份报告中写道。

另据科创板日报 7 月 24 日援引外媒报道，苹果供应链消息称，2023 年 iPhone 15 零部件备货力道不及 2022 年同期，略估初步备货量仅约 8300 万 ~ 8500 万支水准，同比下降逾 8%。2022 年同期 iPhone 备货预估量约 9000 万支以上，甚至“还有喊到近 1 亿支”。

之前市场认为，手机市场已开始出现回温，但大立光董事长林恩平认为，这只是中低阶手机市场销售的略为走升，至于高阶市场的销售，客户端看法仍然相对保守，主要问题在于“卖不好”。

美国银行分析师 Wamsi Mohan 在报告中指出，iPhone 15 设备可能会推迟“几周”，部分机型或将推迟到 10 月上市，但 The Information 认为苹果仍将如期在 9 月份上市 iPhone 15 的 Pro 系列。(来源：每日经济新闻)

### 与 App Store 专家会面交流

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/7ED4820B-E3B1-4F08-A0FE-1708671981CC/2048.jpeg)

加入我们，参与 8 月 1 日至 8 月 24 日的在线讲座，了解最新的 App Store 功能并获取问题的解答。我们将在多个时区以多种语言进行实时演讲和答疑。

探索 App Store 定价机制升级，包括增强的全球定价机制、用于按店面管理定价的工具，以及额外的价格点。
你将学习如何通过 App 分析来衡量用户获取情况，以及如何使用 App Store 的各项功能来发展你的订阅业务。
探索产品页优化如何助你测试产品页的不同元素，以找出哪些元素最能引起用户的共鸣。
了解自定产品页如何助你创建额外的产品页版本，以突出显示特定功能或内容。
你还能了解怎样通过 Game Center 来提高曝光度和参与度，以及 App 内活动的配置操作。

### 让你的 App 和游戏在 visionOS 模拟器外更进一步

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/4CC97B65-CD76-433A-8139-18D6DD7BB227/2048.jpeg)

**Apple Vision Pro 兼容性评估**

我们可协助你确保 visionOS、iPadOS 和 iOS App 在 Vision Pro 上正常运行。而且，我们会先根据新发布的兼容性核对清单调整你的 App，然后再要求直接在 Vision Pro 上对你的 App 进行评估。

**Apple Vision Pro 开发者实验室**

体验在 Vision Pro 上运行的 visionOS、iPadOS 和 iOS App。你将能够在 Apple 的支持下测试并优化你的 App，为无边的空间画布做好准备。我们分别在库比蒂诺、伦敦、慕尼黑、上海、新加坡和东京设立了实验室。

**Apple Vision Pro 开发者套件**

如果你有任何 visionOS App 的好创意是需要在 Vision Pro 真机上构建和测试的，欢迎申请 Vision Pro 开发者套件。通过持续直接访问 Vision Pro，你将能够快速构建、测试和优化 App，在 visionOS 上提供出色的空间体验。

## 提案

### 通过的提案

[SE-0400](https://github.com/apple/swift-evolution/blob/main/proposals/0400-init-accessors.md "SE-0400") **Init 访问器** 提案通过审查。该提案已在 **三十一期周报** 正在审查的提案模块做了详细介绍。

[SE-0401](https://github.com/apple/swift-evolution/blob/main/proposals/0401-remove-property-wrapper-isolation.md "SE-0401") **移除由属性包装器引起的 Actor 隔离推断** 提案通过审查。该提案已在 **三十一期周报** 正在审查的提案模块做了详细介绍。

[SE-0402](https://github.com/apple/swift-evolution/blob/main/proposals/0402-extension-macros.md "SE-0402") **将 conformance 宏作为 extension 宏** 提案通过审查。该提案已在 **三十三期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0403](https://github.com/apple/swift-evolution/blob/main/proposals/0403-swiftpm-mixed-language-targets.md "SE-0403") **软件包管理器混合语言目标支持** 提案正在审查。

改提案旨在为包含 Swift 和 C 等基于语言的混合源代码的目标添加软件包管理器支持。目前，一个目标的源代码可以是 Swift 或 C 等基于语言（根据SE-0038），但不能同时存在两者。

[SE-0404](https://github.com/apple/swift-evolution/blob/main/proposals/0404-nested-protocols.md "SE-0404") **允许在非泛型上下文中嵌套协议** 提案正在审查。

允许在非泛型的结构体、类、枚举和 actors 中嵌套协议。

## Swift论坛

1) 提议[DocC 中的数学排版](https://forums.swift.org/t/pitch-mathematical-typesetting-in-docc/66418 "DocC 中的数学排版")

提出了一个新的 DocC 指令，@Math：

```Swift
/// The sample variance of the collection.
/// - Returns: The sample variance:
/// @Math("sample-variance.xml", description: "Sum, from i = 1 to n, of the squared norm of x_i minus mu. Everything divided by n minus 1.")
/// where 𝑛 is the collection's `count` and ‖𝑥ᵢ - 𝜇‖ is the Euclidean distance from each element 𝑥ᵢ to the sample mean 𝜇.
func sampleVariance …
```

![](https://files.mdnice.com/user/17787/40fb523c-b052-4582-90e1-abd730fa72fb.png)

**动机**

文档页面通常需要包含数学表达式。例如，Apple 的 Accelerate 1 文档页面（使用 DocC 制作）通过方程式和矩阵来丰富文档的内容，以帮助阐明文档的文本内容。

虽然已经可以将数学表达式添加到 DocC 文档中，但所有现有的方法都还不够完善。

* 对于只包含单行的表达式，使用 Unicode 数学符号通常就足够了，比如 `‖𝑥ᵢ - 𝜇‖²`。但是对于包含多行的表达式，使用 Unicode 数学符号往往不够美观或不易阅读。例如，对于上面所示的 TL;DR 表达式，能做到的最好效果是 `¹⁄₍ₙ₋₁₎ ∑ᵢ₌₁ⁿ ‖𝑥ᵢ - 𝜇‖²`。而且，很多时候，多行表达式在 Unicode 数学符号中根本无法表示。例如，Unicode 中没有上标希腊字母。矩阵也是无法表示的。

* 可以将排版好的数学表达式（例如 `LaTeX` 的 .tex 文件或 MathML 的 .xml 文件）编译为图像（比如 .png 或 .svg 格式）。这需要保持 2 - 3 个文件同步：浅色模式下的图像、深色模式下的图像，以及可选的（但最好有的）源文件。这就是 Accelerate 文档所采用的方法（不包含深色模式支持）。

* 也可以使用链接中提到的第六种方法，这是我个人比较喜欢的方式，但它也有自己的缺点（在链接的帖子中有详细介绍）。

因此，为 DocC 提供对数学排版的一流支持将是一个受欢迎的补充。有许多不同的方法可以实现这一点，所以我在此发布帖子是为了让我们讨论潜在的解决方案。我将包含我个人的首选方案，以及一些替代方法。

**建议的解决方案**

保持简单：采用 MathML 编写，输出 MathML。DocC 输出的是网页；我认为我们应该充分利用这一事实，并在可能的情况下坚持使用 Web 标准。与 LaTeX 相比，MathML 的语法更加繁琐，但这个解决方案具有以下优势：

* 不添加任何依赖，比如 MathJax 或 KaTeX。
* 避免了在运行时将 LaTeX 编译为 SVG（或将 LaTeX 编译为 MathML，或将 MathML 编译为 SVG）的性能问题。对于前两种情况（LaTeX 转 SVG 和 LaTeX 转 MathML），MathJax 是臭名昭著的，因为它可能导致屏幕上有许多方程式时的滞后。
* 无需额外工作即可适应明暗模式，因为 MathML 元素使用当前的字体颜色。可以试一下：检查 DocC 网页，添加一个带有一些 MathML 的 `<math>` 标签，然后在明暗模式之间切换。
* 是最容易实现和维护的。在验证源 MathML 有效性后，DocC 只需将其未经修改地粘贴到网页中。

另外，无论输入是 MathML 还是 LaTeX，只要输出是 MathML（而不是 SVG 等其他格式），都将具有很好的可访问性，因为用户可以通过屏幕阅读器浏览 <math> 方程式。这比仅提供 alt 文本要好，因为在 DocC 支持数学排版之前，这是我们能做的最好的方式。 （话虽如此，MathJax 对于屏幕阅读器的支持也非常出色。）

作为未来的方向，我们可以考虑支持 LaTeX 作为源语言。如果我们这样做，我认为我们应该将 .tex 文件编译为 MathML（而不是 SVG、PNG 等）以保持一致性和最佳可访问性。另外，我们应该在编译文档时将源 LaTeX 编译为 MathML（即不通过 MathJax 或 KaTeX 在运行时进行编译），以获得更轻的文档网页并避免性能问题。

2) 讨论[在扩展范围内找不到类型 Bar](https://forums.swift.org/t/cannot-find-type-bar-in-scope-in-extension/66394 "在扩展范围内找不到类型 Bar")

给定以下代码：

```swift
struct Foo {
}

extension Foo {
    struct Bar {
    }
}
```

在下面这个看似无害的扩展中，会产生错误：Cannot find type 'Bar' in scope

```swift
extension Foo.Bar {
    static func bar () -> Bar { // Error: Cannot find type 'Bar' in scope
        Bar ()
    }
}
```

然而，使用 typealias 可以解决这个问题。

```swift
extension Foo.Bar {
    typealias Bar = Foo.Bar

    static func bar () -> Bar { // Okay
        Bar ()
    }
}
```

看不出来。有谁能解释这个错误的原因吗？

这两者不是等价的吗？

```swift
extension Foo {
    struct Bar {
        static func bar () -> Bar {
            Bar ()
        }
    }
}
extension Foo.Bar {
    static func bar () -> Bar {
        Bar ()
    }
}
```

**回答：**

值得注意的是，在扩展中，令人惊讶的是，Self 解析为 Bar：

```swift
struct Foo {    
}

extension Foo {
    struct Bar {
    }
}

extension Foo.Bar {
    static func bar () -> Self {
        return Self ()
    }
}
```

3) 讨论[处理非确定性任务执行顺序](https://forums.swift.org/t/dealing-with-non-deterministic-task-execution-order/66411 "处理非确定性任务执行顺序")

首先，想说明这个问题的范围超出了 TCA 本身，但我很好奇 TCA 是否能提供解决方案。

假设我们希望在 Main Actor 之外向数据库写入数据。

```swift
actor Database {
  func insert(_ value: Int) { print("insert \(value)") }
  func delete(_ value: Int) { print("delete \(value)") }
}
```

然后，我们有一个 Reducer，例如，从 UI 接收输入。

```swift
struct AppReducer: ReducerProtocol {
  struct State: Equatable { … }
  enum Action {
    case insert(Int)
    case delete(Int)
  }
  
  @Dependency(\.database) var database

  var body: some ReducerProtocol<State, Action> {
    Reduce { state, action in
      switch action {
      case let .insert(value):
        return .run { _ in
          await database.insert(value)
        }

      case let .delete(value):
        return .run { _ in
          await database.delete(value)
        }
      }
    }
  }
}
```

如果 Reducer 按照特定的顺序接收操作，由于 Actor 的重入性，数据库可能不会按照相应的顺序被调用。例如，如果 Reducer 接收以下操作：

```swift
viewStore.send(.insert(0))
viewStore.send(.delete(0))
```

由于 Swift Concurrency 中的每个挂起点都涉及非确定性的执行顺序，数据库可能会以错误的顺序执行，打印出：

```
delete 0
insert 0
```

在 GCD 世界中，会在串行队列上执行数据库写入操作，但是使用 Swift Concurrency 似乎没有很好的方法来模拟这种行为。因为每个挂起点都涉及非确定性的执行顺序。想知道是如何处理这个问题的。是否有根本不同的方式来思考 Swift Concurrency 中的设计模式？在其他情况下也遇到过这个问题，例如按照拍摄顺序显示照片。它适用于任何存在输入流进入异步进程并产生与输入相同顺序的输出的情况。

**回答：**

TCA 测试存储在序列化到主执行器时将表现出确定性（这是当前版本的配置选项，在即将发布的 1.0 版本中将成为默认设置）。

对于应用程序代码，如果需要在继续之前完全处理一个操作，可以使用 await：

```swift
await viewStore.send(.insert(0)).finish()
viewStore.send(.delete(0))  // 在上面的操作完成之前不会执行
```

4) 讨论[我只想编写能在任何地方使用的扩展](https://forums.swift.org/t/i-just-want-to-write-extensions-that-i-can-make-available-wherever-i-want/66407 "我只想编写能在任何地方使用的扩展")

**提问：**

为 String 和 Int 等类型编写和使用扩展很有趣，但是当这样做时，拉取请求没有获得批准，因为它们不符合 SOLID 原则。希望可以在协议内编写扩展，这样就可以在继承协议的任何地方使用扩展。

**回答：**
  
在 Swift 中，扩展遵循与任何其他类型声明相同的访问控制规则，因此，如果发现编写的扩展范围太广，可能希望利用一些工具来帮助解决这个问题。

例如，可以通过将扩展放在一个模块中，并且不将其设为 `public` 来限定其作用域，这样只有该模块中的类型才能看到并调用在该扩展中定义的方法。

或者，如果团队关心的是这些扩展是否合适，因为添加了在所有 String/Int/ 或其他类型上都不合理使用的功能，因此不应该广泛访问，那么更好的解决方案可能是引入一个新的特定于领域的类型，它包含一个 String/Int/ 或其他类型，并在其上提供特定于领域的接口。（例如，URL 类型可以被实现成包含一个 String，并提供相应工具的方式，而不是在 String 本身上提供 URL 类型的扩展）。”

5) 讨论[Enum Tuple case 组合/分解差异](https://forums.swift.org/t/enum-tuple-case-composing-decomposing-disparity/66406/1 "Enum Tuple case 组合/分解差异")

在这个例子中：

```swift
typealias Tuple = (first: Int, second: Int)

enum TupleEnum {
    case tuple(Tuple)
}

func foo(value: TupleEnum) {
    switch value {
    // case let .tuple(t: Tuple): break // 很明显
    // case let .tuple((first, second)): break // 很明显
    case let .tuple(first, second): break // ✅
    }
    TupleEnum.tuple(first: 0, second: 0) // 🛑 枚举 case 'tuple' 需要一个类型为 'Tuple' (也就是 '(first: Int, second: Int)') 的单一参数
}
```

可以使用两个单独的变量匹配一个接受元组的枚举 case，但不能反过来做：用两个单独的变量构造该 case。

同样在这个例子中：

```swift
typealias Tuple = (first: Int, second: Int)

enum PairEnum {
    case pair(first: Int, second: Int)
}

func bar(e: PairEnum) {
    switch e {
    // case let .pair(first, second): break // 很明显
    case let .pair(v: Tuple): break // ✅
    }
    let tuple = Tuple(first: 0, second: 0)
    PairEnum.pair(tuple) // 🛑 枚举 case 'two' 需要2个单独的参数
}
```

可以使用元组匹配接受两个单独变量的枚举 case，但不能反过来：用元组构造该 case。

是否可以以某种方式修复这个问题，使组合和分解行为保持一致？

**回答：**

更有趣的是，通过传递到泛型上下文，可以这样做：

```swift
enum PairEnum {
  case pair(first: Int, second: Int)
}

func apply<T, U>(_ f: (T)->U, _ x: T) -> U {
  return f(x)
}

let tuple = (first: 0, second: 0)
let result = apply(PairEnum.pair, tuple)    // 这是有效的！
```

...只是不能直接这样做，因为存在 SE-0029。

6) 讨论[为什么将类型元数据转换为 AnyObject 后，最后会调用 destroy_value 以销毁 AnyObject？](https://forums.swift.org/t/why-does-casting-type-metadata-to-anyobject-later-result-in-destroy-value-being-called-on-the-anyobject/66371 "为什么将类型元数据转换为 AnyObject 后，最后会调用 destroy_value 以销毁 AnyObject？")

> 此帖子可能看起来有点抽象和学术，但它源自一个真实的问题！

给定以下代码：

```swift
class A {
}

func b() {
  _ = A.self as AnyObject
}
```

编译器为函数 b 生成以下原始 SIL 代码：

```swift
%0 = metatype $@thick A.Type                    // user: %1
%1 = thick_to_objc_metatype %0 : $@thick A.Type to $@objc_metatype A.Type // user: %2
%2 = objc_metatype_to_object %1 : $@objc_metatype A.Type to $AnyObject // user: %3
destroy_value %2 : $AnyObject                   // id: %3
%4 = tuple ()                                   // user: %5
return %4 : $()                                 // id: %5
```

为什么在函数的末尾有一个 `destroy_value`？据我所见，没有平衡的“retain”存在吗？

**回答：**

1. `AnyObject` 值默认始终被视为已保留，因此编译器必须释放它。
2. 当将一个类转换为 `AnyObject` 时，编译器可以选择保留它，但它选择不这样做，因为它知道类是永久存在的，因此可以通过不执行此操作来节省代码大小和运行时间。

这两个局部推理的结果导致了遇到的问题。如果释放操作与创建 `AnyObject` 值的地方足够远（例如，可能将一个类分配给全局变量，然后稍后将其他内容分配给它），对（1）进行更智能的处理是不可能的。因此，唯一100％正确的选择是在（2）方面更加保守，从而为这种罕见的使用情况提供好处，但同时为其他所有人带来不必要的操作成本。

7) 讨论[为什么会有这种设计模式？](https://forums.swift.org/t/why-this-pattern/66392 "为什么会有这种设计模式？")

这与一般编程以及 Swift 本身都有关。

从 UIKit 中，我们得到了以下函数：

```swift
func touchesBegan(
    _ touches: Set<UITouch>,
    with event: UIEvent?
)
```

如果没有事件对象，这个函数几乎没有意义。文档并没有提到会收到空事件。那么为什么事件是一个可选类型呢？
  
**回答：**

我不认为 UIKit 会用空事件调用 `touchesBegan()`，但这是一个需要重写方法并手动转发事件的 API，如果您没有处理事件，则需要手动转发，但该转发可能无法正确转发事件。不幸的是，最初允许转发空事件，而在事后将其更改为非可选类型是困难的。

如果同样的 API 是在今天使用 Swift 设计的，我怀疑事件参数将不会是可选的。

## 推荐博文

[ @backDeployed 用于将函数的可用性扩展到旧版本的操作系统](https://www.avanderlee.com/swift/backdeployed-function-back-deployment/ " @backDeployed 用于将函数的可用性扩展到旧版本的操作系统")

**摘要：** 文章主要介绍了 @backDeployed 属性以及如何将函数的可用性扩展到旧的操作系统版本。 @backDeployed 属性是 Swift 5.8 首次实现的一项功能，并且在较低的最小部署目标和框架对比下，允许将新的声明提供给应用程序。文章详细解释了 @backDeployed 如何工作，并通过一个假设的 "Temperature" 类型的例子进行了演示。 @backDeployed 属性允许将函数回溯部署并使其对运行在旧版操作系统的应用程序可用。文章还指出，功能回溯部署主要对 SDK 开发者有用，同时也解释了为什么苹果不能将所有新的API回溯部署到旧的 OS 版本。使用 @backDeployed 属性进行函数回溯部署对于 SDK 开发者来说是一个很好的工具，能够使其 API 支持更有老旧的操作系统版本。虽然这不能解决所有新 API 的回溯部署问题，但它已经允许你使用一些新的、独立的 Swift API 。 

[Swift HTTP Types 的介绍](https://www.swift.org/blog/introducing-swift-http-types/ "Swift HTTP Types 的介绍")

**摘要：**  这篇 Swift 官方博客介绍了一个名为 "Swift HTTP Types" 的新的开源软件包。该软件包旨在为 Swift 中的客户端/服务器 HTTP 操作提供共享的通用类型。
文章指出，网络化应用中的网络技术对于许多用例来说在 Swift 中是无处不在的，包括客户端、服务器、中介和其他网络参与者。在苹果平台上，系统的 HTTP 实现通过 Foundation 框架中的 URLSession API 进行暴露。而对于 Swift 服务器项目，推荐使用 SwiftNIO 实现 HTTP。
为了在 Swift 中提供最佳的 HTTP 使用体验，共享的通用类型在许多项目中至关重要。 Swift HTTP Types 提供了一种表示 HTTP 消息核心构建块的通用表现形式。它包括 HTTPRequest 和 HTTPResponse ，分别代表客户端和服务器使用的 HTTP 消息。通过在多个项目中采用这些类型，可以在不同框架之间共享更多的代码，并消除在使用多个框架时的类型转换成本。

[Qunar 客户端 iOS 实时活动接入实践](https://juejin.cn/post/7260523399252475961?searchId=202307281123557A68223DBAE2C4960FFC/ "Qunar 客户端 iOS 实时活动接入实践")

**摘要：** 这篇文章介绍了去哪儿（Qunar）客户端如何实时接入了苹果在 iOS16 上推出的实时活动 (Live Activities) 功能。该功能允许应用在用户锁屏界面上展示实时信息，与常规推送相比，实时活动可以在一定时间段内持续展示，并于合适的时机自行消失，为用户提供更优秘体验。
通过实时活动功能，去哪儿的用户可以在出行全周期内，通过锁屏或灵动岛看到最新实时的出行信息。根据 Qunar 的数据，该功能自上线以来影响力显著，其中50%的用户已经与此功能互动，超过80%的用户因此而享受到更便捷的出行信息展示。目前，实时活动主要覆盖了航班和火车的出行场景，未来还可能延伸至船票、汽车票、景点门票等业务线场景，为 Qunar 的产品生态带来更大的贡献。
作者还详细介绍了实时活动的原理和机制，包括如何在主 APP 端启动一个实时活动实例，如何利用推送服务进行数据更新，如何关闭或更新实时活动等，并分享了在接入过程中遇到的问题及解决思路，希望帮助读者更好地理解和接入实时活动功能。。

## 话题讨论

**苹果公司正在考虑在今年秋季推出新款 iPhone Pro 时提高其高端手机的价格，那么如果到时候新款 iPhone Pro 在国内的价格超过了一万元，你还会买吗？**

1. 必须买，因为贵不是它的缺点，也不是我的缺点。
2. 超过一万元的话，那我现在的 iphone 还是可以将就用的。
3. 我有钱但不代表我傻，手里的钱买两斤排骨它不香吗？
4. 不买，当它超过一万快的时候，我的爱国情怀已悄然攀升。
5. 别说一万块钱啦，就是降价到五千，我也不买。

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
