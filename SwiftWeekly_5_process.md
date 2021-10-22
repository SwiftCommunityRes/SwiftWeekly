
## 前言

> 为了 Swift 社区周报持续稳定的发布更新，我们希望邀请 Swift 爱好者参与**周报编辑**，同时邀请赞助商对我们平台赞助支持。

## 入门任务
**SR-15312** [Swift-DocC] [添加 “version” 命令到 docc 命令行工具中](https://bugs.swift.org/browse/SR-15312 "Add 'version' command to docc command line tool") 

**SR-15312** [Swift-DocC] [当浏览器 URL 不是小写时，主教程导航下拉菜单无法将当前教程字体加粗](https://bugs.swift.org/browse/SR-15313 "Primary tutorial navigation dropdown fails to bold the current tutorial when browser URL is not lowercased") 

## 新闻和社区
**Franklin Schrans** 宣布 [Swift-DocC](https://swift.org/blog/swift-docc/) 将要[开源](https://github.com/apple/swift-docc).

**Marin Todorov** 终于[披露](https://twitter.com/icanzilb/status/1448555769050304512)了他关于 [`Swift Markdown`](https://github.com/apple/swift-markdown) 的工作.

**Federico Zanetello** 写了一篇[文章](https://www.fivestars.blog/articles/warn_unqualified_access/ "warn_unqualified_access")来说明 `@warn_unqualified_access` 的使用.

**Dave DeLong** 解释了如何[简化 Swift 中的向后兼容性](https://davedelong.com/blog/2021/10/09/simplifying-backwards-compatibility-in-swift/ "Simplifying Backwards Compatibility in Swift")。

`Swift-DocC` 的文档现在已经发布在 [Swift.org](https://swift.org/documentation/docc/) (使用 [Swift-DocC!](https://forums.swift.org/t/documentation-for-swift-docc-is-now-on-swift-org/52914)).


## 正在审查的提案
**SE-0325** [附加包插件 API](https://github.com/apple/swift-evolution/blob/main/proposals/0325-swiftpm-additional-plugin-apis.md "Additional Package Plugin APIs") 正在[审查中](https://forums.swift.org/t/se-0325-additional-package-plugin-apis/52788)。

**SE-0303** 在 SwiftPM 中引入了定义构建工具插件的能力, 允许自定义工具在构建打包时被调用。为了支持该特性， **SE-0303** 引入了最小初始 API，插件能够通过该接口获取那些被唤起构建的 Target 的相关信息。

该提案扩展了插件 API 以提供更多上下文，包括更丰富的包图表示。 这是为将来支持新类型的插件做准备。

## Swift 论坛



## 推荐博文

### iOS 系列

[百度一面总结（含答案）](https://mp.weixin.qq.com/s/ZprPxK8NbMqpP9flmWRagg)

[使用 Swift 实现 Promise](https://mp.weixin.qq.com/s/PYzQN5HYXLU1JuXBAZNyhQ)

我最近在找如何使用 Swift 实现 `Promise` 的资料，因为没找到好的文章，所以我想自己写一篇。通过本文，我们将实现自己的 `Promise` 类型，以便明了其背后的逻辑。

[用 Swift 实现轻量的属性监听系统](https://mp.weixin.qq.com/s/8_utYi3y7I3ukh4VpnIM3A)

本文的主要目的是解决客户端开发中对“模型的一处修改，UI 要多处更新”的问题。当然，我们要知晓解决方案的细节和思考过程，以及看到其能达到的效果。我们会用到函数式编程的思想，以及伟大的“泛型”。


### SwiftUI 系列

[用 SwiftUI 实现 3D Scroll 效果](https://mp.weixin.qq.com/s/hfe1m5bNiA0DzdFTEvi9sQ)

学完本教程后，你就可以在你的 App 中把这种 `3D` 效果加入任何自定义的 SwiftUI 视图。

[如何让 SwiftUI 的列表变得更加灵活](https://mp.weixin.qq.com/s/TD0I96HSUoTNmOmfySCtYQ)

`List` 可能是 `SwiftUI` 附带的内置视图中最常用的一种，它使我们能够在任何 `Apple` 平台上呈现“类似于表格视图”的用户界面。今年，`List` 获得了许多非常重要的升级，使其更加灵活和易于定制。让我们看看都有哪些新功能。

[使用 SwiftUI 创建万花尺](https://mp.weixin.qq.com/s/snJJi9KYViFErdJAP1HEPQ)

为了完成一些真正意义上的绘图工作，我将带您通过创建一个简单的带 SwiftUI 的 `spirograph`。“Spirograph”是一种玩具的商标名称，你把一支铅笔放在一个圆圈里，然后绕着另一个圆圈的圆周旋转，创造出各种几何图案，称为轮盘赌——就像赌场游戏一样。

## 关于我们

公众号是由 Swift 爱好者共同维护，我们会分享以 Swift 实战、SwiftUI、Swift 基础为核心的技术内容，也整理收集优秀的学习资料。欢迎关注公众号：**Swift社区**，后台点击进群，联系我们获取更多内容。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">


感谢 SwiftWeekly 与我们的合作，开启 Swift 周报中文版发布之旅。周报仓库：https://github.com/SwiftCommunityRes

后续还会翻译大量资料到我们公众号，有感兴趣的朋友，可以加入我们，扫码添加微信

<img width="300" alt="fzhanfei" src="https://files.mdnice.com/user/17787/9a7911bf-75f2-40f5-866b-3171868bb92c.jpg">
