## 前言

**本期是 Swift 编辑组自主整理周报的第十期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

十期磨一剑，废铁亦有形，**Swift社区**就是你梦想已久的香格里拉，哪怕青冥长天，纵然绿水波澜！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果汽车计划 2026 年推出，大降级！苹果汽车售价或低于 10 万美元，不支持完全自动驾驶
> 
> 提案：Swift 选择加入 `Reflection` 元数据
> 
> Swift 论坛：使用较新的 macOS 版本生成 `Package.swift` 文件
>
> 推荐博文：用 ChatGPT 写 SwiftUI
> 
> **话题讨论：** 
> 
> 你如何看待各地疫情管控放开

## 新闻和社区

### 12 月 12 日，参与新一周的 Ask Apple 活动

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/019C1E1E-C787-48F6-A858-12BFD1B7C326/2048.jpeg)

欢迎继续参与新一周激动人心的 Ask Apple，与 Apple 专家直接交流沟通，获取关于最新技术和设计问题的解答；或者只是随意听听，从对话中学习。针对如何使用最新的框架、改善 App 的 UI 设计、使用 Beta 版 OS 软件和工具进行开发等主题大胆提问。

活动将于 12 月 12 日至 16 日举行，届时将提供多种语言和多个时区的在线一对一咨询和小组 Q&A。现已面向 Apple Developer Program 和 Apple Developer Enterprise Program 的当前成员开放注册。

### 苹果汽车计划 2026 年推出，大降级！苹果汽车售价或低于 10 万美元，不支持完全自动驾驶

12 月 6 日，苹果宣布推出 Apple Music Sing 功能，该功能可以让用户通过可调节的人声和实时歌词演唱自己喜欢的歌曲。此外据彭博社报道，苹果已经缩减了其汽车项目，计划在 2026 年之前推出定价在 10 万美元以下的汽车。苹果不再计划发布完全自动驾驶的汽车，其原来想制造一辆没有方向盘和油门的自动驾驶汽车，现在已经放弃。

### Apple 宣布 App Store 定价机制最重大升级，新增 700 个价格点

Apple 今日宣布对 App Store 进行问世至今最全面的定价机制升级，为开发者提供新增的 700 个价格点和全新定价工具，让开发者更轻松地针对不同国家和地区的 App Store 设定价格、管理外币汇率变化等。

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/E73B40B4-60FF-476B-9B85-D4A051078351/2048.jpeg)

### 假日将至，请为您的 App 做好准备

App Store 最繁忙的季节即将到来！确保及时更新您的 App 和产品页面，并在岁末假日到来之前做好准备。很高兴今年的整个假日季期间同样会开放 App 提交，我们非常期待看到您提交的 App。平均而言，90% 的提交内容会在 24 小时内得到审核。但请注意，在 12 月 23 日至 27 日，完成审核所需的时间可能略长一些。外国的圣诞节就相当于中国的春节，所以 12 月 23 日至 27 日就相当于中国的春节放假哟。

## 提案

### 正在审查的提案

[SE-0379](https://github.com/apple/swift-evolution/blob/main/proposals/0379-opt-in-reflection-metadata.md "SE-0379") **Swift 选择加入 Reflection 元数据** 提案正在审查。

该提案旨在通过改进现有机制，并提供机会在使用 Swift Reflection 元数据的 API 中表达对反射元数据的要求，从而提高 Swift Reflection 元数据的安全性、效率和保密性。

**Swift-evolution 线程**：[该提案的讨论主题](https://forums.swift.org/t/pitch-3-opt-in-reflection-metadata/58852 "该提案的讨论主题")。感兴趣的小伙伴可以参与讨论交流。

[SE-0380](https://github.com/apple/swift-evolution/blob/main/proposals/0380-if-switch-expressions.md "SE-0380") **if 和 switch 表达式** 提案正在审查。

本提案介绍了使用 `if` 和 `switch` 语句作为表达式的功能，主要内容包含：

* 函数、属性和闭包的返回值
* 为变量赋值
* 声明变量

## Swift论坛

1)讨论 [Comparable 下 == 的危险默认实现](https://forums.swift.org/t/dangerous-default-implementation-of-under-comparable/61928 "Comparable 下 == 的危险默认实现")

2)提议[Mach Port API](https://forums.swift.org/t/mach-port-api/61930 "Mach Port API")

**简介:** Mach Port API 是一种难以安全使用的神秘技术。
但是，作为我们操作系统的一个组成部分，它们有时需要处理。

该提案广泛使用了mach port术语。
如果您想复习基础知识，[请查看端口、端口权限、端口集和端口命名空间](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Mach/Mach.html#//apple_ref/doc/uid/TP30000905-CH209-TPXREF104)。

**动机:** Mach ports 很难正确设置，主要是由于管理 mach port 权限的方式。 程序员需要在头脑中跟踪类型、生命周期和其他状态。

Swift 的高级类型系统，最近增加了 [move-only types](https://github.com/apple/swift-evolution/blob/main/proposals/0366-move-function.md)，提供了一个新的机会来创建一个能够在编译时防止整个类错误的 Mach port 接口。

**建议的解决方案:**
建立不同的类型来表示接收、发送和发送一次的权利。
提供 Mach port权限的自动生命周期管理，这与普通的 OOP 对象不同。

3)议案 [Noncopyable (或者 “move-only”) 结构和枚举](https://forums.swift.org/t/pitch-noncopyable-or-move-only-structs-and-enums/61903 "Noncopyable (或者 “move-only”) 结构和枚举")

4)议案 [@globalConstructor](https://forums.swift.org/t/pitch-globalconstructor/61901 "@globalConstructor")

**简介:** `@globalConstructor` 属性提供了一种在启动可执行文件或加载动态库时自动调用函数的方法。

**动机:** 在许多用例中，您可能想要执行代码而不必直接调用它。

**例如：**
在您希望将库插入应用程序的位置进行调试，而无需手动调用库重建应用程序
包含可选库的插件系统将自己注册到主应用程序以更改行为
希望在启动时进行 1 次设置而不要求开发人员显式调用其配置的第三方库作者
如今，在这些情况下，开发人员不得不回退到 Objective-C/C++/C（使用 __attribute__((constructor)))，即使他们只需要调用一个 Swift 函数。

**建议的解决方案:**

添加一个新的 `@globalConstructor` 属性，该属性可以添加到顶级函数，以便在启动可执行文件或加载包含该函数的动态库时自动调用它们。

5)讨论[SE-0380：if 和 switch 表达式](https://forums.swift.org/t/se-0380-if-and-switch-expressions/61899 "SE-0380：if 和 switch 表达式")

6)议案[使用较新的 macOS 版本生成 Package.swift 文件](https://forums.swift.org/t/pitch-generate-package-swift-files-with-newer-macos-versions/61925 "使用较新的 macOS 版本生成 Package.swift 文件")

**简介:** 目前，没有明确定义支持的最低平台版本的 Swift Package Manager 包会自动默认为第一个支持的版本，对于许多平台来说，这是 2017 年的版本。这在某些情况下会增加新生成的包的摩擦。

**动机:** 当前，在 macOS 上构建全新的 Swift Package Manager 包时，构建目标是 2017 年的 macOS 10.13。当他们添加诸如 swift-syntax 之类的具有更高最低支持版本的依赖项时，这可能是一种令人沮丧的新用户体验，导致他们必须立即弄清楚如何配置此选项。

**建议的解决方案:**

我建议我们自动将 macOS 上生成的新包的最低支持版本添加到用户当前的 macOS 版本中。 例如，不是生成这个 Package.swift 内容：

```Swift
let package = Package(
    name: "name",
    ...
)
```

目前在 macOS 上我们将生成以下内容：

```Swift
let package = Package(
    name: "name",
    platforms: [.macOS("13.0")],
    ...
)
```

7)讨论 [“withUnsafeBytes”已弃用](https://forums.swift.org/t/withunsafebytes-is-deprecated/61891 "“withUnsafeBytes”已弃用")

8)讨论 [Linux 上标准库的自动编译是否损坏？](https://forums.swift.org/t/is-auto-compilation-of-the-standard-library-on-linux-broken/61918 "Linux 上标准库的自动编译是否损坏")

9)讨论 [Read/modify, yield, 和 non-escaping closures](https://forums.swift.org/t/read-modify-yield-and-non-escaping-closures/61902 "Read/modify, yield, 和 non-escaping closures")

10)议案 [Swift 中的 Objective-C 实现](https://forums.swift.org/t/pitch-objective-c-implementations-in-swift/61907 "Swift 中的 Objective-C 实现")
我们提出了 `@objc` 类的替代方案，其中 `Objective-C` 标头 `@interface` 声明由 Swift 扩展实现。 生成的类将在 Swift 中实现，但与 Objective-C 类没有区别，完全支持 ObjC 子类化和运行时技巧。
使用 `@objcImplementation`，您可以像编写 Objective-C 类一样手写头文件，但不是在 Objective-C 中实现方法和属性，而是在 Swift 中实现它们。

## 推荐博文

[ChatGPT 注册攻略](https://zhuanlan.zhihu.com/p/589572374 "ChatGPT 注册攻略")

**摘要：** Chat GPT 由人工智能公司 Open AI 于近日推出，其对自己的定义是（优化对话的语言模型）非常火爆，近期不断有研究者发布与 Chat GPT 对话的内容，但其不支持中国大陆用户的注册，把一众想尝试进去玩一玩的人拒之门外。这里为大家提供一种注册方式。核心内容在使用国外手机号获取验证码。
  
[使用 OpenAI 的 ChatGPT 写 SwiftUI 代码](https://www.createwithswift.com/prototyping-swiftui-interfaces-with-openais-chatgpt/ "Prototyping SwiftUI interfaces with OpenAI's ChatGPT")

**摘要：** 上面介绍了如何注册 ChatGPT，本篇文章介绍如何使用 ChatGPT 写 SwiftUI 代码。你觉得 ChatGPT 以后能代替基础人工吗？

[SwiftUI 布局协议 - Part 1](https://mp.weixin.qq.com/s/SfqdGs8TbEjxISgrsy_yIg)

**摘要：** 今年 SwiftUI 新增最好的功能之一必须是布局协议。它不但让我们参与到布局过程中，而且也给了我们一个很好的机会去更好的理解布局在 SwiftUI 中的作用。

## 话题讨论

**你如何看待各地疫情管控放开**

123

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
