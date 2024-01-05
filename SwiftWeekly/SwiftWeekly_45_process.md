## 前言

**本期是 Swift 编辑组自主整理周报的第四十三期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

渺小不可怕，可怕的是比你优秀的强者还比你更加努力。**Swift社区**不会辜负每一位努力的勇士，优秀终将与你不期而遇！👊👊👊

> **周报精选**
>
> 新闻和社区：
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
1) 提议[概括“AsyncSequence”和“AsyncIteratorProtocol”](https://forums.swift.org/t/pitch-generalize-asyncsequence-and-asynciteratorprotocol/69283 "概括“AsyncSequence”和“AsyncIteratorProtocol”")
文章详细介绍了 AsyncSequence 和 AsyncIteratorProtocol 的两个基本问题的解决方案：定制和限制的 @rethrows 属性，以及迭代 AsyncSequence 时的 Sendable 检查问题。 这包括在 提议-并发模块中的类型化抛出中描述的 AsyncSequence 和 AsyncIteratorProtocol 中采用类型化抛出，以及采用隔离参数，以便 AsyncSequence 和 AsyncIteratorProtocol 在抛出的错误类型和参与者隔离上都是多态的。

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
```Swift
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
FooBar 符合 Foo。 Foo 有一个带有属性 baz 的扩展。 因此，FooBar包含一个名为baz的成员属性。

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

## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
