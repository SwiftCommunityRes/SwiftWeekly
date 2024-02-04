## 前言

**本期是 Swift 编辑组整理周报的第四十七期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

倘若穷途末路，那便势如破竹。**Swift社区**在你心里种花，人生才不会荒芜！👊👊👊

> **周报精选**
>
> 新闻和社区：营收有望再创新高 巴克莱或将惨遭打脸？
> 
> 提案：Swift Backtrace API
> 
> Swift 论坛：讨论为什么不支持 `var myArray: [weak MyClass]`
>
> 推荐博文：Swift 有些场景其实不必加 final
>
> **话题讨论：** 
> 
> 把“被裁”说成“主动离职”算撒谎吗? 
>
>**上期话题结果**

![](https://files.mdnice.com/user/17787/d70a6cc9-7e83-4a59-842a-066702ceb689.jpg)

技术型人才都转行跑滴滴，送外卖，做销售。那么未来的新科技研发何去何从。

## 新闻和社区

### 苹果财报来袭：营收有望再创新高 巴克莱或将惨遭打脸？

鉴于本月初巴克莱、Piper Sandler 和 Redburn Atlantic 接连下调了苹果的股票评级，同时苹果爆料“一哥”郭明预计 iPhone出货量将下降 15% ，此次苹果的财报尤为受到关注。

对于投资者来说，他们不仅希望了解苹果的销售表现，还希望更深入地了解 iPhone 的销售业绩和前景，尤其是在中国的销售业绩。

大中华区营收预计减少

从华尔街分析师们的预期来看，市场仍然多数预计苹果能够在该财季取得强劲表现，并预计 iPhone 销售前景依旧乐观。假如果真如此，可能会开始扭转该公司近期相对疲软的股票表现。

据华尔街分析师预计，苹果第一财季每股盈利为 2.11 美元，营收为 1179 亿美元，都将比去年有所增长——去年同期苹果公布每股盈利为 1.88 美元，营收为 1172 亿美元。

市场调查机构 IDC 和 Canalys 近期分别发布的最新报告称，2023 年苹果成为智能手机全球销量第一，这也是苹果首次超过三星登顶智能手机年度销量冠军。基于 iPhone 去年的强劲表现，华尔街已经有分析师预测，苹果第一财季营收将创下历史新高，。

不过，苹果在大中华区的整体营收预计将从 239 亿美元降至 235 亿美元。大中华区是苹果仅次于北美和欧洲的第三大销售区域。

分析人士表示，华为高端智能手机带来竞争压力，以及中国市场需求走软，正在削弱苹果在该地区的销售前景。

iPhone 营收依旧乐观

分部门来看，华尔街预计苹果 iPhone 的营收将达到 686 亿美元，较去年同期的 657.8 亿美元有所上升。

苹果的 Mac 收入可能也将略有回升，分析师预计该季度销售额为 79 亿美元，而去年同期为 77 亿美元。

但分析师预计苹果 iPad 的营收将从去年的 94 亿美元下降逾 20 亿美元，至 70.6 亿美元。有分析称，鉴于苹果将在 3 月份推出新款 ipad 和 mac 电脑，这可能有助于提高这两个业务部门在未来一年的销量。

可穿戴设备、家居和配件本季度将带来 120 亿美元的收入，预计低于去年第一季度的 135 亿美元。这主要是由于去年末苹果公司与医疗设备制造商 Masimo 进行但专利战，迫使苹果公司暂时将这款设备下架。在那之后，虽然苹果已经从其 Series 9和Ultra 2 手表中删除了引发争议的血氧传感器组件，但目前尚不清楚这对销售有多大影响。

与此同时，苹果服务部门的销售额预计将从 208 亿美元增至 234 亿美元。

### Apple 为在全球范围内提供迷你 App 和游戏访问的流媒体游戏服务和 App 发布新选项

2024 年 1 月 25 日

三月份将上线新的分析报告，供全球范围内的开发者使用

开发者还可以为其 App 启用新的登录选项

Apple 发布了与 App 向用户提供 App 内体验的方式相关的新选项，涉及流媒体游戏和迷你程序。这些新选项适用于全球范围内的 App。开发者现在可以提交单个 App 来流式传输其目录中提供的所有游戏。

App 还将能够为其中的流媒体游戏、迷你 App、迷你游戏、聊天机器人和插件提升曝光率。

此外，迷你 App、迷你游戏、聊天机器人和插件将能够接入 Apple 的 App 内购买系统，从此即可向用户提供付费数字内容或服务，例如单个聊天机器人的订阅。

App Store 上的 App 中提供的每项体验都必须遵守《App Store 审核指南》中的所有适用准则，而托管 App 的年龄分级将取决于该 App 中包含的最高年龄分级内容。

Apple 宣布的这些变化反映了 Apple 开发者社区的反馈，并践行了 App Store 的使命 — 即为用户提供一个值得信赖的平台来探索喜爱的 App 并助力全球开发者发展自己的业务。托管此内容的 App 有责任确保其中包含的所有软件符合 Apple 在用户体验和安全性上的高标准。

新的 App 分析报告
Apple 为开发者提供了强大的面板和报告，帮助他们通过“App 分析”、“销售和趋势”以及“支付和财务”报告来衡量 App 的表现。Apple 将为全球范围内的开发者上线新的分析报告，以帮助他们更深入地了解自己的业务和 App 的表现，这些新的报告将继续保持 Apple 的长期承诺，确保用户的个人身份无法被识别。

Apple 将通过 App Store Connect API 提供 50 多个新报告，其中包含以下方面的更多指标，以帮助开发者分析 App 的表现和发现优化机会：

参与度 — 增加了 App Store 上与开发者的 App 互动或将 App 分享给其他人的用户数量的信息；

商务 — 增加了下载次数、销售额、收入、预购量以及使用 App Store 的安全 App 内购买系统完成的交易数量的信息；

App 使用 — 增加了崩溃次数、活跃设备数、安装次数、App 删除次数等的信息。

框架使用 — 增加了 App 与操作系统功能 (例如 PhotoPicker、小组件和 CarPlay 车载) 交互的信息。

我们将于 3 月份向开发者提供有关报告详情和访问权限的更多信息。

开发者将能够通过 API 方便地向第三方授予其报告的访问权限。

App 中的登录选项更加灵活
Apple 正在更新其《App Store 审核指南》中关于使用“通过 Apple 登录”的内容，以践行 Apple 保护用户隐私的使命。“通过 Apple 登录”让用户能够使用其 Apple ID 轻松登录 App 和网站，此功能从设计之初就以隐私保护和安全性为重。从今天开始，在 App 中提供第三方或社交登录服务的开发者将可以选择提供“通过 Apple 登录”，或提供同等注重隐私保护的其他登录服务。

### Swift Student Challenge 将于 2 月 5 日开放申请

2024 年 1 月 23 日

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/5D41BDFB-09E7-4A11-8376-C037FBF3DCF3/2048.jpeg)

2024 年 Swift Student Challenge 将于 2 月 5 日开放申请，我们非常期待。

正在寻找灵感？ 了解挑战赛的往届获奖者，深入了解他们打造 App 的动力。

刚刚上手？ 获取工具、提示和指导，了解创建出色 App Playground 所需的一切。

## 提案

### 通过的提案

[SE-0417](https://github.com/apple/swift-evolution/blob/main/proposals/0417-task-executor-preference.md "SE-0417") **任务执行器偏好** 提案通过审查。该提案已在 **四十四期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0422](https://github.com/apple/swift-evolution/blob/main/proposals/0422-caller-side-default-argument-macro-expression.md "SE-0422") **表达式宏作为调用方默认参数** 提案正在审查。

该提案旨在取消之前在 [SE-0382 表达式宏](https://github.com/apple/swift-evolution/blob/main/proposals/0382-expression-macros.md "SE-0382 表达式宏")中设定的限制，以允许非内置表达式宏作为调用方默认参数表达式。
>SE-0382 表达式宏提案在24期周报中做了详细介绍。

[SE-0421](https://github.com/apple/swift-evolution/blob/main/proposals/0421-generalize-async-sequence.md "SE-0421") **推广 AsyncSequence 和 AsyncIteratorProtocol 的效果多态性** 提案正在审查。

该提案在两个方面推广了 `AsyncSequence`：

1. 通过采用类型化的 throws 实现了适当的 throws 多态性。
2. `AsyncIteratorProtocol` 上 `next` 要求的新重载包括一个隔离参数，以抽象化 `actor` 的隔离。

[SE-0420](https://github.com/apple/swift-evolution/blob/main/proposals/0420-inheritance-of-actor-isolation.md "SE-0420") **继承 actor 隔离性** 提案正在审查。

在 Swift 的 actor 设计下，Swift 中的每个函数都具有 actor 隔离性：它要么是隔离到某个特定的 actor，要么是非隔离的。有时候，将函数赋予与其调用方相同的 actor 隔离性是有用的，这样可以让函数访问 actor 隔离的数据，或者仅仅是为了避免不必要的暂停。该提案允许异步函数选择使用这种行为。

[SE-0419](https://github.com/apple/swift-evolution/blob/main/proposals/0419-backtrace-api.md "SE-0419") **Swift Backtrace API** 提案正在审查。

今年我们通过向 Swift 添加对回溯的一流支持，来提高 Swift 在命令行和服务器端开发中的可用性。

回溯支持包括两个部分：第一个是实际的回溯实现，第二个是 Swift 标准库中的新 API 界面。该提案涉及到后者。

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

用户怀疑该问题可能与 ContentView 中 @Environment(\.modelContext) 的使用以及 ContentView 内 VStack 上 `.modelContainer(for:Assignment.self)` 的放置有关。 他们寻求帮助来了解可能导致坠机的原因和潜在的解决方案。

建议的修复方法是从 ContentView 中删除 modelContext 并考虑将 .modelContainer（用于：Assignment.self）放在 MyApp 中的 WindowGroup 上，因为应用程序中似乎只使用了一个模型和存储。

6) 讨论[在字符串插值中附加文字](https://forums.swift.org/t/appending-literals-in-string-interpolation/69749 "在字符串插值中附加文字")

**内容大概**

用户正在询问字符串插值中 appendLiteral 方法的用法和潜在限制。 `public mutating funcappendLiteral(_literal:String)` 的文档提到它不应该直接调用，并且由编译器在解释字符串插值时使用。

用户在特定情况下希望自定义字符串插值的行为，特别是在本地化字符串的上下文中。 他们提供了一个示例，其中使用可变大小写的字符串插值动态构造本地化字符串键。 当使用变量进行插值时，默认行为会插入 %@ 说明符，这不是所需的结果。

为了克服这个问题，用户建议使用名为 asLiteral 的自定义 appendInterpolation 方法来扩展 LocalizedStringKey.StringInterpolation，该方法在内部调用appendLiteral。 此自定义方法允许他们避免 %@ 说明符并构建所需的本地化密钥。 用户担心未来潜在的问题或违反最佳实践的行为。

他们寻求澄清这种方法是否可以接受，或者是否有更好的解决方案可以在不违反任何规则的情况下实现预期结果。

该摘要捕获了用户对 appendLiteral 的正确使用以及他们在 Swift 中为本地化字符串键自定义字符串插值的具体情况的询问。

## 推荐博文

[Swift OpenAPI Generator 1.0 版本发布](https://www.swift.org/blog/swift-openapi-generator-1.0/ "Swift OpenAPI Generator 1.0 版本发布")

**摘要：**  Swift OpenAPI Generator 是一个用于生成类型安全、符合惯例的 Swift 代码的工具，根据 OpenAPI 文档自动生成 API 调用和服务器实现所需的代码。支持 OpenAPI 规范版本 3.0 和 3.1 ，提供更灵活的抽象方式，使开发人员能够以 API 优先的方式进行服务器开发。

生成的客户端代码为每个操作提供了一个方法，可与任何提供 Swift OpenAPI Generator 集成包的 HTTP 库一起使用。生成的服务器代码通过 "APIProtocol" 协议定义了每个操作的方法要求，适用于任何提供Swift OpenAPI Generator集成包的Web框架。

[SwiftUI 中的 visionOS ornament](https://swiftwithmajid.com/2024/01/30/visionos-ornaments-in-swiftui/ "SwiftUI 中的 visionOS ornament")

**摘要：**  这篇博客介绍了在 Swift 中使用 SwiftU I构建 visionOS 应用程序的方法，重点介绍了新的 SwiftUI API 中的 ornament 概念。ornament 是一种用于在不干扰窗口内容的情况下呈现与窗口相关的控件和信息的用户界面组件。文章首先展示了如何使用 TabView 创建一个基本的 ornamen t，然后介绍了如何使用 SwiftUI 的 Toolbar API 在 ornament 中添加操作控件。

此外，文章还详细讲解了如何创建自定义 ornaments ，包括控制其位置、外观和感觉。最后，总结了如何使用 SwiftUI 框架来改善 visionOS 上应用程序的用户体验。以帮助开发人员更好地适应 visionOS 平台。

[Swift 有些场景其实不必加 final](https://juejin.cn/post/7313242001113677862/ "Swift 有些场景其实不必加 final")

**摘要：**  这篇文章深入探讨了在 Swift 中使用 final 关键字的场景和最佳实践。作者首先介绍了 final 关键字的作用，包括防止类被继承和优化执行性能。文章指出了一些场景下是不必手动添加 final 的，比如私有类/属性和具有默认访问权限（internal）的类。特别是在使用 Whole Module Optimization（WMO）编译模式时，编译器能够自动推断是否需要添加 final。

然而，对于公共类，作者强调了需要主动考虑是否添加 final ，特别是当提供库给上层调用时，以确保性能和防止意外继承。文章在最后提到在维护项目时，主动添加 final 可以作为一种强文档的方式，提醒未来的使用者。

## 话题讨论

近日，有网友在社交平台爆料称自己因为隐瞒裁员经历说成是主动离职而被取消了 offer 。在职场中，有些人可能选择将自己被裁员的情况描述为主动离职。把“被裁”说成“主动离职”算撒谎吗? 

1. 算，不诚实
2. 算适度美化而已
3. 不算，很正常

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
