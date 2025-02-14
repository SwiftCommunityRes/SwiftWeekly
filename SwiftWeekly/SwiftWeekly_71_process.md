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
1) 讨论[使用 Swift Build 改进 SwiftPM 构建](https://forums.swift.org/t/evolving-swiftpm-builds-with-swift-build/77596 "使用 Swift Build 改进 SwiftPM 构建")

Swift 论坛于 2025 年 2 月 1 日宣布了一个名为 Swift Build 的新开源项目，该项目将成为 Swift 工具链的一部分，并用于优化 Swift 包管理器（SwiftPM）的构建系统。该项目的目标是在所有受支持的平台上统一构建体验，并提供更强大、灵活的构建功能。

Swift Build 主要特性:
1.	基于 SwiftDriver 的构建
* Swift Build 将采用 SwiftDriver（Swift 编译器驱动的库实现），以提高构建任务的调度效率，并优化构建依赖图。
* 这将使 SwiftPM 的构建系统更可扩展，并更容易适应未来的改进。
2.	增强的构建配置
* Swift Build 将引入更强大的 构建配置系统，使开发者能够在 Package.swift 文件中定义更灵活的构建规则。
* 目前 SwiftPM 仅支持基本的构建配置（如 debug/release），未来将允许更细粒度的配置，如 针对特定平台、架构或环境的自定义设置。
3.	显式模块构建（Explicit Module Builds）
* 传统的 SwiftPM 构建过程依赖于隐式模块，可能导致 并行构建效率低下 以及 模块依赖解析问题。
* Swift Build 将采用 显式模块构建，减少模块间的争用，提高并行构建性能，并确保模块依赖解析的正确性。
4.	支持更多产品类型
* 目前 SwiftPM 主要用于构建库和命令行工具，但 Swift Build 未来将支持 GUI 应用程序、Web 服务 等更多类型的产品。
* 这将使 SwiftPM 在 iOS、macOS 和 Server-Side Swift 领域的应用更加广泛。
5.	跨平台一致性
* Swift Build 的架构设计将确保在不同平台（macOS、Linux、Windows）上提供一致的构建体验。
* 这对于 跨平台开发 和 Swift 生态系统的标准化 具有重要意义。

未来发展方向

Swift Build 的推出是 SwiftPM 发展中的一个重要里程碑，它将大幅提升 Swift 生态系统的构建能力，使其更加现代化和可扩展。未来，该项目可能会进一步优化增量编译、缓存机制，以及支持更复杂的构建系统集成，如与 C++ 交互等。

Swift 社区鼓励开发者关注该项目的进展，并参与讨论，共同推动 SwiftPM 的演进。

2) 提议[[经修改后接受] SE-0453：InlineArray（以前称为：Vector，固定大小的数组）](https://forums.swift.org/t/accepted-with-modifications-se-0453-inlinearray-formerly-vector-a-fixed-size-array/77678 "[经修改后接受] SE-0453：InlineArray（以前称为：Vector，固定大小的数组）")

2025年2月5日，Swift 论坛宣布接受了提案 SE-0453，但进行了若干修改。 该提案引入了一个名为 InlineArray 的新类型，旨在提供固定大小的数组功能。
* 原提议的初始化方法：
```Swift
public init<E: Error>(with next: (Index) throws(E) -> Element) throws(E)
```
将去掉参数标签，改为：init(_:)。

* 在审查过程中，有人指出 InlineArray 的下标操作与 Span 类型不同。 语言指导小组决定让 InlineArray 采用 Span 中缺失的下标操作。

关于命名：

语言指导小组对该类型的命名进行了深入讨论，考虑了审查线程中的意见和私人反馈。 最终决定采用 InlineArray 这一名称，原因如下：
* 关于 Vector 名称： 小组同意，Swift 与其他语言（如 C++ 和 Rust）对“vector”一词的不同理解可能导致混淆。 此外，Vector 与数学向量的关联性不足，难以仅凭此理由采用该名称。
* 关于 FixedSizeArray 名称： 虽然该名称准确描述了类型的行为，但未能体现该类型在复制时的性能特征。 InlineArray 通过 Inline 前缀，强调了其存储方式和性能特性。

综上，InlineArray 这一名称既传达了类型的固定大小特性，又强调了其内联存储和复制行为。 语言指导小组认为，这一命名能够有效避免潜在的性能误解。

感谢所有参与审查的人士，您的贡献使 Swift 语言更加完善。

3) 提议[非弹性模块的可扩展枚举](https://forums.swift.org/t/pitch-extensible-enums-for-non-resilient-modules/77649 "非弹性模块的可扩展枚举")

2025年2月4日，Swift 论坛成员 Franz Busch 和 Pavel Yaskevich 提出了一个名为“为非弹性模块引入可扩展枚举”的新提案。 该提案旨在解决非弹性（non-resilient）模块中枚举类型在 API 演进过程中遇到的问题。目前，Swift 包中的公共 API 避免使用枚举类型，因为在不破坏现有代码的情况下，无法向公共枚举添加新案例。该提案建议对非弹性模块中的枚举行为进行调整，使其与弹性模块中的行为保持一致。具体而言，未标记为 @frozen 的枚举将被视为可扩展的，这意味着在未来可以添加新案例，而不会破坏现有代码。对于从其他模块（不在同一包内）导入的此类枚举，开发者在使用 switch 语句时，需要添加 @unknown default: 分支，以处理可能的新增案例。然而，对于同一包内的模块之间的枚举使用，switch 语句仍要求穷尽所有已知案例，无需添加 @unknown default: 分支。该提案的目标是统一 Swift 语言中弹性和非弹性模式下的枚举行为，简化库维护，并鼓励在公共 API 中更广泛地使用枚举。

4) 提议[可替换的库插件](https://forums.swift.org/t/pitch-replaceable-library-plugins/77605 "可替换的库插件")

2025年2月2日，Swift 论坛成员提出了一个名为“可替换库插件”（Replaceable Library Plugins，简称 RLP）的新提案。 该提案旨在为 Swift 包管理器（SwiftPM）引入对动态库的支持，特别是在 Linux 环境中。目前，SwiftPM 在 Linux 上缺乏对非系统二进制库依赖项的支持，这意味着每当应用程序的某个组件发生变化时，开发者需要重新编译并部署整个应用程序。RLP 的引入将允许开发者将这些变化频繁的组件打包为动态库，并在不重新编译整个应用程序的情况下进行替换和升级。这些动态库将通过现有的 .artifactbundle 格式进行分发。需要注意的是，RLP 主要面向组织内部或特定客户的内部使用，组织需要定义自己的“组织定义平台”（Organization-Defined Platforms，ODP），以确保二进制兼容性。要创建 RLP，开发者需要使用 -enable-library-evolution 标志构建一个普通的 SwiftPM 库产品，并将其打包为 .artifactbundle。该提案的目标是为 SwiftPM 引入动态库支持，特别是在 Linux 环境中，以提高应用程序的模块化和可维护性。

5) 讨[在 Swift 中使用 C 库：思考](https://forums.swift.org/t/using-the-c-library-from-swift-thoughts/77648 "在 Swift 中使用 C 库：思考")

2025年2月4日，Swift 社区成员 Alastair Houghton 在 Swift 论坛上发起了关于在 Swift 中使用 C 标准库的讨论。 讨论的起因是为 FreeBSD 添加支持的拉取请求中，当前的实现滥用了 Glibc 模块，而 FreeBSD 并不使用 Glibc。这引发了关于创建统一的 C 标准库模块的想法，以简化跨平台开发者在不同操作系统上导入 C 标准库的过程。

当前问题：
* 导入差异： 开发者需要根据操作系统条件导入不同的 C 标准库模块，例如：

```Swift
    #if os(Linux)
    import Glibc
    #elseif os(macOS) || os(iOS) || ...
    import Darwin
    #elseif os(Windows)
    import CRT
    #else
    #error We need a C library!
    #endif
```

这种方式增加了代码的复杂性和维护成本。

* 类型不一致： 同一 C 类型在不同平台上的导入方式可能不同，例如 FILE * 可能被导入为 OpaquePointer、UnsafeMutablePointer<FILE> 或 UnsafeMutablePointer<FILE>?，这取决于 C 库的定义方式，导致在 Swift 中使用这些类型时缺乏一致性。

建议的解决方案：

讨论中提出了创建统一的 C 标准库模块的想法，例如：

* 标准库模块： 允许开发者通过以下方式导入特定的 C 标准库：

```Swift
    import C99 // 或 C11、C23 等
```

* 扩展库模块： 提供一个模块，包含常见的 C 扩展函数，并统一命名，例如：

```Swift
    import CExtensions
```

在该模块中，函数 strcasecmp 可以在 Windows 上使用，即使在 Windows 上该函数名为 _stricmp。

实现挑战：

然而，实现上述方案并非易事，主要挑战包括：
* 模块化限制： Clang 模块要求每个 C 类型只能由一个模块定义。例如，FILE 类型必须由定义它的 C 库模块唯一提供。如果在其他地方重新定义该类型，可能会导致编译错误。
* 头文件问题： 特别是 Glibc 的头文件，存在难以模块化的问题，导致 Glibc 模块存在缺陷，修复这些问题也相当困难。

Alastair Houghton 表示，虽然他个人希望能够通过导入统一的 C 标准库模块来简化跨平台开发，但实现这一目标需要仔细考虑，远非简单地编写一些新的头文件和模块映射那么简单。

他还提到，平台指导小组（Platform Steering Group）对该问题表示兴趣，但目前尚未直接开展相关工作。

## 推荐博文


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
