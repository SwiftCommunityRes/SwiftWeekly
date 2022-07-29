## 前言

前几期周报内容是同步翻译的英文版周报，目前英文版停更，周报停滞半年多。经过多次讨论，我们决定**重启周报**，分模块整理内容同步给大家。

周报内容模块分为：**新闻**、**提案**、**Swift论坛**、**推荐博文**。初期计划每两周发布一期，欢迎志同道合的朋友一起加入周报整理。

昨日的生活与工作是否也曾迷茫？对新技术渴望突破的心是否依旧执着？**Swift社区**，为你的技术栈添砖加瓦，你，准备好了吗？

## 新闻和社区

### 苹果先买后付服务被警告：破坏这一新兴行业的竞争

据英国《金融时报》7月27日报道，美国消费者金融保护局罗希特·乔普拉向硅谷发出警告。大型科技公司进入“先买后付”贷款业务会破坏这一新兴行业的竞争，他还对客户数据的使用提出了质疑。此前6月6日苹果公司在年度开发者大会上推出“先买后付”的`“Apple Pay Later”`服务，允许用户6周内分4期付款，期间不产生利息等其他费用。（via 泰山财经）

### 与 App Store 专家会面交流

准备好与专家在线交流探讨，了解如何充分利用 `App Store` 的功能。探索如何吸引新顾客、测试营销策略、添加订阅等等。在整个 8 月，苹果官方将在多个时区以多种语言进行实时演讲和答疑。如果您也是苹果开发者的话，最近肯定收到了相关的邮件邀请吧，不知道您是否参加了本次会面交流呢？

### 即将从 XML Feed 过渡到 App Store Connect API

`App Store Connect REST API` 让您可以跨各种开发者工具自定义任务并实现任务自动化，使工作流程更灵活、更高效。从 **2022 年 11 月**开始，您将需要使用此 API 来代替 `XML Feed`，从而实现对 App 内购买项目、订阅、元数据和 App 定价的自动化管理。XML Feed 将继续为现有的 `Game Center` 管理功能提供支持。

### 新功能 RoomPlan

使用 [RoomPlan](https://developer.apple.com/augmented-reality/roomplan/ "Introducing RoomPlan") 创建房间的 3D 户型图，包括家具的尺寸和类型等关键特征。这个是由 ARKit 提供支持的全新 Swift API 能够利用 iPhone 和 iPad 上的摄像头和激光雷达扫描仪将现实环境带入您的 App 中。

![](https://github.com/SwiftCommunityRes/image/blob/main/weekly/weeklynew01.png?raw=true)

使用详情可以观看 WWDC22 中的 [使用 RoomPlan 创建参数 3D 房间扫描](https://developer.apple.com/videos/play/wwdc2022/10127/ "Create parametric 3D room scans with RoomPlan")

### 立即注册 WWDC22 实验室和聊天室

[注册实验室和线上聊天室](https://developer.apple.com/news/?id=kvwb7ph4 "Sign up now for WWDC22 labs and lounges")，即可在一整周内与 Apple 工程师、设计师和专家在线交流。

![](https://github.com/SwiftCommunityRes/image/blob/main/weekly/weeklynew02.png?raw=true)

### 已推出 Xcode 14 Beta 版

包含了适用于所有 Apple 平台 SDK 的 `Xcode 14 Beta` 版现已推出。利用简洁且强大的 Swift 和 SwiftUI 以及全新的跨平台 App 体验，使用编辑器的增强功能更快捷地编写代码，并着手开始进行从 `Xcode Cloud` 到 `TestFlight` 以及 `App Store` 的测试和部署。

[下载 Xcode 14 Beta 版](https://developer.apple.com/xcode/ "Xcode 14 Beta")

## 提案

//TODO
内容待完善

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
