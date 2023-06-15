## 前言

**本期是 Swift 编辑组自主整理周报的第二十一期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

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

[ Swift OpenAPI Generator 的介绍](https://www.swift.org/blog/introducing-swift-openapi-generator/ " Swift OpenAPI Generator 的介绍")

**摘要：** Swift OpenAPI Generator是一个 SwiftPM 插件，它可以生成客户端代码或服务器端代码，以便处理 HTTP 调用。 OpenAPI 是一种用于记录HTTP服务的规范，可以使用YAML或JSON编写，并可被工具读取，以帮助自动化工作流程，例如生成必要的代码以发送和接收HTTP请求。Swift OpenAPI Generator 可以帮助我们通过 OpenAPI 文档描述HTTP请求和响应的结构，包括 HTTP 方法、 URL 路径和查询参数、HTTP状态码和内容类型，使用 JSON Schema 描述响应体的结构，使得我们能够在开发应用程序时生成网络代码，而不需要手动编写和维护网络代码，专注于核心业务逻辑。要使用 Swift OpenAPI Generator 插件，需要添加 SwiftPM 依赖项以及运行时库和传输实现，然后使用生成的API客户端或服务器端存根。 Swift OpenAPI Generator 支持大多数常用特性，但仍有一些特性需要实现，项目跟踪进展情况可以使用 GitHub issues 

[ Swift 宏：使用新的表达方式扩展 Swift](https://www.avanderlee.com/swift/macros/ " Swift 宏：使用新的表达方式扩展 Swift")

**摘要：**  Swift 宏是在 Swift 5.9发布的一项新功能，它允许你通过自定义编译时检查和生成新的代码，在编译时将它们写入到你的文件中，从而消除冗余的样板代码。本文讲解了宏的工作原理、如何编写自定义宏以及如何进行测试，以验证一个允许在编译时验证 URL 并在 URL 有效时返回解包值的宏的例子。本文还讨论了宏的不同角色，包括独立和附加宏，并解释了为什么你可能考虑在代码中使用宏。

[在 Swift 服务器端 Vapor 和客户端应用之间共享 Swift 代码](https://www.avanderlee.com/swift/share-swift-code-swift-on-server-vapor/ "在 Swift 服务器端 Vapor 和客户端应用之间共享 Swift 代码")

**摘要：** 这篇博客讨论了在客户端应用和后端服务器之间共享 Swift 代码的好处以及如何通过 Swift 包和 Vapor 实现这一目标。通过共享模型和端点定义，您可以确保两个侧面都使用相同的层，避免出现意料之外的请求失败。博客提供了定义软件包结构、暴露模型、共享端点定义和在后端软件包中配置端点的代码示例。此外，它提供了一个通用方法，用于请求端点并在客户端应用中使用它们。作者还提到了优化适用于所有支持的 HTTP 方法的代码的重要性。

## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
