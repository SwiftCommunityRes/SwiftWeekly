## 前言

**本期是 Swift 编辑组自主整理周报的第十二期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

烟花，如此短暂，却如此的奔放热烈。**Swift社区**，积聚无数力量，却只为给你展现一刹那辉煌！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果市值两年来首次跌破2万亿美元
> 
> 提案：
> 
> Swift 
>
> 推荐博文：
> 
> **话题讨论：** 
> 
> 

## 新闻和社区

### 苹果市值两年来首次跌破2万亿美元

鞭牛士 1 月 4 日消息，据报道，当地时间 1 月 3 日，苹果（AAPL）收报 125.07 美元，跌幅 3.74% ，市值 1.99 万亿美元。市值一夜蒸发 773 亿美元（约 5345 亿元人民币）。

![](https://pics1.baidu.com/feed/9f510fb30f2442a728df5cb731352e40d0130255.jpeg@f_auto?token=ab29cd88610dbb90d3a05cb075caaa43)

Tech 星球 1 月 4 日消息，据凤凰网科技，在遭遇了去年的大幅下跌后，苹果公司市值本周二继续大幅缩水，自 2021 年 3 月以来首次跌破 2 万亿美元，面临被微软公司超越的风险。而就在一年前，苹果曾成为首家市值触及 3 万亿美元的公司。

截至周二收盘，苹果股价下跌 3.7% ，至 125.07 美元。此前，法国巴黎银行分析师杰罗姆·拉梅尔(Jerome Ramel)将苹果股票评级从“跑赢大盘”下调至“中性”，并将其目标价从 180 美元下调至 140 美元。拉梅尔还将 iPhone 2023 财年的出货量预期从 2.45 亿部下调至 2.24 亿部，以反映代工商富士康的供应链问题以及消费者削减在高端手机上的支出。

与此同时，投资者还担心，全球经济放缓和高通胀可能会损害消费者对苹果设备的需求。日本媒体报道称，苹果已经要求供应商减少为其耳机、手表和笔记本电脑生产零部件。

在经历了周二的下跌后，苹果目前的市值为 1.99 万亿美元，稍稍领先微软，后者的市值约为 1.8 万亿美元。苹果、微软、亚马逊、谷歌母公司 Alphabet 、脸书母公司 Meta 目前在标普 500 指数中的市值占比约为 18% ， 低于 2020 年一度达到的 24% 。

### TrendForce集邦咨询：疫情影响，2022年iPhone 14系列出货量滑至7,810万支

富士康（Foxconn）郑州厂自 10 月起至今持续受疫情影响，稼动率仍难突破七成，而 10 月底正值苹果（Apple）新机销售的冲刺期，其中 Pro 系列因受市场青睐而持续调升生产比重，使得作为 Apple Pro 系列主力组装厂的富士康备感压力，即便有富士康深圳厂支持生产，但仍缓不济急，故 TrendForce 集邦咨询下调 2022 年 iPhone 14 系列出货量至 7,810 万支。

### 富士康独供地位不再，立讯确定将加入iPhone 15 Pro Max生产行列

富士康长年稳站 Pro 系列的独家组装，但苹果基于风险控管，原本即有意找寻其他业者加入生产组装行列，并且在 iPhone 14 Pro 系列上试行，富士康由于疫情影响稼动率，这也让立讯精密（Luxshare）成为 iPhone 15 Pro Max 组装供应链行列之一，目前其 iPhone 代工厂仍坐落中国，越南厂则是以苹果周边为主，目前尚无 iPhone 产线规划。

## 提案

### 通过的提案


### 正在审查的提案


## Swift论坛
1) 讨论 [SE-0384：导入前向声明的 Objective-C 接口和协议](https://forums.swift.org/t/se-0384-importing-forward-declared-objective-c-interfaces-and-protocols/62392 "SE-0384：导入前向声明的 Objective-C 接口和协议")

2) 讨论 [Swift 6 语言模式的设计优先级](https://forums.swift.org/t/design-priorities-for-the-swift-6-language-mode/62408 "Swift 6 语言模式的设计优先级")
Swift 6 重点领域
Swift 语言工作组确定了三个重点领域，Swift 的系统改进将取决于源代码不兼容的更改。 涉及 Swift 6 源代码不兼容更改的提案应解决以下多个领域之一：

默认情况下的数据竞争安全性：默认情况下的数据竞争安全性是对只能在新语言版本中上演的模型的重大转变，但它有很大的回报，因为它使并发程序更容易正确编写。 Swift 6 将需要加强围绕 Sendable 和 actor-isolation 检查的语义，但可能还需要额外的更改或功能来使在该安全模型中工作更容易。

性能可预测性：Swift 提供了一种富有表现力的相当高级的编程模型，可以抽象掉不必要的细节。 然而，Swift 开发可能会遇到性能“悬崖”，其中一个小的变化可能会导致程序运行时性能意外下降（例如，由于写时复制数据类型的过度复制）或 Swift 工具的性能（ 例如，“表达式太复杂”错误）。Swift 6 可以考虑更改默认语言语义以提高性能可预测性，例如通过调整有关变量生命周期的规则，使某些带有运行时成本的功能选择加入而不是选择退出，或调整类型推断规则以启用 一个性能更好的类型检查器实现。

包生态系统的可扩展性：Swift 语言和社区的长期健康取决于拥有一个强大的包生态系统。 Swift 语言和包管理器可能需要进行调整，以便更轻松地扩展包生态系统。 例如，Swift 的模块系统可能会得到改进，以限制模块的实现依赖性对其客户端模块的影响，从而使模块和包更能适应变化。

3) 讨论 [Vapor：如何使用 async-http / Vapor 客户端获取响应 URL](https://forums.swift.org/t/vapor-how-to-get-response-url-using-async-http-vapor-client/62418 "Vapor：如何使用 async-http / Vapor 客户端获取响应 URL")

4) 讨论 [如何使用函数的返回值而不是使用@Binding 在视图之间传递数据？](https://forums.swift.org/t/how-can-i-use-return-values-from-functions-instead-of-using-binding-to-pass-data-between-views/62413 "如何使用函数的返回值而不是使用@Binding 在视图之间传递数据？")

5) 提议 [在闭包中隐式使用guard self](https://forums.swift.org/t/implicit-guarding-self-in-closures/62386 "在闭包中隐式使用guard self")
受 SE-0365 的启发：
```Swift
{ [guarded self] in
    dismiss()
}
```
在这里guard self 以确保 self（否则返回），这通常在这种情况下使用：
```Swift
{ [weak self] in
    guard let self else { return }
    dismiss()
}
```

6) 讨论 [改变一个属性包装器](https://forums.swift.org/t/mutating-a-property-wrapper/62403 "改变一个属性包装器")
Property wrapper一个栗子：
```Swift
@propertyWrapper
public struct PropertyWrapper {
    public var projectedValue: Self {
        get { self }
        _modify { yield &self }
    }

    public var wrappedValue: Int {
        get { box.value }
        set { box.value = newValue }
    }

    private var box: Box

    public init(wrappedValue: Int) {
        self.box = Box(value: wrappedValue)
    }

    public mutating func needsCopyOnWrite() -> Bool {
        !isKnownUniquelyReferenced(&box)
    }
}

private final class Box {
    var value: Int

    init(value: Int) {
        self.value = value
    }
}
```
如何使用：
```Swift
struct Struct {
    @PropertyWrapper
    var property: Int

    var propertyWrapper: PropertyWrapper {
        get { _property.projectedValue }
        _modify { yield &_property.projectedValue }
    }
}

var s = Struct(property: 123)

print(s.$property.needsCopyOnWrite()) // true
print(s.propertyWrapper.needsCopyOnWrite()) // false
```

7) 讨论 [保持任务实例超出其主体执行的警告？](https://forums.swift.org/t/caveats-of-keeping-task-instance-beyond-its-bodys-execution/62400 "保持任务实例超出其主体执行的警告？")

8) 讨论 [SE-0379: Opt-in Reflection Metadata](https://forums.swift.org/t/returned-for-revision-se-0379-opt-in-reflection-metadata/62390 "SE-0379: Opt-in Reflection Metadata")
更改反射生成的默认行为:

该提案规定，在 Swift 6 语言模式下，反射的默认行为应该成为选择加入。 社区对提案的这一方面反应不一，许多开发人员担心这会对现有代码中普遍使用打印、镜像和其他基于反射的 API 产生影响。 关于支持“按使用量付费”模型和提供丰富的运行时设施之间的紧张关系，有很好的哲学讨论。 该提案建议通过使依赖反射的 API 在其参数中添加 Reflectable 约束来解决这种紧张关系。 然而，对于许多 API 来说，这是一个问题，特别是标准库设施，如打印和相关的字符串化功能，旨在尽最大努力处理任何值。 要求通过潜在的许多 API 层线程化通用约束只是为了添加一些日志记录或 printf 调试将是一个严重的强加。 但是，消除对这些约束的需求会使编译器没有面包屑来帮助开发人员制作所有需要的类型 Reflectable 或 Custom*StringConvertible； 开发人员必须通过大量专门测试来发现和修复运行时影响。

Language Workgroup 还注意到 Swift 项目先前尝试追溯更改运行时行为，特别是 SE-0083，它通过从运行时中删除 Foundation 类型桥接来简化动态转换行为。 当时的核心团队最终拒绝了该提议，因为考虑到该提议的动态性质，他们无法想出一种方法来评估对 Swift 生态系统的影响，并有足够的把握认为该变化不会造成过度破坏。 语言工作组对更改默认反射行为也有类似的担忧； 即使默认更改受语言版本限制，我们希望开发人员采用 Swift 6 以获得静态并发安全和其他更改的好处，并期望他们也审计项目的动态行为以防止意外的反射依赖项将是一个障碍 更新他们的语言版本模式。 如果没有评估更改默认设置对现实世界影响的计划，我们就不会接受这种更改。

Reflectable 的本质和动态投射支持:

提案规定 Reflectable 和 Sendable 一样是一个标记协议； 然而，与真正的标记协议不同，约束的存在对运行程序可用的元数据类型具有真正的运行时影响。 此外，与遵循协议不同，反射元数据不能通过其定义模块之外的扩展追溯添加到类型中。 因此，尽管将其作为通用约束是一种很好的语言设计，但将其称为标记协议或协议似乎不太正确。

该提案还规定，程序员可以通过动态转换查询一个类型是否携带全反射元数据？ 可反射。 如果 Reflectable 是一个标记协议，那么它如何在完全通用的情况下工作还不清楚，因为尽管我们可能静态地将表达式 x 识别为？ 可反射的，不可能将 x 处理为？ T 表示在运行时绑定到 Reflectable 存在类型的泛型类型参数 T。 但是，语言工作组还认为，在新的 Reflection 库中将此功能表达为独立的查询功能可能会更好，这样可以降低它必须与整个动态转换基础结构进行交互的复杂性。

现在的语言中存在一个非协议泛型约束——AnyObject 约束，只有类和没有见证表的类存在性才能满足。 编译器在内部将其归类为“布局约束”，因为它不需要明确的一致性，但其布局本质上满足约束要求的类型会隐式满足它。 目前还有一些其他布局约束只为优化器实现以允许部分专门化，但其中一些，特别是按位可复制类型的约束，在 C++ 行话中称为“平凡”或“POD”，也可以浮出水面 在语言中。 Reflectable 可能也适合这个系列，因为当编译器设置为发出所有反射元数据时，它不需要明确的“一致性”； 虽然它不是专门针对类型值的布局的约束，但它确实对该类型的元数据布局施加了约束。

调试器支持:

需要进一步考虑的实现的一个方面是它与调试器的交互。 LLDB 的 Swift 支持目前严重依赖全反射元数据来提供完整的功能，语言工作组希望看到一个计划来确保调试支持可用

## 推荐博文

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
