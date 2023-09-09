## 前言

**本期是 Swift 编辑组整理周报的第三十七期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

浅尝辄止必将黯然神伤，坚持不懈终会柳暗花明。**Swift社区**值得与之同行，一起成就卓越！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果跌近 3% 市值两天蒸发 1898亿 美元
> 
> 提案：包迭代提案正在审查
> 
> Swift 论坛：提议用户定义的元组一致性
>
> 推荐博文：Swift 中的线程安全性和使用锁的方法
>
> **话题讨论：** 
> 
> HUAWEI Mate 60 Pro 和 iPhone 15 你会如何选择？

**上期话题结果**

![](https://files.mdnice.com/user/17787/dc237f3b-c4d9-405f-96ef-1e913c5cfed3.jpg)

这个结果反映了人们对核污水排放问题的担忧，以及对个人健康和环境保护的重视。

## 新闻和社区

### 苹果跌近 3% 市值两天蒸发 1898 亿 美元

苹果股价连续两天大跌，实属罕见。截至收盘，苹果报 177.56 美元，跌幅 2.92% ，最新市值 2.8万 亿美元。苹果连续两天累计跌幅 6.5% ，其市值两天蒸发 1898 亿 美元（约 13911 亿元）。

![](https://files.mdnice.com/user/17787/bc24b290-75fc-4510-87fc-c43c618683ec.png)

消息面上，据中国基金报，一方面，下周公布 iPhone 15 系列手机，会跟目前卖爆的华为手机形成激烈竞争，另一方面有报道称 iPhone 手机在某些场合已被禁用。

另据报道，欧盟公布最严数字监管名单，苹果等科技巨头名列其中。

据上海证券报，欧盟将于周三公布首批受《数字市场法案》（简称 DMA ）监管的服务清单。这份清单将列出部分“守门人”，即处于绝对垄断地位的科技巨头。目前苹果、微软、亚马逊、Alphabet、Meta 和三星等已经在名单上，这些公司将承担不得滥用市场支配地位打压或并购竞争对手、与竞争对手建立链接等 DMA 规定的义务。

根据 DMA 的规定，“看门人”公司指在数字市场上扮演了关键的角色，拥有巨大的市场影响力，因此需要受到更严格的监管。具体条件为：公司年营业额超过 75亿 欧元、市值超过 750 亿 欧元(820 亿 美元)，在欧盟拥有 4500万 月活用户的平台。不过，在这些原始指标之外，欧盟方面对这些规定拥有一定的自由裁量权。

与此同时，欧盟委员会还启动了四项市场调查，以进一步评估微软 Bing、Edge 和微软广告以及苹果 iMessage 是否能获豁免。

苹果公司的一位发言人表示，该公司仍然“非常担心 DMA 给我们的用户带来的隐私和数据安全风险。”“我们的重点将是如何减轻这些影响，并继续为我们的欧洲客户提供最好的产品和服务。(来源：每日经济新闻)

### iPhone 15 系列订单量下滑，苹果公司面临双重市场冲击

9 月 4 日，根据第三方机构的消息称，苹果公司预计 2023 年下半年全球智能手机市场将呈现疲软态势，因此订购的 iPhone 15 数量可能会减少。

此前，苹果公司宣布 2023 年的秋季新品发布会时间为北京时间 9 月 13 日凌晨一点，备受瞩目的 iPhone 15 系列智能手机也将在发布会上正式亮相。

![](https://files.mdnice.com/user/17787/ef172311-dad7-475b-970b-f0a0d0723110.png)

随着发布会的时间临近，iPhone 15 系列的供应链备货情况也受到行业关注。

有分析师透露称，苹果公司在今年 8 月份就已经向供应链下达了 iPhone 15 系列在今年下半年的订单，订单量在 8000 万部到 9000 万部之间。

然而，2022 年 8 月份 iPhone 14 即将亮相的时候，苹果公司向供应链下达的 iPhone 14 系列订单在 9000万 部到 1 亿部之间，如今 iPhone 15 的订单量，相比去年 iPhone 14 的订单出现了大幅下滑！

8 月份的时候，苹果公司下达订单量主要考虑的是下半年的市场情况。对于订单量的下滑，苹果公司给出的原因是全球智能手机市场的疲软。

根据 Canalys 发布的研究数据显示，2023 年上半年，全球智能手机出货量达 5.28 亿部，同比下降 12% ，中国智能手机市场的出货量为 1.32 亿部，同比下滑 8% 。

无论是中国手机市场，还是全球手机市场，都没有从手机行业的下行中走出来，出货量仍在下跌。(来源：腾讯网新行情Pro)

### 苹果的对手回来了

8 月 29 日中午，在没有任何预告、发布会的情况下，华为官方发布了《致华为用户的一封信》，信中称华为推出了“ HUAWEI Mate 60 Pro 先锋计划”，当天 12 时 08 分在华为商城正式上线华为 Mate 60 Pro。

![](https://files.mdnice.com/user/17787/4332804f-27e3-47a3-b423-21d0c4357d26.png)

虽然毫无征兆，但是华为 Mate 60 Pro 依然受到了广泛关注，华为的消息一下子就冲上了微博热搜。

随后，在短短几个小时之内，华为商城首批 Mate 60 Pro 就被抢购一空，无数网友直呼华为赶紧出下一批！

更令人惊喜的是，华为 Mate 60 Pro 的网速已经达到了 5G 水平，还有卫星通话功能，这预示着手机内的芯片质量已经达到了 5G 芯片水平，华为真正劫后重生，王者归来。

这一下子，苹果公司直接慌了神，慌慌张张地宣布将于 9 月 13 日发布 iPhone 15 系列手机，作为对华为发布新手机的对冲。

苹果公司和华为，可以说是手机行业的老对手了。2019 年，如果不出意外的情况下，华为当年的手机销量、市场份额将会全面超越苹果，成为全球第一大手机厂商。

然而，在那之后所有人都看到了，华为的供应链出现了危机，不得不将荣耀子品牌脱离，甚至在手机全面进入 5G 时代的时候，只能推出 4G 的手机。

今年上半年，华为手机的销量已经彻底跌出了行业前 7 的位置，业内一度认为华为有可能会退出手机行业了。

然而，如今华为真正攻克了难关，携 Mate 60 王者归来，直接震撼了全球手机市场！
 
9 月 4 日，据媒体报道称，华为已将 Mate 60 系列手机的订单量提升至 1500 - 1700 万台。

业内人士预测，Mate 60 Pro 将有望成为华为 Mate 系列销量最高的手机，最终的订单量将在 1700 万台左右。(来源：腾讯网新行情Pro)

## 提案

### 通过的提案

[SE-0405](https://github.com/apple/swift-evolution/blob/main/proposals/0405-string-validating-initializers.md "SE-0405") **具有编码验证的 String Initializers** 提案通过审查。该提案已在 **三十五期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0408](https://github.com/apple/swift-evolution/blob/main/proposals/0408-pack-iteration.md "SE-0408") **包迭代** 提案正在审查。

在基于值和类型参数包提案 SE-0393 的基础上，这个提案使允许在值参数包中对每个元素进行迭代，并使用 `for-in` 语法将每个值绑定到本地变量。

### 驳回的提案

[SE-0403](https://github.com/apple/swift-evolution/blob/main/proposals/0403-swiftpm-mixed-language-targets.md "SE-0403") **软件包管理器混合语言目标支持** 提案被驳回。该提案已在 **三十四期周报** 正在审查的提案模块做了详细介绍。

## Swift论坛

1) 提议[用户定义的元组一致性](https://forums.swift.org/t/pitch-user-defined-tuple-conformances/67154 "用户定义的元组一致性")

**介绍**

元组无法符合当今的协议，这以明显的限制形式表现出来，例如无法使用可哈希值的元组作为字典键。

**动机**

SE-0283 的动机先前解决了元组符合某些标准库协议的愿望，该动机提出了对 Equatable、Comparable 和 Hashable 元组的内置语言支持。 独立地，Swift 并发工作添加了一个语言扩展，其中可发送值的元组本身就是可发送的。 我们建议将所有这些特殊情况行为与用户定义的元组一致性统一起来，现在可以使用参数包（SE-0393）来表达。 SE-0283 和 SE-0393 都将元组一致性列为未来方向。

**建议的解决方案**

我们建议引入参数化扩展语法，如泛型宣言中所述。 在一种特定情况下，允许使用此语法以最通用的形式声明元组一致性：

```Swift
extension <each T> (repeat each T): P where repeat each T: P { ... }
```

我们还将允许描述元组的通用类型别名通过条件一致性进行扩展； 我们建议将以下元组类型别名添加到标准库中以方便实现：

```Swift
protocol Shape {
  func draw()
}

typealias Tuple<each Element> = (repeat each Element)

extension Tuple: Shape where repeat each Element: Shape {
  func draw() {
    repeat (each self).draw()
  }
}
```

回想一下，协议中的要求是由具体符合类型的见证人实现的。 在上面，我们声明了一个元组扩展，因此draw()的见证者在元组上实现了协议要求 draw()。 实际的实现对每个元素调用 draw()，它本身符合 Shape。 请注意在 draw() 主体的重复模式中每个 self 的使用。

**详细设计**

任何未标记元组都可以通过“最通用”未标记元组类型的类型替换来获得。 如果每个 T 都是某种类型参数包，则这个最通用的类型是（重复每个 T）； 即，由每个 T 的元素的包扩展形成的元组类型。

如今，扩展的扩展类型必须是名义类型，无论是结构、枚举、类还是协议。 我们建议允许扩展最通用的元组类型； 这称为元组扩展。 由于扩展可以声明协议一致性，因此元组扩展可以实现最通用元组类型的协议要求。 这称为元组一致性。

这意味着元组扩展中 self 的类型是（重复每个 T），其中每个 T 是声明一致性的扩展的通用参数。 由于 SE-0399，对包扩展表达式中每个 self 的引用将扩展到元组的元素上。

与结构、枚举和类的扩展一样，元组扩展中的 Self 指的是 self 的类型，即（重复每个 T）。

一旦声明了对某个协议 P 的元组一致性，只要元组的元素满足元组一致性的条件要求，任意元组类型都将满足 P 的一致性要求。 我们将在下面看到，条件要求必须恰好由重复每个 T:P 的一个要求组成。当对元组类型的值调用协议要求时，由元组类型的元素形成一个包； 这成为调用协议见证中每个 T 的通用参数。

**孤儿规则**

在大多数情况下，元组一致性的行为就好像它们是标准库类型上的用户定义的追溯一致性。 特别是，两个模块定义两个不同的元组符合同一协议是无效的。 因此，我们禁止元组符合定义模块之外的协议。

**单元素元组展开**

根据参数包提案中规定的规则，单元素元组类型在替换后展开。 这意味着元组一致性必须与此展开保持一致。

这对元组一致性可以采取的形式施加了一些限制。 我们可以通过交换图的形式理解以下所有限制。 最上面一行显示了最通用的元组类型、相应的元组一致性以及某些关联类型 A 的见证。现在，我们对每个对象应用替换，将每个 T 的类型参数包替换为包含单个具体类型的包， 说 X。我们要求图中所有在同一对象处开始和结束的路径都产生相同的结果：

```Swift
(repeat each T) ---> [(repeat each T): P] ---> (repeat each T).A
      |                        |                        |
      |                        |                        |
      v                        v                        v
      X -------------------> [X: P] -----------------> X.A
```

具体而言，这些限制如下：

* 元组扩展必须声明符合一个协议。

* 此一致性的条件要求必须精确重复每个 T: P，其中每个 T 是扩展的类型参数包，P 是一致性协议。

* 也就是说，一个元组扩展扩展 Tuple: P ，其中重复每个 T: Q 是没有意义的，因为在单元素情况下，它会衰减到 X: P 其中 X: Q; 当 P 和 Q 可能是不相关的协议时，一般情况下该陈述是错误的。

* P 的关联类型要求 A 必须由其底层类型恰好为 (repeat (each T).A) 的类型别名见证； 也就是说，从每个元素投影 A 的元组类型。

也就是说，如果 X.A 是 Int，Y.A 是 String，那么我们别无选择，只能要求 (X, Y).A 等于 (Int, String)。
请注意，由于所有这些规则，空 tuple() 将符合每个具有元组一致性的协议。

**动态行为**

上述规则使我们能够保证元组一致性见证永远不会被单元素包调用，在这种情况下调用将直接转发到元素一致性。 因此，元组一致性中 Self 的运行时类型必须始终是真正的元组类型，而不是未包装的元素。

如果某个函数本身使用参数包从包中形成元组值，则对该值调用协议要求将调用元组一致性见证或单个元素的见证，具体取决于包的大小。

**标记元组和方差**

元组标签不是参数包可以抽象的东西。 然而，表达式类型系统定义了标记元组和相应的未标记元组之间的子类型关系。

与类类比，如果在非最终类 C 上声明了一致性，并且存在 D 继承自 C 的子类关系，则该一致性也被 D 继承。

为了在类继承的情况下用 D 替换 C 是有效的，我们要求 Self 仅用于协变或逆变位置，而不是不变的。 因此，我们必须对元组施加与当前对非最终类相同的限制。

这允许以下操作：

* 符合 Equatable 等协议，Self 出现在参数位置。
* 符合假设的 Clonable 协议，具有返回 Self 的 `func clone() -> Self` 要求。

另一方面，这是禁止的：

* 符合要求Self位置不变的协议，例如 `func f() -> G<Self>`。

在这种情况下，采用标记元组并将 `G<>` 应用于相应的未标记元组类型并不完全合理。

**使用范围**

由于上面概述的微妙的静态和动态行为，我们期望元组一致性仍然是一项高级功能。 对于许多目的，最好通过 SE-0398 声明一个特殊用途的可变参数泛型结构，并使其符合协议，因为这提供了完全的灵活性，而不会在一致性方面出现任何复杂情况：

```Swift
struct EggFactory<each Bird> {}

extension EggFactory: OmletMaker where repeat each Bird: Chicken {}
```

此模式还允许可变参数类型定义自定义构造函数和访问器以强制不变量等。

元组应该只符合具有明显“代数”实现的协议，该实现以归纳方式推广到元素类型的所有组合，例如上面讨论的三个标准库协议。

例如，使元组符合 IteratorProtocol 可能不是一个好主意，因为至少有两个明显的实现； 要么是压缩，要么是串联（在这种情况下，我们还需要要求所有序列具有相同的元素类型，这是元组一致性甚至无法表达的）。

2) 讨论[dispatchPrecondition 是实现 @unchecked Sendable 类型的合理方法吗？](https://forums.swift.org/t/is-dispatchprecondition-a-reasonable-way-to-implement-an-unchecked-sendable-type/67159 "dispatchPrecondition 是实现 @unchecked Sendable 类型的合理方法吗？")

我正在尝试提高我对何时使用 `@unchecked Sendable` 有意义的理解。

举个例子，使用 `dispatchPrecondition` 保证值只能在主线程上读取或修改：

```Swift
/// A wrapper that guaruntees that its value is only read or modified on the main thread.
/// For simplicity assume `T` is a value type.
final class MainThreadWrapper<T> {

  init(_ value: T) {
    dispatchPrecondition(condition: .onQueue(.main))
    _value = value
  }

  var value: T {
    get {
      dispatchPrecondition(condition: .onQueue(.main))
      return _value
    }
    set {
      dispatchPrecondition(condition: .onQueue(.main))
      _value = newValue
    }
  }

  private var _value: T

}
```

为了便于讨论，我们假设包装的值是值类型（而不是引用类型），因此我们不需要考虑不经过值设置器的修改。

使用 `@unchecked Sendable` 一致性将该类型设置为可发送是否合理？

```Swift
// Is this reasonable, given the expectations of Sendable?
extension MainThreadWrapper: @unchecked Sendable { }
```

使用这种类型时不可能出现数据竞争。 如果在错误的线程上使用了不正确的类型（例如，在主要参与者之外的任务中），`dispatchPrecondition` 将失败并阻止不允许的使用：

```Swift
struct NotSendable {
  var value: String
}

let wrapper = MainThreadWrapper(NotSendable(value: "foo"))

Task {
  // Allowed by the compiler since wrapper is Sendable, 
  // but a triggers a runtime error:
  print(wrapper.value)

  await MainActor.run {
    // Safe, prints "NotSendable(value: "foo")"
    print(wrapper.value)
  }
}
```

鉴于这种类型可以安全地跨并发域传递，而不会出现数据竞争，我倾向于认为这是 `@unchecked Sendable` 的合理用例。

人们怎么看？ 我特别有兴趣听到任何潜在的反驳意见。

**回答**

这里的包装器确实保证了底层数据的“安全”，但如果该类型在主队列之外使用过，它会崩溃。 这仅适用于声明为 `@MainActor` 的类型...但是一旦你以这种方式对其进行注释，那么你就已经获得了跨并发域的保证，即你将成为主要演员。

关于“安全”对你意味着什么，`@unchecked Sendable` 是一个承诺，你的类型可以在任何并发域中使用，并且仍然保护其自己的状态。 我认为这样标记你的包装纸是不正确的。 它仍然只能安全地从主队列使用。 （如果不是这种情况，它就会快速而有效地崩溃。）

3) 讨论[Swift 不会使用 ReferenceWritableKeyPath 编译dictionary，除非它是一个类属性](hhttps://forums.swift.org/t/swift-wont-compile-dictionary-with-referencewritablekeypath-unless-its-a-class-property/67148 "Swift 不会使用 ReferenceWritableKeyPath 编译dictionary，除非它是一个类属性")

这段代码编译可以通过：

```Swift
@objcMembers final class DriversLicense1: NSObject {
    private let map: [String: ReferenceWritableKeyPath<DriversLicense1, String>] = [
        "DAA": \DriversLicense1.nameFull,
    ]
    private(set) var nameFull: String = ""

    override init() {
        super.init()

        for (key, keyPath) in map {
            self[keyPath: keyPath] = key
        }
    }
}
```

但是，这段代码编译不能通过 - 错误是：

```Swift
cannot convert value of type 'KeyPath<DriversLicense2, String>' to expected dictionary value type 'ReferenceWritableKeyPath<DriversLicense2, String>'
```
```Swift
fileprivate let map: [String: ReferenceWritableKeyPath<DriversLicense2, String>] = [
    "DAA": \DriversLicense2.nameFull,
]
@objcMembers final class DriversLicense2: NSObject {
    private(set) var nameFull: String = ""

    override init() {
        super.init()

        for (key, keyPath) in map {
            self[keyPath: keyPath] = key
        }
    }
}
```

为什么？

**回答**
这绝对感觉像是一个诊断可能更有帮助的地方 - 如果你尝试直接在同一位置使用设置器，你会得到更好的消息：

无法分配给属性：“nameFull”设置器无法访问

似乎我们可以查看尝试 `KeyPath -> (Reference)WritableKeyPath` 转换的情况，并提供特殊的诊断，如果我们可以在 setter 在当前范围内可见的情况下形成适当的可写密钥路径。

4) 讨论[无法从 Objective C 类调用 swift 扩展方法](https://forums.swift.org/t/unable-to-call-swift-extension-method-from-objective-c-class/67174 "无法从 Objective C 类调用 swift 扩展方法")

我为 ViewController 类创建了 swift 扩展，并在其中定义了一种方法。 当我尝试从同一个 Obj-c ViewController 调用相同的方法时，它给出了以下错误：

`ViewController` 没有可见的 `@interface` 声明选择器 `testMe`

我的代码如下：

Objective-C类

```Swift
#import <UIKit/UIKit.h>

@interface ViewController : UIViewController

@end

@implementation ViewController

- (void)viewDidLoad {

[super viewDidLoad];

[self testMe]; // No visible @interface for 'ViewController' declares the selector 'testMe'

}
@end
```

Swift extension:
// ViewController+extnesion.swift

```Swift
import UIKit

@objc public extension ViewController {
    
    func testMe() {
        print("Vish")
    }
}
```

**回答**

你的 .m 文件需要导入 Swift 编译器发出的兼容性标头。

5) 讨论[使用类型包的通用结构无法在属性中使用相同类型包存储闭包](https://forums.swift.org/t/generic-struct-using-type-pack-cant-store-closure-using-same-type-pack-in-property/67145 "使用类型包的通用结构无法在属性中使用相同类型包存储闭包")

```Swift
struct Foo<each T> {
    let foo: (repeat each T) -> Void

    init(
        fn: @escaping (repeat each T) -> Void
    ) {
        self.foo = fn
    }
}
```

编译器使用 Xcode 15.0 beta 8 (15A5229m) 和 swift-DEVELOPMENT-SNAPSHOT-2023-09-04-a 工具链响应以下消息

```Swift
error: type of expression is ambiguous without a type annotation
        self.foo = fn
        ~~~~~~~~~^~~~
```

## 推荐博文

[SwiftDataKit：让你在 SwiftData 中使用 Core Data 的高级功能](https://juejin.cn/post/7275590714712883256?searchId=20230908113707B1CB34D5F133E8B64AD9 "SwiftDataKit：让你在 SwiftData 中使用 Core Data 的高级功能")

**摘要：**  SwiftDataKit 旨在帮助开发者在 SwiftData 中使用 Core Data的高级功能。由于 SwiftData 是 Core Data 的继任者，它在多个方面都对 Core Data 进行了改进和扩展。然而，当前版本的 SwiftData 还不能完全实现 Core Data 的所有高级功能，这对一些开发者而言可能是一个困扰。

为了解决这个问题，作者创建了 `SwiftDataKit` 库，通过提取 SwiftData 中底层的 Core Data 对象，使开发者能够在 SwiftData 中使用 Core Data 的高级功能 

[Swift 中的线程安全性和使用锁的方法](https://swiftwithmajid.com/2023/09/05/thread-safety-in-swift-with-locks/ "Swift 中的线程安全性和使用锁的方法")

**摘要：**  这篇文章讨论了 Swift 中的线程安全性和使用锁的方法。首先介绍了线程安全性的重要性，并提到了在代码库中发现的相关问题。接着通过一个简单的示例代码演示了状态管理的概念，并说明了这种代码可能导致数据竞争和竞争条件的情况。

为了解决这个问题，作者介绍了使用锁机制来控制对共享变量的并发访问。为了实现线程安全，博客展示了如何在 Swift 中使用 `OSAllocatedUnfairLock` 和 `NSRecursiveLock` 两种类型的锁。最后，博客总结了保证类的线程安全性的重要性，并鼓励在开发过程中早期就投入时间来构建类型安全的代码。

[ Swift 语言底层原理剖析 - Array 系列-高阶函数](https://juejin.cn/post/7275225666029797433?searchId=20230908125940173984B583F745BF08A0 " Swift 语言底层原理剖析 - Array 系列-高阶函数")

**摘要：** 文章介绍了Swift的数组中的 `filter`, `forEach`, `map` , `compactMap`, `flatMap`, `reduce` 等函数内部源码，剖析实现逻辑。Array系列的高阶函数其实是 `Collection` 的高阶函数，同样适合与 `Dictionary` ， Set 等其他集合类型。整体的设计也比较巧妙，用到了很多 Swift 特有的 `Protocol` 特性，对我们日后设计 Swift代 码也会有一些启发。

## 话题讨论

近期华为推出了“ HUAWEI Mate 60 Pro 先锋计划”，真正劫后重生，王者归来。而苹果公司将于 9 月 13 日发布 iPhone 15 系列手机，真正的王者碰撞开始了，那么假如你近期考虑换手机的话，你会如何选择呢？

1.果粉无需抉择，犹豫一秒都是对苹果的不尊重。
2.果断选华为呀，超高的性价比，绝对理性的选择。
3.我觉得一两千块钱的小米就挺好的，我再买两斤排骨不香吗？

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
