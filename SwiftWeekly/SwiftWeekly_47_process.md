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
1) 提议[SerialExecutor 的自定义隔离检查](https://forums.swift.org/t/pitch-custom-isolation-checking-for-serialexecutor/69786 "SerialExecutor 的自定义隔离检查")
**内容大概**
该提案建议通过为 SerialExecutor 引入自定义隔离检查来改进 Swift Concurrency 中的动态隔离检查。 该提案解决了由于同步、非隔离函数中缺乏静态信息而导致当前动态隔离断言失败的情况。 其动机通过一个示例来说明，其中参与者直接使用自定义执行器，从而导致错误的参与者执行器假设。 该提案旨在允许检查通过并恢复隔离信息，即使 Swift 并发运行时无法证明但目标执行器可以证明这一点。 该提案包括简介、动机、提出的解决方案、详细设计、扩展执行器比较机制、对异步代码的影响、未来方向、考虑的替代方案和修订。 完整的提案可以在这里找到。连接：https://github.com/ktoso/swift-evolution/blob/wip-executor-checkIsolated/proposals/NNNN-custom-isolation-checking-for-serialexecutor.md#proposed-solution

2) 讨论[从本地 HTML 文件创建属性字符串](https://forums.swift.org/t/creating-an-attributed-string-from-a-local-html-file/69753/1 "从本地 HTML 文件创建属性字符串")
**内容大概**
用户尝试在 Mac 应用程序的临时目录中显示来自 HTML 文件和 CSS 文件的属性字符串。 他们已使用所提供文章中的代码成功创建了临时目录，并确认已创建具有预期内容的 HTML 文件。

但是，当尝试使用以 URL 作为参数的 NSAttributedString 初始值设定项从 HTML 文件创建 NSAttributedString 时，会遇到代码 65806 的错误，并且控制台消息为“(null)”。 尽管 Google 搜索没有产生与此错误代码相关的结果，但用户尝试了另一种方法，即使用 String 结构的 write 方法将文本写入 URL。 不幸的是，这也会导致相同的 65806 错误代码。

此外，用户尝试使用 NSAttributedString 类方法 loadFromHTML 创建属性字符串，但此方法返回 Void 而不是属性字符串。

用户寻求有关如何从本地 HTML 文件成功创建属性字符串并解决神秘的 65806 错误的指导。

3) 讨论[每次外部状态更新时，Reducer 状态都会重新计算，即使使用 @ObservableState](https://forums.swift.org/t/reducer-state-keeps-recomputing-every-time-an-outside-state-updates-even-with-observablestate/69788 "每次外部状态更新时，Reducer 状态都会重新计算，即使使用 @ObservableState")
**内容大概**
用户在使用可组合架构 (TCA) 构建的 SwiftUI 应用程序中重新计算减速器状态时遇到问题。 具体来说，他们注意到 ShareLinkButtonView 在其自身范围之外发生的每次状态更新时都会消失。 该问题似乎与每次外部状态更新并触发整个视图重新渲染时视图重新计算或重新初始化有关。

ShareLinkButtonView 设计为仅在满足特定条件（ideaSnapshot 非零）时显示按钮。 用户正在 RootStore 中使用 @ObservableState 属性包装器来管理状态，但他们不确定为什么状态会被不必要地重新计算。

用户正在寻求有关如何防止对 RootStore 状态进行不必要的重新计算的指导。 他们在 RootStore.State 结构中使用 @ObservableState 属性包装器，并为 ShareLinkButtonView 和 RootStore 提供了相关代码片段。 这些操作涉及从 Firebase 初始化和检索 IdeaSnapshotModel，所需的行为是仅在成功检索 ideaSnapshot 时显示按钮。

潜在的解决方案可能涉及审查 @ObservableState 的使用，考虑数据流和依赖性，并确保在可组合架构中适当处理状态突变。 检查状态更新如何触发重新渲染以及是否存在影响 ShareLinkButtonView 可见性的任何意外副作用也可能会有所帮助。

4) 讨论[为什么不支持 var myArray: [weak MyClass]](https://forums.swift.org/t/why-not-support-var-myarray-weak-myclass/69764/2 "为什么不支持 var myArray: [weak MyClass]")
**内容大概**
为什么不支持 var myArray: [weak MyClass] - 使用 Swift - Swift 论坛
我认为 [weak MyClass] 不存在的原因是它在释放引用时的行为。 弱变量必须是可选的，因为当引用被释放时它会变成 nil。 无主只是假设它已分配，如果没有分配则崩溃。

在 [weak MyClass] 中，如果其中一个引用被释放，会发生什么？ 它会将自己从数组中删除吗？ 当元素随机失效时，这可能会引起一些混乱。 它会像一个可选的并且变为零吗？ 那么定义 [weak MyClass] 可能不足以清楚地表明它不是 [MyClass] 而是 [MyClass?]。

当然，可能已经有一些方法可以通过属性包装器或其他方式在 swift 中实现弱数组。 然而，要在 swift 中轻松完成此操作的语法可能需要在添加之前进行一些修改。

那么定义 [weak MyClass] 可能不足以清楚地表明它不是 [MyClass] 而是 [MyClass?]。

这个问题本身可以很容易地通过要求使用 [weak MyClass?] 来解决，就像弱属性一样。

虽然我不知道是否还有其他更令人担忧的方面（例如，由于数组的行为类似于值类型，但在底层的堆上进行内存分配和释放而导致不可忽略的性能影响），但我解释这一点的方式 语法会产生歧义：
从字面上理解，这意味着一旦弱实例集合中的某个对象被释放，它就会被替换为 nil。 这就是属性的处理方式。 虽然这可能没问题，但我认为人们通常会认为它已从集合中删除。
这也引发了一个有趣的问题，即有多少人会通过保留 nil 对象的集合来“浪费”内存......:smiley:

当然，这两种选择都是可能的，我的观点是，在我看来，[weak MyClass] 不够精确，不足以成为一种语言功能（就像这样）。 @sveinhal 的示例表明了这一点：弱集合需要有自己的自定义实现，该实现是根据所需的任何具体行为量身定制的。 也许一个提供一些更常见方法来做到这一点的小包会是一个很好的项目？

5) 讨论[来自镜像主题的数组构造函数？](https://forums.swift.org/t/array-constructor-from-mirror-subject/69781 "来自镜像主题的数组构造函数？")
**内容大概**
该提案建议在 Swift 中为数组类型引入一个新的初始值设定项，允许从镜像主题创建它。 该初始化程序专门针对提高元组的可用性，目前这在某些操作方面提出了挑战。

作者发现了使用元组作为固定大小数组的问题，特别是在尝试逐个元素打印其内容时。 虽然元组是表示固定大小数组的常见方法，但由于它们的预期用途是用作临时值，因此将它们视为集合仍存在一些顾虑。 该提案考虑了异构元组的潜在问题，例如迭代和映射的困难。

为了解决这些问题，作者建议允许从镜像主题初始化数组。 它们为数组类型的扩展提供了一个代码片段，该代码片段利用镜像类型来启用此初始化。 概述的好处包括鼓励将元组转换为数组以供长期使用，提供对 Collection 和 Array 方法的访问，改进使用数组而不是元组的函数参数传递，以及限制异构元组的转换。

该提案承认潜在的缺点，例如将结构转换为数组的能力以及是否需要结构到数组转换的一般问题。 总的来说，所提出的初始化程序旨在通过方便地转换为数组来增强使用元组的实用性和多功能性。

6) 讨论[使用 swiftdata 时应用程序崩溃](https://forums.swift.org/t/app-crashing-when-using-swiftdata/69748 "使用 swiftdata 时应用程序崩溃")
**内容大概**
用户在 iPad Pro 上的 Swift Playground 中使用 SwiftData 时遇到应用程序崩溃的情况。 尝试保存类模型时会出现此问题，并且在预览窗口和运行应用程序时都会发生此问题，特别是在输入特定导航链接（时间表）时。 用户为其应用中的不同文件提供了代码片段，包括 MyApp、ContentView、Schedule、UnitConversions、Assignment、AssignmentView 和 AddAssignment。

遇到的错误消息是：“在 ModelContainer.swift 的第 144 行发现致命错误，未能找到当前活动的分配容器。”

用户怀疑该问题可能与 ContentView 中 @Environment(\.modelContext) 的使用以及 ContentView 内 VStack 上 .modelContainer(for:Assignment.self) 的放置有关。 他们寻求帮助来了解可能导致坠机的原因和潜在的解决方案。

建议的修复方法是从 ContentView 中删除 modelContext 并考虑将 .modelContainer（用于：Assignment.self）放在 MyApp 中的 WindowGroup 上，因为应用程序中似乎只使用了一个模型和存储。

6) 讨论[在字符串插值中附加文字](https://forums.swift.org/t/appending-literals-in-string-interpolation/69749 "在字符串插值中附加文字")
**内容大概**
用户正在询问字符串插值中appendLiteral方法的用法和潜在限制。 public mutating funcappendLiteral(_literal:String) 的文档提到它不应该直接调用，并且由编译器在解释字符串插值时使用。

用户在特定情况下希望自定义字符串插值的行为，特别是在本地化字符串的上下文中。 他们提供了一个示例，其中使用可变大小写的字符串插值动态构造本地化字符串键。 当使用变量进行插值时，默认行为会插入 %@ 说明符，这不是所需的结果。

为了克服这个问题，用户建议使用名为 asLiteral 的自定义appendInterpolation 方法来扩展 LocalizedStringKey.StringInterpolation，该方法在内部调用appendLiteral。 此自定义方法允许他们避免 %@ 说明符并构建所需的本地化密钥。 用户担心未来潜在的问题或违反最佳实践的行为。

他们寻求澄清这种方法是否可以接受，或者是否有更好的解决方案可以在不违反任何规则的情况下实现预期结果。

该摘要捕获了用户对appendLiteral 的正确使用以及他们在Swift 中为本地化字符串键自定义字符串插值的具体情况的询问。

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
