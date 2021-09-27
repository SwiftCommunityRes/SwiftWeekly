
## 前言

本期周报开始，将会引入**推荐博文**模块，主要为大家分享展示优秀的 iOS 技术博文，如果大家阅读到优秀的文章欢迎在文末留言告诉小编，大家资源共享共同进步。

iPhone 13 新品上架，你们都买了吗？苹果声称，iPhone 13 拥有全新的双摄像头系统，采用超快的 `A15` 芯片，提高电池的续航能力。

我们不仅要关注新的 iPhone 13，几天前，`Xcode 13` 与 [Swift 5.5](https://forums.swift.org/t/swift-5-5-released/52247 "Swift 5.5") 也一起发布了。这是 Swift 5.5 更新的[列表](https://twitter.com/simjp/status/1440318174856036354 "列表")，这个版本发布了很多新功能。Xcode 13 的发布说明可以在这里找到：[iOS & iPadOS 15 Release Notes](https://developer.apple.com/documentation/ios-ipados-release-notes/ios-ipados-15-release-notes "iOS & iPadOS 15 Release Notes")。

现在已经开始将**并发**功能向后部署到旧的 Swift 版本上。

> 为了 Swift 社区周报持续稳定的发布更新，我们希望邀请 Swift 爱好者参与**周报编辑**，同时邀请赞助商对我们平台赞助支持。

## 新闻和社区

**Cory Benfield** 告诉我们 [Swift Crypto 2.0.0 已经发布](https://forums.swift.org/t/swift-crypto-2-0-0/52308 "Swift Crypto 2.0.0")。

## 入门任务

**SR-15218**: [Compiler] [增强 CGFloat/Double 之间的可互转，允许 optional 之间的互转](https://bugs.swift.org/browse/SR-15218 "Enhance interchangeable CGFloat/Double to allow interchange between optional")

## Commits 和 pull requests

**salinas-miguel** 的 PR 已合并：[删除了 Swift 项目对 macOS 上的 Foundation 的依赖](https://github.com/apple/swift/pull/39216 "Remove Foundation dependency")。

Doug Gregor 创建了一个 `pull request` [对 Swift 向后部署支持并发](https://github.com/apple/swift/pull/39342 "Back-deployment support for Swift concurrency")。

## 正在审查的提案

**SE-0323**：[Asynchronous Main 语义](https://forums.swift.org/t/se-0323-asynchronous-main-semantics/52022 "Asynchronous Main Semantics") 正在审查中。

程序设置通常发生在 `main` 函数中，开发人员希望在程序的其他部分运行之前执行操作。`Objective-C`、`c++` 和 `C` 都有初始化，这些初始化在 `main` 入口点执行之前运行，并且可以与   Swift 的并发系统交互。在 Swift 并发模型中，开发人员编写的异步 `main` 函数被包装在一个任务中，并在 `main` 入口点运行时被放入到主队列中。如果初始化时在主队列中插入了一个任务，那么该任务可能会在 `main` 函数之前执行，所以设置是在初始化任务运行之后执行的。

**SE-0324**：[对 C 函数的指针参数放宽诊断](https://forums.swift.org/t/se-0324-relax-diagnostics-for-pointer-arguments-to-c-functions/52019 "Relax diagnostics for pointer arguments to C functions")正在审查中。

`C` 有特殊的指针别名规则，例如允许 `char *` 为其他指针类型别名，并允许指向有符号和无符号类型的指针别名。 某些 `C` `API` 的可用性依赖于在这些规则的边界内轻松转换指针的能力。 Swift 通常不允许类型化指针转换。请参阅[SE-0107 UnsafeRawPointer API](https://github.com/apple/swift-evolution/blob/main/proposals/0107-unsaferawpointer.md "UnsafeRawPointer API")。让 Swift 编译器在调用从 `C` 头文件导入的函数时允许在 `C` 规则内进行指针转换将显著提高互操作性，而不会对类型安全产生负面影响。

## Swift 论坛

**Ashley Garland** 介绍一些新实验出来的 [Swift Package Manager 代码段](https://forums.swift.org/t/swift-snippets/51947 "Swift Snippets")。

我们都知道通过示例学习是很棒的，尤其是对于代码。 我想创建最小、最简单的方法来为 `Swift packages` 提供示例代码，我刚刚在 [Swift Package Manager](https://github.com/apple/swift-package-manager/commit/a0ffd92a2c80f2c4677d696e248f4cfbec9d6540 "Swift Package Manager") 中完成了一些正在进行的工作。

**Filip Sakel** 提出了一项[改进 Property-wrapper-related 的初始化](https://forums.swift.org/t/pitch-refining-property-wrapper-related-initialization/52049 "Refining Property wrapper  related Initialization")的提案。

[SE 0258](https://github.com/apple/swift-evolution/blob/master/proposals/0258-property-wrappers.md "SE 0258") 引入了 `property wrappers`，[SE 0293](https://github.com/apple/swift-evolution/blob/main/proposals/0293-extend-property-wrappers-to-function-and-closure-parameters.md#detailed-design "SE 0293") 使用类似函数的声明对其进行了扩展。 今天，`property wrappers` 初始化由于其日益增长的多功能性而表现出不一致。 具体来说，成员初始化使用复杂的、记录不足的规则，并且 `projection` 初始化仍然有限。该提案将简化具有包装属性的类型的合成成员初始化，并扩展 `projection` 值初始化以包括全局、类型和局部包装属性。

**Jordan Rose** 开始讨论[删除 Optional 变量的隐式初始化](https://forums.swift.org/t/pre-pitch-remove-the-implicit-initialization-of-optional-variables/52300 "remove the implicit initialization of Optional variables")。

在 Swift 6 中，可选变量与所有其他变量一样，默认情况下不会初始化。 局部变量和全局变量得到修复，添加 `= nil`。 属性仅在附加到有关未初始化变量的错误的注释中修复，这显然不是正确的做法，只有 Swift 5 中需要这么做。 不过，迁移者也可以自动应用该修复程序。

## 推荐博文

### iOS 系列

[如何在 Swift 中实现状态机？](https://mp.weixin.qq.com/s/vkbN_d3tR_Ym_gJYBVGCOw)

简言之：我们通常称作的状态机是有限状态机的简称，它是一种**数学计算模型**。

[避免 Swift 单元测试中的强制解析](https://mp.weixin.qq.com/s/DawFZMOuU5jbaw0Bi0gOhw)

强制解析（使用 `!`）是 Swift 语言中不可或缺的一个重要特点（特别是和 Objective-C 的接口混合使用时）。它回避了一些其他问题，使得 Swift 语言变得更加优秀。

[iOS 识别虚拟定位调研](https://mp.weixin.qq.com/s/ZbZ4pFzzyfrQifmLewrxsw)

最近业务开发中，有遇到我们的项目 app 定位被篡改的情况，在 android 端表现的尤为明显。为了防止这种黑产使用虚拟定位薅羊毛，iOS 也不得不进行虚拟定位的规避。

### 实时文讯

[Xcode 13 更新了哪些内容](https://mp.weixin.qq.com/s/DwClglO_fOYDfLsINU_hdw)

[开发者需要了解的 iOS 15](https://mp.weixin.qq.com/s/E5vTD9QDgKfVErWxCv4wjg)

[Xcode 13 正式版发布，来看看有什么新特性](https://mp.weixin.qq.com/s/4OGxPn-dgDc-jjtM-DtqGQ)


### SwiftUI 系列

[为什么 SwiftUI 的修饰符顺序很重要](https://mp.weixin.qq.com/s/K_i8bvcaHDfVMUsQTv3MOw)

每当我们将修饰符应用于 `SwiftUI` 视图时，我们实际上都会创建一个，应用了更改的新视图 —— 我们不仅仅是修改现有的视图。

[为什么 SwiftUI 的视图使用结构体](https://mp.weixin.qq.com/s/gSeFOMrjze6KE_X6WwWAZQ)

如果您曾经为 `UIKit` 或 `AppKit`（Apple 的 iOS 和 macOS 原始用户界面框架）编程，您会知道它们使用类而非结构体来构造视图。`SwiftUI` 更喜欢将结构体用于整体视图。

[如何结合 Core Data 和 SwiftUI](https://mp.weixin.qq.com/s/ZQSbu7dzwC-XbGcUcBkjAw)

`SwiftUI` 和 `Core Data` 之间相差将近十年。尽管时间相距遥远，Apple 还是投入了大量工作以确保这两种强大的技术能够完美地相互配合使用，这意味着 `Core Data` 就像始终以这种方式设计一样，已集成到 SwiftUI 中。


## 关于我们

公众号是由 Swift 爱好者共同维护，我们会分享以 Swift 实战、SwiftUI、Swift 基础为核心的技术内容，也整理收集优秀的学习资料。欢迎关注公众号：**Swift社区**，后台点击进群，联系我们获取更多内容。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">


感谢 SwiftWeekly 与我们的合作，开启 Swift 周报中文版发布之旅。周报仓库：https://github.com/SwiftCommunityRes

后续还会翻译大量资料到我们公众号，有感兴趣的朋友，可以加入我们，扫码添加微信

<img width="300" alt="fzhanfei" src="https://files.mdnice.com/user/17787/9a7911bf-75f2-40f5-866b-3171868bb92c.jpg">
