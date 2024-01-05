## 前言

**本期是 Swift 编辑组整理周报的第四十四期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

每天接受一点正能量，拥抱积极向上的生活态度，就像**Swift社区**，逐渐变得闪闪发光！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果中国工厂正加速生产Vision Pro，有望于明年2月上市
> 
> 提案：推断方法和关键路径文本的 Sendable
> 
> Swift 论坛：讨论在 Raspberry Pi Pico 上运行的嵌入式 Swift
>
> 推荐博文：使用 Swift 的异步 Operation 实现并发执行任务
>
> **话题讨论：** 
> 
> 想在组内晋升的速度更快，你认为以下哪个标准更重要呢？

**上期话题结果**

![](https://files.mdnice.com/user/17787/b677ed19-4ebe-4e2e-a83f-823336dbb178.jpg)

根据投票结果显示了程序猿对于职业领域中性别平等的关注，强调了专业能力和领导风格的重要性。

## 新闻和社区

### 苹果中国工厂正加速生产 Vision Pro，有望于明年2月上市

![](https://pics6.baidu.com/feed/359b033b5bb5c9ea824950a5c6b0f10d3bf3b350.jpeg@f_auto?token=e96ace0fc5e825697f2c5ce5614ebec5)

苹果 Vision Pro 离消费者越来越近了。

12 月 21 日消息，据外媒援引知情人士消息称，苹果公司正加速拓展 Vision Pro 混合现实头显的产能，为 2 月份的发售做好准备。

报道中提及，这款新头显设备的生产工作正在中国工厂全速进行，并且已持续了数周，目标是在明年 1 月底之前准备好面向客户的产品，并计划在 2 月首次亮相零售店。

与此同时，周三苹果还向软件开发人员发送了一封电子邮件，鼓励他们使用最新的工具测试他们的应用程序，并将他们的软件反馈发送给苹果，从而为 Vision Pro “做好准备”。

Vision Pro 于 2023 年 6 月发布，搭载了 12 个摄像头、5 个传感器和 6 个麦克风，采用双芯片设计，包含 M2 芯片以及苹果专门为 Vision Pro 设计的 R1 芯片。该产品凭借着出色的交互性和顶级的硬件堆叠受到业内关注。

但也受制于其设计复杂性，此前一度有苹果被迫大幅削减 Vision Pro 产量预测的消息传出。7 月，《金融时报》援引与苹果和中国代工商立讯精密关系密切的两名人士称，苹果仅准备在 2024 年生产不到 40 万台 Vision Pro ，同时推出更实惠版本的 Vision Pro 计划已被推迟。

随后有关 Vision Pro 生产的消息不断传出，今年 9 月，立讯精密董事长王来春曾透露，公司正在为明年初上市的苹果头显 Vision Pro 做生产准备。12 月 12 日，界面新闻从供应链获悉，因为 OLEDoS 显示屏的产能瓶颈被中国内地公司突破并进入一供，目前供应链已经做好了年产 100 万台的准备。

Vision Pro 是苹果公司自 2015 年开始销售智能手表以来推出的又一个新产品类别，对于苹果的重要程度不言而喻。据了解，苹果已经在开发该设备操作系统的下一版本 VisionOS ，该软件预计将于 2024 年晚些时候推出，同时还将推出与苹果其他主要设备相关的操作系统。

### 美媒：苹果将在美暂停销售最新款智能手表

参考消息网 12 月 20 日报道 据美国《纽约时报》网站 12 月 18 日报道，苹果公司 18 日表示，将从 21 日开始暂停其最新款智能手表的线上销售。该款手表在实体店的销售也将在 12 月 24 日之后暂停。

两个月前，苹果公司输掉了关于其智能手表用来检测人们脉搏的技术专利案。该公司被要求在圣诞节后停止销售苹果 Series 9 和 Ultra 2 这两款智能手表，这可能会在假日购物的最后一周引发该手表销量的激增。

苹果公司采取这一举措前，美国国际贸易委员会今年 10 月的裁决认定，苹果公司的几款智能手表侵犯了位于美国加利福尼亚州马西莫公司的专利。

法庭上，马西莫公司详细讲述了苹果公司如何挖走其高管和其他十几名员工，紧跟着如何又发布了一款配备脉搏血氧计的手表。而该技术是马西莫公司的专利。

为了避免全面禁止销售，苹果公司曾有两个月与马西莫公司达成协议，以获得该公司的技术许可，或者也可以请求拜登政府推翻这一裁决。

马西莫公司首席执行官乔·基亚尼在接受采访时说，但苹果公司没有就相关技术许可与其谈判。相反，苹果公司已推动拜登总统否决国际贸易委员会的裁决，基亚尼之所以知道这些，是因为政府就苹果公司的请求与马西莫公司进行了接触。

基亚尼在谈到国际贸易委员会时说：“他们试图让该机构看起来像在帮助专利流氓。”

对基亚尼的言论，苹果公司没有回应置评请求。苹果公司在一份声明中称：“苹果公司强烈反对这一命令，正在寻求一系列法律和技术方案，以确保消费者可以买到苹果手表。”拜登政府没有立即回应置评请求。

## 提案

### 通过的提案

[SE-0412](https://github.com/apple/swift-evolution/blob/main/proposals/0412-strict-concurrency-for-global-variables.md "SE-0412") **全局变量的严格并发性** 提案通过审查。该提案已在 **四十一期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0418](https://github.com/apple/swift-evolution/blob/main/proposals/0418-inferring-sendable-for-methods.md "SE-0418") **推断方法和关键路径文本的 Sendable** 提案正在审查。

此提案聚焦于在使用并发时围绕函数作为值和关键路径文本语言的一些边缘情况。我们建议为部分和未应用的方法推断 `Sendability`。我们还建议通过允许开发人员控制关键路径文本是否是 Sendable，来解除 SE-0302 放置在关键路径文本上的 Sendability 限制。目标是在不对 Swift 进行重大更改的情况下提高灵活性、简便性和人机工程学。

[SE-0417](https://github.com/apple/swift-evolution/blob/main/proposals/0417-task-executor-preference.md "SE-0417") **任务执行器偏好** 提案正在审查。

Swift Concurrency 使用任务和 actor 来建模并发，并主要依赖于 actor 隔离来确定特定代码应在何处执行。

SE-0392 最近引入的自定义 actor 执行器允许自定义特定 `SerialExecutor` 实现代码应该在其中运行，同时隔离到特定的 actor。这使得开发人员可以对 actor 的确切线程语义获得一定控制，例如，通过确保特定 actor 执行的所有工作都在专用队列或线程上完成。

然而，目前一般任务和非隔离的异步函数没有同样的灵活性，非隔离的异步函数总是在由 Swift Concurrency 管理的默认全局并发线程池上执行。

[SE-0416](https://github.com/apple/swift-evolution/blob/main/proposals/0416-keypath-function-subtyping.md "SE-0416") **键路径文字作为函数的子类型** 提案正在审查。

目前，键路径文字只能被狭义地转换为与参数和返回类型完全匹配的函数。该提案允许键路径文字参与到我们允许在任意函数类型之间进行的完全泛化的转换中，使得以下代码能够在没有错误的情况下编译：

```swift
let _: (String) -> Int? = \.count
```

### 驳回的提案

[SE-0415](https://github.com/apple/swift-evolution/blob/main/proposals/0415-function-body-macros.md "SE-0415") **函数体 Macros** 提案被驳回。该提案已在 **四十三期周报** 正在审查的提案模块做了详细介绍。

[SE-0414](https://github.com/apple/swift-evolution/blob/main/proposals/0414-region-based-isolation.md "SE-0414") **基于区域的隔离** 提案被驳回。该提案已在 **四十三期周报** 正在审查的提案模块做了详细介绍。

## Swift论坛

1) 讨论[在 Raspberry Pi Pico 上运行的嵌入式 Swift](https://forums.swift.org/t/embedded-swift-running-on-the-raspberry-pi-pico/69001 "在 Raspberry Pi Pico 上运行的嵌入式 Swift")

**内容概括**

Nikolai Ruhe 和一位合作者成功在 Raspberry Pi Pico 10 微控制器 (RP2040 MCU) 上运行嵌入式 Swift 26 代码。 该代码可在 GitHub 上找到，通过使用 Swift 直接操作 MCU 的内存映射寄存器来闪烁 Pico 的板载 LED。

该设置涉及在 Raspberry Pi Pico C/C++ SDK 3 上构建的主 C 程序，并使用 CMake 作为构建系统。 定义了一个名为 SwiftLib 的 Swift 库，使用 CMake 进行编译，并静态链接到主可执行文件中。 主 C 程序和 SwiftLib 之间的通信是通过 C 标头实现的。

为了控制 LED，Swift 代码利用 RP2040 MCU I/O 块的特定内存地址，根据 C 代码调用的函数切换 GPIO 引脚。 虽然这一成就令人兴奋，但也强调了一些需要改进的领域：

1. 从 `CMake` 过渡到 Swift Package Manager (SwiftPM)，以便更轻松地进行构建管理和其他 Swift 库的集成。 然而，由于 SDK 的复杂性以及与 CMake 的密切联系，将 Pico C SDK 与 SwiftPM 集成可能具有挑战性。
2. Swift-MMIO 的集成，由于 SwiftPM 尝试在嵌入式 Swift 模式下构建 `SwiftSyntax` 不兼容，因此遇到了困难。 解决此问题需要指定 SwiftPM 应为主机和目标平台构建哪些目标。
3. 解决由于缺少内存分配和原子等运行时函数而导致的链接器错误。 虽然空的实现使链接器保持沉默，但这并不是一个理想的解决方案。 嵌入式 Swift 中的 `-no-allocations` 模式可能会部分解决这个问题，尽管它可能无法涵盖所有必要的运行时函数。

该团队热衷于改进这些方面，并希望简化在 Raspberry Pi Pico 上运行嵌入式 Swift 的流程，同时集成更多 Swift 库并增强与构建系统的兼容性。

2) 提议[SE-0413: Typed throws](https://forums.swift.org/t/accepted-se-0413-typed-throws/69099 "SE-0413: Typed throws")

**内容概括**

SE-0413，Typed Throws 的提案，经过 11 月 16 日至 12 月 7 日的审核后已被接受。

审查过程中，重点关注了以下具体细节：

1. 括号：有人讨论了在 throws 声明语法中使用括号的问题，其中一些人表示不喜欢 throws(CatError) 格式。 虽然承认不喜欢括号，但它被认为是目前解决语法中潜在歧义的最佳选择。 如果经验表明不会引入歧义，未来的修订可能会考虑删除它们。
2. 显式错误类型注释：审核期间的反馈强调了在 do/catch 块中对显式错误类型注释的需求。 该提案已更新为允许（但不强制）通过语法 do throws(ErrorType) 指定错误类型。
3. Rethrows 关键字：关于类型化抛出可能会使 rethrows 关键字变得多余的讨论已得到认可。 然而，目前尚未做出有关其未来的决定。 该提案概述了替代方案，但推迟了决定以供稍后考虑。

Steve Canon 对社区的参与表示感谢，并指出尽管进行了漫长而激烈的讨论，但仍产生了宝贵的见解并有助于完善提案。

总体而言，该过程虽然广泛，但受到了积极评价，并认可了社区在塑造和增强 Swift 作为一种语言方面所做的贡献。

3) 讨论[对于 static func main() throws 该怎么办？](https://forums.swift.org/t/what-to-do-about-static-func-main-throws/69031 "对于 static func main() throws 该怎么办？")

**内容概括**

讨论围绕 Swift 中 static func main() throws 的行为以及潜在的改进展开。

1. 处理 Main() 中的错误：有人建议，从 main() 中抛出错误应该打印错误，然后以状态代码退出（例如 exit(1)），而不是崩溃。 这种行为被认为是合理的默认行为。
2. 标准化系统错误类型：有人提出了标准化系统错误类型的想法，当抛出该类型时，会触发特定的预定义行为。 然而，由于其潜在的特定于应用程序的性质，人们对标准化持怀疑态度。
3. 提案探索：之前曾尝试过解决方案，但遇到了障碍，包括关于直接暴露退出以及 Linux 上 `CommandLine.arguments` 中不一致的讨论。 有一个潜在的计划提出一个更全面的主入口点，包括传递参数和返回代码，尽管这可能不是主要用于抛出目的。
4. 从顶级代码返回：Doug 关于直接从顶级代码返回的能力（尤其是在保护块内）的建议引起了人们的兴趣。 在某些情况下，例如从 main 提前退出，此功能可以取代当前的 fatalError。

然而，由于时间和资源的限制，立即推动这些提案存在不确定性。

讨论涉及改进 main() 中的错误处理、探索标准化错误类型的潜力，以及考虑早期退出和顶级代码中的错误处理的替代方案。 尽管人们对这些想法很感兴趣，但由于资源限制，立即实施尚不确定。

4) 讨论[ swift 运行时实际上如何应对内存压力？](https://forums.swift.org/t/how-does-the-swift-runtime-actually-respond-to-memory-pressure/69024 "swift 运行时实际上如何应对内存压力？")

**内容概括**

讨论的重点是 Swift 的内存管理行为以及操作系统级内存限制下的处理。

1. 观察 Swift 的内存使用情况：值得注意的是，除非施加操作系统级别的内存限制（例如 MemoryHigh 或 MemoryMax），否则 Swift 的内存使用量往往会持续增长。 在守护进程配置中实现这些限制似乎可以使 Swift 重用分配的内存，而不是不断地从操作系统请求新的内存页面。
2. 接近内存限制的行为：尽管设置了这些内存限制，但当提交大量连续的内存密集型工作时，应用程序在接近这些限制时有时会变得无响应。 即使当前内存使用量与设置限制之间存在很小的差距（大约 1.1MB），也会发生这种情况。
3. 无响应的根本原因：无响应的原因是守护进程级内存限制，而不是系统级内存耗尽。 没有观察到交换，并且操作系统保持响应。 如果没有内存限制，随着时间的推移，Swift 往往会消耗所有可用内存，从而影响包括 SSH 在内的其他进程，并需要重新启动系统来中断。
提出的主要问题是：

Swift 运行时如何对操作系统级内存限制做出反应？

如何防止或减轻接近这些限制时的冻结行为？

本质上，该调查旨在深入了解 Swift 在施加内存限制方面的行为，并寻求解决方案来防止应用程序在接近这些限制时冻结，尽管在守护进程级别强制执行内存上限。

**回复**

Swift 运行时会传递到 malloc 和 free，因此你实际上只是在此处分析系统分配器的内存使用模式。 不同的 malloc 实现可能会以你喜欢的方式重复使用内存。

标准 glibc 分配器的行为通常不太好，我们在服务器生态系统中听到了大量报告，人们转而使用替代分配器，并看到了一种更稳定的内存使用方式。 然而，很难普遍地说 tcmalloc 或 jemalloc 是最好的分配器，因为它总是取决于分配模式。 我希望在 Swift 中看到的是能够像 Rust 的 GlobalAllocator 4 所允许的那样挂钩全局分配器。

这将允许我们为各种分配器出售包，人们可以根据包进行切换，而不是捆绑和预加载分配器

5) 讨论[嵌套 .init() 与 Constructable() 令人惊讶的编译性能](https://forums.swift.org/t/surprising-compilation-performance-of-nested-init-vs-constructable/69052 "嵌套 .init() 与 Constructable() 令人惊讶的编译性能")

**内容概括**

用户在 Swift 中执行性能测试，涉及使用两种不同方法初始化嵌套结构：**类型化 init 和裸 init**。 使用不同的 Xcode 版本对代码进行了测试，一致地，.init 方法比类型化 init 方法更快。

该测试涉及重复创建嵌套结构的实例（从 0 到 999），尽管类型化 init 方法需要类型推导，但它在多个 Xcode 版本中始终比 .init 方法慢。 这种差异很明显，Xcode 15.2 中 .init 方法的速度是原来的两倍多。

用户对观察到的性能差异感到困惑，因为类型化的 init 方法应该推断类型，通常会导致更快的执行。 他们提到了使用嵌套 .init 方法导致性能显着降低的实例，需要键入所有内容才能提高性能。

讨论涉及探索 Swift 嵌套结构初始化中类型化 init 和 .init 方法之间意外的性能差异。 尽管由于类型推导，类型化 init 理论上会更快，但 .init 方法在特定测试场景中始终表现出卓越的性能。

6) 提议[Swift 异步算法提案：AsyncBackPressuredStream](https://forums.swift.org/t/swift-async-algorithms-proposal-asyncbackpressuredstream/69067 "Swift 异步算法提案：AsyncBackPressuredStream")

**内容概括**

讨论涉及提议将 SE-0406 包含到 swift-async-algorithms 包中，SE-0406 引入了对 AsyncStream 的反压支持。 该提案附有修订后的提案以及特定拉取请求 (PR) 中提供的实现。

该提案中概述的主要变化包括：

1. 在 AsyncAlgorithms 中引入新的 Async[NonThrowing]BackPressuredStream 类型，而不是向 Async[Throwing]Stream 添加新的工厂方法。
2. 为水印策略添加自定义元素大小计算，当流的元素是集合时特别有用，允许考虑水印集合的元素计数。

该提案邀请对 SE-0406 的纳入和修改提供反馈和想法。 社区响应普遍表示支持将此功能合并到异步算法包中，因为它对于确保正确的异步数据流具有重要意义。

人们一致认为，此类功能至关重要，但正确实施具有挑战性，因此拥有 Apple 支持的中心实施地点是有益的。 一些成员表示更喜欢包方法，而不是直接将这些功能嵌入到标准库中，因为它提供了按照自己的节奏进行演变和调整的自由，尽管包依赖性存在潜在的缺点。

总体而言，该提案因其增强异步数据流的重要性和潜力而获得了积极的反馈，同时还讨论了将这些功能集成到包中而不是标准库中的优点。

7) 提议[SE-0270：在非连续元素上添加 Collection 操作](https://forums.swift.org/t/accepted-se-0270-add-collection-operations-on-noncontiguous-elements/69080 "SE-0270：在非连续元素上添加 Collection 操作")

**内容概括**

SE-0270 的第四次审查于 12 月 6 日至 18 日进行，重点是添加对非连续元素的收集操作。 这次审查的目的是重新评估标准库接受的提案，并考虑审查公告中概述的小修改。

审核期间的反馈主要围绕语言指导小组 (LSG) 讨论的两个关键问题。

1. RangeSet包含：争论的焦点是RangeSet作为一种特殊的数据结构是否适合包含在标准库中。 虽然 LSG 通常不愿独立添加此类专用结构，但这里的上下文是在非连续集合元素上添加算法。 为了有效地表达这些算法，使用像 RangeSet 这样的类型变得至关重要。 考虑到这些算法的更广泛必要性，LSG 发现包含 RangeSet 等专门集合以提高 API 效率更为明智。
2. API 命名：讨论了各种 API 的命名，特别是 RangeSet 和索引方法。 一些审稿人认为命名不一致并建议进行修改。

然而，LSG 对提议的名称感到满意。 RangeSet 被认为是更通用的结构，并且像 `index(of:)` 这样的方法名称被认为是合适的，因为 RangeSet<IndexType> 代表了比单独的集合索引集更广泛的概念。

经过讨论和考虑，SE-0270 已被接受纳入标准库。 审核经理 John McCall 对所有贡献者的宝贵参与表示感谢，并强调他们在推动 Swift 作为一种语言发展方面所发挥的作用。

## 推荐博文

[iOS - 渲染原理](https://juejin.cn/post/7078881864030617607 "iOS - 渲染原理")

**摘要：**  文章详细介绍了 iOS 中的渲染原理。首先，讲解了图像渲染流水线的步骤，包括应用处理阶段、几何处理阶段、光栅化阶段和屏幕成像。接着，讨论了渲染流水线可能引发的问题，如屏幕撕裂和掉帧，并提出了解决方法。
  
然后，介绍了 iOS 中的渲染框架，包括 CALayer 和 Core Animation ，以及它们在渲染流程中的作用。最后，详细解释了 Core Animation 渲染的全流程，包括事件处理、布局、绘制、打包和显示等步骤。整篇文章深入浅出地介绍了 iOS 中的渲染原理和相关框架，对理解iOS应用的图像渲染过程具有一定的帮助。

[Swift 编译优化 - 代码优化](https://juejin.cn/post/7309313938785124371 "Swift 编译优化 - 代码优化")

**摘要：**  本文讨论了 Swift 编译优化中的代码优化问题。首先介绍了复杂的运算对编译耗时的影响，建议避免过多次运算和超过两种运算符号的计算式。接着通过几个示例展示了不同类型推断方式对编译耗时的影响，包括简单的类型推断、加法计算、加法和减法计算、多种运算符号计算等。
  
然后讨论了字符串的拼接方式，推荐使用 "(str1) + (str2)" 的方式。接下来介绍了类型推断中的变量定义和明确类型声明对编译时间的影响，并给出了具体示例。另外，还讨论了 CGSize、CGRect、Dictionary 和Array 等类型中避免计算、解包和三目运算等优化建议。最后，提到了删除 Xib 文件和转换为 String 的优化方法，并给出了相关示例。

[使用 Swift 的异步 Operation 实现并发执行任务](https://juejin.cn/post/7314093226956554250 "使用 Swift 的异步 Operation 实现并发执行任务")

**摘要：**  文章介绍了使用 Swift 的异步 Operation 实现并发执行任务的方法。通过异步 Operation，可以在其内部执行耗时任务而不阻塞主线程 UI，提高用户体验。异步操作相比同步操作更灵活，可以手动启动、执行耗时任务、将任务派发到另一个队列，并且易于管理任务的执行顺序和依赖关系。
  
文章还演示了创建异步 Operation 的步骤，包括重写 isAsynchronous 属性和管理异步 Operation 状态的方法。通过使用多线程和 KVO ，确保任务能够正常异步工作，提高代码的可读性和维护性。

## 话题讨论

想在组内晋升的速度更快，你认为以下哪个标准更重要呢？
  
1. 工作经验/时间长短
2. 对项目贡献多业绩多
3. 掌控细节并且获得组员的信任
4. 喜欢创新和求知，对自己也高要求
5. 对项目的发展有长远的大局观
  
欢迎在文末留言参与讨论。


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。