## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第九十五期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

永远向光而行，不停留回望阴影，让琐事随风，让脚印慢慢流淌成诗篇。新的一年，就奔赴下一场热爱与山海！👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：苹果iPhone或迎涨价，全球存储芯片短缺成焦点；苹果成立即将满50年，库克承诺将庆祝；Apple Support AI功能升级，新增诊断程序
> * **提案**：SE-0502 正式通过；SE-0506 至 SE-0511 正在审查
> * **Swift 论坛**：Dictionary.mapValuesWithKeys、所有权注解讨论、AsyncAlgorithms withDeadline、整数泛型参数、文档参数名规范等多项讨论
> * **推荐博文**：Swift 分层缓存设计、AutoreleasePool 原理实践、Subscripts 进阶指南

上期话题投票结果如下：

![](https://files.mdnice.com/user/47553/e827be2e-02b0-49a5-b4a5-6bde4dc9215f.jpg)

## 话题讨论

### 本期话题：**“四天工作制”从实验走向主流，会成为未来的必然趋势吗？**

2026年初，四川一家集成电路公司宣布“每周工作4天、周五带薪休假，薪酬不变。**“四天工作制”从实验走向主流，会成为未来的必然趋势吗？**

1. 会，这是以人为本、增效降耗的必然未来。
2. 不会，其成为“主流”面临难以逾越的结构性障碍，并可能产生新的不公平。

欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### 苹果iPhone或迎涨价？全球存储芯片短缺成焦点

*2026 年 2 月 6 日｜来源：环球市场播报*

全球存储芯片短缺冲击智能手机市场。苹果 CEO 库克表示公司有多种应对手段，但未明确是否涨价。分析师认为，苹果凭借行业影响力能从长期供应商处保障芯片供应，而中小手机厂商面临更大压力。若苹果维持原价，iPhone 市场吸引力将提升；若率先提价，则为竞争对手留下跟涨空间。IDC 数据显示，存储芯片短缺或导致 2026 年全球智能手机市场出货量出现 2023 年以来的首次同比下滑。

### 苹果成立即将满50年！库克已告知员工将会庆祝

*2026 年 2 月 6 日｜来源：快科技*

苹果公司将于 4 月 1 日迎来成立 50 周年。CEO 库克已告知员工将进行庆祝活动，具体形式待揭晓。苹果公司最初名为苹果电脑公司，由史蒂夫•乔布斯、斯蒂夫•盖瑞•沃兹尼亚克和罗纳德•杰拉尔德•韦恩于 1976 年 4 月 1 日在乔布斯父母的车库里创立。2007 年推出 iPhone 后，公司更名为苹果公司。

![](https://files.mdnice.com/user/47553/d2bde0c7-6921-4071-b111-22b84b3cf454.png)

### 苹果将为Apple Support带来更多AI功能 功能升级界面焕新

*2026 年 2 月 4 日｜来源：CNMO科技*

苹果在 Apple 支持应用中测试的 AI 支持助手迎来新升级，新增诊断程序功能，可展示设备健康状况与性能表现。界面标签从 "Chat" 更改为 "Ask"，并移除"早期预览版"标注，表明功能已从测试阶段转向正式发布。该助手自去年 8 月开始测试，利用 AI 技术解答设备问题并引导用户解决常见故障。

![](https://files.mdnice.com/user/47553/643be18d-eb9e-4d69-b61b-65b913348fc2.png)

## 提案

### 通过的提案

[SE-0502](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0502-exclude-private-from-memberwise-init.md "SE-0502")
**从成员初始化器中排除私有初始化属性** 提案已通过审查。

该提案此前已在 **第九十三期周报** 的「正在审查的提案」模块中做过详细介绍。本次通过，将提升类型演进的安全性，减少无意义的可见性变化对 API 的破坏。

### 正在审查的提案

[SE-0506](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0506-advanced-observation-tracking.md "SE-0506")
**高级观察跟踪** 提案正在审查。

该提案为 `@Observable` 类型增加了两个新的观察入口点，允许更精细的控制和高级行为。这是一套用于高级用例的专业工具，例如开发中间件基础设施或小部件系统的基础。大多数使用观察的开发人员仍然最好使用 `@Observable`，并可能与 `Observations` 类型一起迭代事务值。然而，在需要的高级用例中，该提案填补了急需的空白。

[SE-0507](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0507-borrow-accessors.md "SE-0507")
**借用和突变访问器** 提案正在审查。

借用访问器——与新关键字 `borrow` 和 `mutate` 一起引入——允许使用借用语义实现计算属性和下标。这些增强了现有的 `get`、`set`、`yielding borrow` 和 `yielding mutate` 访问器，以完成"访问者的远景"中描述的设计。

与 `get` 访问器不同，借用访问器可以在不复制的情况下公开存储的值；与 `yielding borrow` 和 `yielding mutate` 访问器不同，借用访问器不需要协程的开销，这使得它们在不能完全内联时性能更高。借用访问器只能公开值，其存储保证在包含值的下一次突变之前是有效的。

[SE-0508](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0508-array-expression-trailing-closures.md "SE-0508")
**数组表达式尾随闭包** 提案正在审查。

该提案增加了在数组和字典等集合类型的初始化表达式中使用尾随闭包的支持，以提升集合构造时的语法一致性与可读性。

[SE-0509](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0509-swift-sboms-via-swiftpm.md "SE-0509")
**Swift软件包管理器的软件物料清单（SBOM）生成** 提案正在审查。

SBOM（软件物料清单）提供了人工制品中包含的软件组件的详细清单。SBOM 允许开发人员改进和分析其 Swift 项目的软件供应链安全配置文件（例如，确定正在使用的依赖项是否存在漏洞）。此外，一些公司、政府和其他监管机构要求为审计目的制作 SBOM。SBOM 有两种常见的格式：CycloneDX 和 SPDX。

[SE-0510](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0510-dictionary-mapvalues-with-keys.md "SE-0510")
**介绍 Dictionary.mapValuesWithKeys** 提案正在审查。

该提案建议添加一个方法 `Dictionary.mapValuesWithKeys`，将 `Key` 传递到转换闭包。这使我们能够将字典值与其相关的密钥上下文转换，而不会产生重新分配字典存储的性能成本，这在使用 `init(uniqueKeysWithValues:)` 或 `reduce(into:)` 时是不可避免的。

[SE-0511](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0511-swiftpm-add-target-plugin.md "SE-0511")
**SwiftPM添加目标插件命令** 提案正在审查。

该提案引入了一个新的 `swift package add-target-plugin` 命令，允许开发人员直接从命令行将插件使用情况添加到 `Package.swift` 清单中的现有目标中。这建立在 SE-0301 中引入的软件包编辑命令之上。

## Swift论坛

### 1、SE-0510：为 Dictionary 增加 `mapValuesWithKeys`

作者：Slava Pestov ｜ 发布日期：2026 年 2 月 13 日
[阅读原帖](https://forums.swift.org/t/se-0510-dictionary-mapvalueswithkeys/84547 "SE-0510: Dictionary.mapValuesWithKeys")

该提案正式进入 Swift Evolution 审查阶段，旨在为 `Dictionary` 添加一个新的映射方法 `mapValuesWithKeys(_:)`，使开发者能够在转换字典值时同时访问每项对应的键（Key）。

**动机：**
当前的 `mapValues(_:)` 只给出值（Value）本身，而如果想基于键和值联合生成新值，就只能用 `reduce(into:)` 或 `uniqueKeysWithValues` 组合这些方法，这既不直观又可能有性能开销。

**主要修改示例：**

```swift
extension Dictionary {
  func mapValuesWithKeys<T>(
    _ transform: (Key, Value) throws -> T
  ) rethrows -> Dictionary<Key, T>
}
```

这样调用时就可以直接：

```swift
let result = dict.mapValuesWithKeys { key, value in
  "\(key): \(value)"
}
```

**讨论亮点：**

* 直接支持键值对映射，比现有 workaround 更简洁、更高效
* 社区普遍支持这一增强，认为对日常字典转换很实用
* 此 API 不改变现有行为，不破坏兼容性，只是新增更多表达力和便利性

**简要点评：**
SE-0510 让标准库更好支持基于键和值联合映射的场景，减少 boilerplate 代码，是对 `Dictionary` API 实用性的一次提升。


### 2、讨论：Escapable、Span、所有权注解等

作者：Guillaume Lessard 等 ｜ 发布日期：2026 年 2 月 14 日
[阅读原帖](https://forums.swift.org/t/escapable-span-ownership-annotations-etc/84566 "Escapable, Span, ownership annotations, etc.")

这篇帖子围绕 Swift 新的所有权和内存模型展开，涉及多个关键主题。

**动机：**
Swift 在借用/所有权模型中引入了 `Escapable` 标注、`Span`/`RawSpan` 等新特性，社区需要探讨这些特性的语义、适用场景以及是否需要更统一的注解语法。

**主要内容：**

* **`Escapable` 语义讨论：** 现阶段 Swift 在借用/所有权模型中有一个 `Escapable` 标注（用于表明值可以逃逸当前作用域），社区在探讨其适用场景、名称是否准确、以及是否需要更明确的语义
* **`Span` 所有权与借用规则：** 讨论中提到了 `Span`/`RawSpan` 等连续内存视图的所有权语义、借用限制、可逃逸性等，在设计更安全的内存访问语义时需考虑各种边界条件
* **Ownership 注解统一：** 讨论还涉及是否应统一所有权相关的注解语法、让 compiler 更清晰推断/检查借用逃逸情况，例如更精确地指定哪些闭包可以捕获某些借用
* **未来扩展与语言方向：** 社区进一步探讨了未来如何发展所有权模型、是否需要引入更细粒度的生命周期注解等

**讨论亮点：**

* 支持更统一、精确的所有权/借用语义注解，以增强编译器检查和类型安全
* 同时也有人担心语法复杂度增加，建议先在库层实践再在语言层统一
* 讨论涉及很多低层设计权衡，是 Swift 所有权生态长期关注的方向

**简要点评：**
这是一场关于 Swift 借用/所有权体系（特别是 `Escapable`、`Span`、逃逸注解等）的深度讨论，对未来标准库和语言在内存安全与所有权控制的长期方向提供了有价值的参考。


### 3、提案：AsyncAlgorithms 增加 `withDeadline`

作者：Philippe Hausler ｜ 发布日期：2026 年 2 月 15 日
[阅读原帖](https://forums.swift.org/t/asyncalgorithms-withdeadline/84604 "AsyncAlgorithms withDeadline")

该提案针对 AsyncAlgorithms package，建议为现有的一些 async 算法添加一个统一支持"截止时间（deadline）"的扩展 API，便于在异步流处理、等待组合时指定超时边界。

**动机：**
当前用户需要在每次异步操作时手动使用 `async let`/`Task` 再加 `sleep(until:)` 或手动检查超时，这种模式重复且容易出错。该提案旨在让常见模式（如在流处理、合并、并发等待中加截止时间）更易用。

**核心设计：**

```swift
func withDeadline<T>(
    _ deadline: Instant,
    operation: () async throws -> T
) async throws -> T
```

在调用时可以写：

```swift
try await withDeadline(.now + .seconds(5)) {
    try await someLongRunningAsyncWork()
}
```

**讨论亮点：**

* 与现有 `Task.timeout`/`Task.sleep` 结合如何协同
* 如何确保 deadline 能正确 propagate 取消，并且避免丢失错误信息
* 是否应作为全局工具函数，还是作为 AsyncAlgorithms 的扩展方法

**简要点评：**
为 AsyncAlgorithms 引入统一的 deadline 支持，能提升异步算法库的 ergonomics，让超时场景更易表达，是对现有异步组合操作的实用增强。


### 4、提案：为协议引入整数泛型参数

作者：Kavon Farvardin ｜ 发布日期：2026 年 2 月 14 日
[阅读原帖](https://forums.swift.org/t/integer-generic-parameters-for-protocols/84553 "Integer generic parameters for protocols")

这个 pitch 提出让 Swift 协议支持整数泛型参数（integer generic parameters），围绕最大度量、缓存大小等与"数值"语义有关的编程模式提供更灵活的抽象。

**动机：**
当前 Swift 泛型参数只能用于类型标识等语义，而无法在协议声明中以整数作为参数。但在很多领域（如 fixed-size buffer、矩阵库、数字算法）中，"整数参数"非常有用，可提升类型表达力和静态检查。

**核心设计：**

允许协议（或类型）带整数泛型参数，例如：

```swift
protocol FixedBuffer<Capacity: Int> { … }
```

或限制某些实现只能在指定整数字面量下实例化：

```swift
struct Matrix<Element, Rows: Int, Columns: Int> { … }
```

当前不允许的语法：

```swift
protocol FixedWidthVector<Length: Int> { … }
```

**讨论亮点：**

* 如何让整数泛型参数具有约束（例如 `Capacity >= 0`）
* 是否引入整数类型范围约束语法
* 与现有泛型编译器类型检查机制整合的复杂度
* 与其他语言（如 C++ 模板整数参数）的对比

**简要点评：**
如果被采纳，整数泛型参数可让 Swift 在泛型编程中支持更多静态度量约束，提升性能优化和类型表达力，是向更强泛型表达迈出重要一步。

### 5、讨论：文档中的内部参数名 vs 外部参数名

作者：David S-Tone ｜ 发布日期：2026 年 2 月 14 日
[阅读原帖](https://forums.swift.org/t/internal-vs-external-parameter-names-in-documentation/84571 "Internal vs external parameter names in documentation")

这篇帖子探讨了 Swift 文档系统（特别是 DocC）显示函数参数名时应使用内部参数名还是外部参数名的问题，对库作者、使用者都有影响。

**动机：**
Swift 函数签名可以有外部参数名（用于调用时）和内部参数名（用于函数体），在文档中应展示哪个名字（外部、内部或两者）一直是社区关注点。文档显示外部参数名有助于用户理解如何调用 API，而显示内部名有助理解参数在实现中的用途。

**示例：**

```swift
func foo(external internalName: Int) { … }
```

**讨论亮点：**

* **DocC 当前行为：** 默认展示外部参数名（调用名），有时同时展示内部名
* **何时显示内部名：** 有观点认为，对于描述实现语义、在代码示例中解释参数含义时，内部名有用
* **一致性与清晰性：** 有人建议在函数定义附近展示两者，并清楚区分用途
* **Edge Cases：** 对于没有外部参数名的情况（如 `_:`）如何在文档中清晰呈现也是讨论点

**简要点评：**
这是一场关于 API 文档可读性与一致性的讨论，核心在于让 DocC 能更智能地根据场景展示适当的参数名，从而改善用户阅读接口说明时的体验。

## 推荐博文

以下三篇文章非常值得一读，适合本周“提升技能 + 开阔思路”：

[Swift 中的分层缓存设计：平衡性能、内存与数据一致性的实践方案](https://juejin.cn/post/7603383059151667242/ "Swift中的分层缓存设计：平衡性能、内存与数据一致性的实践方案")

**摘要：** 本文深入探讨了一种超越单一缓存策略的先进方案——分层缓存设计。该方案的核心智慧在于，它并非简单地将内存与磁盘缓存叠加，而是通过一个精妙的策略驱动架构，让数据在速度极致但容量有限的内存层（L1）与容量巨大但速度较慢的磁盘层（L2）之间智能流动，从而在高性能、低内存占用和数据一致性这三个往往相互矛盾的目标之间取得了优雅的平衡。

文章从统一的缓存协议抽象开始，逐步构建了一个包含内存缓存与磁盘缓存的完整Swift实现。其最具创新性的部分在于引入了一套灵活的缓存策略模式（如优先返回缓存并后台更新的cacheThenFetch，或确保数据强一致的cacheElseFetch），允许开发者根据具体业务场景（如用户头像展示或权限校验）选择最合适的数据一致性模型。此外，文中还详细阐述了热点数据自动提升、缓存预热、并发安全等高级优化技巧。

[Swift 中的 AutoreleasePool：原理、实践与最佳使用场景](https://juejin.cn/post/7602454700504563753/ "Swift 中的 AutoreleasePool：原理、实践与最佳使用场景")

**摘要：**  文章从自动释放池的底层分页栈结构实现讲起，阐明了其通过延迟释放来管理对象生命周期的原理。重点部分在于其实战应用：例如，在包含数千次迭代的循环中处理大量图像或数据时，使用autoreleasepool可以确保临时对象在每次循环后即被及时回收，而非堆积到整个循环结束，这对于维持应用内存的平稳至关重要。此外，在单元测试中，它也是验证对象是否正确释放的得力工具。

[Swift 下标（Subscripts）详解：从基础到进阶的完整指南](https://juejin.cn/post/7564996702819827758/ "Swift 下标（Subscripts）详解：从基础到进阶的完整指南")

**摘要：**  Swift 下标（Subscripts）远不止是访问数组和字典的语法糖，它是一种强大的语言特性，允许我们为自定义类型赋予直观的“中括号”访问能力。本文系统地介绍了下标的核心语法、从只读到读写的实现，并深入探讨了多参数下标、下标重载以及类型下标等进阶用法。

文章的精髓在于展示了如何将下标与其他现代 Swift 特性结合，创造出更具表现力和安全性的代码。例如，通过与属性包装器（Property Wrappers）结合，可以轻松实现线程安全的集合访问；与结果构造器（Result Builders）结合，则能构建出声明式的领域特定语言（DSL）。


## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
