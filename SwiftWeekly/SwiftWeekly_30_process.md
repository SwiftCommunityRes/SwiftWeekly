## 前言

**本期是 Swift 编辑组自主整理周报的第二十一期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

求人不如求己，你多一样本领，就少一点啊乞求；**Swift社区**让你多一样技能，少一些嘲讽！👊👊👊

> **周报精选**
>
> 新闻和社区：码出新宇宙，WWDC23 就在眼前
> 
> 提案：
> 
> Swift 论坛：
>
> 推荐博文：
> 
> **话题讨论：** 
> 
> 有博主在视频社交平台说，2023年已然迎来了经济危机，只是有些人不愿意相信而已，那么你认为国内2023年是否真的进入了经济危机？


**上期话题结果**

![](https://files.mdnice.com/user/17787/c465cfe7-1b3a-49d3-820c-e7b06fd7738b.png)

上期话题讨论结果表明对于 AI 是否会取代软件工程师的问题，大家的观点存在分歧，而实际的结果可能**取决于 AI 技术的发展和与人类工程师的协作方式的演变**。让我们拭目以待。

## 新闻和社区

### App、App 内购买项目和订阅即将实行税率调整

App Store 的交易和支付机制旨在帮助你在覆盖全球的 175 个国家和地区的商店中，以 44 种货币为你的产品和服务便捷地进行定价与销售。Apple 会为开发者管理其中 70 多个国家和地区的税收，而且你还能够为 App 和 App 内购买项目分配税务类别。我们会根据税务法规的变化，定期更新你在某些地区的收益。

从 5 月 31 日起，你从 App 和 App 内购买项目 (包括自动续期订阅) 销售中获得的收益将进行调整，以反映以下税率调整。请注意，相关内容的价格将保持不变。

加纳：增值税率从 12.5% 上调至 15%。
立陶宛：对于符合条件的电子书和有声书，增值税率从 21% 下调至 9%。
摩尔多瓦：对于符合条件的电子书和期刊，增值税率从 20% 下调至 0%。
西班牙：收取 3% 的数字服务税。
由于巴西税务法规的变化，在巴西开展的所有 App Store 销售现由 Apple 代扣税款。我们会按月代扣代缴应向相应税务机关缴纳的税款。自 2023 年 6 月开始，你可以在 5 月份的收入中查看从你的收益中扣除的税款金额。巴西境内的开发者不会受到这一变化的影响。

以上调整生效后，App Store Connect 中“我的 App”的“价格与销售范围”部分会随即更新。一如既往，你可以随时更改你的 App 和 App 内购买项目的价格 (包括自动续期订阅)。现在，你可以从 900 个价格点中选择，为任何店面更改定价。

### 码出新宇宙

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/B6D2ADBF-1563-457E-82CE-374A654AA6B0/2048.jpeg)

WWDC23 就在眼前。太平洋夏令时间 6 月 5 日上午 10 点，Apple 主题演讲将在 apple.com 和 Apple Developer App 线上提供，为本次大会拉开序幕。你还可以通过同播共享，邀请朋友一起观看。

现在，符合条件的开发者可以开始报名参加活动了。相关活动包括 Q&A、“会见演讲者”以及社区暖场活动等线上聊天室活动，旨在促进你与开发者社区和 Apple 专家的沟通和交流。

### Apple 公证服务更新

正如去年在 WWDC (简体中文字幕) 上宣布的那样，如果你目前使用 altool 命令行工具或者 Xcode 13 或更早版本通过 Apple 公证服务对 Mac 软件进行公证，则需要改为使用 notarytool 命令行工具，或者升级到 Xcode 14 或更高版本。自 2023 年 11 月 1 日起，Apple 公证服务将不再接受从 altool 或者 Xcode 13 或更早版本上传的内容。已经过公证的现有软件可以继续正常工作。

Apple 公证服务是一个自动化系统，它会扫描 Mac 软件中有没有恶意内容，检查有没有代码签名问题，并快速返回结果。对软件进行公证可向用户保证，Apple 已检查且未发现软件中包含恶意软件。

为改进 Apple 平台的安全性和隐私保护，用于验证 App 和关联 App 内购买项目销售的 App Store 收据签名媒介证书将更新为使用 SHA-256 加密算法。此更新将分多个阶段完成，新的 App 和 App 更新可能会受影响，具体取决于它们验证收据的方式。

### Apple 设计大奖入围名单公布

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/020C144B-0FE5-49A1-ADB2-7B01072574C7/2048.jpeg)

Apple 设计大奖旨在表彰在多元包容、乐趣横生、出色互动、社会影响、视觉图像，以及创新思维等类别中表现出色的 App 和游戏。马上一睹今年的入围作品，我们将在太平洋夏令时间 6 月 5 日下午 6:30 揭晓获奖者，敬请关注。

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

## 话题讨论
**有博主在视频社交平台说，2023年已然迎来了经济危机，只是有些人不愿意相信而已，那么你认为国内2023年是否真的进入了经济危机？**

1.是的。确实已经经济危机了，今年工作很难找，同事比以前更卷啦，各种裁员消息不断。

2.经济危机不可能。五一淄博接待游客超过了100万人次，人挤人的旅游景象依然常在。

3.经济危机应该是相对的。对于大多数上班族来说，2023年很难，奉劝大家且行且珍惜。

