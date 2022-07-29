## 前言

前几期周报内容是同步翻译的英文版周报，目前英文版停更，周报停滞半年多。经过多次讨论，我们决定**重启周报**，分模块整理内容同步给大家。

周报内容模块分为：**新闻**、**提案**、**Swift论坛**、**推荐博文**。初期计划每两周发布一期，欢迎志同道合的朋友一起加入周报整理。

昨日的生活与工作是否也曾迷茫？对新技术渴望突破的心是否依旧执着？**Swift社区**，为你的技术栈添砖加瓦，你，准备好了吗？

## 新闻和社区

### 即将从 XML Feed 过渡到 App Store Connect API

`App Store Connect REST API` 让您可以跨各种开发者工具自定义任务并实现任务自动化，使工作流程更灵活、更高效。从 **2022 年 11 月**开始，您将需要使用此 API 来代替 `XML Feed`，从而实现对 App 内购买项目、订阅、元数据和 App 定价的自动化管理。XML Feed 将继续为现有的 `Game Center` 管理功能提供支持。

### 新功能 RoomPlan

使用 [RoomPlan](https://developer.apple.com/augmented-reality/roomplan/ "Introducing RoomPlan") 创建房间的 3D 户型图，包括家具的尺寸和类型等关键特征。这个是由 ARKit 提供支持的全新 Swift API 能够利用 iPhone 和 iPad 上的摄像头和激光雷达扫描仪将现实环境带入您的 App 中。

![](https://files.mdnice.com/user/17787/ffa3c808-e6d2-4676-aa7f-14432950013f.png)

使用详情可以观看 WWDC22 中的 [使用 RoomPlan 创建参数 3D 房间扫描](https://developer.apple.com/videos/play/wwdc2022/10127/ "Create parametric 3D room scans with RoomPlan")

### 立即注册 WWDC22 实验室和聊天室

[注册实验室和线上聊天室](https://developer.apple.com/news/?id=kvwb7ph4 "Sign up now for WWDC22 labs and lounges")，即可在一整周内与 Apple 工程师、设计师和专家在线交流。

![](https://files.mdnice.com/user/17787/1a24a5c0-77b7-4d83-be72-664ff7927d11.png)

### 已推出 Xcode 14 Beta 版

包含了适用于所有 Apple 平台 SDK 的 `Xcode 14 Beta` 版现已推出。利用简洁且强大的 Swift 和 SwiftUI 以及全新的跨平台 App 体验，使用编辑器的增强功能更快捷地编写代码，并着手开始进行从 `Xcode Cloud` 到 `TestFlight` 以及 `App Store` 的测试和部署。

[下载 Xcode 14 Beta 版](https://developer.apple.com/xcode/ "Xcode 14 Beta")

## 提案
### 通过的提案
[SE-0352: 隐式开放的存在类型](https://github.com/apple/swift-evolution/blob/main/proposals/0352-implicit-open-existentials.md#introduction 'Implicitly Opened Existentials') **状态：Swift 5.7 已实现**
Swift 中的存在类型允许存储一个特定类型为未知的值，且可能在运行时更改。被存储值的动态类型，我们称为存在类型的底层类型，仅由它遵循的协议集以及潜在的超类知道。尽管存在类型对于表达动态类型的值非常有用，但由于它们的动态性质，它们一定受到限制。最近的提议使[存在类型更加明确](https://github.com/apple/swift-evolution/blob/main/proposals/0335-existential-any.md 'existential types more explicit')，以帮助开发人员理解这种动态性质，并通过消除一些限制[使存在类型更具表现力](https://github.com/apple/swift-evolution/blob/main/proposals/0309-unlock-existential-types-for-all-protocols.md 'making existential types more expressive')。但是存在类型的一个基本类型仍然存在，一旦你有一个存在类型的值，你就很难对其使用泛型。开发者通常会通过 “protocol 'P' as a type cannot conform to itself” 这样的报错信息，遇到这样的问题。

[SE-0352: 隐式开放的存在类型](https://github.com/apple/swift-evolution/blob/main/proposals/0352-implicit-open-existentials.md#introduction 'Implicitly Opened Existentials') 已于 2022 年 5 月 18 日完成，核心团队已决定接受该提案。第二次审查的重点是关注向前兼容性，当一个调用唤起一个隐式开放的存在类型，必须被抹除类型以防止存在的动态类型内存泄漏到返回值中。当存在类型的表达能力增加，我们可能会有能力使用一个更具体的类型作为这一个调用的返回类型，这可能造成源中断。为了避免这种情况，该提案要求在调用中显式地作为任何 P 类型注释，其中今天可以表达的返回类型将丢弃对被类型擦除的原始关联类型的约束，如提案中的示例所示：
```swift
protocol P {
  associatedtype A
}
protocol Q {
  associatedtype B: P where B.A == Int
}

func getP<T: P>(_ p: T)
func getBFromQ<T: Q>(_ q: T) -> T.B { ... }

func eraseQAssoc(q: any Q) {
  let x = getBFromQ(q)          // 错误，必须指定 "as any P" 由于缺少 T.B.A == Int 的约束
  let y = getBFromQ(q) as any P // 可以, 明确抛弃约束
}
```

[SE-0353: 受约束的存在类型](https://github.com/apple/swift-evolution/blob/main/proposals/0353-constrained-existential-types.md 'Constrained Existential Types') **状态：Swift 5.7 已实现**
存在类型补完了 Swift 类型系统中的抽象能力。与泛型一样，它们使函数能够获取和返回多种可能的类型。 与泛型参数类型不同，存在类型在作为输入传递给函数时不需要预先知道。此外，当从函数返回时，可以删除具体类型（隐藏在协议接口后面）。在这个领域出现了一系列活动，[SE-0309](https://github.com/apple/swift-evolution/blob/main/proposals/0309-unlock-existential-types-for-all-protocols.md#covariant-erasure-for-associated-types 'SE-0309: unlock existential types for all protocols') 解除了对使用具有关联类型的协议作为存在类型的剩余限制，而 [SE-0346](https://github.com/apple/swift-evolution/blob/main/proposals/0346-light-weight-same-type-syntax.md 'SE-0346: light weight same type syntax') 为关联类型协议的轻量级约束语法铺平了道路。该提案直接基于这些想法，旨在在存在类型的上下文中重用轻量级关联类型约束的语法。

```swift
any Collection<String>
```

[SE-0356: Swift 代码片段](https://github.com/apple/swift-evolution/blob/main/proposals/0356-swift-snippets.md 'Swift Snippets')
该提案描述了编写称为片段的新形式示例代码的约定。 片段是简短的单文件示例，可以在 Swift 包中构建和运行，可以访问该包中的其他代码，并且可以以多种方式使用。


### 正在审查中的提案
[SE-0359: 构建时间常数值](https://github.com/apple/swift-evolution/blob/main/proposals/0359-build-time-constant-values.md 'Build-Time Constant Values') **状态：已接受**
构建时间常数值是一个 Swift 语言特性，要求在编译时知道某些值。这是通过属性、`@const`、约束属性和函数参数来实现的，以使其具有编译时可知的值。这些信息为未来更丰富的编译时特性奠定了基础，例如在编译时提取和验证值。

[SE-0362: 即将到来的语言改进的逐渐采用](https://github.com/apple/swift-evolution/blob/main/proposals/0362-piecemeal-future-features.md 'Piecemeal adoption of upcoming language improvements') **状态：已接受**
Swift 6 积累了许多对语言有源码兼容性影响的改进，从而在以前的语言模式（Swift 4.x 和 Swift 5.x）中默认情况下无法启用它们。这些改进已经在背后为 Swift 6 语言模式的 Swift 编译器中实现，但他们对于开发者是无法访问的，并将持续直到 Swift 6 作为一个可获得的语言模式。这有很多原因为什么我们应该思考尽快提供这些改动。

- 开发者希望很快从这些改进中受益，而不是等到 Swift 6 可用。
- 向开发者提供这些改进比 Swift 6 提供更多体验优先级更高，如果有必要，允许我们针对 Swift 6 进一步调试它们。
- 对于某些模块，所有在 Swift 6 中改动的总数或许会造成迁移繁重，并且在 Swift 4.x/5.x 中逐一采纳这些语言改动，可以使过渡期路径变得丝滑。

一些提案已经引入了定制解决方案来提供迁移路径：[SE-0337](https://github.com/apple/swift-evolution/blob/main/proposals/0337-support-incremental-migration-to-concurrency-checking.md 'support-incremental-migration-to-concurrency-checking') 添加了 `-warn-concurrency` 以在 Swift 4.x/5.x 中启用与 `Sendable` 相关检查的警告。 [SE-0354](https://github.com/apple/swift-evolution/blob/main/proposals/0354-regex-literals.md 'regex-literals') 添加标志 `-enable-bare-slash-regex` 以启用 `/.../` 正则表达式语法。尽管它不是提案的一部分，但对 [SE-0335](https://github.com/apple/swift-evolution/blob/main/proposals/0335-existential-any.md 'existential-any') 的讨论包括对编译器标志的请求，以在存在类型上要求使用 `any` 。这些都具有相同的风格，即选择现有的 Swift 4.x/5.x 代码进行改进，这些改进将出现在 Swift 6 中。

这个提议明确地包含了零碎的、有意采用的特性，这些特性在 Swift 6 之前出于源代码兼容性的原因而保留。它为逐步采用 Swift 6 特性建立了一条直接路径，以在 Swift 4.x/5.x 代码库中获得它们的优势，并顺利迁移到 Swift 6 语言模式。开发人员可以使用新的编译器标志 `-enable-upcoming-feature X` 为该模块启用名为 `X` 的特定功能，并且可以以这种方式指定多个功能。当开发人员移动到下一个主要语言版本时，该语言版本将隐含 `X` 并且编译器标志将被拒绝。这样，即将推出的功能标志只会累积到下一个主要的 Swift 语言版本，然后被清除，所以我们不会将语言分叉成不兼容的方言。

## Swift论坛

1. [SwiftUI 中的新功能](https://developer.apple.com/forums/tags/wwdc2022-10052 "What's new in SwiftUI") 围绕 `WWDC2022-10052` 内容进行讨论

2. [Swift 正则表达式](https://developer.apple.com/forums/tags/wwdc2022-110357 "Meet Swift Regex") 围绕 `WWDC2022-110357` 内容进行讨论

3. [SwiftUI 导航](https://developer.apple.com/forums/tags/wwdc2022-10054 "The SwiftUI cookbook for navigation") 围绕 `WWDC2022-10054` 内容进行讨论

4. [Swift 图表](https://developer.apple.com/forums/tags/wwdc2022-10137 "Swift Charts") 围绕 `WWDC2022-10137` 内容进行讨论

5. 使用 [cmake 构建 swift](https://forums.swift.org/t/using-cmake-to-build-swift-instead-of-build-script/59095 "Using cmake to build swift") 而不是 `build-script`。

`build-script` 是 `build-script-impl` 的 python 包装器，本身是一个 `shell` 脚本，然后运行 CMake，执行可以构建项目的工作主体。 例如，如果您想执行 `utils/build-script -x`，将调用 `cmake -G Xcode`。

6. **Visual Studio Code** [增加扩展包](https://forums.swift.org/t/introducing-swift-for-visual-studio-code/54246 "VSCode extension") 支持 Swift 开发

7. [SwiftNIO _ChannelInboundHandler 与 DocC 不兼容](https://forums.swift.org/t/swiftnio-channelinboundhandler-is-docc-incompatible/58611 "SwiftNIO _ChannelInboundHandler is DocC incompatible")

在阅读 swift-biome 中的 `SwiftNIO` 文档时，遇到一个问题。文档其中引用了 3 个带下划线的属性。例如：`_ChannelInboundHandler`、`_EmittingChannelHandler` 等，但是这些属性在 swift-biome 和其他基于 `SymbolGraphGen` 的工具是不可见的，包括 DocC。

8. [Foundation 中基于 KeyPath 的对比 API](https://twitter.com/natpanferova/status/1547103127429857280 "KeyPath-based comparison API in Foundation")

在 `Foundation` 中引入的 `KeyPathComparator` API，比 Swift 中的 `sorted(by:)` 方法更清晰。这个 API 可以根据数组中的某个特定元素进行排序。

![](https://github.com/SwiftCommunityRes/image/blob/main/FXhpnbMacAE1d6P.jpg?raw=true)


## 推荐博文

**SwiftUI 动画系列**，文章结合动画 Gif 原图和源码为案例，深入探讨了如何创建应用 SwiftUI 动画。

[高级 SwiftUI 动画 — Part 1：Paths](https://mp.weixin.qq.com/s/5KinQfNtcovf_451UGwLQQ)

**摘要：** 本文主要介绍了显式动画和隐式动画，以及针对 Animatable 协议的相关讨论。

[高级 SwiftUI 动画 — Part 2：GeometryEffect](https://mp.weixin.qq.com/s/rE_HILLt-uxzScS7wXh5jw)

**摘要：** 主要介绍使用新工具 GeometryEffect 创建 SwiftUI 动画。GeometryEffect是一个符合Animatable 和 ViewModifier 的协议。

[高级 SwiftUI 动画 — Part 3：AnimatableModifier](https://mp.weixin.qq.com/s/M6MW3idXS6jZJtl4Mz5DGQ)

**摘要：** 本文主要介绍使用 AnimatableModifier 完成更加复杂的动画效果。AnimatableModifier 是一个 ViewModifier，符合 Animatable 协议，如果对这个协议不了解可以阅读之前发布的两篇文章。

[SwiftUI 动画进阶 — Part4：TimelineView](https://mp.weixin.qq.com/s/9OBtFNb5ddnx4_fS93Mnrg)

**摘要：** 前三篇高级 SwiftUI 动画是作者在实战中总结的内容。本篇文章，我们将详细地探索 TimelineView。

[SwiftUI 动画进阶 — Part 5：Canvas](https://mp.weixin.qq.com/s/0kkHpzv4Y9O5d7InEAKbEw)

**摘要：** 本篇文章将探索 Canvas 视图。从技术上讲，它不是一个动画视图，但当它与第四部分的 TimelineView 结合时，可以现实很多有趣的功能。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的各种交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。

周报仓库：https://github.com/SwiftCommunityRes 文章中外引链接较多，可以点击 **阅读原文** 更加方便阅读。
