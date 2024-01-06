
## 前言

**本期是 Swift 编辑组整理周报的第四十五期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

我能有什么办法，失去和拥有都由不得我.**Swift社区**也和你一样伤心无奈，但新的一年还是要积极坚强的生活！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果或将扩充健康版图，为 Apple Watch X 铺路
> 
> 提案：推断方法和关键路径文本的 Sendable 提案通过审查
> 
> Swift 论坛：讨论在循环中初始化强制属性的推荐方法？
>
> 推荐博文：手把手教你用 Swift 实现命令行工具

> **话题讨论：** 
> 
> 过去的 2023 年你完成了哪些目标？

**上期话题结果**

![](https://files.mdnice.com/user/17787/f0928233-780d-461d-b200-298fc1467e91.jpg)

根据投票结果可以看出在晋升过程中，组内成员普遍认为实际项目贡献至关重要。然而，领导风格、人际关系以及对未来发展的长远考量也受到了一定程度的重视。

## 新闻和社区

### 苹果或将扩充健康版图，为Apple Watch X铺路

![](https://files.mdnice.com/user/17787/6e5c9342-1de5-45a6-8838-c2a2fce353c1.png)

全球市值最大的科技公司 + 前全球最大社交健身公司，会碰撞出什么样的火花？想想就能脑补出一部强强联合横扫全球的励志热血片。

上周，深水资产管理公司（Deepwater Asset Management）发布了 2024 年预测报告，其中一项预测就是苹果收购派乐腾（Peloton）公司。深水作为全球知名的资产管理公司，其预测报告还是有一定的可信度的。

大家对苹果肯定很熟悉了，那这个派乐腾又是何方神圣呢？派乐腾主营业务是销售可以联网的健身器材硬件，以及提供付费订阅的流媒体健身课程，在巅峰时期还加设了服装产品线。在 2020 年乘着「居家经济」的东风，派乐腾的股价频频上涨，屡创历史新高，一度登上了全球最大社交健身公司的宝座。

深水资产管理公司预测，如果苹果收购派乐腾，除了能通过健身器材来完善智能手表和健身追踪软件外，还能为苹果的订阅收入增加约 17 亿美元（约合人民币 121.38 亿元）。

首先，从品牌层面上看，派乐腾在居家健身领域无疑是先行者，凭借健身器材与订阅课程相结合的模式强化了用户的体验感，其中「大屏观感」是许多用户选择派乐腾的直接原因。如果完成收购，派乐腾的品牌效应会直接提升苹果在健康领域的影响力，收获大批经过筛选的忠实用户。

Apple Watch X，收购案的最大收益者。医疗健康将是苹果未来的发展方向，想不到还有其他什么产品比它更重要。这是苹果首席运营官威廉姆斯（Jeff Williams）在一场公开活动上发表的原话。

回顾苹果健康业务 9 年的发展历程，战略上主要分为两个方向。一是打造运动和健身功能吸引消费者；二是与传统医疗系统或医学机构开展合作。

Apple Watch和iPhone则是苹果健康业务的重要载体，负责给用户提供健康和健身领域的功能。其中大部分的功能都是围绕 Apple Watch 展开的，包括心率测量、睡眠监控、女性健康等。2022 年公布的 iOS 16 和 watchOS 9 中，就涵盖了多达 17 种健康功能，如今更是加入了心理健康、视力健康。

因此此时传出苹果收购派乐腾的风声，相信很可能是苹果为 Apple Watch 发布十周年之作做准备。

早在去年 1 月，就有某供应链透露消息，指苹果将在 Apple Watch 发布十周年推出类似于 iPhone X 的重大设计调整。大意是跳过 Apple Watch Series 9，直接发布 Apple Watch X。

据彭博社科技记者马克·古尔曼（Mark Gurman）报道，Apple Watch X 有望成为迄今为止 Apple Watch 最大的一次更新。有望采用更薄的表壳和新的表带，磁吸设计的表带连接方式，以及 Micro LED 显示屏。

当然，无论 Apple Watch X 在产品方面有多大调整，始终觉得智能功能才是智能手表区别于传统手表的核心。收购派乐腾将补充 Apple Watch 在健身器材上的空缺，用户在运动监测类型上的选择将更加丰富。两者建立连接，也会在一定程度上提升用户体验感。

### 更新后的《Apple Developer Program 许可协议》现已发布

2023 年 12 月 22 日

《Apple Developer Program 许可协议》已经过修订，以便为更新后的政策提供支持，并对相关内容做出阐释。具体修订内容包括：

* 定义，第 3.3.3 (N) 节：将“Tap to Present ID”更新为“ID Verifier (证件验证系统)”
* 定义，第 14.10 节：更新了有关管辖法律和地点的术语
* 第 3.3 节：为了清晰起见，对条款进行了重新组织和分类
* 第 3.3.3 (B) 节：阐释了隐私和第三方 SDK
* 第 6.7 节：更新了有关分析的条款
* 第 12 节：阐释了保修免责声明
* 附件 1：更新了 Apple 推送通知服务和本地通知的使用条款
* 附件 9：Apple Developer Program 会员资格中包含 Xcode Cloud 计算时间的更新条款

## 提案

### 通过的提案

[SE-0418](https://github.com/apple/swift-evolution/blob/main/proposals/0418-inferring-sendable-for-methods.md "SE-0418") **推断方法和关键路径文本的 Sendable** 提案通过审查。该提案已在 **四十四期周报** 正在审查的提案模块做了详细介绍。

[SE-0416](https://github.com/apple/swift-evolution/blob/main/proposals/0416-keypath-function-subtyping.md "SE-0416") **键路径文字作为函数的子类型** 提案通过审查。该提案已在 **四十四期周报** 正在审查的提案模块做了详细介绍。


## Swift论坛

1) 提议[概括“AsyncSequence”和“AsyncIteratorProtocol”](https://forums.swift.org/t/pitch-generalize-asyncsequence-and-asynciteratorprotocol/69283 "概括“AsyncSequence”和“AsyncIteratorProtocol”")

文章详细介绍了 AsyncSequence 和 AsyncIteratorProtocol 的两个基本问题的解决方案：定制和限制的 `@rethrows` 属性，以及迭代 AsyncSequence 时的 Sendable 检查问题。 这包括在 提议-并发模块中的类型化抛出中描述的 AsyncSequence 和 AsyncIteratorProtocol 中采用类型化抛出，以及采用隔离参数，以便 `AsyncSequence` 和 `AsyncIteratorProtocol` 在抛出的错误类型和参与者隔离上都是多态的。

您可以在 GitHub 上查看提案草案，网址为 swift-evolution/proposals/NNNN-generalize-async-sequence.md

2) 讨论[在循环中初始化强制属性的推荐方法？](https://forums.swift.org/t/recommended-way-to-initialise-a-mandatory-property-in-a-loop/69280/4 "在循环中初始化强制属性的推荐方法？")

**内容概括**
讨论的目的是寻求有关在循环等迭代过程中初始化 Swift 结构中的强制属性 (let) 的建议。 他们尝试在结构体的 init() 函数中使用 while 循环，但由于编译器要求在退出初始化程序之前初始化所有属性而遇到错误。

```Swift
struct Bing {
    let bang: String

    init() {
        while true {
            // do something iterative

            if /* some condition */ {
                bang = "bong"
                break
            }
        }

    }
}
```

他们考虑了各种方法：

1. 为属性设置默认值，该值适用于简单类型，但不适用于更复杂的类型。
2. 当满足条件时使用带有break的repeat-while循环，在可读性、安全性和清晰度之间提供平衡。
承认解决这个问题类似于停止问题，并且编译器通常很难进行此类分析。
3. 讨论 Swift 中循环表达式的可能性，类似于 Rust 或 Haskell 等函数式语言，其中循环可以“生成”一个值，帮助编译器进行必要的检查。
他们欣赏形式化循环“生成”值的想法的潜在好处，从而实现更好的编译器检查，但发现与围绕一切都是表达式构建的语言相比，针对此类功能提出的语法有点笨拙。

总之，他们寻求一种特定于 Swift 的解决方案，用于在迭代过程中初始化结构中的强制属性，并讨论在 Swift 中针对此类场景引入循环表达式的挑战和潜在好处。

3) 讨论[为什么 self 是一个强引用？](https://forums.swift.org/t/why-is-self-a-strong-reference/69264 "为什么 self 是一个强引用？")

**内容概括**

讨论发现，通过将[类转换为结构](https://github.com/attractivechaos/plb2/pull/36)，消除分析结果中观察到的保留和释放调用，他们的 Swift 基准测试有了显着的性能改进。 他们质疑为什么这些调用在某些方法中是必要的，特别是当应保证 self 在整个方法执行过程中有效时。

回答认为 Swift 隐式 main 中的变量是全局变量，容易被重新赋值，需要额外的保留来保护。 他们提出了替代方案，例如将变量更改为常量或重组代码以使用真正的局部范围。

此外，他们还提到了对代码所做的更改，通过用 UnicodeScalar 数组替换 String 来减轻保留和释放调用，并强调了 String 由于处理字素簇而导致的复杂性以及分配、保留和释放调用的潜力。

也有人警告在性能至关重要时不要使用字符串或字符，并建议避免使用此类类型以减轻 ARC（自动引用计数）流量。 他们还建议在分析 ARC 行为时删除打印语句以排除与字符串相关的代码，尽管无需运行或分析修改后的代码。

4) 讨论[接受 Type 并返回该 Type 的实例的通用函数](https://forums.swift.org/t/generic-function-that-accepts-a-type-and-returns-instance-of-that-type/69269/1 "接受 Type 并返回该 Type 的实例的通用函数")

**问题**

该问题是由于尝试在 Swift 协议函数中使用类型参数根据条件返回特定类型实例 (shadowFilter) 而引起的。 协议 ObjectRequestable 有一个方法 getObject<T>(type: T.Type) -> T? 旨在返回特定类型的实例（如果在一致类中可用）。

然而，在 FilterManager 的实现中，尝试将 ShadowFilter 返回为 T 会导致编译器错误，因为无法将 ShadowFilter 直接转换为泛型类型 T。编译器还会标记 ShadowFilter.self 的表达式模式与泛型类型之间的不匹配。 T 型。

这里的挑战在于尝试在协议函数内有条件地返回特定类型实例，而不需要直接类型转换。

为了实现所需的功能，可能需要替代方法或不同的代码结构方式。
  
```swift
protocol ObjectRequestable {
    func getObject<T>(type: T.Type) -> T?
}

struct ShadowFilter {
    let width: Float
}

struct RainbowFilter {
    
}

class FilterManager: ObjectRequestable {
    
    private let shadowFilter = ShadowFilter(width: 8)
    
    func getObject<T>(type: T.Type) -> T? {
        switch type {
        case ShadowFilter.self: return shadowFilter
        default: return nil
        }
    }
}

let filterManager = FilterManager()
// Should contain the shadowFilter instance.
let shadow = filterManager.getObject(type: ShadowFilter.self)
// Should contain nil.
let rainbow = filterManager.getObject(type: RainbowFilter.self)
```
  
**回答**
  
这样写可行的：
  
```Swift
func getObject<T>(type: T.Type) -> T? {
    if let v = shadowFilter as? T { return v }
    else { return nil }
}
```

5) 讨论[覆盖默认协议实现](https://forums.swift.org/t/overriding-default-protocol-implementations/69260 "覆盖默认协议实现")
我最近试图为协议 Foo 设置一个默认实现，它可以根据对象是否也符合另一个协议 Bar 为其属性 baz 返回不同的值。 当执行下面的操作时，结果是运行时崩溃 EXC_BAD_ACCESS。

```Swift
protocol Foo {}

protocol Bar {
    var baz: Bool { get }
}

class FooBar: Foo, Bar {}

class FooBaz: Foo, Codable {}

extension Foo {
    var baz: Bool {
        return (self as? Bar)?.baz ?? false
    }
}

let fooBar = FooBar()
let fooBaz = FooBaz()

func doSomething(with foo: Foo) {
    print(foo.baz)
}

doSomething(with: fooBar)
doSomething(with: fooBaz)
```
  
**回答**
  
FooBar 符合 Foo。 Foo 有一个带有属性 baz 的扩展。 因此，FooBar包含一个名为 baz 的成员属性。

FooBar 符合 Bar。 Bar 需要名为 baz 的属性的实现。 由于 FooBar 包含一个名为 baz 的成员属性，其签名与 Bar 的要求（它从 Foo 获得的属性）相同，因此编译器选择它来满足要求。

当您获取 FooBar 实例上的属性 baz 时，它将 self 转换为 Bar，然后获取其 baz 属性。 但是，由于 Foo 的 baz 属性满足了 Bar 的 baz 属性要求，因此该属性最终会递归调用其 getter 直到堆栈溢出

6) 讨论[SSWG-0027: MongoKitten](https://forums.swift.org/t/sswg-0027-mongokitten/69249 "SSWG-0027: MongoKitten")
[SSWG-0027：MongoKitten](https://github.com/swift-server/sswg/blob/main/proposals/0027-mongokitten.md) 的审核现已开始，持续两周，直至 2024 年 1 月 17 日。

**介绍**

MongoDB 是一种流行的 NoSQL 数据库管理系统，它使用面向文档的数据模型。 MongoKitten 是一个 MongoDB 客户端库，支持所有非企业功能。 它通过 BSON 的编码器和解码器支持 Codable，并且供应商专门提供基于 async/await 的 API。

**动机**

MongoKitten 是 Swift 生态系统的一个长期库，自 2015 年以来一直在开发。MongoDB 还创建了另一个数据库驱动程序，该驱动程序提供了包装其内部 C 实现的 Swift API。 然而，该驱动程序是生态系统中的一个相对较新的成员，自此已停产。

为 MongoDB 提供解决方案对于 Swift 生态系统至关重要，因为它服务于数据库市场的很大一部分。

**建议的解决方案**

MongoKitten 分为多个模块。

MongoCore 包含 MongoDB 有线协议的基本实现。

MongoClient包含一个基于该协议的MongoDB客户端。 它包含用户与 MongoDB 通信所需的所有工具。 它具有发送和接收消息以及进行身份验证的能力。 此外，MongoClient 还具有用于发送/读取消息的帮助程序，在此类连接上发送和接收符合 Codable 的消息。 最后，MongoClient 有一个 MongoDB Cluster 客户端实现，充当连接池，同时还观察集群拓扑的变化。

MongoKittenCore 是一个包含以 Codable 类型实现的最常用消息的模块。

MongoKitten 模块本身导入上述所有内容，并提供更高级别的 API 用于与 MongoDB 交互。 这是大多数用户最终与之交互的库。

最后，Meow 模块提供类似 ORM 的帮助程序，通过使您的 Codable 类型符合模型协议，可以快速存储和读取 MongoDB 中的实体。

## 推荐博文

[swift 中的冻结枚举和非冻结枚举](https://juejin.cn/post/7317288133455937599 "swift 中的冻结枚举和非冻结枚举")

**摘要：**  本博客探讨了在 Swift 中的冻结枚举和非冻结枚举的概念。回顾了在传统的 Objective-C 和 C 中，枚举类型是一个整数列表，并介绍了非冻结枚举和冻结枚举的概念，类比了 OC 中的 NS_ENUM 和NS_CLOSED_ENUM 。在 Swift中，用户定义的枚举基本上都是冻结枚举。
  
对于非冻结枚举，讨论了在使用 switch 语句时需要增加 @unknown default 来处理未来可能的case新增情况。相对于 default， `@unknown default` 在未列举 case 时会产生警告，而 default 不会。博客最后总结了处理非冻结枚举时的最佳实践，强调了使用 @unknown default 或 `@unknown case`  来做兜底处理的必要性，以避免在枚举有新增 case 时导致异常情况的发生。

[手把手教你用 Swift 实现命令行工具](https://juejin.cn/post/7310448854628859919 "手把手教你用 Swift 实现命令行工具")

**摘要：**  这篇博客讲解了用 Swift 实现命令行工具，选择 Swift 的原因包括对 Swift 开发者友好以及 Swift 作为完全开源的语言具有更强的语言抽象能力、类型系统安全性和性能。通过一个计算器示例，教读者创建项目、引入依赖（ ArgumentParser 库），以及实现加法和汇率转换功能。详细介绍了 ArgumentParser 的优点和核心逻辑，同时展示了命令行调试和发布安装的方法，最后鼓励使用Swift进行小工具开发。

[使用 SwiftUI 创建康威生命游戏](https://swdevnotes.com/swift/2023/conways-game-of-life-with-swiftui "使用 SwiftUI 创建康威生命游戏")

**摘要：**  这篇博客中作者使用 SwiftUI 创建康威生命游戏（Conway's Game of Life）。Conway's Game of Life 是一款自动游戏，由一个 2D 网格组成，其中的细胞可以是活的或死的。每个细胞在下一代的状态基于其周围细胞在当前一代中的状态，遵循一些简单的规则。
  
文章首先，使用 SwiftUI 的 Grid 容器视图展示游戏状态并在游戏变化时进行动画处理；其次，实现根据游戏的四个规则从一代到下一代改变细胞状态的逻辑。展示了使用 Canvas 视图的不同方法，包括从 2D 数组和从模型获取数据的两种方式。
  
文章还介绍了使用 SwiftUI 创建康威生命游戏的不同视图，包括使用 Grid 和 Canvas 的不同布局方式。LifeModel 用于包含和控制生命游戏的核心逻辑，而 LifeViewModel 则用于在模型和视图之间进行桥接，实现数据的传递和控制。CanvasFromModelView 演示了如何使用 Canvas 视图显示来自 LifeModel 的数据。

## 话题讨论

过去的 2023 年你完成了哪些目标？（多选）
1. 健康生活：保持健康饮食，维持理想的体重和健康状态。
2. 职业发展：升职加薪，或者转换到自己满意的工作领域。
3. 学业进步：获得更高的学历，提升专业技能。
4. 财务自由：投资取得收益，实现财务独立和自由。
5. 幸福家庭：建立和谐家庭关系，或者迎接新成员的到来。
6. 旅行冒险：探索新的旅行地，或者完成一次特别的旅行。
7. 精神成长：培养更多的兴趣爱好，深化对某领域的了解。
8. 社交关系：建立更多深厚的友谊，拓展社交圈。
9. 志愿者服务：参与社区服务或慈善事业。
10. 爱情奇迹：寻找到理想的爱情关系。

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
