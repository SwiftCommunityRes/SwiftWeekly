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

3) 讨论[`1 << x` 类型推断](https://forums.swift.org/t/1-x-type-inference/69417 "`1 << x` 类型推断")
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

5) 讨论[~Copyable和Completion Handlers](https://forums.swift.org/t/copyable-and-completion-handlers/69383 "~Copyable和Completion Handlers")
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

## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
