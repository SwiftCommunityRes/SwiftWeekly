## 前言

**本期是 Swift 编辑组自主整理周报的第十三期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

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

## 新闻和社区


## 提案


## Swift论坛
1) 讨论[从 Realm 数据库迁移提示？](https://translate.google.com/?sl=en&tl=zh-CN&text=Migrating%20from%20Realm%20Database%20Tips%3F&op=translate "从 Realm 数据库迁移提示？")
**提问**
目前正在寻求迁移到更轻量级的解决方案（realm 目前对我的用例来说太过分了）并且想迁移到 grdb，但不必将 realm 作为依赖项持续一年或更长时间......

**回答**
在没有 Realm 库的情况下，您是否能够读取 Realm 数据库文件的内容？ 否则，您必须将 Realm 作为依赖项保留，直到您的用户迁移完毕。
您可以通过发布能够要求用户升级的应用程序版本来缩短时间跨度。 这将允许您使用“Realm-only”、“Realm-to-GRDB”和最终的“GRDB-only”版本进行过渡。

2) 提议[允许protocol嵌套在非通用上下文中](https://forums.swift.org/t/pitch-allow-protocols-to-be-nested-in-non-generic-contexts/65285 "允许protocol嵌套在非通用上下文中")
**介绍**
允许协议嵌套在非通用struct/class/enum/actors 和函数中。

**动机**
将标称类型嵌套在其他标称类型中允许开发人员表达内部类型的自然范围——例如，String.UTF8View 是嵌套在 struct String 中的 struct UTF8View，它的名称清楚地传达了它作为 UTF-8 代码接口的用途 - 字符串值的单位。

但是，嵌套目前仅限于在其他struct/class/enum/actors 中的 struct/class/enum/actors； 协议根本不能嵌套，因此必须始终是模块中的顶级类型。 这很不幸，我们应该放宽此限制，以便开发人员可以表达自然作用于某些外部类型的协议。

**建议的解决方案**
我们将允许在非泛型struct/class/enum/actors 中以及在不属于泛型上下文的函数中嵌套协议。

例如，TableView.Delegate 自然是与表视图相关的委托协议。 开发人员应该这样声明它——嵌套在他们的 TableView 类中：
```Swift
class TableView {
  protocol Delegate: AnyObject {
    func tableView(_: TableView, didSelectRowAtIndex: Int)
  }
}

class DelegateConformer: TableView.Delegate {
  func tableView(_: TableView, didSelectRowAtIndex: Int) {
    // ...
  }
}
```
目前，开发人员采用复合名称（例如 TableViewDelegate）来表达可以通过嵌套表达的相同自然范围。

作为一个额外的好处，在 TableView 的上下文中，可以使用更短的名称来引用嵌套协议委托（与所有其他嵌套类型一样）：
```Swift
class TableView {
  weak var delegate: Delegate?
  
  protocol Delegate { /* ... */ }
}
```
协议也可以嵌套在非泛型函数和闭包中。 不可否认，这在某种程度上是有限的实用性，因为对此类协议的所有一致性也必须在同一功能内。 但是，也没有理由人为地限制开发人员在函数中创建的模型的复杂性。 一些代码库（值得注意的是，Swift 编译器本身）使用带有嵌套类型的大型闭包，并且它们受益于使用协议的抽象。
```Swift
func doSomething() {

   protocol Abstraction {
     associatedtype ResultType
     func requirement() -> ResultType
   }
   struct SomeConformance: Abstraction {
     func requirement() -> Int { ... }
   }
   struct AnotherConformance: Abstraction {
     func requirement() -> String { ... }
   }
   
   func impl<T: Abstraction>(_ input: T) -> T.ResultType {
     // ...
   }
   
   let _: Int = impl(SomeConformance())
   let _: String = impl(AnotherConformance())
}
```

3) 提议[PermutableCollection 协议](https://forums.swift.org/t/permutablecollection-protocol/65314 "PermutableCollection 协议")
**简介**
该提案旨在添加一个 PermutableCollection 协议，该协议将位于集合协议层次结构中的 Collection 和 MutableCollection 之间。

**动机**
在某些情况下，人们希望能够移动和排序元素，同时不允许（或限制）元素的突变。 鉴于大量不太重要的收集协议，这是一个值得注意的遗漏。 创建自定义集合类型时，PermutableCollection 协议在任何强制元素唯一性和/或身份的有序集合中都是首选。 用例将包括即将推出的 OrderedDictionary 和 OrderedSet。 对于不可变和可变集合，它还可以提供对 Swift 使用的底层（并且可能是高度优化的）排序算法的统一访问。

**设计**
协议设计简单，只需一个 swapAt 要求
```Swift
/// A collection that supports sorting.
protocol PermutableCollection<Element> : Collection where Self.SubSequence : PermutableCollection {

  mutable func swapAt(_ i: Index, _ j: Index)
  
}
```
通过 swapAt 函数，通过扩展添加额外的排序函数实现
```Swift
extension PermutableCollection {

  mutating func move(fromOffsets source: IndexSet, toOffset destination: Int) {
    // move algorithm enacts changes via swapAt()
  }
    
  mutating func partition(by belongsInSecondPartition: (Element) throws -> Bool) rethrows -> Index {
    // partition algorithm enacts changes via swapAt()
  }
  
  mutating func sort() where Self: RandomAccessCollection, Self.Element: Comparable {
    // partition algorithm enacts changes via swapAt()
  }
  
  // ... more permutation operations that mimic those available for MutableCollection
  
}
```

4) 讨论[Vapor和query缓存？](https://forums.swift.org/t/vapor-and-query-caching/65278 "Vapor和query缓存？")

5) 讨论[在 Swift 系统中，如何将文件内容读取为字符串？](https://forums.swift.org/t/in-swift-system-how-does-one-read-a-files-contents-to-a-string/65294 "在 Swift 系统中，如何将文件内容读取为字符串？")
**提问**
我有一个文件的 FileDescriptor：

let fd = try FileDescriptor.open(<#filepath#>, .readOnly)
我可以使用 fd.read(into:) 将文件内容加载到 UnsafeMutableRawBufferPointer，但这是将文件内容加载到字符串中的正确第一步吗？ 如果是这样，

在将它传递给 fd.read(into:) 之前，
1. 我需要使用 .allocate(byteCount:alignment:) 分配 UnsafeMutableRawBufferPointer。 正确的 byteCount 取决于文件的大小。那么如何使用 Swift System 获取文件的大小呢？
2. 如何从 UnsafeMutableRawBufferPointer 获取字符串？

**回答**
可以参考这个Git库：https://github.com/tayloraswift/swift-unidoc/blob/master/Sources/System/FileDescriptor.swift

6) 讨论[为什么我不能使用@dynamicMemberLookup 转发enum cases？](https://forums.swift.org/t/why-can-t-i-forward-enum-cases-with-dynamicmemberlookup/65290 "为什么我不能使用@dynamicMemberLookup 转发enum cases？")

7) 讨论[如何在 swift-foundation 中正确地进行性能测试？](https://forums.swift.org/t/how-to-do-performance-testing-properly-in-swift-foundation/65282 "如何在 swift-foundation 中正确地进行性能测试？")
**提问**
我想对比一下swift-foundation和Xcode自带的JSONDecoder解码的速度。
我在一个新项目中使用单元测试和 measureBlock 以及在 swift-foundation 中使用 JSONEncoderTests 对其进行了测试。
swift-foundation 中的 JSONDecoder 看起来太慢了，我认为这是因为 swift-foundation 还没有作为一个库被引入。

##  推荐博文

[iOS crash 报告分析系列 - 看懂 crash 报告的内容](https://juejin.cn/post/7238802590661476412/ "iOS crash 报告分析系列 - 看懂 crash 报告的内容")

**摘要：** 本篇文章主要介绍了iOS崩溃报告的解读方法，从报告的Header、Exception information、Diagnostic messages、Backtraces、Thread state和Binary images六个部分详细讲解了各字段含义，并提供示例代码帮助读者更好地理解。同时也引导读者去深入学习符号化的相关知识来获得更多信息。通过阅读本文，开发者可轻松看懂代码中产生的崩溃报告，并进行问题定位和处理。

[SwiftUI 中 LinearGradient的用法](https://swdevnotes.com/swift/2023/lineargradient-in-swiftui/ "SwiftUI 中 LinearGradient的用法")

**摘要：** 这篇博文探讨了在 SwiftUI 中使用 LinearGradient 为对象创建渐变颜色效果。它展示了如何定义颜色数组、使用标准和自定义起点和终点，以及设置坐标以改进铅笔对象上的颜色笔尖。本文还包括用于创建具有各种起点终点组合的不同线性渐变的示例代码。文章以示例结束，展示了如何使用这些技术来自定义一支蓝色铅笔或整套铅笔的外观。

[Swift 中的动态成员查找](https://swiftwithmajid.com/2023/05/23/dynamic-member-lookup-in-swift/ "Swift 中的动态成员查找")

**摘要：** 本文介绍了 Swift 语言中的动态成员查找（Dynamic Member Lookup）特性。通过在类型上使用 @dynamicMemberLookup 属性，我们可以重载该类型的 subscript 方法来更方便地访问其数据。但是，这也意味着缺乏编译时安全性。为了解决这个问题，本文提到了使用 KeyPath 作为参数的 subscript 方法来实现编译时安全检查。最后，作者建议我们可以谨慎地使用 @dynamicMemberLookup 特性来改进 API 设计。



## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
