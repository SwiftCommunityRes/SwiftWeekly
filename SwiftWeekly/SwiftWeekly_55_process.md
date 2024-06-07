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

1) 提议[SwiftOS，一项提案](https://forums.swift.org/t/swiftos-a-proposal/72048 "SwiftOS，一项提案")
**内容概括**
该帖子提出了创建一个名为“SwiftOS”的开源操作系统的想法，该系统完全用 Swift 构建，灵感来自 Apple 的 XNU 内核和 Darwin OS 项目。该提议背后的主要动机是为希望开发新设备但具有 Apple 技术（如 Swift 的自动引用计数 (ARC)）提供的更好性能和内存管理功能的独立设备制造商提供 Android 的替代方案。

设想中的 SwiftOS 将设计为在 ARM 和 RISC-V 架构上运行，支持各种设备，如微控制器、服务器、智能手机、平板电脑、XR 耳机等。它将采用 SwiftUI、WebAssembly 和本地 AI/LLM 处理等现代技术。目标是创建一个通用标准层，允许开发人员使用 SwiftUI 为 Apple 设备构建应用程序，并让它们在 SwiftOS 驱动的设备上无缝运行。

该提案表明，SwiftOS 可能成为下一代 NEXTstep OS，并可能被 Apple 自身采用用于其商业产品，同时仍允许在其设备上使用专有代码和服务。它应该强制执行最新的 Swift 并发要求并支持 Swift Charts 和 Swift Data 等技术。

该帖子承认创建这样一个操作系统可能涉及技术和业务挑战，但表达了希望世界运行在 Darwin、Swift 和 SwiftUI 而不是 Linux、Dart/Flutter 和 JavaScript/React 上的愿望。

该帖子还包括其他开发人员对构建操作系统所面临的挑战和机遇的看法，例如将 Swift 推向极限、管理中断和中断安全、自定义分配器支持以及重新考虑现有操作系统（如 XNU 和 BSD）的设计决策。还提供了有关操作系统开发的各种资源的参考。

2) 讨论[超出 SE-0301 的包清单编辑命令](https://forums.swift.org/t/package-manifest-editing-commands-beyond-se-0301/72085 "超出 SE-0301 的包清单编辑命令")
**内容概括**
讨论了在 Swift Package Manager 中引入其他命令来编辑软件包清单的想法，这些命令除了已接受的提案 SE-0301 中指定的三个命令（add-product、add-target、add-dependency）之外。作者已经实现了这三个命令，还提出了一个新命令“add-target-dependency”，用于向特定目标添加依赖项。

随着软件包清单编辑命令的数量不断增加，本文提出了一个问题：是否应继续将这些命令添加为“swift package”的子命令，或者是否应考虑采用不同的分组方法。建议两种可能的分组：

1. “swift package manifest <command>” - 所有清单编辑命令都将分组在“manifest”子命令下。

2. “swift package product <command>”和“swift package target <command>” - 分离产品相关命令和目标相关命令，其中一些命令可能涉及清单编辑。

然后，作者邀请大家就如何最好地组织这些命令提出想法和意见。

另一位开发人员回应道，分享了他们对交互式和批处理场景中命令行参数使用的看法。他们认为，命令中的深层层次结构会使发现和使用更加困难，尤其是在具有自动完成或帮助功能的交互式场景中。建议保留现有的两级层次结构（swift > package），以提高可发现性和易用性。

3) 讨论[不可复制类型和隐式转换](https://forums.swift.org/t/noncopyable-types-and-implicit-conversions/72121 "不可复制类型和隐式转换")
**内容概括**
讨论了 Swift 中的隐式类型转换问题以及它们如何与不可复制类型交互，尤其是在引入不可复制泛型之后。它提供了一个示例，其中从不可复制类型 `Foo` 到 `Foo?` 和 `any Fooable & ~Copyable` 的隐式转换会导致消费操作，从而导致错误，因为该值被消费了不止一次。

作者承认这种行为可能会让大多数人感到困惑，因为他们可能认为 `test` 函数中借用的参数是消费操作的来源，而实际上是调用者 `conversions` 执行了隐式转换，导致了消费。

为了解决这种困惑，作者提出了两个想法：

1. 在执行隐式转换时发出警告，可以通过编写 `consume foo` 来消除警告。仅在转换发生在变量上的情况下才需要此警告，而不适用于 `return foo` 或 `test(Foo())` 等情况，因为这些情况显然是最后一次使用或不转换变量。

2. 使隐式转换显式化，要求用户显式编写转换，例如 `test(foo as Foo?)` 或 `test(.some(foo))`。

另一位开发人员在帖子中发表评论，认为其中一些转换可能通过某种技巧借用，因为无法从不可复制类型借用到可选或超类是一种损失。他们还提到，要求 `consume` 对于当前时期是合理的，而这些转换实际上会执行消费，但他们没有预料到需要更改函数签名设计以适应这种行为的存在和缺失。

4) 讨[写入时有条件复制/克隆](https://forums.swift.org/t/conditional-copy-clone-on-write/72120 "写入时有条件复制/克隆")
**内容概括**
在 Swift 中实现持久二叉树数据结构，以及当有多个引用节点时有条件地复制或克隆节点（写时复制语义）的挑战。作者正在寻找最佳实践或方法来匹配 Swift 中 Rust 的 `Rc::make_mut` 的行为。

作者为二叉树提供了一个简化的 `Node` 类实现，并解释了 `insert` 函数的问题，如果只有一个引用节点，则应该就地改变节点，或者如果有多个引用，则创建一个副本并改变副本。

作者探讨了一些潜在的解决方案：

1. 使用像 `Swift-CowBox` 这样的库来实现写时复制语义，但提到它可能会影响性能。
2. 利用 `__shared` 和 `__owned` 关键字，但不确定它们是否提供了正确的解决方案。
3. 使用修改访问器来控制可变性。
4. 将节点表示为递归枚举而不是可选项，但担心性能影响。

然后作者提出了 Swift 中安全持久树的当前最佳实践以及如何匹配 Rust 的 `Rc::make_mut` 行为的问题。

另一位开发人员回应了以下几点：

1. 将节点表示为值类型（结构或枚举）对于 Swift 中的一般情况可能效率较低，但不可复制的泛型可能会改善这种情况。
2. 澄清 Swift 中的类（引用类型）可以变异，无论声明为 `var` 还是传递为 `inout`。`inout` 参数仅与值类型（结构、枚举和非类协议）相关。
3. 建议在 Swift 中与 Rust 的 `Rc::make_mut` 最接近的函数可能是 Foundation 框架中的 `CFGetRetainCount` 函数，该函数在 Apple 平台上可用，并且可能通过 swift-corelibs-foundation 项目在 Linux/Windows 上可用。当保留计数大于 1 时，此函数可用于复制条件复制行为。

总之，该帖子寻求在 Swift 中为持久二叉树数据结构实现写时复制语义的指导，并且开发人员提供了有关潜在解决方案的见解，包括使用 `CFGetRetainCount` 函数和阐明引用类型的 `inout` 参数的行为。

5) 讨论[代码生成：Swift 语法还是 Mustache？](https://forums.swift.org/t/code-generation-swift-syntax-or-mustache/72131 "代码生成：Swift 语法还是 Mustache？")
**内容概括**
讨论了 Swift 语法和 Mustache 之间的区别，以及它们各自的代码生成用例。

Swift 语法是 Swift 语言语法的具体实现，用于低级代码操作和支持 Swift 宏。它适用于生成样板代码，例如单元测试样板、请求/响应 DTO 以及与特定用例相关的其他样板代码。

另一方面，Mustache 是一种用于渲染模板的模板语言，通常用于服务器端 HTML 渲染。它不依赖于特定的编程语言，可以在 JavaScript、Ruby 等各种语言中找到。

本文建议，对于生成样板代码，宏或 Sourcery 等工具是首选方法。宏的编写可能很复杂，因此如果需要属于常见情况，建议首先寻找现有的解决方案。

一位开发人员分享了他们在公司广泛使用 swift-syntax 为 AWS Lambda 函数生成样板代码的经验。他们发现，使用 SyntaxBuilders 时，swift-syntax 功能强大、可组合、可重用且易于阅读。他们提供了一个最小的代码片段，演示了如何使用 swift-syntax 生成 Decodable 结构。

提到的 swift-syntax 的另一个优点是它与 swift-parser 和 swift-format 集成，允许在同一步骤中高效地评估文件更改并进行格式化。

此外，swift-syntax 支持对现有源代码文件进行操作，从而可以在 Package.swift 文件中手动管理非自动生成的目标，而不是依赖于 gyb 等模板工具。

总体而言，这篇文章重点介绍了 Swift Syntax（低级代码操作和生成）和 Mustache（模板）的不同用途，并提倡使用 swift-syntax 生成样板代码，尤其是在处理复杂或特定用例时。

## 推荐博文


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
