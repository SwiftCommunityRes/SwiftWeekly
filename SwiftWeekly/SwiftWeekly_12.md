## 前言

**本期是 Swift 编辑组自主整理周报的第三期**，每个模块还在调整磨合期。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

夏夜恬静月色柔，绵绵思绪埋心头，**Swift社区**常逗留，今夕明朝百事欧。欧拉欧拉👊👊👊

> **周报精选**
>
> 新闻和社区：苹果曝出严重安全漏洞！黑客或可完全接管设备
> 
> 提案：改进指针系列初始化和缓冲区
> 
> Swift 论坛：使用 Swift 5.5 / Xcode 14 构建后崩溃
>
> 推荐博文：iOS16 引入 SwiftUI Charts

## 新闻和社区

### 苹果曝出严重安全漏洞！黑客或可完全接管设备

当地时间 8 月 19 日（周五），苹果公司（Apple）呼吁用户立刻下载最新更新。就在两天前，该公司报告了一个重大的安全漏洞，据称可以让黑客接管苹果设备。
在周三发布的安全更新中，苹果表示该漏洞可能已被用于攻击行为。

“这就是我们所说的零日漏洞，也就是在公司发现并能够做出回应之前，已经被黑客所使用过的漏洞，” 美国麦迪安网络安全公司（Mandiant）的高级威胁情报顾问杰米·科利尔（Jamie Collier）介绍道。

据介绍，受本次漏洞影响的设备涵盖了几乎所有的苹果产品。其中，手机包括 iPhone 6S 及以后的型号；平板包括第五代及以后的 iPad，所有 iPad Pro，以及 iPad Air 2；电脑则是运行 MacOS Monterey 的 Mac。此外，该漏洞还能影响到部分型号的 iPod。@看看新闻

### App 和 app 内购买项目即将实行税率和价格调整

2022 年 8 月 19 日的下周开始，加纳和土耳其 App Store 的 App 及 App 内购买项目 (自动续期订阅除外) 的价格将有所提高。加纳的价格提升将包含 **12.5%** 的新增值税和 **6%** 的附加税。

您的收益将随之进行调整，并会根据不含税的价格来进行计算。《付费 App 协议》的附录 B 已更新，表明 Apple 在加纳征收和汇付适用税款。

此外，如果您在 App Store Connect. 中选择了适当的税收类别，爱沙尼亚的电子出版物的收益已经进行了调整，以反映增值税从 **9%** 下调至 5%。

以上调整生效后，在“我的 App”中“价格与销售范围”部分会随即更新。您可以随时在 App Store Connect 中更改您的 App 和 App 内购买项目的价格 (包括自动续期订阅)。如果您有提供订阅项目，您可以选择为现有订阅者保留当前价格。

苹果发言人没有立即透露这个电池百分比调整是否会延续到 iOS 16 的最终版本。这次更新目前只出现在开发者版和公测版。新 iOS 系统将于今年秋天发布，可能是在 9 月份，届时苹果预计将发布 **iPhone 14**。@凤凰网科技

### 苹果 AppleOne 将捆绑销售电话套餐：英国运营商EE是第一家

英国运营商 EE 近日宣布，它将成为第一家将苹果 Apple One 与电话套餐捆绑在一起的运营商。EE表示，苹果 Apple One 将从 8 月 31 日起包含在其 Full Works 计划中。该计划将包括 Apple One 的个人版订阅，每月费用为 14.95 英镑（约 122.44 元人民币）。

苹果 Apple One 订阅包将最多六项苹果服务捆绑到一个订阅中，个人版单独订阅价格为每月 14.95 美元（约 101.51 元人民币），包括四项苹果服务：50GB 的 iCloud+、Apple Music、Apple TV+ 和 Apple Arcade 订阅。

iPhone13 系列成美国最畅销手机机型# 2022 年 Q2 美国最畅销的 10 款智能手机机型，包括苹果、三星、联想三个品牌。其中，苹果 iPhone 13、iPhone 13 Pro Max、iPhone 13 Pro 包揽前三位。三星 Galaxy S21、Galaxy S22 / Ultra 等 5 款新机进入畅销榜前十，Galaxy S22 Ultra 5G 为 2022 年 Q2 美国最畅销的安卓机型。(来源：(来源： 极目新闻))

### 赔偿 2 亿元！苹果因搜包耽误员工下班，遭 1 万多人集体起诉

据路透社 8 月 15 日报道消息，当地时间 13 日，美国加州一名法官已经签署了苹果公司的 3050 万美元（约合人民币 2 亿元）的和解协议。该诉讼持续 9 年，诉讼称苹果公司没有为下班时检查员工行李的时间付费。

起诉源于苹果之前的一项规定，这项规定要求在下班时检查苹果员工的包和个人物品。2013 年，一群苹果公司员工因被迫接受行李检查起诉苹果公司，称公司没有为搜包的时间付费。原告称，苹果零售员工在下班后通常要等几分钟，有时甚至更长时间，才能检查完他们的行李，然后才能离开他们工作的商店。在被提起诉讼后，苹果不再对员工下班前进行搜包检查。

据纽约邮报 2015 年 6 月的报道，公布的一份法庭文件显示，至少有两名苹果零售店员工直接向首席执行官库克投诉，称该公司将检查零售员工行李作为安全预防措施的规定令人尴尬和有辱人格。

集体诉讼于 2015 年被驳回，随后他们决定上诉。州法院在 2020 年对苹果作出裁决，称期望员工不带个人物品上班是不切实际的。联邦法院随后恢复了此案，美国地方法院法官威廉·阿尔苏普去年表示，他计划对原告作出简易判决，并下令对损害赔偿进行审判。

8 月 13 日，阿尔苏普在集体诉讼中批准了和解协议。这标志着该州历史上最大的安全搜查案和解。3050 万美元的和解金将支付给包括居住在加州的 14683 名苹果员工在内的一个群体，平均每位员工获得 1328 美元赔偿金。(来源：极目新闻)

## 提案

### 通过的提案

[SE-0367](https://github.com/apple/swift-evolution/blob/main/proposals/0367-conditional-attributes.md "SE-0367") **优化新属性的条件编译** 提案已通过。该提案已在上期周报正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0371](https://github.com/apple/swift-evolution/blob/main/proposals/0371-isolated-synchronous-deinit.md "SE-0371") **Isolated synchronous deinit** 提案正在审查。

此功能允许 `deinit` 中 `actor` 和 `global-actor` 的 `isolated` 类型 (GAIT)， 访问 `non-sendable` 的 `isolated` 状态，从而解除 [SE-0327](https://github.com/apple/swift-evolution/blob/main/proposals/0327-actor-initializers.md "SE-0327") 施加的限制。这是通过在 `__deallocating_deinit()` 中实现，为跳转到执行程序提供运行时支持。


[SE-0370](https://github.com/apple/swift-evolution/blob/main/proposals/0370-pointer-family-initialization-improvements.md "SE-0370") **改进指针系列初始化和缓冲区** 提案正在审查。

`UnsafeMutablePointer` 系列中的类型通常需要手动管理内存分配，包括管理其初始化状态。但是，并非该系列中的每个相关类型都具有一定的功能来管理内存的初始化状态。分配后涉及的状态如下：

1. 没有绑定和没有初始化（从 `UnsafeMutableRawPointer.allocate()` 返回）
2. 绑定到类型，没有未初始化（从 `UnsafeMutablePointer<T>.allocate()` 返回）
3. 绑定到类型，并初始化
  
只要内存未初始化，就可以安全地释放内存。

我们打算完善该系列中每个相关成员的初始化功能：`UnsafeMutablePointer`、`UnsafeMutableRawPointer`、`UnsafeMutableBufferPointer`、`UnsafeMutableRawBufferPointer`、`Slice<UnsafeMutableBufferPointer>` 和 `Slice<UnsafeMutableRawBufferPointer>`。该功能将允许在更多种类的情况下管理初始化状态，包括更轻松地处理部分初始化的缓冲区。

[SE-0365](https://github.com/apple/swift-evolution/blob/main/proposals/0365-implicit-self-weak-capture.md "SE-0365") **增加对协议 CustomDebugStringConvertible 到 AnyKeyPath 的一致性** 提案正在审查。

## Swift论坛

1) 围绕 [提议 Async buffered channel](https://forums.swift.org/t/pitch-async-buffered-channel/59854 "Async buffered channel") 进行的讨论

内容概括：创建一个总集 channel 可以在 Tasks 之间交流，主要用于一个 task 产生的 value 可以被另一个 task 使用。

2) [新问题：使用 Swift 5.5 / Xcode 14 构建后崩溃](https://forums.swift.org/t/new-crash-after-building-with-swift-5-5-xcode-14/59798 "使用 Swift 5.5 / Xcode 14 构建后崩溃")

内容概括：swift 代码使用地址引用传入 NSMutableArray 类型给 Objective-C，Objective-C会返回 Array 的地址给 Swift 代码，当 iteration loop 返回的 array 时发生崩溃。可能原因：Swift ARC 内存优化释放指针引起的崩溃。

3) [用于 SwiftSyntax 的新 Swift 解析器](https://forums.swift.org/t/a-new-swift-parser-for-swiftsyntax/59813 "用于 SwiftSyntax 的新 Swift 解析器")

内容概括：SwiftSyntax 是一个 Swift Package，它可以解析 Swift 代码成一个树状的语义，可以对树进行操控也可以将树状的语义变回 Swift 代码。目前 SwiftSyntaxParser 是一个基于 C++ 库并且 Swift compiler 非常依赖于 C++ 库。
项目目标：完全取代 Swift parser 对 C++ 库的依赖

4) 围绕 [SE-0370 pointer family initialization improvements and better buffer slice](https://forums.swift.org/t/pitch-pointer-family-initialization-improvements-better-buffer-slices/55689 "SE-0370") 展开的讨论

5) [提议：标准库的稳定排序](https://forums.swift.org/t/pitch-document-sorting-as-stable/59880 "提议：标准库的稳定排序")

稳定排序是：在比较相同元素的情况下保持输入的顺序：例子：

```Swift
var roster = [
   Player(first: "Sam", last: "Coffey"),
   Player(first: "Ashley", last: "Hatch"),
   Player(first: "Kristie", last: "Mewis"),
   Player(first: "Ashley", last: "Sanchez"),
   Player(first: "Sophia", last: "Smith"),
]

roster.sort(by: { $0.first < $1.first })
// roster == [
//    Player(first: "Ashley", last: "Hatch"),
//    Player(first: "Ashley", last: "Sanchez"),
//    Player(first: "Kristie", last: "Mewis"),
//    Player(first: "Sam", last: "Coffey"),
//    Player(first: "Sophia", last: "Smith"),
// ]
```

从例子中看出有两个一样的 first: "Ashley", 由于输入 "Hatch" 在 "Sanchez" 之前, 稳定排序之后顺序不变。

6) [访问变量时只运行一次函数的最佳方法](https://www.reddit.com/r/swift/comments/wwgblk/best_way_to_run_a_function_only_once_while/ "访问变量时只运行一次函数的最佳方法")

7) [确保 viewDidLoad 中的嵌套闭包在函数运行之前完成的最佳方法](https://www.reddit.com/r/swift/comments/wvpxmn/what_is_the_best_way_to_make_sure_a_nested/ "确保 viewDidLoad 中的嵌套闭包在函数运行之前完成的最佳方法")

## 推荐博文

[在 iOS 16 中使用 SwiftUI Charts 创建折线图](https://swdevnotes.com/swift/2022/create-a-line-chart-with-swiftui-charts-in-ios-16/ "在 iOS 16 中使用 SwiftUI Charts 创建折线图")

**摘要：** Apple 在 `WWWDC 2022` 上推出了 `SwiftUI Charts`，在 `SwiftUI` 视图中实现图表功能变得非常容易。如下图：

![](https://files.mdnice.com/user/17787/67441474-df56-42c8-8ce4-ec4e3a1f1a25.png)

[在 iOS 16 中使用 SwiftUI Charts 自定义折线图](https://swdevnotes.com/swift/2022/customise-a-line-chart-with-swiftui-charts-in-ios-16/ "在 iOS 16 中使用 SwiftUI Charts 自定义折线图")

**摘要：** iOS 16 中引入的 SwiftUI Charts，可以快速的实现各种统计图，通过图表直观的呈现数据。本文介绍了几种自定义的折线统计图。

[如何在 SwiftUI 中创建条形图](https://swdevnotes.com/swift/2021/how-to-create-bar-chart-swiftui/ "如何在 SwiftUI 中创建条形图")

**摘要：** 本文展示了如何创建一个垂直条形图，其中 Y 轴表示每个类型的值。如下图：

![](https://files.mdnice.com/user/17787/369e7b63-cf7c-40bc-816d-d33e2bb6d137.png)

[如何在 SwiftUI 中创建水平条形图](https://swdevnotes.com/swift/2021/horizontal-bar-chart-in-swiftui/ "货拉拉 iOS 司机端线程治理总结")

**摘要：** 根据 UI 设计以及交互需求，有时候统计图需要调整 X 和 Y 轴。本文主要介绍了如何创建水平的条形图，如下图：

![](https://files.mdnice.com/user/17787/190c7254-5ee2-4f01-a298-4594d21acfb3.gif)

[使用 SwiftUI 的 Eager Grids](https://github.com/SwiftCommunityRes/article-ios/blob/main/resource/%E4%BD%BF%E7%94%A8%20SwiftUI%20%E7%9A%84%20Eager%20Grids.md "使用 SwiftUI 的 Eager Grids")

**摘要：** 本篇文章主要讲解如何使用 `Eager Grids` 绘制网格视图，其中讲解了十几种网格的实现方法，并详细介绍了网格的实现原理。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
