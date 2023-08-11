## 前言

**本期是 Swift 编辑组整理周报的第三十五期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

是站在生命之巅，嘲笑死神的无能？还是跪在生活边缘，寻求生存的可能？**Swift社区**始于渺小，行至辽阔！👊👊👊

> **周报精选**
>
> 新闻和社区：五天市值蒸发 2000 亿美元，苹果公司怎么了？
> 
> 提案：具有编码验证的 `String Initializers`
> 
> Swift 论坛：Swift 分布式追踪
>
> 推荐博文：iOS ReplayKit 与 屏幕录制
>
> **话题讨论：** 
> 
> 苹果公司正在考虑在今年秋季推出新款 iPhone Pro 时提高其高端手机的价格，那么如果到时候新款 iPhone Pro 在国内的价格超过了一万元，你还会买吗？

**上期话题结果**

![](https://files.mdnice.com/user/17787/d83bb1a9-5218-4d1c-892c-bc767e2cfe00.jpg)

从投票结果可以看出来，购买决策不再仅仅只受价格影响，用户更注重手机性能、价值、国产支持等多个方面。你怎么看～

## 新闻和社区

### 五天市值蒸发 2000 亿美元，苹果公司怎么了？

不久前的 6 月份，苹果公司刚成为首家市值超过 3 万亿美元的企业，但其最新一季的财报却引发了投资者对其手机与其他设备需求不振的担忧。

8 月 4 日，苹果公司公布了三季度财报。财报显示，苹果第三财季营收 817.97 亿美元，不及上一财年同期的 829.59 亿美元，较上一财季的 948.36 亿美元大幅下滑。在看到新一季财报数据后，投资者惊讶地发现，这家巨无霸上市公司的营业收入已经连续 3 个财季下滑，且苹果在第四季展望中预测当季表现也不大会有差别。

公司股价接连下跌

苹果公司三季报发布日恰在其新产品 iPhone15 系列新机上市前，但市场预期苹果手机这一新机型受追捧程度不如以往。在悲观情绪影响下，苹果公司股价在 8 月 4 日财报公布日重挫 4.8% ，创下今年以来最大单日跌幅，市值一天之内蒸发逾 1600 亿美元。而后，苹果股价并未能止住跌势，截至本周一（8 月 7 日），苹果的股价已经遭遇“五连跌”，股价暴跌近 10% ，总市值蒸发超过 2000 亿美元，约合人民币 1.44万 亿元。

美国银行的分析师在一份业绩报告中表示，苹果正面临美国智能手机市场疲软的大环境。此外，估值过高可能也是苹果此次下跌的又一重要原因。对于苹果销售额的“三连降”，第一手机界研究院院长孙燕飙表示，消费电子市场持续低迷削弱了对智能手机的需求，叠加创新力不足难以拉动新机销量，苹果手机的销售收入连续下滑。如果苹果在第四财季的销售额继续同比下降，这将是该公司 20 年来销售额同比下降持续时间最长的一次。（来源：金融时报）

### 在你的 App 中帮助顾客解决账单问题

正如我们在 4 月份宣布的那样，很快，你的顾客就能直接在你的 App 中解决付款问题，以便更轻松地继续订阅你的内容、服务和高级功能。

自 2023 年 8 月 14 日起，如果自动续期订阅因账单问题而无法续订，你的 App 中会显示一个系统提供的表单，提示顾客更新其 Apple ID 的付款方式。你可以在沙盒中先测试一下此表单，还可以使用 StoreKit 中的 messages (英文) 和 display (英文) 来推迟或禁止显示此表单。这项功能在 iOS 16.4 和 iPadOS 16.4 或更高版本中提供，无需采取任何操作即可采用。

### 需要声明原因的 API 列表现已推出

Apple 致力于保护我们平台上的用户隐私。我们知道，有一小部分 API 可能会被滥用来通过信息指纹收集用户设备的相关数据，这是我们的 Developer Program 许可协议禁止的一种做法。为了防止滥用这些 API，我们在 WWDC23 (英文) 上宣布了开发者需要在 App 的隐私清单中声明使用这些 API 的原因。这将有助于确保 App 仅将这些 API 用于预期用途。在这个流程中，你需要选择一个或多个能够准确反映你的 App 如何使用相应 API 的批准原因，并且你的 App 只能出于你选择的原因使用相应 API。

从 2023 年秋季开始，如果你上传到 App Store Connect 的新 App 或 App 更新使用了需要声明原因的 API (包括来自第三方 SDK 的内容)，而你没有在 App 的隐私清单中提供批准的原因，那么你会收到通知。从 2024 年春季开始，若要将新 App 或 App 更新上传到 App Store Connect，你需要在 App 的隐私清单中注明批准的原因，以准确反映你的 App 如何使用相应 API。

如果目前批准原因的涵盖范围内并未包含某个需要声明原因的 API 的用例，且你确信这个用例可让你的 App 用户直接受益，请告诉我们。

## 提案

### 通过的提案

[SE-0403](https://github.com/apple/swift-evolution/blob/main/proposals/0403-swiftpm-mixed-language-targets.md "SE-0403") **软件包管理器混合语言目标支持** 提案通过审查。该提案已在 **三十四期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0405](https://github.com/apple/swift-evolution/blob/main/proposals/0405-string-validating-initializers.md "SE-0405") **具有编码验证的 String Initializers** 提案正在审查。

我们建议添加新的 `String` 可失败 `Initializer`s，用于验证编码输入，并在输入包含任何无效元素时返回 `nil`。

## Swift论坛
1) 讨论[Swift 字符串比较不将连字等同于其组件](https://forums.swift.org/t/swift-string-comparison-doesnt-consider-ligatures-equivalent-to-their-components/66665 "Swift 字符串比较不将连字等同于其组件")

**内容大概**

我刚刚发现 Swift 字符串将 "office" 和 "oﬃce" 视为不相等，这让我感到惊讶，因为它将 "caña" 和 "caña" 视为相等（即，都是组合和分解形式）。对于一般用户来说，这些情况是等价的 - 它们只是以不同的方式表示相同的字形（至少在某些字体中是如此）。

我进行了一些调查，似乎这是因为 Swift 承诺在 Unicode 术语中使用 "规范" 比较，而不是 "兼容" 比较。文档提到了这一点，但没有解释其含义。

我进一步查找并发现了有关 Unicode 中连字的一些争议和历史，这可能会为此提供一些启示（例如，目前 Unicode 关于连字的观点似乎是不应该用于字距调整，例如 "ﬃ"，但它仍然包含一些"不恰当" 的连字 - 再次，如 "ﬃ" - 这些连字是在这种心态转变之前添加的）。

`NSString` 也类似，除非你在使用 `compare(_:options:)` 时选择了 `caseInsensitive` 选项，这时它会将连字视为其分解形式。这很奇怪，因为这与字符大小写无关。

我猜这篇文章主要是向其他人提供信息和警告。但我很好奇为什么 Swift 选择执行 "规范" 比较，而不是 "兼容" 比较？此外，似乎在 Swift 标准库中没有办法执行 "兼容" 比较 - 必须导入 Foundation 才能获取字符串重叠部分，以便访问前面提到的 `NSString` 方法。

**回答**

兼容性分解是 Unicode 在需要与早期编码兼容（作为超集）的情况下所迫不得已的妥协。如果这些字符直接提议给 Unicode，它们将永远不会被编码。通常情况下，即使您在使用它们，也可能是在做错误的事情，因为它们所编码的内容（例如连字）不是文本的属性，而是显示格式的属性。

在 Unicode 的观点中，它们本身就不应该出现在原始字符串中。然而，将它们折叠到规范形式会丢失有关格式的信息，因此不能安全地应用于实际使用了它们的传统文本。（以“ff”为例，不是每一对“f”都要在显示中连接；那些跨越复合词两半的“f”应该保持分开。不能通过简单查看上下文来恢复这种区别，需要手动进行或通过字典查询来完成。）这与类似“ñ”的规范分解根本不同，后者在规范化过程中不会丢失信息。

如果想知道两个字符串是否在兼容性方面是等价的，则可以使用 Foundation 的 `decomposedStringWithCompatibilityMapping` 方法。

2) 提议[Swift 分布式追踪](https://forums.swift.org/t/pitch-swift-distributed-tracing/66679 "Swift 分布式追踪")

**动机**

虽然 [Logging](https://github.com/apple/swift-log "Logging") 和 [Metrics](https://github.com/apple/swift-metrics "Metrics") 可以用于仪器化应用程序的特定部分，但 [Distributed Tracing](https://github.com/apple/swift-distributed-tracing "Distributed Tracing") 提供了对整个分布式系统的整体视图。与这两者一起，分布式跟踪将完成“可观察性的三大支柱”。

与 Logging 和 Metrics 一样，如果在库和框架中直接使用一个共同的 API 来实现分布式跟踪，社区将从中受益最多。最终用户应该能够自由选择合适的后端实现，而无需更改他们正在使用的库或框架。

**建议的解决方案**

Swift 分布式跟踪围绕着创建跨度（span），这些跨度共同形成一种树状结构。跟踪可以由在单个服务中记录的跨度组成，也可以跨多个服务传播。Swift 分布式跟踪使用基于任务本地的 [Swift Service Context](https://github.com/apple/swift-service-context "Swift Service Context") 来实现透明的传播，无需手动传递上下文。

我们提出的解决方案是一个针对三个“角色”的库：

* 终端用户
* 库和框架作者
* 跟踪器后端实现

**用户端**

最终用户是从分布式跟踪中受益的人。他们选择适合自己需求的跟踪后端，使用具有内置的 Swift 分布式跟踪支持的库，并在自己的代码中进行手动仪器化。

**库和框架作者**

诸如 HTTP 服务器/客户端、数据库库等库/框架最了解如何仪器化其库的内部。他们使用 Swift 分布式跟踪 API 实现通用的跟踪支持，而无需考虑特定的跟踪后端。

例子:
* [Hummingbird](https://github.com/hummingbird-project/hummingbird/releases/tag/1.6.0 "Hummingbird")
* [Soto](https://github.com/soto-project/soto-core/pull/575 "Soto")

**跟踪后端实现**

最后一个难题是跟踪器后端实现。它们为导出跟踪 span 提供特定于供应商的支持。

例子

[Swift OTel](https://github.com/slashmo/swift-otel "Swift OTel") 公开了一个导出到 [OpenTelemetry Collector](https://opentelemetry.io/docs/collector "OpenTelemetry Collector") 的跟踪器。这已经允许该跟踪库的采用者导出到与 OpenTelemetry 兼容的流行后端，例如 Zipkin、Jaeger、Honeycomb 等。

**到期理由**

我们提议这个软件包处于“孵化”成熟度级别。 我们相信这个包是服务器生态系统的重要构建块，就像许多服务器和客户端库采用 [swift-log](https://github.com/apple/swift-log "swift-log") 和 [swift-metrics](https://github.com/apple/swift-metrics "swift-metrics") 一样。

该项目已经成熟超过3年，有多个活跃的维护人员，并且在生产环境中满足了采用要求。

3) 讨论[AttributedString 索引获取导致 nil 值的内部解包](https://forums.swift.org/t/attributedstring-index-fetching-causes-internal-unwrap-of-nil-value/66677 "AttributedString 索引获取导致 nil 值的内部解包")

**问题描述**

我有一个富文本字符串，其中一个子字符串正在被替换，但是会引发 fatalError：

```Swift
var string = AttributedString("café")
let replaceIndex = string.index(beforeCharacter: string.endIndex)
let range = replaceIndex..<string.endIndex
string.replaceSubrange(range, with: AttributedString("e"))
let next = string.index(afterCharacter: replaceIndex)
//                ^---- Unexpectedly found nil while unwrapping an Optional value
assert(next == string.endIndex)
```

这令人惊讶，因为我认为在更改之前，索引会保持稳定。更奇怪的是，改变如何创建范围不会导致失败。以下代码可以正常工作：

```Swift
var string = AttributedString("café")
let range = range(of: "é")!
string.replaceSubrange(range, with: AttributedString("e"))
let next = string.index(afterCharacter: replaceIndex)
assert(next == string.endIndex)
```

使用 ASCII 字符而不是重音符号 'é' 不会导致两种范围技术中的任何一种失败。我仔细分析了开源实现，试图揭示出现 nil 可选值的源头，但我看不到任何问题，我认为这与当前发布的代码不同。

对于我哪里的逻辑出了问题，有什么建议吗？

我使用的是 macOS 13.4.1 和 Xcode 15b5。

**回答**

明确一点，`RangeReplaceableCollection` 的变异操作可能会使现有索引失效，因为这些索引可能包含对于变异集合不再有效的信息（例如，在字符串的情况下，计算的字节偏移不再有效）。从 `RangeReplaceableCollection.replaceSubrange(_:with:)` 文档中可以看出：

> 调用此方法可能会使任何现有索引在与此集合一起使用时失效。

并且，这个方法几乎是 `RangeReplaceableCollection` 上所有其他操作的基础，所以人们应该假设（除非为特定类型另有说明）任何可能改变索引相关信息的变异操作都会使现有索引失效。

4) 提议[导入语句的访问级别](https://forums.swift.org/t/pitch-access-level-on-import-statements/66657 "导入语句的访问级别")

这是一个关于在 Swift 中更好地控制依赖和导入的提案。通过这个特性，可以将导入标记为公共的（当前的常规导入方式），对于模块的实现细节，可以标记为内部，对于源文件的实现细节，可以标记为私有或文件私有。

另外，更新后的包访问级别允许将依赖标记为仅对同一包中的模块可见。这会像源文件中的常规访问级别一样进行强制执行。将作为内部导入的声明只能从内部声明或更低的访问级别中引用，而在公共或包声明中使用则会报错。

下面是一个典型的用例，其中依赖项是我们不希望在模块 API 中暴露给客户端的实现细节，以及预期的诊断信息：

```Swift
internal import DatabaseAdapter

internal func internalFunc() -> DatabaseAdapter.Entry { ... } // Ok

public func publicFunc(entry: DatabaseAdapter.Entry) { ... }
// error: function cannot be declared public because its parameter uses an internal type

public func useInBody() {
    DatabaseAdapter.foo() // Ok
}

@inlinable
public func useInInlinableBody() {
    DatabaseAdapter.foo()
    // error: global function 'foo()' is internal and cannot be referenced from an '@inlinable' function
}
```
该提案还定义了一组条件，其中可以从客户端隐藏依赖项。这提供了一种强大的方法来完全隐藏实现细节，并可以加快客户端的构建时间。

这个提案旨在提供一个正式且更清晰的替代方案，来取代 `@_implementationOnly`。与此相反，此版本提供了熟悉的诊断信息，更多级别的控制，以及与非弹性模块和 `@testable` 客户端更好的兼容性。

根据社区对建议的 Swift 6 行为的反应，我们可以将其纳入该提案。

5) 讨论[序列化文件访问的 Actor](https://forums.swift.org/t/actors-that-serialise-file-access/66652 "序列化文件访问的 Actor")

**问题描述**

我想知道使用 Actor 是否是保护资源免受并发访问的好选择，例如一个文件目录。在过去，我曾使用 dispatch queues 实现这种情况。使用 Actor 作为阻塞文件访问 API 的通道点的优缺点是什么？

**回答**

> 仅仅是在文件系统中进行典型的CRUD操作

在这里，Actor并不能帮助你。即使在 Actor 可重入性的考虑之外，从 Actor 外部调用的 Actor 方法的执行顺序也无法保证。

CRUD 操作已经是线程安全的（如果它们不是，那将是一个相当令人失望的文件系统）。由于 Actor 不以执行方法的调用顺序“串行化”任何内容，因此不需要 Actor。

可能需要的是一个 FIFO 队列，这就是（串行的）DispatchQueue 解决方案为此提供的好处。

现在，如果谈论的是将一系列操作有效地“原子化”（例如，在枚举目录时不允许同时对其进行变异），那么需要保护的是一些可变状态，Actor 可以保护它。在我看来，这是比 CRUD 更高层次的抽象。在这方面，我认为 `@tera` 的问题在这里比想象的更相关。

6) 讨论[L-shaped 枚举](https://forums.swift.org/t/l-shaped-enums/66661 "L-shaped 枚举")

**问题描述**

用于缺乏更好的术语，我有很多“L-shaped”枚举，它们具有一些不同的有效载荷类型和一些共同的有效载荷类型。

以下是一个示例：

```Swift
extension ServerDelegate
{
    enum Request:Sendable
    {
        case get    (Get, EventLoopPromise<ServerResponse>)
        case post   (Post, EventLoopPromise<ServerResponse>)
        case delete (Delete, EventLoopPromise<ServerResponse>)
    }
}
extension ServerDelegate.Request
{
    enum Get { ... }
    enum Post { ... }
    enum Delete { ... }
}
```

这种布局存在问题：

很难访问共同的字段（`EventLoopPromise<ServerResponse>`），除非在枚举上进行 switch 操作。

很难在实际的变体有效载荷上进行 switch，因为您必须使用 _ 忽略共同字段。

这里有一个明显的重构方法，即将变体有效载荷提升到另一个嵌套类型：

```Swift
extension ServerDelegate
{
    struct Request:Sendable
    {
        let operation:Operation
        let promise:EventLoopPromise<ServerResponse>
    }
}
extension ServerDelegate.Request
{
    enum Operation:Sendable
    {
        case get    (Get)
        case post   (Post)
        case delete (Delete)
    }
}
extension ServerDelegate.Request.Operation
{
    enum Get { ... }
    enum Post { ... }
    enum Delete { ... }
}
```

但这感觉像是过多的嵌套和（过多？）的类型结构，与我尝试建模的复杂性成正比。而且 `ServerDelegate.Request.Operation.Get`、`ServerDelegate.Request.Operation.Post` 等枚举本身可能还有更多的嵌套结构。

我们有哪些替代方案呢？”

**回答**

命名空间中的点是嵌套的结果，这与这里的类型结构并不是真正的基本关系。提供便利的 API 来处理一些 `.init` 繁琐的情况似乎也是合理的，例如：

```swift
extension Request {
  static func get(url: URL, params: [String: String], mintPromise: () -> EventLoopPromise) -> Self { ... }
}
```

## 推荐博文

[iOS ReplayKit 与 屏幕录制](https://juejin.cn/post/7217692600647254071/ "iOS ReplayKit 与 屏幕录制")

**摘要：** 这篇文章主要介绍了使用 Apple 的 ReplayKit 框架来实现屏幕录制功能，包括应用内录制和系统级录制。 ReplayKit 从 iOS 9中第一次提供，已经发展并增强了许多特性。文章对创建和接入 ReplayKit  Extension ，系统级录制流程，以及在 LOOK 直播中的实践例子等进行了详细介绍。然而，屏幕录制开发面临着一些挑战，如内存限制、开发和调试困难、内存控制等。文章强调在开发过程中要小心应对这些问题，保持内存使用远离 50MB 的限制阈值，以及充分利用日志来解决问题，使能够优雅地完成屏幕录制功能。 

[TheRouter-iOS 轻量化路由中间件](https://juejin.cn/post/7264503433965518911/ "TheRouter-iOS 轻量化路由中间件")

**摘要：**  TheRouter 是一款由货拉拉打造的轻量级路由中间件，旨在支持 Android 和 iOS 平台。该中间件在 iOS 端吸取了其他语言的特性，增加了注解功能，强化了路由在 iOS 端的使用体验。 TheRouter 摒弃了传统 iOS 的 target-action 或 protocol 理念，对齐了更广泛的后台或 Android 应用。主要功能包括依赖注入、硬编码消除、动态化能力和页面导航跳转能力。文章详细解释了 TheRouter 的实现原理，如注解式依赖注入，路径硬编码处理等，并提供了详细的使用介绍和示例。

[iOS App Store 上架被拒 case](https://juejin.cn/post/7116301510887079967/ "iOS App Store 上架被拒 case")

**摘要：** 这篇文章主要记录了 App Store 上架过程中遇到的一些被拒绝的案例，以及对应的原因分析和解决策略。案例涵盖了从功能完整性、信息需要、隐私确认，到软件需求和上传被拒等不同阶段的问题。文章还详细阐述了各种问题的产生原因，如 APP 功能不全、集成未使用的库、隐私信息填写不全等，并提出相应的解决方案。通过这些案例的分享，开发者可以理解和学习如何避免类似的错误，更顺利地完成 App Store 的上架过程。

## 话题讨论

**报道称曾红极一时的少儿编程培训，如今现爆雷隐患。你认为儿童是否有必要提早接触编程课？**

1. 有必要：编程课可以激发儿童创造力，培养解决问题的能力。
2. 没必要：缺乏基础和成熟度，编程需要数学和逻辑思维能力，导致理解困难和挫败感。
3. 因人而异：有些儿童适合提早接触，有天赋和热情，发挥潜力，其他儿童可以在稍后阶段考虑。

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
