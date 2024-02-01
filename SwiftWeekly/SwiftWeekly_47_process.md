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

## 推荐博文

[Swift OpenAPI Generator 1.0 版本发布](https://www.swift.org/blog/swift-openapi-generator-1.0/ "Swift OpenAPI Generator 1.0 版本发布")

**摘要：**  Swift OpenAPI Generator 是一个用于生成类型安全、符合惯例的 Swift 代码的工具，根据 OpenAPI 文档自动生成 API 调用和服务器实现所需的代码。支持 OpenAPI 规范版本 3.0 和 3.1 ，提供更灵活的抽象方式，使开发人员能够以 API 优先的方式进行服务器开发。生成的客户端代码为每个操作提供了一个方法，可与任何提供 Swift OpenAPI Generator 集成包的 HTTP 库一起使用。生成的服务器代码通过 "APIProtocol" 协议定义了每个操作的方法要求，适用于任何提供Swift OpenAPI Generator集成包的Web框架。

[SwiftUI 中的 visionOS ornament](https://swiftwithmajid.com/2024/01/30/visionos-ornaments-in-swiftui/ "SwiftUI 中的 visionOS ornament")

**摘要：**  这篇博客介绍了在 Swift 中使用 SwiftU I构建 visionOS 应用程序的方法，重点介绍了新的 SwiftUI API 中的 ornament 概念。ornament 是一种用于在不干扰窗口内容的情况下呈现与窗口相关的控件和信息的用户界面组件。文章首先展示了如何使用 TabView 创建一个基本的 ornamen t，然后介绍了如何使用 SwiftUI 的 Toolbar API 在 ornament 中添加操作控件。此外，文章还详细讲解了如何创建自定义 ornaments ，包括控制其位置、外观和感觉。最后，总结了如何使用 SwiftUI 框架来改善 visionOS 上应用程序的用户体验。以帮助开发人员更好地适应 visionOS 平台。

[Swift 有些场景其实不必加 final](https://juejin.cn/post/7313242001113677862/ "Swift 有些场景其实不必加 final")

**摘要：**  这篇文章深入探讨了在 Swift 中使用 final 关键字的场景和最佳实践。作者首先介绍了 final 关键字的作用，包括防止类被继承和优化执行性能。文章指出了一些场景下是不必手动添加 final 的，比如私有类/属性和具有默认访问权限（internal）的类。特别是在使用 Whole Module Optimization（WMO）编译模式时，编译器能够自动推断是否需要添加 final。然而，对于公共类，作者强调了需要主动考虑是否添加 final ，特别是当提供库给上层调用时，以确保性能和防止意外继承。文章在最后提到在维护项目时，主动添加 final 可以作为一种强文档的方式，提醒未来的使用者。

## 话题讨论

近日，有网友在社交平台爆料称自己因为隐瞒裁员经历说成是主动离职而被取消了 offer 。在职场中，有些人可能选择将自己被裁员的情况描述为主动离职。把“被裁”说成“主动离职”算撒谎吗? 

1. 算，不诚实
2. 算适度美化而已
3. 不都这么说吗?
4. 不算，很正常

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
