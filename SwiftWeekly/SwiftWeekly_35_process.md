## 前言

**本期是 Swift 编辑组整理周报的第三十五期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

是站在生命之巅，嘲笑死神的无能？还是跪在生活边缘，寻求生存的可能？**Swift社区**始于渺小，行至辽阔！👊👊👊

> **周报精选**
>
> 新闻和社区：五天市值蒸发2000亿美元，苹果公司怎么了？
> 
> 提案：
> 
> Swift 论坛：
>
> 推荐博文：
>
> **话题讨论：** 
> 
> 苹果公司正在考虑在今年秋季推出新款 iPhone Pro 时提高其高端手机的价格，那么如果到时候新款 iPhone Pro 在国内的价格超过了一万元，你还会买吗？

**上期话题结果**

![](https://files.mdnice.com/user/17787/9206a50e-e85e-4b70-bcff-5396ed536173.jpg)

这只是一个简单的投票结果，虽然不能完全反映实际的社会情况，但是也能帮助大家了解目前的生活状态（仅作参考）。

## 新闻和社区

### 五天市值蒸发2000亿美元，苹果公司怎么了？

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

> 
> 提案：
> 
> Swift 论坛：
>
> **话题讨论：** 
> 
> 有博主在视频社交平台说，2023年已然迎来了经济危机，只是有些人不愿意相信而已，那么你认为国内2023年是否真的进入了经济危机？

>**上期话题结果**

## 新闻和社区


## 提案


## Swift论坛
1) 讨论[Swift 字符串比较不考虑与其组件等效的连字](https://forums.swift.org/t/swift-string-comparison-doesnt-consider-ligatures-equivalent-to-their-components/66665 "Swift 字符串比较不考虑与其组件等效的连字")
**内容大概**
我刚刚发现 Swift String 认为“office”和“office”是不平等的，这让我感到惊讶，因为它认为例如 “caña”和“caña”相等（即组合形式和分解形式）。 对于外行来说，这些情况是等效的 - 它们只是表示相同字素的不同方式（至少在某些字体中）。

我做了一些挖掘，似乎这是因为 Swift 承诺使用 Unicode 术语中的“规范”比较，而不是“兼容”比较。 文档提到了这一点，但没有解释这意味着什么。

我进一步挖掘并发现了 Unicode 中关于连字的一些争议和传奇历史，这可能对此有所启发（例如，当前 Unicode 对连字的看法似乎是它们不应该用于字距调整目的，例如“ﬃ”是 ，但它仍然包含“不适当的”连字 - 再次，如“ﬃ” - 是在这次改变主意之前添加的）。

NSString 类似，除非您使用带有 caseInsensitive 选项的 Compare(_:options:) ，在这种情况下，它认为连字等于其分解形式。 这很奇怪，因为这与字符大小写无关。

我想这篇文章主要只是对其他人的仅供参考/警告。 但我很好奇为什么 Swift 选择进行“规范”比较而不是“兼容”？ 似乎也无法在 Swift 标准库中进行“兼容”比较 - 您必须导入 Foundation 来获取字符串覆盖，以便访问上述 NSString 方法。
**回答**
兼容性分解是由于需要与早期编码兼容（作为超集）而对 Unicode 做出的让步。 如果直接向 Unicode 提议，具有兼容性分解的字符将永远不会用 Unicode 进行编码。 一般来说，如果您甚至使用它们，那么您就做错了，因为它们编码的内容（例如连接）不是文本的属性，而是显示格式的属性。 在 Unicode 看来，它们从一开始就不属于原始字符串。 然而，折叠它们会导致该格式级别的信息丢失，因此它不能安全地应用于使用它们的旧文本。 （在“ff”的例子中，并不是每对“f”都应该在显示中连接起来；那些横跨复合词两半的“f”应该保持分开。你无法通过粗略的观察再次恢复这种区别 在上下文中，您需要手动或通过字典查找来完成。）这与“ñ”等规范分解有根本的不同，其中“恢复”是微不足道的，因此标准化不会有损。

如果您想知道两个字符串在兼容性方面是否等效，那么 Foundation 的 decomposedStringWithCompatibilityMapping 就是您所需要的。

2) 提议[Swift 分布式追踪](https://forums.swift.org/t/pitch-swift-distributed-tracing/66679 "Swift 分布式追踪")
**动机**
[Logging](https://github.com/apple/swift-log) 和 [Metrics](https://github.com/apple/swift-metrics) 使您能够检测应用程序的特定部分，而 [Distributed Tracing](https://github.com/apple/swift-distributed-tracing) 则提供整个分布式系统的整体视图。 与这两者一起，分布式追踪将完成“可观察性的三大支柱”。

与日志记录和指标一样，如果直接使用一个通用 API 在库和框架中实现分布式跟踪，社区将从中受益最多。 最终用户应该能够自由选择合适的后端实现，而无需更改他们正在使用的库或框架。

**建议的解决方案**
Swift 分布式跟踪围绕创建跨度，它们一起形成树状结构。 跟踪可以由单个服务中记录的跨度组成，也可以跨多个服务传播。 Swift 分布式跟踪使用基于任务本地的 [Swift Service Context](https://github.com/apple/swift-service-context) 来透明地实现传播，无需手动传递上下文。

我们提出的解决方案是一个针对三个“角色”的库：

* 终端用户
* 库和框架作者
* 跟踪器后端实现

**用户端**
最终用户是从分布式跟踪中受益的人。 他们选择适合自己需求的跟踪后端，使用内置 Swift 分布式跟踪支持的库，并通过手动检测来增强自己的代码。

**库和框架作者**
HTTP 服务器/客户端、数据库等库/框架最了解如何检测其库的内部结构。 他们使用 Swift 分布式跟踪 API 实现通用跟踪支持，而无需考虑特定的跟踪后端。

例子:
* [Hummingbird](https://github.com/hummingbird-project/hummingbird/releases/tag/1.6.0)
* [Soto](https://github.com/soto-project/soto-core/pull/575)

**跟踪器后端实现**
最后一个难题是跟踪器后端实现。 它们为导出跟踪跨度提供特定于供应商的支持。

例子
[Swift OTel](https://github.com/slashmo/swift-otel) 公开了一个导出到 [OpenTelemetry Collector](https://opentelemetry.io/docs/collector) 的跟踪器。这已经允许该跟踪库的采用者导出到与 OpenTelemetry 兼容的流行后端，例如 Zipkin、Jaeger、Honeycomb 等。

到期理由
我们提议这个软件包处于“孵化”成熟度级别。 我们相信这个包是服务器生态系统的重要构建块，就像许多服务器和客户端库采用 [swift-log](https://github.com/apple/swift-log) 和 [swift-metrics](https://github.com/apple/swift-metrics) 一样。

该项目已经成熟超过3年，拥有多个活跃维护者并满足生产中的采用要求。

3) 讨论[AttributedString 索引获取导致 nil 值的内部解包](https://forums.swift.org/t/pitch-mathematical-typesetting-in-docc/66418 "AttributedString 索引获取导致 nil 值的内部解包")
**问题描述**
我有一个属性字符串，其中有一个子字符串被替换，但出现了 fatalError：
```Swift
var string = AttributedString("café")
let replaceIndex = string.index(beforeCharacter: string.endIndex)
let range = replaceIndex..<string.endIndex
string.replaceSubrange(range, with: AttributedString("e"))
let next = string.index(afterCharacter: replaceIndex)
//                ^---- Unexpectedly found nil while unwrapping an Optional value
assert(next == string.endIndex)
```
这是令人惊讶的，因为我认为指数在变化之前会保持稳定。 奇怪的是，改变我创建范围的方式并不会导致失败。 这工作正常：

```Swift
var string = AttributedString("café")
let range = range(of: "é")!
string.replaceSubrange(range, with: AttributedString("e"))
let next = string.index(afterCharacter: replaceIndex)
assert(next == string.endIndex)
```
使用 ASCII 字符代替尖锐的“e”不会导致任一范围技术失败。 我拼凑了开源实现，试图找出 nil 可选的来源，但我看不到任何东西，并认为它与当前发布的代码不同。

对我的逻辑哪里出了问题有什么建议吗？

我使用的是 macOS 13.4.1 和 Xcode 15b5。

**回答**
需要明确的是，RangeReplaceableCollection 突变允许使现有索引无效，因为这些索引可能包含对于突变集合不再正确的信息（例如，在字符串的情况下，计算出的字节偏移量不再有效）。 来自 RangeReplaceableCollection.replaceSubrange(_:with:) 文档：
```code
Calling this method may invalidate any existing indices for use with this collection.

```
而且，此方法充当 RangeReplaceableCollection 上几乎所有其他操作的支柱，应该假设（除非针对特定类型另有记录）任何可能更改索引任何内容的变异操作都会使现有索引无效。

4) 提议[导入语句的访问级别](https://forums.swift.org/t/pitch-access-level-on-import-statements/66657 "导入语句的访问级别")
这是对 Swift 中的依赖项和导入进行更多控制的建议。 使用此功能，您可以将导入标记为公共（当前常规导入），将模块的实现详细信息标记为内部，将源文件的实现详细信息标记为私有或文件私有。 此外，较新的包访问级别允许将依赖项标记为仅对同一包的模块可见。 然后像源文件中声明的典型访问级别一样强制执行。 作为内部导入的声明只能从内部声明或更低级别的声明中引用，在公共或包声明中使用将报告为错误。

这是一个典型的用例，其中依赖项是我们不想在模块 API 中向客户端公开的实现细节以及预期的诊断：
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
该提案还定义了一组可以对客户端隐藏依赖项的条件。 这提供了一种完全隐藏实现细节的强大方法，并且可以加快客户端的构建时间。

[提议链接](https://github.com/xymus/swift-evolution/blob/access-level-imports/proposals/xxxx-access-level-imports.md)

该提案旨在为 @_implementationOnly 提供官方且更干净的替代品。 相比之下，该版本提供了熟悉的诊断、更多级别的控制以及与非弹性模块和@testable 客户端的更好兼容性。

根据社区对建议的 Swift 6 行为的反应，我们可以将其作为本提案的一部分。

5) 讨论[序列化文件访问的Actor](https://forums.swift.org/t/actors-that-serialise-file-access/66652 "序列化文件访问的Actor")
**问题描述**
我想知道Actor是否是保护资源免受并发访问的好选择，例如文件目录。 过去我使用dispatch queues实现了这个场景。 使用参与者作为阻止文件访问 API 的漏斗点有哪些优点和缺点？
**回答**
“只是文件系统中典型的CRUD操作。”
Actor在这里不会帮助你。 即使除了 Actor 重入性考虑之外，也无法保证从 Actor 外部的站点调用的 Actor 方法的执行顺序。

CRUD 操作已经是线程安全的。 （如果不是的话，这将是一个相当令人失望的文件系统。）由于Actor不会按照调用顺序执行方法来“序列化”任何内容，因此您不需要actor。

您可能需要的是 FIFO 队列，这就是（串行）DispatchQueue 解决方案给团队带来的好处。

现在，如果您正在谈论使操作序列有效地“原子”（例如，当有人枚举目录时不允许您改变目录），那么您就拥有了actor可以保护的一些可变状态。 我认为这是比 CRUD 更高的抽象级别。

6) 讨论[L形enum](https://forums.swift.org/t/l-shaped-enums/66661 "L形enum")
**问题描述**
由于缺乏更好的术语，我有很多“L 形”枚举，它们具有一些不同的有效负载类型和一些常见的有效负载类型。

这是一个例子：
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

在不切换枚举的情况下很难访问公共字段（EventLoopPromise<ServerResponse>）

很难打开实际的变体有效负载，因为您必须忽略公共字段

这里有一个明显的重构，即将变体有效负载提升到另一个嵌套类型：
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
但这感觉就像很多嵌套和很多（过多？）类型结构与我试图建模的东西的复杂程度成正比。 ServerDelegate.Request.Operation.Get、ServerDelegate.Request.Operation.Post 等枚举本身可能具有更多嵌套结构。

我们有什么选择？

**回答**
好吧，命名空间点是嵌套的结果，这对于这里的类型结构来说并不是真正的基础。 提供便利的 API 来处理一些 .init 汤似乎也是合理的，例如：
```Swift
extension Request {
  static func get(url: URL, params: [String: String], mintPromise: () -> EventLoopPromise) -> Self { ... }
}
```

## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
