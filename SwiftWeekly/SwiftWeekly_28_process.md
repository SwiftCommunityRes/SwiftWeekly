## 前言

**本期是 Swift 编辑组自主整理周报的第十九期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

用鞭子抽打，陀螺才会旋转。览**Swift社区**，技能方可升华！👊👊👊

> **周报精选**
>
> 新闻和社区：外媒：iPhone 的平均售价直逼 1000 美元创历史新高
> 
> 提案：
> 
> Swift 论坛：
>
> 推荐博文：
> 
> **话题讨论：** 
> 
> 

## 新闻和社区

### 外媒：iPhone 的平均售价直逼 1000 美元创历史新高

近日根据调研公司公布的数据显示，全球智能手机市场表现整体下行，不过高端手机近三年同比都呈现增长趋势，尤其是 600 美元以上的机型。市场研究机构 CIRP 的数据报告显示在 2023 年第一季度 iPhone 的平均售价达到 988 美元 ( 约合人民币 6837 元 ) ，同比增长 12%，创历史新高，其中 iPhone 14 Pro 以及 iPhone 14 Pro Max 是 iPhone 系列最受欢迎的型号，虽然两款手机价格相对较高，但还是占据了总销量的近一半。去年同期 iPhone 的平均售价为 882 美元，2021 年的收尾价为 847 美元。

![](http://zkres2.myzaker.com/202305/645351248e9f095a955c2015_1024.jpg)

相比之下 iPhone 14 的两款入门款机型的表现平平，而且跟上一代机型基本相同，大家宁愿买 iPhone 13 也不愿意买 iPhone 14。此外，用户对于手机存储空间的需求也在增加，导致更多人选择了更高容量的手机，这也进一步提升了平均售价。

### 分析师：iPhone需求良好，苹果股价还能涨22%

根据 Refinitiv 的预期，苹果最新财季的每股收益预计为 1.43 美元，营收为 929.7 亿美元，暗示将同比下滑 4.4%。另据 FactSet 的估计，苹果最新财季 iPhone 的收入预计将同比下滑 3.8% 至 486.6 亿美元，且预计包括 iPhone 在内的每条硬件产品线都会出现同比下滑。

不过，Wedbush 高级分析师 Daniel Ives 在发给《每日经济新闻》记者的置评邮件中称，根据他们最近对亚洲供应链的调查，他们认为苹果周四盘后发布的财报中，iPhone 的营收应该至少与预期一致。

“我们认为，尽管宏观形势不稳，但由于较高的平均售价和 iPhone14 Pro 的整体升级活动，以及 iPhone 本季度在关键的中国市场的需求明显上升，该产品线的营收可能会出现一些上升。随着本季度 App Store 营收的增长，我们认为苹果的服务收入应该是稳定的，结合起来应该转化为苹果的核心收入，至少应该符合市场预期，我们维持对苹果的‘跑赢大盘’评级和 205 美元的目标价。”这意味着，苹果较周三收盘价 167.45 美元还有 22% 的上涨空间。

“苹果在中国的市场份额正在增加，美国和欧洲的需求也保持良好，我们估计目前约有 25% 的 iPhone 用户在过去四年多的时间里没有换过新机。由于备受期待的周年纪念版iPhone 15 将于 9 月份发布，从 iPhone 14 到 iPhone 15 的过渡看起来将比过去的 iPhone 换代周期更加稳定。我们还认为，iPhone 的平均售价将升至 900 美元 ~ 925 美元左右，这将是下一个 iPhone 周期一个值得关注的趋势。”Daniel Ives补充道。
### 准备好迎接即将在 5 月 9 日推出的增强全球定价机制

借助 App Store 世界级的商务和支付系统，你能够便捷高效地为国际市场设定均衡的价格，根据外汇汇率或税费的变化进行调整，还可以管理每个店面的价格。上个月，我们推出了重大定价机制升级，其中包括将增强全球定价机制的适用范围扩展至所有购买类型。如今，更新后的价格点将跟随各个国家或地区最常见的定价方式，并且将根据金融数据机构提供的公开汇率信息做调整，在全球范围内与你为基准店面设定的价格保持平衡，因此更适用于当地顾客。

谨此提醒，自 2023 年 5 月 9 日起，App Store 各店面的现有 App 和一次性 App 内购买项目的价格都将以产品当前在美国店面的价格为基础进行更新，除非你在 2023 年 3 月 8 日后进行了相关更新。你随时可以使用 App Store Connect 或 App Store Connect API 更新基准店面的国家或地区。如果你选择进行更新，在 App Store 根据外汇变化或新的税费生成全球均衡价格时，你所选基准店面的价格将不会受到调整。你还可以选择手动调整多个所选店面中的价格，而不使用均衡的价格。

## 提案


## Swift论坛

1) 讨论[避免未使用的异步结果的可发送警告](https://forums.swift.org/t/avoiding-sendable-warning-for-unused-async-result/64633 "避免未使用的异步结果的可发送警告")
*** 内容大概 ***
有一个独立于专用actor的功能：
```Swift
@globalActor
final class SomeDedicatedActor {
    actor Actor {}
    static let shared = Actor()
}

@SomeDedicatedActor
func f() async -> [Any] {
    // ...
}
```
我们通常从与@SomeDedicatedActor 隔离的其他函数调用 f()，但我们有一个调用是我们想从不同的 actor 进行的。 我们做这个调用纯粹是为了 f 的副作用，根本不关心返回结果。 我希望以下构造是有效的，但是通过 Targeted/Complete Sendable 检查，我们会收到警告：
```Swift
@MainActor
func g() async {
    // ⚠️ Non-sendable type '[Any]' returned by implicitly asynchronous call
    // to global actor 'SomeDedicatedActor'-isolated function cannot cross
    // actor boundary
    _ = await f()
}
```
如果不使用 Swift 会忽略跨角色边界传输结果是否合理？

* 如果是这样，那么这只是一个虚假的警告，还是这个构造现在实际上是不安全的（因为该值确实强行跨越参与者边界）？
* 如果不是，是否有理由必须跨界传输结果？

*** 回答 ***
如果该值是不可发送的，它可能具有只允许在其原始 actor 中发生的 deinit 效果。 因此，忽略结果实际上必须“避免返回”actor 的结果，因为它必须在离开 actor 的隔离上下文之前销毁该值。 这对我来说似乎相当微妙，但也许它与编写一个返回非 Sendable 类型的隔离方法是一致的，因为您永远无法使用隔离之外的结果。

2) 讨论[在函数参数列表中使用 $ 进行绑定](https://forums.swift.org/t/using-for-binding-in-function-parameter-list/64645 "在函数参数列表中使用 $ 进行绑定")
*** 内容大概 ***
最近发现可以像这样在闭包参数中使用 $ 变量名：
```Swift
Bind("Title") { $title in
      TextField(title, text: $title)
}
```
然而，对于像这样的函数参数来说，同样的事情似乎是不可能的：
```Swift
func foo(title $title: Binding<String>) {
      TextField(title, text: $title)
}
```
但是编译器在函数声明处给出了一个错误：
```Swift
Cannot declare entity named '$title'; the '$' prefix is reserved for implicitly-synthesized declarations
```
*** 回答 ***
您需要在参数上使用属性包装器。
```Swift
func foo(@Binding title: String) {
  TextField(title, text: $title)
}

foo($title: .constant("R.I.P. Taylor Hawkins 🥁"))
```

3) 讨论[Task - 等待变量更改](https://forums.swift.org/t/task-awaiting-for-variable-change/64626 "Task - 等待变量更改")
*** 内容大概 ***
在使用 Task 时有一个如何解决问题的建议。
在等待 Task 内部的一些变量更改以进一步移动。
意思是说：
```Swift
Task {
  ... for example here comes some complex code that is sending requests 
   through web socket to outer world, 
   response from websocket will change the variable result on this clas 
   but out of this scope

   // with this line we are waiting for variable change with reasonable timeout
   do {
      try await @change(variable: self.result, timeout:10 sec)
   } catch {
      ... timeout
      print("we are waiting too long for server response")
   }
}
```
*** 回答 ***
您目前可以使用异步序列解决此问题。 现在的一个常见模式是执行以下操作：
```Swift
static func main() async {
  var cont = AsyncStream<Int>.Continuation!  
  let stream = AsyncStream<Int> { cont = $0 }
  let continuation = cont
  
  setupWebsocket(continuation)

  for await element in stream {
    // process the result
  }
}

func setupWebsocket(continuation: AsyncStream<Int>.Continuation) {
  // Setup the web socket and at some point call the following code
  continuation.yield(2) // Yield your result
}
```
另一件可能对这里有帮助的事情是当前正在发生的 Observation pitch，这将允许你观察类并让 Task 改变它； 然而，重要的是你需要确保一切都是线程安全的。

4) 更新[Foundation 的下一步计划 - 2023 年 4 月更新](https://forums.swift.org/t/whats-next-for-foundation-april-2023-update/64637 "Foundation 的下一步计划 - 2023 年 4 月更新")
链接：https://www.swift.org/blog/future-of-foundation/
更多相关的详细信息链接：https://www.swift.org/blog/foundation-preview-now-available/

5) 更新[Swift Evolution Dashboard支持即将推出的Feature Flags](https://forums.swift.org/t/swift-evolution-dashboard-support-for-upcoming-feature-flags/64617 "Swift Evolution Dashboard支持即将推出的Feature Flags")
Swift Evolution Dashboard 现在包括对即将推出Feature Flags的支持。

Swift 5.8 引入了使用新编译器选项启用即将推出的功能的能力：-enable-upcoming-feature 后跟即将推出的功能的名称。

这些即将到来的特征标识符被称为即将到来的特征标志或简称 UFF。
（详见 SE-0362 1）

随着Dashboard的更新，您现在可以轻松找到所有带有即将推出的功能标志的提案以及用于每个功能的标志名称。

您可以使用 Swift Evolution 仪表板来：

* 查看提案的 UFF（如果有的话）
* 按名称搜索 UFF
* 过滤以查看所有带有 UFF 的提案
* 新的 UFF 过滤器按钮与现有的搜索字段和状态过滤器结合使用。

## 推荐博文

[SwiftUI 中的 Deeplink URL 处理](https://www.avanderlee.com/swiftui/deeplink-url-handling/ "SwiftUI 中的 Deeplink URL 处理")

**摘要：** 本文讨论深度链接（ deeplinks ）以及如何在 SwiftUI 中配置应用程序来处理它们。深度链接允许用户通过打开特定位置，在启动后深入进入您的应用程序，例如基于所点击的链接打开某个菜谱或电影等。本文提供了在 Xcode 中配置URL类型和使用视图修饰符或 AppDelegate/SceneDelegate 方法处理传入 URL 的步骤。此外，它建议使用深度链接进行其他场景，例如使用特定账户登录或在预发布和生产环境之间切换。该文章还强调了考虑安全性时定义支持 Deeplink URL 的重要性。

[抖音 Swift 编译优化 - 基于自定义 Toolchain 编译提速 60%](https://juejin.cn/post/7221444501956886588 "抖音 Swift 编译优化 - 基于自定义 Toolchain 编译提速 60%")

**摘要：** 本篇博客主要介绍了抖音团队基于自定义 Toolchain 提出的 Swift 编译优化方案，重点讨论在全部模块化后解决依赖瓶颈所采用的方法以及优化效果。通过裁剪 Clang Header 指定内容来降低 OC 头文件预编译耗时，并采用细粒度控制方案，实现编译提速 60%。文章还分享了方案拆解、快速验证、开发调试、验证上线等具体流程，对于有需要进行Swift编译优化的读者可以参考此文中给出的思路和方法。

[Swift 最佳实践之 Property Wrapper](https://juejin.cn/post/7222189908429275173 "Swift 最佳实践之 Property Wrapper")

**摘要：**  本文介绍了 Swift 5.1 中引入的 Property Wrapper，它是对属性的一层封装，隐藏与属性相关的逻辑细节从而提高代码复用性。文章详细讲解了 Property Wrapper 的定义、使用、初始化以及 Projected Value 等概念，并通过示例展示了在 SwiftUI、线程安全保护、Codable 和 User Defaults 存储等方面应用 Property Wrapper 的方法和好处。最后还指出了使用 Property Wrapper 标记属性时需要注意的限制。


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
