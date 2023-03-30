## 前言

**本期是 Swift 编辑组自主整理周报的第十七期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

考验人的才能不在于他是否拿到一副好牌，而在于他能打好一副坏牌。选择**Swift社区**，教你打好人生的每一张卡牌！👊👊👊

> **周报精选**
>
> 新闻和社区：WWDC23 将于北京时间 6 月 6 日举行
> 
> 提案：
> 
> Swift 论坛：
>
> 推荐博文：
> 
> **话题讨论：** 
> 
> 当代大学生脱掉孔乙己长衫，选择普通的非技术岗位就业，这算是一种思想的进步吗？

## 新闻和社区

### WWDC23 将于北京时间 6 月 6 日举行

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/4508744A-29D9-43A0-9B71-E245065F041C/2048.jpeg)

万勿错过北京时间 6 月 6 日至 10 日为期一周丰富多彩的技术和社区活动，现在就添加到你的日历吧。你将能抢先了解 Apple 平台、技术和工具的最新动态，还有机会与 Apple 专家和其他开发者互动。以上活动均免费在线举行。

此外，Apple 将于太平洋夏令时间 6 月 5 日在 Apple Park 举办面向开发者和学生的全天特别活动。我们将一起观看主题演讲和 State of the Union 视频，与部分 Apple 团队会面交流，在 Apple 设计大奖颁奖典礼上为卓越的 App 欢呼庆祝，还能一起乐享当晚的活动。

另外，富有才华的学生们还可通过展现自己的创造力，角逐 Swift Student Challenge 并获得奖励。

### 4 月 25 日起将实行以下 App Store 内容提交要求

自 2023 年 4 月 25 日起，提交至 App Store 的 iOS、iPadOS 和 watchOS App 必须使用 Xcode 14.1 或更高版本构建。你可以从 Mac App Store 中免费获得最新版本的 Xcode 14，其中包含适用于 iOS 16、iPadOS 16 和 watchOS 9 的最新 SDK。

当你构建 App 时，我们强烈建议你利用 iOS 16、iPadOS 16 和 watchOS 9 中的最新改进。

iOS 16 满载全新的个性化功能、更具深度的智能技术，以及更多无缝式的沟通与共享方式，让 iPhone 的体验更进一步。利用“实时活动”帮助用户通过 iPhone 14 Pro 上的锁定屏幕和灵动岛，直接了解你的 App 中正在发生的事情。借助 App Intents，用户可以通过语音或轻点方式快速完成与你的 App 相关的任务。此外，你还可以充分利用 MapKit、ARKit 和 Core ML 等技术中的最新增强功能。

iPadOS 16 引入了新的效率功能，让你能够在 iPad 上提供引人入胜的协作体验，构建更丰富、更直观的 App 和强大的专业工作流程。你可以为 iPad App 带来桌面级功能，如编辑器风格的导航栏、增强的文本编辑菜单和外置显示器支持。同时，Metal 3 也引入了多项强大功能，可协助你的游戏和专业 App 在最新一代的 iPad Pro 和 iPad Air 上充分发掘 Apple 芯片的潜能。

watchOS 9 为 watchOS App 提供了强大的新通信功能。你可以在更多 Apple Watch 表盘上通过丰富的复杂功能提供及时资讯，支持用户从你的 App 中分享内容，让用户直接通过 Apple Watch 进行 VoIP 通话等。此外，watchOS App 的结构经过简化，更是让管理项目变得前所未有的简单。

## 提案


## Swift论坛

1) 提议[使`Never`符合`Codable`](https://forums.swift.org/t/pitch-conform-never-to-codable/64056 "使`Never`符合`Codable`")
**介绍**
扩展 Never 使其符合 Encodable 和 Decodable 协议，统称为 Codable。

**动机**
Swift 可以为任何具有 Codable 成员的类型综合 Codable 一致性。 泛型类型通常通过约束它们的泛型参数来参与这种综合一致性，例如 Either 类型：
```Swift
enum Either<A, B> {
    case left(A)
    case right(B)
}

extension Either: Codable where A: Codable, B: Codable {}
```
这样，两个泛型参数都是 Codable 的 Either 实例本身就是 Codable，例如 Either<Int, Double>。 但是，由于 Never 不可编码，因此使用 Never 作为参数之一会阻止条件一致性，即使编码或解码像 Either<Int, Never> 这样的类型是完全没问题的。

**建议的解决方案**
标准库应该向 Never 类型添加 Encodable 和 Decodable 一致性。

**详细设计**
Encodable 一致性很简单——因为不可能有 Never 实例，encode(to:) 方法可以简单地为空。
Decodable 协议需要 init(from:) 初始化器，它显然不能创建 Never 实例。 如果尝试解码，该实现会抛出 DecodingError。

2) 提议[导入带有 ARC 指针成员的 C 结构体](https://forums.swift.org/t/pitch-import-c-structs-with-arc-pointer-members/64059#introduction-1 "导入带有 ARC 指针成员的 C 结构体")
**介绍：**
目前，Swift 可以导入 C 结构，其成员是 Swift 可导入的值类型，例如 int、BOOL 和 __unsafe_unretained ARC 指针，它们都是简单的构造和可析构的。 基于 Akira 在 LLVM 中启用强引用和弱引用的工作，我们应该能够导入这些类型和声明。

**动机：**
自 2018 年以来，这些指针类型已可用于 Objective-C/Objective-C++（以及之前的 Objective-C++），而 Swift 迄今为止尚未扩展以导入它们。 这是 Swift <> C++ 互操作的必要部分，我们应该能够移植值类型的引用类型成员的默认和成员构造和销毁，包括 Objective-C 语言模式中结构中的 ARC 指针。 Puyan 已经在此处合并了一些使用 C++ interop 构建这些类型的代码。

**建议的解决方案：**
```Objective-C
#import <Foundation/Foundation.h>

typedef struct WithArcPointers {
    __unsafe_unretained NSString *usUR;
    __strong _Nonnull NSString *sStr;
    __weak _Nullable NSString *wStr;
    NSInteger count;
} WithArcPointers;
```
应该导入到 Swift 作为
```Swift
struct WithArcPointers {
  init(usUR: String!, sStr: String, wStr: String?, count: Int)
  var usUR: Unmanaged<NSString>!
  var sStr: String
  weak var wStr: NSString?
  var count: Int
}
```
应保留各种 arc 存储类型，并在可能的情况下尊重预期的类型桥接和可空性注释。 弱成员在 Swift 端必须是 Optional，并且 __unsafe_unretained 必须是非桥接类型的 Unmanaged。 这些结构应该是成员可构造的，如果它们不包含非空成员，那么也可以通过可用的 init() 轻松构造。

结构中的非空弱引用虽然在 Clang 中是合法的，但不会被导入并且编译器将发出适当的诊断，因为 Swift 要求弱引用是可选的。 C 声明可能也应该有一个诊断，与适当错误的 ObjC 类一致，但这超出了本提案的范围。

3) 提议[可变序列](https://forums.swift.org/t/pitch-variadic-sequences/64072 "可变序列")
Swift 可以通过在方法定义中允许重复的参数序列来使可变参数表达式更强大。

这是在 Swift 5.7 语法中有效的可变参数函数定义和调用：
```Swift
func myFunction(_ value: (name: String, age: Int)..., and otherName: String) {}

myFunction((name: "Ada", age: 26), (name: "Bob", age: 21), and: "Carl")
```
但是，我相信相同的定义/调用应该具有如下所示的能力：
```Swift
func myFunction(name: String..., age: ...Int, and anotherParameter: String) {}

myFunction(name: "Ada", age: 26, name: "Bob", age: 21, and: "Carl")
```
这可能是一种称为可变序列的新语言功能，其中可以在方法定义中包含任意数量的序列参数。 请注意新的 ...Int 语法：这表示可变序列的结尾。 此功能为开发人员在编写方法调用时提供了更友好的体验。

至于在函数实现中获取可变参数序列，可以使用美元符号语法。 或者，每个可变序列元素都可以通过参数名称作为元组数组获得。 最后，可以通过使用 for in 循环 [1] 来迭代可变序列。
```Swift
func myFunction(a: String..., b: ...Int) {
  let allSequences: [(a: String, b: Int)] = $0
  let allValuesOfA: [String] = a
  let allValuesOfB: [Int] = b

  for myA, myB in $0 {
    let aValue: String = myA
    let bValue: Int = myB
  }
}
```
提议的细节：

每个可变参数序列都以打开和关闭参数开始和结束。 开放参数使用 Type... 语法。 关闭参数使用新的 ...Type 语法。
```Swift
func myFunction(_ open: String..., _ close: ...String) {}
```
可变序列可以包含中间参数。 中间参数的类型使用普通语法：
```Swift
// Variadic sequence with 3 elements
func myFunction(_ open: String..., _ middle: String, _ close: ...String) {}

// Variadic sequence with 4 elements
func myFunction(_ a: String..., _ b: String, _ c: String, _ d: ...String) {}
```
可变参数序列可以使用任何需要的类型。
```Swift
func myFunction<T>(_ a: String..., _ b: Double, _ c: ...T, _ d: Int) {}

myFunction("Swift", 5.7, objectA, "Objective-C", 2.0, objectB, 1234)
```
对具有可变序列参数的函数的调用可以根据需要包含尽可能多的重复：
```Swift
myFunction("A", 1, "B", 2, "C", 3, "D", 4) {}
```
Varadic 序列元素可以命名为 [2]：
```Swift
func myFunction<A, B>(property path: KeyPath<A, B>..., _ middle: Comparison, value: ...B) {}

myFunction(property: \.name, .equals, value: "Ada", property: \.age, .greaterThan, value: 21)
```
方法定义中可能存在多个不同长度的可变序列。 在这种情况下，每个相应的序列都是使用 $0、$1、$2 等获得的：
```Swift
func myFunction(_ a: String..., _ b: ...Int, _ c: Double..., _d: Date, _ e: ...Int) {
  let abValues: [(String, Int)] = $0
  let cdeValues: [(Double, Date, Int)] = $1
}
```
可变参数序列可以与常规参数和现有的可变参数一起使用：
```Swift
func myFunction(_ a: String..., _ b: ...Int, _c: Double, _ d: Int...)
myFunction("Ada", 26, "Bob", 21, 5.7, 1, 2, 3, 4)
```

4) 讨论[有没有办法从字符串中验证 URL](https://forums.swift.org/t/pitch-observation-revised/63757 "有没有办法从字符串中验证 URL")
可以用第三方库：GitHub：[vapor/validation](https://github.com/vapor/validation/blob/master/Sources/Validation/Validators/URLValidator.swift)

5) 讨论[“KeyPath”会产生内存泄漏吗？](https://forums.swift.org/t/does-keypath-produce-memory-leaks/64050 "“KeyPath”会产生内存泄漏吗？")
回答：是的，KeyPath 实例在第一次使用时被缓存并保留在内存中直到程序结束。

6) 讨论[当序列元素为 Dictionary.Key 时，For-in 与 forEach()](https://forums.swift.org/t/for-in-vs-foreach-when-sequence-element-is-dictionary-key/64053 "当序列元素为 Dictionary.Key 时，For-in 与 forEach()")
```Swift
extension Dictionary {
    func f1(keys: any Sequence<Key>) {
        for key in keys {
            let value = self[key]
        }
    }
    func f2(keys: any Sequence<Key>) {
        keys.forEach { key in
            let value = self[key]
        }
    }
}
```
在 for-in 中，key 的类型被推断为 Any，而在 forEach() 中，其类型为 Key。 这是设计使然还是错误？
回答：
首先，要知道这一点，但 f1 和 f2 实际上应该采用一些 Sequence<Key> 类型的参数，而不是任何类型的参数，这将使错误消失。
这是一个已知的限制，将来可能会被取消。 让我试着分解一下。

从 f2: forEach 开始可以保留具体的 Key 类型，这要归功于 SE-0353：受限存在类型中的 Covariant Erasure with Constrained Existentials 1。 所以这是相对简单的。
对于 f1，编译器基本上将 for 循环重写为 while 循环，如下所示：
```Swift
var iterator = keys.makeIterator()
while let key = iterator.next() {
    …
}
```
如果我们手动编写这个 while 循环，我们会在第一行的 makeIterator() 调用中遇到错误：

错误：推断结果类型“any IteratorProtocol”需要显式
由于通用要求的丢失而导致的强制
编译器强制我们将 keys.makeIterator() 编写为任何 IteratorProtocol，以确认迭代器变量失去了其 Element == Key 的知识，这就是为什么 for 循环中的元素类型为 Any 的原因。

在 SE-0352: Implicitly Opened Existentials 中类型擦除结果值时“丢失”约束中描述了几乎这种情况：

当涉及打开的存在类型的调用结果被类型擦除时，可能一些关于返回类型的信息无法用存在类型表示，因此上述“上界”将丢失信息。

该部分还提到，未来的编译器版本可以通过恢复现在更多的类型信息来提高语言的表达能力。 它甚至明确提到了可能有助于解决此问题的主要关联类型 SE-0353。

总而言之，当从任何 Sequence<T> 生成迭代器时，编译器似乎可以（并且最终应该）保留元素类型信息，但这尚未实现（如果实现，它可能也会有 经历 Swift Evolution）。

7) 讨论[Void 作为关联类型？](https://forums.swift.org/t/void-as-an-associated-type/64043 "Void 作为关联类型？")

## 话题讨论

**当代大学生脱掉孔乙己长衫，选择普通的非技术岗位就业，这算是一种思想的进步吗？**

1. 必须算啊，勇于突破陈旧观念，值得尊敬。
2. 不能算的，选择了普通非技术岗位，意味着自己的大学生涯毫无价值体现。
3. 无所谓进步与否，只不过是当今经济环境下的无奈选择罢了。
## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
