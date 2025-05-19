## 前言

**本期是 Swift 编辑组自主整理周报的第五十期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

间歇性的努力和蒙混过日子，都是对之前努力的清零。时间永不停歇，社会时刻发展，**Swift社区**也在华丽蜕变！👊👊👊

> **周报精选**
>
> 新闻和社区：
> 
> 提案：
> 
> Swift 论坛：
>
> 推荐博文：
>
> **话题讨论：** 
> 
> 
>
>**上期话题结果**


## 新闻和社区  


## 提案


## Swift论坛
1) 提议[宣布成立生态系统指导小组](https://forums.swift.org/t/announcing-the-ecosystem-steering-group/79892 "宣布成立生态系统指导小组")

Swift 核心团队宣布成立“生态系统指导小组”（Ecosystem Steering Group），旨在加强 Swift 开发者生态系统的支持结构。该小组将专注于开发者和文档工具的演进、Swift.org 网站、包管理器以及包生态系统的支持工作。此外，还将支持 Swift 向更多平台的扩展，并简化创建此类移植的工具。该小组还将支持 Swift 在云端 IDE 和持续集成系统等标准或行业领先的开发者生产力工具中的发展。核心团队将选择生态系统指导小组的首批成员。

2) 讨论[为什么 InlineArray 类型语法糖提案进入评审阶段？](https://forums.swift.org/t/why-did-the-inlinearray-type-sugar-proposal-come-to-review/79817 "为什么 InlineArray 类型语法糖提案进入评审阶段？")

Swift 社区成员对 InlineArray 类型语法糖（如 [5 x Int]）的提案进入正式评审阶段感到疑惑，认为该提案尚未充分讨论。一些成员指出，类似的语法在十年前曾短暂讨论过，但并未形成共识。他们担心当前的评审流程可能忽视了社区的反馈，导致讨论变得形式化。对此，核心团队成员 John McCall 表示，提案进入评审并不意味着已被接受，后续将在语言指导小组（LSG）中进行深入讨论，欢迎社区继续提出替代方案。他强调，过度猜测评审流程会影响建设性的讨论，并计划将相关讨论移至新线程，以保持评审的专注性。

3) 提议[已接受 SE-0481：weak let](https://forums.swift.org/t/accepted-se-0481-weak-let/79895/7 "已接受 SE-0481：weak let")

Swift 核心团队正式接受了 SE-0481 提案，引入对 weak let 的支持，允许开发者声明弱引用的不可变变量。此前，Swift 强制所有 weak 变量必须使用 var 声明，这在 Sendable 类型中引发了问题，因为可变属性与 Sendable 要求不兼容。该提案解决了这一限制，使得开发者可以在不引入额外封装结构的情况下，声明符合 Sendable 要求的弱引用属性。此外，提案还明确了在闭包中对 weak 捕获的处理方式，默认将其视为不可变，除非明确声明为可变，从而增强了语言的一致性和类型安全性。该变更被认为是源代码兼容的，并为 Swift 的并发和内存管理特性提供了更强的支持。

4) 提议[轮询期望（Polling Expectations）](https://forums.swift.org/t/pitch-polling-expectations/79866 "轮询期望（Polling Expectations）")

Swift 社区成员 Rachel Brindle 提出在 Swift Testing 框架中引入“轮询期望”（Polling Expectations）的功能，旨在提升测试异步或延迟行为的能力。该功能允许开发者在指定的时间段内持续评估一个表达式，直到其通过（passesOnce）或在整个时间段内始终通过（passesAlways）。这对于测试如 ViewModel 属性在网络请求或数据库查询后更新的场景尤为有用。 ￼

目前，该功能的初步实现已在 swiftlang/swift-testing 的 polling-expectations 分支中提供，需通过 @_spi(Experimental) import Testing 引入。示例代码如下：
```Swift
await #expect(until: .passesOnce) {
    taskDispatcher.finishedTaskCalled == "Important Task"
}
```
社区成员对该提案表示支持，并就 API 设计展开讨论。有人建议将 passesOnce 和 passesAlways 分为不同的宏，以更清晰地表达其语义。此外，关于使用超时时间（timeout）作为停止条件的可行性也引发了讨论。由于 Swift Testing 的并行测试运行器可能导致测试时间不稳定，使用固定的超时时间可能会导致测试结果不一致。因此，有人建议改为使用评估次数作为停止条件，以提高测试的可靠性。 ￼

该提案仍在积极讨论中，欢迎社区成员提出更多建议和反馈。

5) 提议[演进嵌入式 Swift 文档](https://forums.swift.org/t/evolving-embedded-swift-documentation/79818 "演进嵌入式 Swift 文档")

随着嵌入式 Swift 的不断发展和社区的壮大，原先托管在 swiftlang/swift 仓库中的文档面临以下挑战： ￼
1.	文档难以被发现，且未在 GitHub 仓库之外托管。
2.	贡献文档需要克隆 swiftlang/swift 仓库并导航复杂的 swift-ci 流程，对新贡献者而言具有一定门槛。
3.	文档试图涵盖多个构建系统、SDK 集成和语言模式等广泛主题，单人维护难以应对不断增长的内容。 ￼

为了解决这些问题，文档已迁移至 swift-embedded-examples 仓库，并采用 DocC 目录结构进行组织。初步迁移版本已在 Swift Package Index 上可供查看。 ￼

新文档结构（仍在完善中）包括：
•	嵌入式 Swift 概览：从 swiftlang/swift 移植的愿景文档。
•	入门指南：如使用 Swiftly 安装 nightly 工具链的指南。
•	示例教程：基于 swift-embedded-examples 仓库的示例驱动教程，例如 Raspberry Pi Pico 的 LED 闪烁项目。
•	构建系统支持：涵盖 Bazel、CMake、Make、SwiftPM 和 Xcode 的集成指南（目前为占位符）。
•	SDK 支持：如与 Raspberry Pi Pico 的集成（需更新以适应现代 Swift CMake 用法）。
•	语言细节：包括 ABI、存在类型（Existentials）和非最终泛型方法等主题（大部分需重写）。
•	开发进展：如状态页面和 Swift 6.x 的发行说明（后者尚缺）。 ￼ ￼

目前文档仍在积极开发中，社区成员被鼓励参与内容撰写、结构优化和信息流改进等工作。有兴趣的开发者可在论坛中分享想法、提交 GitHub issue 或发起 pull request。

## 推荐博文

[三方 QuicklySwift 使用](https://juejin.cn/post/7505963040308396083/ "三方 QuicklySwift 使用")

**摘要：**  QuicklySwift 是一个专注于提升 SwiftUI 及 UIKit 开发效率的第三方库，通过扩展 UIKit 组件提供了一系列便捷方法。该库的核心优势在于简化了常见的 UI 开发任务，使开发者能够以更少的代码实现相同的功能。

在 UIView 方面，它提供了快速添加子视图和设置约束的功能，采用链式语法让代码更加简洁易读。对于 UIStackView ，它简化了堆栈视图的创建和配置过程，使得构建复杂的UI布局变得更加高效。 UITextField 的扩展则让开发者能够轻松设置占位符、限制输入长度，并实时监听文本变化。

 UIButton 的扩展方法让事件绑定变得更加直观，同时支持监听按钮的选中状态变化。 UITableView 的相关扩展使得注册单元格、配置行数和内容变得更加便捷，还提供了监听行选中事件的功能。UIScrollView的扩展则专注于滚动和内容大小变化的监听。

此外，UIViewController 的扩展简化了生命周期事件的监听，而 UIAlertController 的扩展则让弹窗的创建变得更加简单，支持自定义按钮和取消操作。

总体而言，QuicklySwift通过一系列精心设计的扩展方法，显著提升了SwiftUI 和U IKit 的开发效率，减少了重复代码，使开发者能够更专注于业务逻辑的实现。详细文档可参考其 GitHub 仓库。

[Swift 交叉编译：在 macos 上构建 swift vapor 项目的 linux 可执行文件](https://juejin.cn/post/7503756869786959908/ "Swift 交叉编译：在 macos 上构建 swift vapor 项目的 linux 可执行文件")

**摘要：** 本文介绍了如何在 macOS 上利用 Swift 静态 Linux SDK 交叉编译 Vapor 项目，生成可直接在 Linux 服务器运行的可执行文件。通过静态链接技术，避免了传统动态库依赖问题，简化了部署流程。文章还对比了静态库与动态库的优缺点，并给出具体构建步骤和注意事项，帮助开发者高效完成跨平台编译。

[Swift 隔离机制](https://www.massicotte.org/isolation-intuition "Swift 隔离机制")

**摘要：** swift 的并发模型中，“隔离”（isolation）是编译器防止数据竞争的核心机制，但它的抽象方式与其他同步机制截然不同。作者通过类比 self 的作用，揭示隔离的本质：它由函数的定义决定，而非调用方式。在同步代码中，隔离状态固定不变，只有异步调用（如 await）可能触发隔离变化。

以 SwiftUI 的 @MainActor 协议为例，文章拆解了协议成员、类型定义和全局推断如何共同影响隔离规则。例如，即使某个函数未被显式标记隔离，但如果它属于 @MainActor 协议的成员，编译器仍会强制其运行在主线程。作者强调，这种设计可能导致看似矛盾的行为——比如非隔离函数调用 @MainActor 方法时，编译器会报错，因为隔离状态无法在同步代码中动态切换。

闭包的隔离行为进一步体现了这一规则。普通闭包默认继承外部隔离，但通过 @MainActor 显式标记时，若外部无隔离则会触发编译错误。而 Task 的特殊之处在于它能继承外部隔离，而 Task.detached 则会强制创建独立上下文。

尽管隔离机制复杂，作者认为开发者可以通过类比 self 的学习过程逐步掌握它。理解编译器的检查逻辑后，并发代码的安全性将显著提升。这一过程需要练习，但最终会像熟悉面向对象编程一样自然。


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
