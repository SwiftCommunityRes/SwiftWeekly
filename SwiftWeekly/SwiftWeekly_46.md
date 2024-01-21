## 前言

**本期是 Swift 编辑组整理周报的第四十六期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

没有永远的上游，但我们可以永远向上游。**Swift社区**让你如鱼得水，激流勇进！👊👊👊

> **周报精选**
>
> 新闻和社区：卖不动了？iPhone 15 系列跌破 5000 元大关
> 
> 提案：Low-Level Atomic Operations 提案通过审查
> 
> Swift 论坛：讨论 `1 << x` 类型推断
>
> 推荐博文：Swift 的内购测试

> **话题讨论：** 
> 
> 你是否设想过自己35岁之后该做什么工作呢？

### 卖不动了？iPhone 15 系列跌破 5000 元大关

【环球网科技综合报道】连日来，苹果全线产品在官方旗舰店以及线上平台迎来降价。
1 月 15 日早间，苹果（中国大陆）官网发布降价信息，1 月 18 日 - 21 日苹果部分产品新春促销，iPhone 15 全系列参与活动，手机产品最高降价 500 元，苹果笔记本电脑产品最高降价 800 元。
继苹果官网降价后，京东也宣布年货节活动，苹果产品京东自营旗舰店 iPhone 15 系列最高可减 1050 元、iPhone 14 最高可减750 元。其中，iPhone 15 Pro Max 256GB 版到手价 8949 元，iPhone 15 Pro 256GB 版到手价 7949 元，iPhone 15 128GB 版到手价 4949 元，以上机型全部可享限时 12 期免息。此外，iPad 指定产品最高优惠 700 元、 MacBook指定型号最高可优惠 1400 元。

![](https://files.mdnice.com/user/17787/a1224b4a-e662-4acd-b636-8e6048943a94.png)

不难看出，相比 1 月 15 日苹果官网所公布的新春降价，此次电商平台优惠力度明显更大。业内人士称，产品接连降价，难道苹果卖不动了？
根据苹果公司 2023 财年财报（截至 2023 年 9 月 30 日），三季度，苹果大中华区营收为 150.84 亿美元，同比下降 2.5%；整体营收为 894.98 亿美元，下降 0.72% ，且除了 iPhone 业务以外的其他所有硬件业务均出现了同比下滑。
而在不久前，据美国投行杰富瑞（Jefferies）分析师发布的报告，苹果公司 iPhone 在中国市场销量下滑的颓势正在加剧，iPhone 销量在 2024 年第一周就出现了断崖式下跌，较上年同期暴跌 30% 。
但 Counterpoint Research 方面指出，苹果依然是高端手机市场无可争议的领导者，不过与 2022 年相比，其市场份额确有所下降。2023 年三季度，苹果手机销量同比下滑 10%，市场占有率由 2022 年同期 15.3% 下降至 14.2% 。华为、小米同期市占率分别提升了 3.8 个百分点和 1 个百分点。

### StoreKit 和审核指南更新

2024 年 1 月 16 日

从即日起，根据美国法院近期的一项判决，《App Store 审核指南》第 3.1.1 部分已更新，以推出 StoreKit 购买链接授权 (美国)。该授权适用于在美国店面的 iOS 或 iPadOS App Store 上提供 App 内购买项目的 App，获得授权的开发者可在 App 内包含自己网站的链接，以告知用户还有其他购买数字商品或服务的方式。

我们认为，Apple 的 App 内购买项目系统是用户购买数字商品和服务极为安全可靠的方式。因此，对于 App 内的数字商品和服务购买，你仍需使用 App 内购买项目系统。如果你考虑同时使用此授权，请务必了解，在你的网站上购买项目的顾客将无法使用某些 App Store 功能，例如“购买前询问”或“家人共享”。而且，Apple 将无法协助顾客处理退款、购买历史记录、订阅管理以及购买数字商品和服务时遇到的其他问题。你将需要与顾客一起解决此类问题。

对于通过 StoreKit 购买链接授权 (美国) 促成的数字购买，Apple 将收取一定的收益抽成。

### 将你的 App 提交到 Apple Vision Pro 的 App Store

2024 年 1 月 8 日

Apple Vision Pro 将拥有全新的 App Store，帮助用户发现并下载各款出色的 visionOS App。我们提供了一个新的页面介绍如何准备 App 并将其提交到 App Store，非常适用于已构建了新的 visionOS App 的开发者，以及将向 Apple Vision Pro 用户提供 iPad 或 iPhone App 的开发者。

## 提案

### 通过的提案

[SE-0410](https://github.com/apple/swift-evolution/blob/main/proposals/0410-atomics.md "SE-0410") **Low-Level Atomic Operations** 提案通过审查。该提案已在 **四十期周报** 正在审查的提案模块做了详细介绍。

[SE-0413](https://github.com/apple/swift-evolution/blob/main/proposals/0413-typed-throws.md "SE-0413") **Typed throws** 提案通过审查。该提案已在 **四十二期周报** 正在审查的提案模块做了详细介绍。

## Swift论坛

1) 提议[字符串插值的默认值](https://forums.swift.org/t/pitch-default-values-for-string-interpolations/69381 "字符串插值的默认值")

**内容概括**

该提案建议向 Swift 添加一项新功能，以解决涉及可选值的字符串插值的挑战。 目前，当在字符串中插入可选值时，开发人员面临警告和提供默认值的选项有限的问题。 所提出的解决方案建议引入新的字符串插值重载，该重载允许开发人员指定默认字符串，而不管可选值的类型如何。

**介绍**

Pitch 建议在插入可选值时使用新的默认值字符串插入语法。

**动机**

字符串插值很强大，但在处理可选值时会变得复杂。
当前的解决方案在处理可选值时涉及繁琐的代码或不需要的输出。

**例子**

演示插入可选字符串和可选整数时的挑战。
当前的解决方案涉及笨拙的代码或零合并运算符的限制。

**建议的解决方案**

引入新的插值重载，允许将预期默认值指定为字符串，而不管值的类型如何。

```Swift
let age: Int? = nil
print("Your age: \(age, default: "missing")")
```

**详细设计**

这个新的插值重载的实现如下所示：

```Swift
extension String.StringInterpolation {
    mutating func appendInterpolation<T>(
        _ value: T?, 
        default: @autoclosure () -> String
    ) {
        self.appendLiteral(value.map(String.init(describing:)) ?? `default`())
    }
}
```

2) 讨论[Swift Rational - 用于处理有理数的 Swift 包](https://forums.swift.org/t/swift-rational-swift-package-for-working-with-rational-numbers/69344 "Swift Rational - 用于处理有理数的 Swift 包")

**内容概括**

Swift Rational 提供了 RationalModule 模块，用于在 Swift 中处理有理数。

RationalModule 导出 Rational 结构。 它符合标准 Swift 协议，如 AdditiveArithmetic、Numeric、Hashable、Comparable 等。

您可以使用分数初始值设定项创建有理值。

```Swift
let half = Rational(2, 4)
print(x.numerator)		// 1
print(x.denominator).	// 2
```

您还可以使用整数初始值设定项。

```Swift
let one = Rational(1)
```

或者只是一个整数文字。

```Swift
let two: Rational<Int> = 2
```

Rational 支持标准算术和比较运算符。

```Swift
Rational(1, 2) + Rational(1, 4)		// Rational(3, 4)
Rational(1)    - Rational(1, 2)		// Rational(1, 2)
Rational(2)    * Rational(3, 4)		// Rational(3, 2)
Rational(1)    / Rational(1, 2)		// Rational(2, 1)
Rational(1, 2) < Rational(3, 4)		// true
```

Github库连接：https://github.com/abdel-17/swift-rational

3) 讨论[1 << x 类型推断](https://forums.swift.org/t/1-x-type-inference/69417 "1 << x 类型推断")

**提问**

发现了这个区别：

```Swift
let x: UInt64 = 1
print(type(of: 1 + x))  // UInt64
print(type(of: 1 << x)) // Int
```

第二个结果是错误还是功能？ 我也希望在那里得到 UInt64 。

**回答**

移位值中的位完全来自左侧，并且移位的限制也来自左侧，因此结果类型始终与左侧匹配。 这使您可以使用 Int8 固定字段来描述 UInt64 值的移位，这完全没问题，因为最大有用移位量为“64”。

4) 讨论[类型转换是如何工作的？](https://forums.swift.org/t/how-does-type-casting-work/69350 "类型转换是如何工作的？")

类型转换如何，例如 as？ 运算符，实施了吗？
例如，考虑 eqZero 函数

```Swift
func eqZero<T>(_ x: T) -> Bool {
    guard let x = x as? Int else { return false }
    return x == 0
}
```

x 参数是否带有类型标记来检查它是否可以在运行时向下转换？
如果是这样，如果不使用此类转换操作，编译器是否足以优化掉此类标签？

**回答**

从技术上讲，传入的不是一个框，它“只是”一个指针，类型作为单独的参数传递。 这对于值已经在堆栈或堆上的情况很有帮助。 当您使用 Any 或 any Blah 时，会出现“box”形式，因为这样值必须与其类型保持关联，但对于泛型和某些 Blah 来说，单独传递它们会更灵活，并且可以减少分配流量。 这也意味着当在参数列表中多次使用该类型时，只需传递一次。

5) 讨论[~Copyable 和 Completion Handlers](https://forums.swift.org/t/copyable-and-completion-handlers/69383 "~Copyable 和 Completion Handlers")

我想编写一些代码，在其中我可以静态地确保将调用完成处理程序。 像这样的东西：

```Swift
struct CompletionHandler<T>: ~Copyable {
    private let f: (T) -> Void
    init(f: consuming @escaping (T) -> Void) { self.f = f }
    consuming func callAsFunction(_ t: T) -> Void {
        f(t)
    }
}
```

基本上，这个想法是，这里的清理需要调用处理程序，因为处理程序的闭包已捕获需要释放或以其他方式解析的资源。
我希望将这种类型的实例传递给另一个函数，如下所示：

```Swift
func invokeHandler<A>(_ completion: consuming CompletionHandler<A>) {
    // don't invoke the handler
}
```

将无法编译，因为尚未调用该类型的唯一消耗路径。
但这段代码看起来不错，我假设 bc 消耗可以简单地取消初始化完成处理程序。 我正在尝试做的事情是否可能或可能已计划但尚未实施？

**回答**

由于提前退出和仿制药等问题，它变得很棘手。 一种思考方式是 ~Ignorable 是与 ~Copyable 类似的条件，但又不同。 其技术术语是“线性类型”或“相关类型”，您可以在此论坛上找到一些先前的讨论。

@escaping 闭包是可复制类型，并且可复制类型的借用/消耗实际上并不能保证对值的生命周期产生静态影响，因为您始终可以通过复制值来延长生命周期。 当调用者可能拥有对值的唯一剩余引用时，使用消费是一种优化，允许调用者存储参数或将其用作聚合返回值的一部分而不复制它，或者只是提前结束其生命周期 。

## 推荐博文

[Swift 的内购测试](https://swiftwithmajid.com/2024/01/09/storekit-testing-in-swift/ "Swift 的内购测试")

**摘要：**  这篇博客介绍了在 Swift 中使用 StoreKitTest 框架进行应用内购买测试的方法。作者首先概述了最近 StoreKit 框架的重大变化，强调了新版本充分采用了 Swift 语言的异步和等待特性。

随后，博客详细介绍了 `StoreKitTest` 框架，该框架允许我们编写测试用例以验证应用在应用内购买、退款、ask-to-buy 和订阅过期等方面的处理能力。通过示例代码，演示了如何使用 SKTestSession 类型执行购买、管理交易、模拟退款以及测试应用对交易更新的反应。博客还提到了创建 StoreKit 配置文件的必要性。

[Swift Evolution：阅读提案并从中学习](https://www.avanderlee.com/swift/swift-evolution-proposals/ "Swift Evolution：阅读提案并从中学习")

**摘要：**  这篇博客介绍了 Swift 编程语言的演进过程，重点关注了通过阅读和学习 Swift Evolution 提案来了解语言变化的方式。作者指出 Swift 的不断演进源于 Swift Evolution 仓库内的公开提案，这些提案是了解最新发展的良好途径。

博客解释了 Swift Evolution 的定义和作用，强调了语言开源的特点，任何人都可以通过提出好的想法来影响未来功能和方向。提案经过讨论和批准后成为发布目标，可以在官方 Swift 网站上进行跟踪。作者还简要概述了从提出一个提案到将其纳入 Swift 发布的过程，强调了提案经历多个状态。读者被鼓励查阅 Swift Evolution 过程文档获取最新状态概述。

[ElasticSearch 与 Swift 集成](https://juejin.cn/post/7326265442837528586/ "ElasticSearch 与 Swift 集成")

**摘要：**  本篇博客详细介绍了 `Elasticsearch` 与 Swift 的集成，旨在帮助开发者将强大的搜索引擎功能整合到 Swift 应用程序中，提升用户体验。文章首先介绍了 Elasticsearch 和 Swift 的背景，分别强调了 Elasticsearch 作为基于 Lucene 的搜索引擎的特性，以及 Swift 作为苹果主要开发语言的优势。

核心概念与联系部分深入解释了集成前需要了解的核心概念，包括 Elasticsearch 的索引、查询、分词、词典等原理，以及 Swift 的类型安全、自动引用计数、高性能等特点。接着，文章详细探讨了集成的操作步骤，包括安装 Elasticsearch 、创建索引、使用 Swift 访问 `Elasticsearch` 、执行搜索查询等步骤。

## 话题讨论

每个年轻人都会慢慢长大，每个程序员也会逐渐变老，你是否设想过自己 35 岁之后该做什么工作呢？

1. 努力成为中高层领导
2. 继续专研技术成为高级程序员
3. 成为培训老师
4. 成为独立开发者带队出来接项目
5. 创业单干，成就梦想
6. 出国，国外程序员对年龄要求甚小
7. 转行跑滴滴，送外卖，做销售。

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
