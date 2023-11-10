## 前言

**本期是 Swift 编辑组整理周报的第四十一期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

生活的富足并非完美无缺，适当的缺憾更能感触幸福。**Swift社区**邀你一起，保持积极向上的心！👊👊👊

> **周报精选**
>
> 新闻和社区：
> 
> 提案：
> 
> Swift 论坛：
>
> 推荐博文：

> **话题讨论：** 
> 
> 

**上期话题结果**



## 新闻和社区

### 2024 年 Swift Student Challenge 公布

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/5D41BDFB-09E7-4A11-8376-C037FBF3DCF3/2048.jpeg)

Apple 很自豪能够支持和激励下一代学生开发者、创作者和企业家。挑战赛为数以千计的学生提供了机会，让他们可以展现自身的创造力和编程能力，并培养可以在职业生涯和更多地方运用的实际技能。从帮助同伴找到合适的心理健康资源，到发现在校园内支持可持续发展工作的方式，Swift Student Challenge 参赛者将发挥他们的创造力，通过开发 App 来解决他们关注的问题。

我们发布了新的编程资源、与社区合作伙伴积极合作，而且比往年更早公布了挑战赛，以便学生们能深入研究 Swift 和整个开发过程，同时教育工作者也能抢先一步为他们提供支持。

申请将在 2024 年 2 月开放三周。

2024 年挑战赛新增了一项机制，我们将在 350 名获奖者中选出 50 名杰出获奖者，并对这些提交了优秀作品的杰出获奖者予以表彰，邀请他们明年夏天前往位于库比提诺的 Apple 园区度过难忘的三天。

### 现推出超过 30 个新的开发者活动

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/E37E35FD-D28B-4204-8107-425410EF41F5/2048.jpeg)

2023 年 11 月 7 日

准备好提升你的 App 或游戏功能了吗？在整个 11 月和 12 月，欢迎参加面向全球开发者量身打造的一系列面对面或在线举办的全新实验室、咨询和讲座等活动。

你将能探索：

App Store 活动：了解关于探索、互动、App 内活动、自定产品页面、订阅推荐做法等众多精彩内容。
Apple Vision Pro 开发者实验室：申请参加位于库比提诺、伦敦、慕尼黑、纽约、上海、新加坡、悉尼或东京的实验室。
Apple Vision Pro 活动：了解如何为 visionOS 设计和构建全新的 App 和游戏世界。
设计和技术咨询：报名获取关于 App 设计、技术实施等方面的一对一指导。
探索在多个时区以多种语言进行的活动。

## 提案


## Swift论坛

## 话题讨论

## 推荐博文

[ Swift 中的崩溃回溯](https://www.swift.org/blog/swift-5.9-backtraces/ " Swift 中的崩溃回溯")

**摘要：**  这篇博客讨论了 Swift 5.9 版本中所包含的一些新的调试代码功能，一个能在实时检查崩溃的外部互动性极强的崩溃处理器，一个可以触发调试器进行即时调试的功能，以及一个可以提升理解在一个使用结构化并发的程序中的控制流程的并发意识后退功能。
在 Swift 5.9 版本之前，一旦你的程序运行失败，你只能看到来自父进程（通常是 shell ）的消息告诉你子进程崩溃了。而现在，你得到的信息将会更具有详细性。
作者还提出了一个名为"交互式后退"的概念。在许多情况下，你可能会发现你在终端开发的程序崩溃了，但你无法复现问题。没有适当的崩溃日志，这可能会让你非常沮丧，你知道你的程序有一个 bug ，但你不知道问题出在哪里，也不知道如何复现它。这个特性的主要思想就是在程序崩溃后将其挂起，从而给你机会附加一个调试器，或对崩溃过程进行更深入的查看。
最后，后退功能支持结构化并发，并且能够正确地逆向穿过异步框架。无论你在哪个平台上，这个新功能都无需特殊要求，只需要回退追踪器能够查找到符号以确定给定框架是否是异步的。

[掌握 SwiftUI 中的 ContentUnavailableView ](https://swiftwithmajid.com/2023/10/31/mastering-contentunavailableview-in-swiftui/ "掌握 SwiftUI 中的 ContentUnavailableView ")

**摘要：**  这篇博客介绍了如何在 SwiftUI中 掌握使用 ContentUnavailableView 类型。 ContentUnavailableView 类型允许我们在应用中表现空状态、错误状态或其他任何内容不可用的状态。文章通过实例演示了ContentUnavailableView 的基本用法以及如何在其中定义描述文本和操作按钮。还介绍了 SwiftUI 为我们提供的一种预制的 ContentUnavailableView 实例，可在搜索屏幕中使用。总的来说，我们学会了如何利用 ContentUnavailableView 以用户友好的方式显示空状态。

[ SwiftUI 中的 visual effects ](https://swiftwithmajid.com/2023/11/07/visual-effects-in-swiftui/ " SwiftUI 中的 visual effects ")

**摘要：** 这篇博客介绍了 SwiftUI 在 WWDC2023 中引入的一种叫做 visualEffect 的新视图修饰符。 visualEffect 允许我们通过访问特定视图的布局信息来附加一组可动画的视觉效果。
通过上述示例，我们可以看到定义了一个文本视图并附加了 visualEffect 视图修饰符。attach visualEffect 视图修饰符时，你需要指定闭包以应用所需的所有效果。闭包提供了两个参数：第一个参数是附加到视图的效果集合的初始状态，是 EmptyVisualEffect 类型的实例；第二个参数是 GeometryProxy 类型的实例，包含可能需要的视图所有布局信息，比如框架、安全区等。现在，所有这些视觉效果都遵循 VisualEffect 协议，可以在 visualEffect 闭包中使用它们。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
