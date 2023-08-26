## 前言

**本期是 Swift 编辑组整理周报的第三十六期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

一米阳光下阴雨绵绵，一米阳光上晴空万里，这就是生活。**Swift社区**伴你一起，走过风雨，沐浴暖阳！👊👊👊

> **周报精选**
>
> 新闻和社区：iPhone 15 全系配 USB-C 苹果拒绝接口和安卓互通
> 
> 提案：对 AsyncStream 的 Backpressure 支持
> 
> Swift 论坛：提议全局变量的严格并发
>
> 推荐博文：WWDC23 10105 - 打造响应更快的相机体验
>
> **话题讨论：** 
> 
> 日本核污水排海，你还会吃海鲜吗？

**上期话题结果**

![](https://files.mdnice.com/user/17787/85a89025-a0a8-48f0-bffe-bd7f7a5acde8.jpeg)

根据投票结果可以看出，大家有不同的想法。小编认为家长应该根据孩子的个性特点和兴趣爱好灵活调整，注重培养他们的创新精神和独立思考能力。

## 新闻和社区

### 消息称苹果公司和印度财政部官员磋商，扩大在印度的制造产能

8 月 25 日消息，根据印度当地媒体 Business Today 报道，苹果印度地区的高管已经和当地财政部会面，探讨扩大 iPhone 在印度产能相关事宜。

消息称本次探讨涉及面很广，印度政府希望以苹果公司带头下，进一步推动本土智能手机制造业，并磋商相关的扶持政策。

而苹果公司在交流中也表示，印度是非常重要的生产地和消费市场，乐于扩大在印度市场的产能，但希望能获得更多的补贴，以及政策福利。

IT之家此前报道，根据市场调查机构 Counterpoint Research 公布的统计数据，2023 年第 2 季度印度市场营收表现首次超过法国和德国，成为苹果第五大 iPhone 市场。

苹果 iPhone 零售业在印度市场的快速增长的同时，苹果也加快了 iPhone 在印度制造的脚步。苹果加大了在印度市场的投资力度，希望供应链实现多元化发展。（来源：IT之家）

###  iPhone 15 Pro 机型新增泰坦灰

新渲染图曝光，消息称苹果 iPhone 15 Pro 机型泰坦灰将替代金色 iPhone15Pro新增灰色。8 月 25 日消息，根据国外科技媒体 9to5Mac 报道，苹果今年将调整 iPhone 15 Pro 和 iPhone 15 Pro Max 两款机型的颜色选项，取消金色，新增灰色。
在最新报道称这种全新灰色官方名称为“泰坦灰”（Titan Gray），并分享了这种颜色的概念渲染图，可以看到“泰坦灰”颜色要比现有的银色 / 白色更深一些，但比深空黑要更淡一些。
该媒体还透露苹果今年推出的 iPhone 15 Pro 机型将会取消暗紫色，并由深蓝色替代。
注： iPhone 14 Pro 机型共有暗紫色、金色、银色和深空黑四种颜色。
苹果预估将于 9 月 12 日发布 iPhone 15 系列，其中 iPhone 15 系列标准版将有黑色，绿色，蓝色，黄色和粉红色。（来源：IT之家）

![](https://files.mdnice.com/user/17787/1e3e2489-9b4e-4202-8189-a234f10d0559.png)

### iPhone 15 全系配 USB-C 苹果拒绝接口和安卓互通

8月19日消息，据供应链最新消息称，iPhone 15 全系将会配备 USB-C 接口，不过不同型号会被差异对待。

按照供应链说法，iPhone 15 标准版只是配备普通版本的 USB-C 接口，而 iPhone 15 Pro 系列则在速度上有明显的提升，同时这个功能只能在 MFi 认证的 USB 数据线下发挥功效。

具体来说就是，iPhone 15 标准版提供 USB 2.0 版本，传输速度最高 480 Mbps，与之前的 Lightning 接口差不多。而 iPhone 15 Pro 系列用的是 USB 3.2，传输速度能达到 20 Gbps，比标准版快 20 倍以上。

对于消费者来说，这将是多年来 iPhone 系列手机最大的改进之一。配备该端口后，iPhone 用户在旅行时不再需要为手机和其他移动设备携带两根不同的充电线，不过想法是好的，但苹果却不会这么干。

按照供应链配件商的说法，苹果不会让 iPhone 15 的 USB-C 接口与安卓通用，即便是有违法的行为，但依然会如此做，毕竟 MFi 认证背后一年是几十亿美元的盈利。

此外，从苹果的备货来看，Pro 系列占比超过 60%，他们也是想从这些细节的地方卡位用户，让大家主动去买高价版本。

![](https://files.mdnice.com/user/17787/3eab2868-eefd-4141-92c3-a3e1835847c5.png)

## 提案

### 正在审查的提案

[SE-0407](https://github.com/apple/swift-evolution/blob/main/proposals/0407-member-macro-conformances.md "SE-0407") **成员 Macro 一致性** 提案正在审查。

SE-0402中从一致性宏到扩展宏的转变包括扩展宏能够了解类型已经遵循了哪些协议(例如，因为遵循了超类或在某处声明了显式一致性)，这样宏就可以避免添加不需要的声明和一致性。这也意味着添加的任何新声明都是扩展的一部分——而不是原始类型定义的一部分——这通常是有益的，因为这意味着(例如)新的初始化器不会抑制成员初始化器。将协议一致性拆分为各自的扩展通常也被认为是一种很好的形式。

然而，有时用于一致性的成员确实需要成为原始类型定义的一部分。例如:

* 非 final 类中的初始化项必须是必需的初始化项，以满足协议要求。
* 非 final 类的可重写成员。
* 存储的属性或大小写只能在主类型定义中。

对于这些情况，成员宏可以生成声明。然而，成员宏并没有提供任何关于应该为哪种协议一致性提供成员的信息，因此宏可能会错误地尝试将一致性成员添加到已经符合协议的类型中(例如，通过超类)。这可能使某些宏(例如实现 `Encodable` 或 `Decodable` 协议的宏)无法实现。

[SE-0406](https://github.com/apple/swift-evolution/blob/main/proposals/0406-async-stream-backpressure.md "SE-0406") **对 AsyncStream 的 Backpressure 支持** 提案正在审查。

SE-0314引入了新的 `Async[Throwing]Stream` 类型，作为根异步序列。这两种类型允许从同步回调（如委托）桥接到异步序列。该提案增加了一种构建异步流的新方法，目的是将 Backpressure 系统桥接成异步序列。此外，该提案旨在澄清消费任务取消和生产方表示终止时的取消行为。

## Swift论坛

1) 提议[宏文字协议](https://forums.swift.org/t/pitch-macro-literal-protocols/66915 "宏文字协议")

目前仅允许在顶层使用宏。 然而，在某些情况下，嵌套宏会很有好处。

例如，我们可以添加具有宏要求的新文字协议：

```Swift
public protocol ExpressibleByMacroIntegerLiteral {
  associatedtype IntegerLiteralType: _ExpressibleByBuiltinIntegerLiteral

  @freestanding(expression)
  macro Init(integerLiteral: IntegerLiteralType) -> Self
}
```

然后用编译器的魔法，酱子：

```Swift
let x: Decimal = 5.3
```

可以变成酱子：

```Swift
let x = #Decimal.Init(integerLiteral: 5.3)
```

然后将扩大

我知道宏的设计目标之一是避免这种不可见的宏使用，但是已经有很多编译器魔法可以通过 _ 文字协议来表达，这将使它们更加通用。

例如，当前如果类型是 `ExpressibleByStringLiteral` 但只有某些字符串文字有效，则唯一的选择是在运行时遇到无效字符串文字时捕获。 这违背了文字的编译时性质，而文字应该允许检查文字。 在基金会提出将 URL 改为 ExpressibleByStringLiteral 时，这个问题在某种程度上被掩盖了，但已经完全解决了。

这个语句：

```Swift
downloadFile(at: "https://apple.com")
```

看起来比这个好很多:

```Swift
downloadFile(at: #URL("https://apple.com"))
```

2) 提议[嵌套 if let 和 guard let](https://forums.swift.org/t/pitch-nested-if-let-and-guard-let/66927 "嵌套 if let 和 guard let")

**介绍**

在 Swift 中，if let 语句通常用于可选的解包。 它通过处理可选值帮助开发人员编写更干净、更安全的代码。

目前，if let 语句解包单个可选值。 然而，在某些情况下，我们希望以更简洁的方式解开嵌套对象的可选属性。

该提案建议扩展 if let 和 Guard let 语句以支持嵌套可选展开。

**1. if let 嵌套**

嵌套 if let 的拟议语法将允许开发人员有条件地解包嵌套对象的可选属性。 如下：

```Swift
if let myOptionalObject?.optionalValue {
    // 'optionalValue' is now safely unwrapped and ready to use // *1
} else {
    // Handle the case where 'optionalValue' is nil
}
```

**2. 嵌套的 guard let**

类似地，所提议的嵌套 Guard Let 语法将允许开发人员有条件地解开嵌套对象的可选属性。 如下：

```Swift
guard let myOptionalObject?.optionalValue else {
    // Handle the case where 'myOptionalObject' or 'optionalValue' is nil
    // This could include returning from the current function, loop, or throwing an error
}

// 'optionalValue' is now safely unwrapped and ready to use // *1
```

3) 提议[全局变量的严格并发](https://forums.swift.org/t/pitch-strict-concurrency-for-global-variables/66908 "全局变量的严格并发")

**介绍**

该提案定义了无数据竞争的全局变量的使用选项。 在此提案中，全局变量包含静态持续时间的任何存储：在全局范围内声明或作为静态成员变量声明的 let 和存储变量。

**动机**

全局状态在并发性中提出了挑战，因为它是可以从任何程序上下文访问的内存。 全局变量在数据隔离检查中受到特别关注，因为它们违背了其他强制隔离的尝试。 

本地且未捕获的变量只能从本地上下文访问，这隐式地隔离了它们。 值类型的存储属性已经通过排他性规则隔离。 

可以通过使用可发送性强制或使用参与者限制来隔离引用类型的包含对象，从而隔离引用类型的存储属性。 但全局变量可以从任何地方访问，所以这些工具不起作用。

**建议的解决方案**

在严格的并发检查下，要求每个全局变量要么与全局参与者隔离，要么两者都隔离：

* 不可变的（immutable）
* 可发送类型（Sendable）

immutable 并且 Sendable 的全局变量可以从任何上下文安全地访问，否则需要隔离。

**详细设计**

这些要求可以在声明时在类型检查器中强制执行。

**源兼容性**

由于增加了限制，因此在使用严格的并发检查时可能需要更改某些类型声明。 然而，此类源代码更改仍然向后兼容任何具有并发功能的 Swift 版本。

**ABI兼容性**

该提案本身不会添加或影响 ABI(Application Binary Interface)，但是它可能对采用的项目引发的类型声明更改可能会影响该项目的 ABI。

**对采用的影响**

在采用严格并发检查的项目中，可能需要修改某些全局变量类型。

**考虑的替代方案**

为了隔离，我们可以隐式锁定变量的访问，而不需要全局参与者。 在提供内存安全的同时，这可能会给线程安全带来问题，因为开发人员可以轻松编写 non-atomic 的模式：

```Swift
// value of global may concurrently change between
// the read for the multiplication expression
// and the write for the assignment
global = global * 2
```

虽然如果我们需要在旧语言模式中做一些源兼容的事情，我们可以考虑隐式锁定，但通常我们的方法只是说旧语言模式是并发不安全的。 

它也不适用于非可发送类型，除非我们强制该值在访问它时保持隔离。我们可能可以通过提议的[跨隔离域安全发送不可发送值](https://forums.swift.org/t/pitch-safely-sending-non-sendable-values-across-isolation-domains/66566 "跨隔离域安全发送不可发送值")功能来实现这一目标，但这可能是一个过于先进的功能，无法作为此类基本问题的解决方案来推动。

我们可以将所有需要隔离的全局变量默认为 `@MainActor`。 可以说，让开发人员考虑选择会更好（例如，也许它应该只是一个 let 常量）。

访问控制在理论上是有用的：例如，我们可以知道全局变量是并发安全的，因为它是文件私有的，并且该文件中的所有访问都来自单个全局参与者上下文，或者因为它永远不会 变异了。 

不过，这比我们通常希望在编译器中进行的分析更加全局化； 我们必须检查上下文中的所有内容，然后开发人员可能很难理解它为什么起作用。

**未来发展方向**

我们不一定需要明确地要求隔离全球参与者； 有空间推断正确的全球行动者。 全局角色约束类型的全局可变变量可以被推断为约束到该全局角色（尽管如果变量是不可变的，则没有必要，因为全局角色约束类类型是可发送的）。

4) 讨论[用 globalActor 标记的方法修改类中的属性](https://forums.swift.org/t/method-marked-with-globalactor-modifying-property-in-class/66898 "用 globalActor 标记的方法修改类中的属性")

```Swift
protocol Po {
    @MainActor
    func foo()
}

class Base: Po {
    var str = ""
    func foo() {
        str = "w"
        print("foo: \(Thread.isMainThread)") // true
    }
}

if #available(macOS 10.15, *) {
    Task {
        let b = Base()
        await b.foo()
    }
} 

RunLoop.main.run()

while true {}
```

我不明白为什么我可以直接在标有MainActor的方法中修改属性？

因为这对我来说似乎是错误的。
我相信 Base 及其属性不在 MainActor 上运行。

**回答**

您在顶层创建 Task，这隐式地使其在 main actor 上运行。 由于 Base 只是一个类（而不是 actor），因此它的方法在其调用者所在的任何上下文中运行，在本例中这是 main actor。
属性和方法可以单独与特定参与者相关联，包括作为协议要求的一部分。 在这种情况下 foo 隐式是 @MainActor，因为 Po 协议如此声明它。

这可能有点太神奇了 - foo 也是隐式异步的，尽管它从未真正被标记为异步，即使在原始协议声明中也是如此。

为了进一步测试这一点，如果您添加到 Base 例如：

```Swift
func bar() {
    foo()
}
```

将收到编译器错误 `Call to main actor-isolated instance method 'foo()' in a synchronous nonisolated context`，表明编译器将 foo 视为 @MainActor（但 Base 的其余部分不是）。

5) 讨论[在 "super.init" 调用之前使用的 "self" 与 "在 super.init 调用时未初始化属性" 冲突](https://forums.swift.org/t/self-used-before-super-init-call-conflicts-with-property-not-initialized-at-super-init-call/66896 "在 "super.init" 调用之前使用的 "self" 与 "在 super.init 调用时未初始化属性" 冲突")

我需要在 init 中创建一个捕获 self 的闭包来初始化属性，但我无法使用 self，因为 super.init 尚未被调用。 但是，我无法调用 super.init，因为该属性尚未初始化！

```Swift
import Foundation

class Base {
}

class Sub: Base {
    let timer: Timer
    var value = 0
    
    // option 1 - try to initialize the property
    override init() {
        // ERROR: 'self' used before 'super.init' call
        timer = .scheduledTimer(withTimeInterval: 1, repeats: true) { [weak self] _ in
            self!.value += 1
        }
        super.init()
    }

    // option 2 - try to initialize super first
    override init() {
        super.init()  // ERROR: Property 'self.timer' not initialized at super.init call
        timer = .scheduledTimer(withTimeInterval: 1, repeats: true) { [weak self] _ in
            self!.value += 1
        }
    }

}
```

除了使属性既可选又可变（在 super.init 期间初始化为 nil，然后在之后更改它）之外，还有什么办法可以解决这个问题吗？

我有点明白为什么编译器不能接受这种情况，但是必须使属性可选且可变，这很烦人，而一旦类完全初始化，它实际上既不应该为零，也不应该变。

**回答**

需要在函数内有一个本地变量：

```Swift
init() {
    var futureSelf: Sub? = nil
    timer = .scheduledTimer(withTimeInterval: 1, repeats: true) { [weak futureSelf] _ in
            futureSelf?.value += 1
        }
    super.init()
    futureSelf = self
}
```

值得注意的是，编译器无法知道采用闭包捕获 self 的对象是否不会立即被调用，并且它试图避免使用半初始化的 self 实例调用闭包。

6) 讨论[显式使用引用类型后是否应该调用 deinit？](https://forums.swift.org/t/should-deinit-be-called-after-explicit-consume-of-reference-type/66920 "显式使用引用类型后是否应该调用 deinit？")

我想通过使用 `_ = Consumer` 对象显式结束演员/类的生命周期，以避免引入具有单独作用域的另一级嵌套。 但是，在显式消费之后不会调用该对象的 deinit。 相反，它是在作用域末尾调用的。 这是预期行为还是编译器错误？ 对于不可复制的结构，它可以按预期工作。

```Swift
class Object {
    deinit { print("deinit object") }
}

struct Noncopyable: ~Copyable {
    deinit { print("deinit noncopyable") }
}

func testDeinitAfterConsume() {
    do {
        let object = Object()
        print("before consume")
        _ = consume object
        print("after consume")
    }
    
    print()
    
    do {
        let noncopyable = Noncopyable()
        print("before consume")
        _ = consume noncopyable
        print("after consume")
    }
}
```

打印结果：

```Swift
before consume
after consume
deinit object

before consume
deinit noncopyable
after consume
```

**回答**

这是可以理解的。 一般来说，每当对象丢失最后一个引用时，类析构器就会运行，而不考虑变量范围。

在某种程度上不鼓励在类去初始化中依赖共享可变状态，并且强烈不鼓励依赖与常规代码中的副作用相关的顺序。 即使没有优化，它通常也会很棘手并且容易出错。

对对象生命周期的显式控制是 Swift 中依赖类取消初始化顺序的官方方法：

```Swift
withExtendedLifetime(object) {
    // Modify shared mutable state without accessing object.
}
```

对于局部变量（包括参数），编译器（5.7 后）遵循一些保守的生命周期规则，以便大多数“看起来正常”的编程模式无需显式生命周期管理即可工作。 事实上，如果我们按照字面意思理解这个示例，则 deinit 将不会发生，并且我们永远不会看到以下输出：

```Swift
deinit object
before consume
after consume
```

额外的安全规则是：

如果不安全指针或弱引用可能依赖于局部变量的生命周期，则编译器会自动扩展该变量持有的任何引用。

如果常规代码在 Swift 外部调用（包括所有 I/O）或跨任务同步（调用异步函数），则类析构器将不会跨这些边界重新排序。 这也意味着程序员可以通过添加同步代码来控制对象的生命周期，而无需 withExtendedLifetime。 在此示例中，调用 “print” 被视为同步点，从而阻止优化。

这里有更详细的描述：https://gist.github.com/atrick/cc03c4d07fb0a7bee92c223ae5e5695b#lexical-variable-scope-can-affect-object-lifetime
在这方面，消耗参数与 “let”、“var” 和非 “消耗” 参数不同，因为它们的生命周期可以在隐式消耗时提前结束：

```Swift
func bar(_ object: consuming Object) {}

func foo(object: consuming Object) {
    bar(object)
    print("after consume")
}
```

总是得到结果：

```Swift
deinit object
after consume
```

这为那些关心 ARC 开销和 CoW 行为的人提供了理想的编程模型。 很快，我希望所有局部变量都具有“消耗”的效果。

## 推荐博文

[掌握 StoreKit2](https://swiftwithmajid.com/2023/08/01/mastering-storekit2 "掌握 StoreKit2")

**摘要：** 本文介绍了 Swift 中的 StoreKit2，这是一个用于构建应用内购买和订阅的框架。文章从配置项目和创建 StoreKit 配置文件开始，介绍了如何使用 Store 类型处理应用内购买逻辑。通过示例代码和说明，文章展示了如何使用 Store 类型来获取和显示应用内购买产品列表，并启动购买流程。还介绍了产品类型和其 purchase 函数，在成功购买时处理交易和验证过程。文章还涉及了处理挂起状态和监视交易更新的方法。此外，提到了 StoreKit2 提供的 currentEntitlements 属性，用于获取活动订阅和已购买产品列表。最后，文章给出了一个基本的 App 结构示例，其中包含了 Store 对象，并在应用程序启动时获取活动交易。 

[ iOS 防 dump 可行性调研报告](https://juejin.cn/post/7251501966592917563 " iOS 防 dump 可行性调研报告")

**摘要：**  文章介绍了如何防止 iOS App 被 dump ，包括代码混淆、加密、完整性检查等多层防御策略，以及服务器端验证、动态加载、API 安全性和多因素认证等方案。此外，监控与告警、定期安全审计和安全培训等后置方案也可以提高 App 的安全性。最后，还介绍了禁止越狱设备的实施方案，以及 DeviceCheck 和 App Attest API 等新技术方案。

[ WWDC23 10105 - 打造响应更快的相机体验](https://juejin.cn/post/7268119060055031865 " WWDC23 10105 - 打造响应更快的相机体验")

**摘要：** 文章介绍了 iOS17 提供了一些新的特性，通过延迟图片处理、快门零延迟、响应捕获等新特性，以及状态监听等措施，能大幅提高相机响应速度，创造更流畅的拍摄体验。

## 话题讨论

**日本核污水排海，你还会吃海鲜吗？**

1. 会
2. 不会

欢迎在文末留言参与讨论。


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
