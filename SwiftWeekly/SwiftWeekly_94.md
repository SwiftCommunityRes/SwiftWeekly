## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第九十四期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

或许你早已明白这世间的规则本就倾斜，可那又怎样？紧握心中的天平，潇洒地对抗整个世界，帅极了！👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：苹果下一任 CEO 基本敲定，特努斯将接棒库克；Siri 将重塑为内置 AI 聊天机器人
> * **提案**：SE-0498、SE-0500 正式通过；SE-0503、SE-0504、SE-0505 正在审查
> * **Swift 论坛**：reduce 支持不可拷贝类型、任务取消屏蔽、RawSpan 安全 API 等多项讨论
> * **推荐博文**：Swift Concurrency、Flutter iOS 混淆、iOS Accessibility 全覆盖

上期话题投票结果如下：

![](https://files.mdnice.com/user/47553/b42440fa-4f0e-437a-a828-20efaed707a7.jpg)

## 话题讨论

### 本期话题：**如果脑机接口技术实现，你会选择将意识上传给机器人吗？**

马斯克研制脑机接口，会将人类意识上传至机器人实现数字永生。**如果将来的某一天真的实现了该项技术，那么在生命即将结束的时候，你会选择将自己的意识上传给机器人代替自己吗？**

1. 愿意，在生命的尽头，有一台机器人帮自己陪伴家人，替自己继续未完成的梦想，太赞了。
2. 不愿意，我卑微辛苦了一辈子，死亡于我而言是一种解脱，我可不想让自己的意识囚禁在机器人身上，继续牛马的人生。
3. 如果有越来越多的人选择上传自己的意识，那么硅基生命取代碳基生物的日期就不远啦，人类文明将会成为历史。

欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### 苹果下一任 CEO 基本敲定：特努斯将接棒库克

*2026 年 1 月 23 日｜来源：快科技*

今年 65 岁的库克自 2011 年从乔布斯手中接过帅印以来，带领市值从 3500 亿美元飙升至近 4 万亿美元，2018 年成为全球首家市值突破 1 万亿美元的上市公司，2022 年又达到 3 万亿美元里程碑。

现在这家巨头要选出新一任 CEO 来接替库克，**特努斯（Ternus）成为热门人选**。据媒体报道，苹果 CEO 库克在 2025 年最后几个月将设计团队交由特努斯负责，扩大了他的职责范围。

不止于此，苹果的软件与硬件设计团队此前由前苹果首席运营官杰夫·威廉姆斯（Jeff Williams）管理，他已于 2025 年从苹果退休。威廉姆斯退休时，苹果曾表示设计团队将直接向库克汇报，但库克已将管理权交给了特努斯。

库克此举旨在让特努斯接触公司各个业务板块，报道称**特努斯将是库克退休后最有可能接任苹果 CEO 的人选**，库克暂无近期退休的计划。特努斯现年 50 岁，是苹果最年轻的高管，若最终升任 CEO，有望长期执掌公司。

资料显示，特努斯 1975 年出生，毕业于宾夕法尼亚大学机械工程专业，2001 年加入苹果产品设计团队，2013 年升任硬件工程副总裁，2021 年晋升为硬件工程高级副总裁，直接向库克汇报工作。

特努斯目前领导苹果硬件工程团队，外界评价其性格沉稳、注重细节、深谙苹果供应链。分析认为，CEO 继任者要面对苹果当前复杂的处境，既需保持全球最盈利公司的地位，又要应对关税、制造业挑战、人工智能领域滞后等问题。

![](https://k.sinaimg.cn/n/spider20260123/137/w600h337/20260123/12cd-323fbedfc3176c5da5d6606f6ea19721.png/w700d1q75cms.jpg?by=cms_fixed_width)

### 苹果第四季度财报前瞻：iPhone 增长放缓，聚焦服务收入

*2026 年 1 月 22 日｜来源：证券市场周刊*

苹果迎来第四季度财报之际，市场预期其财报基调稳健，而非意外上行。硬件需求依然好坏参半，中国市场的不确定性持续存在，股价不再计入强势增长。本次财报关注的重点是执行情况、利润率和服务收入的韧性，而非充满噱头的创新。

考虑到苹果股价现在相对于其历史而言存在较高溢价，因此这次定调很重要。在此背景下，前瞻指引的基调和利润率表现将是决定当前估值是否合理的关键。

![](https://pics2.baidu.com/feed/faf2b2119313b07e88bf02b5939e8f3296dd8ce3.jpeg@f_auto?token=af9eb102f584c40fb8df7c925e3a341d)

市场对于本次苹果（AAPL）财报的关注点主要是：

* iPhone 收入趋势——企稳还是彻底下滑
* 服务收入增长率——15% 左右的增长是最低门槛
* 毛利率——尤其是服务与产品的对比
* 中国市场方面——需求不确定
* 指引基调——保守还是胸有成竹

![](https://pics0.baidu.com/feed/3812b31bb051f819c1bf312845fd54fc2f73e790.jpeg@f_auto?token=14533f7be57373ffd8cfca77848dc3bc)

**服务收入：唯一明确的结构性增长来源**

虽然 iPhone 依然约占苹果收入的一半，但服务收入仍是本财报发布之际唯一明确的结构性增长来源。Mac 和 iPad 的收入呈周期性，而且总体来说是次要方面，很难说会持续增长。

投资者将关注服务收入的增长是否会保持健康的节奏，因为这一分项正日益影响苹果盈利的稳定性。强劲的服务收入势头有助于抵消硬件收入的波动，该分项的任何放缓都难以让市场忽视。

iPhone 周期仍将为整体数据定下基调，但在现阶段，需求走向比规模更为重要。苹果可以接受平缓增长或略微走弱——但是不能出现大幅不及预期。

利润率能最清晰地反映苹果调整收入结构的成效。服务利润率若远高于硬件，这意味着即使平缓的服务增长也能对盈利情况产生巨大影响。

稳定或改善的利润率将证明议价能力和有效的成本控制，就算收入增长依然不乐观也无妨。相比之下，任何实质性的利润率压缩都会引发市场关于需求状况、竞争压力或苹果转嫁成本能力的质疑。

**中国市场区域需求很关键**

中国市场依然是苹果最大的不确定性，这并非因为关税或供应链。该地区的 iPhone 销量越来越多地受到本地竞争等因素的影响，使中国市场成为苹果本应稳定的区域结构中最不可预测的变量。

投资者将密切关注管理层如何谈论中国市场，而非任何单一收入数据。如果对情况的描述是企稳或改善，那么担忧会迅速消退。但更为保守的论调将引发担忧——即使报告中的收入数据坚挺也无用。

![](https://pics2.baidu.com/feed/03087bf40ad162d974acb4a18f96b7fd8b13cdac.jpeg@f_auto?token=ca95bbe0dcebc3920332acba2feedbe3)

自 2012 年以来，苹果一直大量回购股票。这不仅为每股收益带来了节税优化，而且还支撑了估值，但也凸显了公司对资本回报日益仰赖，因为难以实现大规模的原生增长。

即便未宣布有任何战略调整，投资者还是希望能获得自由现金流继续稳健支持持续回购的保证。

和本次发布的诸多内容一样，管理层指引的基调可能比重磅数据更为重要。关于需求、服务收入势头、利润率和资金分配的自信措辞将强化当前叙事，而谨慎或有保留的展望则会迅速将焦点重新集中在估值和下行风险。

这才是市场真正关注的核心。投资者会关注苹果将需求定性为企稳还是面临挑战、服务收入势头是稳健还是趋缓以及 2026 年是否有加速迹象。中性指引和稳定的利润率可能会让市场无动于衷，而谨慎的指引与利润率承压将增加下行风险。

### 苹果计划将 Siri 重塑为内置聊天机器人

*2026 年 1 月 22 日｜来源：每日经济新闻*

据外媒报道，苹果公司计划在今年晚些时候对 Siri 进行重大改造，将其升级为该公司的**首个 AI 聊天机器人**，从而与 OpenAI 和谷歌为主导的生成式 AI 竞争。

据知情人士透露，这款代号为 **Campos** 的聊天机器人将深度嵌入 iPhone、iPad 和 Mac 操作系统，并取代现有的 Siri 界面。聊天机器人功能将在今年晚些时候推出，公司计划在六月的全球开发者大会（WWDC）上首次展示，并在九月正式发布。

国投证券表示，AI 手机方面，根据中国报告大厅预测，2024 年 AI 手机的渗透率预计将达到 16%，预计 2026 年 AI 手机出货量超过 4.7 亿部，渗透率将达到 38%，AI 大模型与智能手机结合有望驱动新一轮换机周期，引领行业发展趋势。

## 提案

### 通过的提案

[SE-0498](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0498-runtime-demangle.md "SE-0498")
**在运行时模块中公开 demangle 功能** 提案已通过审查。

该提案此前已在 **第八十九期周报** 的「正在审查的提案」模块中做过详细介绍。本次通过，标志着 Swift 在运行时类型信息处理能力上又向前迈进了一步。

[SE-0500](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0500-package-manager-templates.md "SE-0500")
**使用自定义模板改进软件包创建：SwiftPM 模板初始化** 提案已通过审查。

该提案此前已在 **第九十期周报** 的「正在审查的提案」模块中做过详细介绍。本次通过，将显著改善 Swift 包管理器的开发体验。

### 正在审查的提案

[SE-0503](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0503-suppressed-associated-types.md "SE-0503")
**抑制与默认值关联类型的默认一致性** 提案正在审查。

关联类型定义了协议中的通用类型。您使用它们来帮助定义协议的要求。此队列有两种关联的类型，元素和分配器：

```swift
/// Queue has no reason to require Element to be Copyable.
protocol Queue<Element>: ~Copyable {
  associatedtype Element
  associatedtype Allocator = DefaultAllocator

  init()
  init(alloc: Allocator)

  mutating func push(_: Element)
  mutating func pop() -> Element
  // ...
}
```

第一个关联类型元素表示必须定义 push 和 pop 的值类型。

任何符合队列的类型都必须定义一个嵌套类型元素，以满足（或见证）协议对其元素的要求。这个嵌套类型可以是名为 Element 的通用参数，名为 Element 的类型别名，等等。虽然符合队列的类型是不可复制的，但其元素类型必须是可复制的：

```swift
/// error: LinkedList does not conform to Queue
/// note: Element is required to be Copyable
struct LinkedList<Element: ~Copyable>: ~Copyable, Queue {
  ...
}
```

这是因为在 SE-427：不可复制的通用性中，推断出 Queue.Element 既是可复制又可逃避的隐性要求，没有办法抑制它。这在实践中是一种表达性限制，因为它阻止了 Swift 程序员根据不可复制或不可逃逸的关联类型来定义协议。

[SE-0504](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0504-task-cancellation-shields.md "SE-0504")
**任务取消屏蔽** 提案正在审查。

该提案引入了一种暂时"忽略"任务取消的新机制，称为任务取消屏蔽。

这可用于确保无论任务的取消状态如何，某些代码都会执行。一个有用的常见情况是运行清理代码，无论任务的取消状态如何，都必须执行该代码。

该提案与最近在 SE-0493 中引入的异步递延语句很好地吻合：支持 async 调用 in defer 主体，这些语句经常用于表达此类资源清理功能。

[SE-0505](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0505-delayed-enqueuing.md "SE-0505")
**执行者延迟排队** 提案正在审查。

（这之前是作为自定义主和全局执行者提案的一部分提出的，但在这里已分为单独的提案。）

Swift 并发运行时提供了一些 C 入口点，允许代码在延迟后或某个时间点在全局执行器上安排作业。这些切入点并不理想；特别是：

* `swift_task_enqueueGlobalWithDelay` 不支持公差，只会使用连续时钟，并且只会在全球执行器上安排
* `swift_task_enqueueGlobalWithDeadline` 时间戳表示为两个 long long，一个表示秒，一个表示纳秒，使用类似的公差格式（或"回旋余地"）。它仅支持内置时钟，并且只会在全局执行器上进行调度

Executor 协议已经为 Swift 代码提供了对作业进行队列的方法，它还应该为 Swift 代码提供一种延迟或截止日期进行队列的方法，这是有道理的。

## Swift 论坛

### 1、提案：允许 `reduce` 产生不可拷贝（noncopyable）结果

作者：Ben Cohen ｜ 发布日期：2026 年 1 月 12 日
[阅读原帖](https://forums.swift.org/t/pitch-allow-reduce-to-produce-noncopyable-results/84073 "Pitch: Allow reduce to produce noncopyable results")

该 pitch 提议**扩展 `Sequence.reduce` 系列 API**，让它们能够：

* 支持 **不可拷贝类型（noncopyable types）** 作为累积结果
* 将累积初始值以 **consuming（消费）** 方式接收，而不是借用，从而避免不必要的拷贝

**动机：**
`reduce` 目前假定初始值是可拷贝的，会在内部复制这份值，这对于不可拷贝类型无法工作。通过让参数以 consuming 语义传入，就可以把值"拿过来"更新，而不需要借用/拷贝，从而让 `reduce` 可用于更多类型。

**主要修改示例：**

```swift
extension Sequence {
  public func reduce<Result: ~Copyable>(
    _ initialResult: consuming Result,
    _ nextPartialResult:
      (_ partialResult: consuming Result, Element) throws -> Result
  ) rethrows -> Result

  public func reduce<Result: ~Copyable>(
    into initialResult: consuming Result,
    _ updateAccumulatingResult:
      (_ partialResult: inout Result, Element) throws -> ()
  ) rethrows -> Result
}
```

这种写法消除了对初始值的隐式拷贝，并允许不可拷贝类型参与归约逻辑。

**讨论亮点：**

* 这种更通用的 `reduce` 与现有习惯一致，`reduce(into:)` 本身已经是 consuming 的
* 社区提出是否也应将类似语义推广到 `AsyncSequence.reduce` 等
* 改动不会破坏现有源码兼容性，但会影响 ABI 调用约定，需要兼容入口保留

**简要点评：**
这是一个贴合 Swift 所有权模型演进方向的提案，将显著提升不可拷贝类型在集合操作中的可用性。

### 2、SE-0504：任务取消屏蔽（Task Cancellation Shields）

作者：John McCall ｜ 发布日期：2026 年 1 月 12 日
[查看提案](https://forums.swift.org/t/se-0504-task-cancellation-shields/84095 "SE-0504: Task Cancellation Shields")

这个提案进入**正式审查阶段**，目标是为 Swift 并发提供一个 API，让你可以在某段异步代码内部**屏蔽（shield）任务取消的可见性** —— 即使父任务已被取消，在这段代码里仍然不"看到"取消状态。

**动机：**
当前没有语言级支持使某些清理或关键代码在取消传播时仍然运行。开发者通常不得不手动创建无结构任务（unstructured task）作为 workaround，这会引入调度延迟和不确定性。shields 提供一种更精确的行为控制。

**核心 API（草案）：**

```swift
public func withTaskCancellationShield<Value>(
  _ operation: () async throws -> Value
) async throws -> Value
```

以及其同步版本，用于屏蔽取消感知，同时运行代码。

**社区讨论要点：**

* 有人认为这个特性对资源清理或第三方库调用非常有用
* 如何命名（shield vs ignore vs defer）引发了深入讨论，因为要准确传达语义
* shield 并不阻止任务实际上被取消，它只是让当前范围内调用 `Task.isCancelled` 返回假，从而不触发取消逻辑

**简要点评：**
该提案旨在增强 Swift 并发，让开发者控制任务取消的可见性，有助于更可靠的清理逻辑，但命名与语义解释仍是社区关注点。

### 3、提案：为 `RawSpan` 提供安全加载值 API

作者：Guillaume Lessard ｜ 发布日期：2026 年 1 月 14 日
[阅读原帖](https://forums.swift.org/t/pitch-2-safe-loading-of-values-from-rawspan/84144 "Pitch: Safe loading of values from RawSpan")

这篇 pitch 提议在标准库中引入一组**安全的 API 用于从 `RawSpan` 载入值**，以及相应的从 `RawSpan` 到 `Span` 的安全转换。

**动机：**
`RawSpan` 目前带有一些不安全（unsafe）方法来从原始内存读取任意类型。虽然原始整数类型可以安全读取，但不安全标记让用户总是心存疑虑。该提案希望提供边界检查、安全加载值接口及控制字节序（endianness）的支持。

**核心设计：**

* 引入新约束 `FullyInhabited` —— 强调类型对于每一种可能的位模式都有合法值
* 为满足条件的类型（例如整数、浮点型等）提供安全 `load(as:)` 方法：

```swift
extension RawSpan {
  func load<T: FullyInhabited>(
    fromByteOffset: Int = 0,
    as: T.Type = T.self
  ) -> T
}
```

* 对于整数类型，还提供支持指定字节序的重载版本

**其他改进：**

* `MutableRawSpan` 增加带字节序控制的 `storeBytes` 方法
* `Span` 添加通过 `RawSpan` 构造的安全初始化器

**社区讨论亮点：**

* 类型是否真的能完全符合 `FullyInhabited`、padding 字节是否安全等问题被热议
* 是否允许手动声明某些结构体也能安全 conform 于 `FullyInhabited`

**简要点评：**
该提案希望减少 unsafe API 使用，让 `RawSpan` 提供更安全、界限检查的内存读取机制，对二进制解析、网络字节操作等场景非常有用。

### 4、讨论：在包生态中推广 `import FoundationEssentials`

作者：Mads Odgaard ｜ 发布日期：2026 年 1 月 13 日
[阅读原帖](https://forums.swift.org/t/the-adoption-of-import-foundationessentials-throughout-the-package-ecosystem/84112 "The adoption of import FoundationEssentials throughout the package ecosystem")

这个讨论聚焦于 Swift 包生态中 **推广使用 `import FoundationEssentials` 代替传统 `import Foundation`**，以减少二进制体积和依赖重量级 ICU 国际化库的问题，这在 Android 等平台对体积敏感的情境下尤为重要。

**主要背景：**

* 在 Android 等环境下，包含完整的 ICU 国际化数据会显著增加最终二进制尺寸，这阻碍了 Swift 在这些生态中的采用
* `FoundationEssentials` 是 Foundation 的一个更轻量的子集，包含核心 API，而不依赖 ICU 国际化组件

**生态挑战：**

* Swift 当前 **会向外泄露导入库的公共 API**（public API of imports），因此简单替换 import 会造成**源不兼容**，需要发布主版本升级
* 多个流行库已有人尝试引入 `import FoundationEssentials`，但因兼容性限制难以全面推广

**社区观点：**

* 有人支持强制切换并接受破坏性变更，以改善整体生态体积问题
* 也有人担心现有生态兼容性及某些依赖完整 Foundation 功能的包无法轻易迁移

**简要点评：**
该讨论旨在推动更轻量化的基础依赖，对于希望减小 Android/Linux/嵌入式平台大小的 Swift 项目尤为重要，但涉及兼容性牵引，需要包维护者协作。

### 5、提案：标准库添加获取当前可执行文件路径的 API

作者：Jonathan Grynspan ｜ 发布日期：2026 年 1 月 14 日
[阅读原帖](https://forums.swift.org/t/pitch-api-to-get-the-path-to-the-current-executable/84137 "API to get the path to the current executable")

这个 pitch 提议在 Swift 标准库中提供一个**统一 API 来获取当前可执行文件的路径**，避免开发者依赖平台特定方法或高层 API（比如 `Bundle.executableURL`）。

**动机：**
许多命令行工具、测试框架和跨平台代码需要在运行时知道自身的可执行路径，但目前只能依赖平台特定 API 或绕过实现细节。提供统一 API 可以让 Swift 项目更便捷地处理如路径查找、资源定位等需求。

**示例：**

```swift
if let executablePath = CommandLine.executablePath {
  // 使用 path 做进一步处理
}
```

**讨论重点：**

* 该 API 仅返回当前执行的可执行文件路径，并不会执行查找其他二进制
* 在测试环境下，返回的路径可能是测试运行工具本身（如 Xcode 的 xctest），因此应文档说明行为
* 社区建议将结果设为 Optional 返回以处理不支持的平台或无法解析的场景

**简要点评：**
该提案希望让 Swift 标准库直接支持可执行路径获取，提高跨平台一致性，简化工具和框架内对自身路径的访问逻辑。

## 推荐博文

以下三篇文章非常值得一读，适合本周"提升技能 + 开阔思路"：

[深入理解 Swift Concurrency：从 async/await 到隔离域](https://juejin.cn/post/7593736655611936768/ "深入理解 Swift Concurrency：从 async/await 到隔离域")

**摘要：** 这篇技术文章讨论了 Swift 并发编程（Swift Concurrency）如何从根本上改变了开发者处理异步任务的方式。

它指出，核心的范式转变是从手动管理"线程"转向由编译器强制执行的"隔离"。通过 async/await、Task 的结构化生命周期管理，特别是 @MainActor 和 actor 构建的隔离域，Swift 在编译阶段就建立了清晰的数据访问规则。这套机制旨在从源头消除数据竞争，让开发者能更安全、更清晰地编写并发代码，而不必再深陷于复杂的线程同步细节之中。

[Flutter iOS 应用在混合开发场景下的混淆与保护方式](https://juejin.cn/post/7597252004713021482/ "Flutter iOS 应用在混合开发场景下的混淆与保护方式")

**摘要：** 这篇文章讨论了 Flutter 混合开发中一个容易被忽视的问题：iOS 端的安全保护。文章指出，尽管项目使用 Flutter，但应用的安全性并不会自动得到保障，逆向分析者往往更关注 iOS 原生的可执行文件和资源。

因此，核心思路是在工程上采取一种务实策略：不过度追求激进的源码混淆，而是将重点放在最终的 IPA 产物上。通过工具对 iOS 二进制文件进行符号混淆、对资源文件进行重命名处理，在破坏代码可读性、增加分析成本的同时，优先确保应用功能的稳定性。这种做法更适合已上线的、构建流程复杂的 Flutter 项目，能以较低的工程代价，有效提升 iOS 侧的安全门槛。

[iOS Accessibility 开发指南](https://juejin.cn/post/7529562624553467955/ "iOS Accessibility 开发指南")

**摘要：** 这篇文章是 iOS 无障碍功能开发的综合指南，旨在帮助开发者创建对所有用户都友好的应用。

文章指出，构建无障碍应用的核心是理解并实现几个关键组件：为视障用户朗读界面的 VoiceOver、允许自由调整文字大小的动态类型、以及为运动障碍用户提供替代交互的开关控制等。

在实践层面，开发者需要为 UI 元素设置清晰的语音标签和提示，确保文字与背景有足够的对比度，并让自定义控件支持无障碍交互。测试环节同样重要，应主动使用 VoiceOver 和无障碍检查器来验证体验。

全文贯穿的核心思想是，无障碍支持并非事后的功能添加，而应是应用设计与开发过程中一项基础且必要的考量，这直接关系到应用的专业性与包容性。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 "进群" 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。

