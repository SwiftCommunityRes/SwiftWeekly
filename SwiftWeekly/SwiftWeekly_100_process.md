## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

一朵花凋零荒芜不了整个春天，一次跌倒也荒废不了整段人生。坚持走下去，凭着耐心和拼搏，生活自会给予你全部答案。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：消息称新版苹果Siri大升级 支持自动删除聊天记录
> * **提案**：
> * **Swift 论坛**：
> * **推荐博文**：

上期话题投票结果如下：



## 话题讨论

### 本期话题：


欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### 消息称新版苹果Siri大升级 支持自动删除聊天记录

*2026 年 5 月 18 日｜来源：TechWeb*

5 月 18 日消息，据马克 · 古尔曼最新爆料，苹果将在 WWDC 2026 大会上发布全新改版的 Siri，这次升级不仅让 Siri 首次以独立应用形态亮相，还正式搭载谷歌 Gemini 大模型。

根据公开报道，苹果已与谷歌达成多年合作协议，将 Gemini 大模型深度集成至 Siri 及苹果基础模型底层。新版 Siri 采用“苹果设计+谷歌算力”的混合架构，前端交互与用户体验仍由苹果把控，后台则由 Gemini 负责处理复杂的多轮对话、语义理解和任务规划。这将使得 Siri 得以迅速补齐生成式对话能力，具备与 ChatGPT 等主流产品正面竞争的实力。

此次升级在强化智能能力的同时，重点加码隐私保护，新增聊天记录自动删除功能，采用私有云端计算架构，且所有用户数据不会用于谷歌的模型训练。

今日，“全新 Siri 自动删除聊天记录”话题冲上热搜。有网友表示，“新版 Siri 的聊天记录可以设 30 天或一年后自动删，这倒是挺方便的，不过如果突然要找聊天记录可就不好找了。”

![](https://upload.techweb.com.cn/s/1080/imgs/2026/0518/1779071818731.png)

此外，新版 Siri 还将带来全新的对话界面，一种是类似 ChatGPT 的全新对话界面，另一种则是仿短信样式的对话列表界面，以进一步提升交互体验。

根据爆料，全新 Siri 将以测试版形式在 WWDC 2026 首发，并随今年秋季的 iOS 27、iPadOS 27 及 macOS 27 系统正式推送。

### 消息称苹果iPhone Fold / Ultra折叠屏手机试产受阻

*2026 年 5 月 18 日｜来源：IT之家*

5 月 16 日爆料，苹果 iPhone Fold / Ultra 折叠屏手机近期试产阶段受阻，现在的核心卡点是铰链，长期高频开合后的可靠性始终达不到苹果的品控及格线。必须要超级完美的解决这个机械损耗问题，不然进度暂时只能硬拖着。

该博主还称，关于屏幕折痕，苹果基本默认接受了，目前的测试结果确实做到了“长期稳定保持”视觉无折痕的状态。

至于铰链的具体问题，该博主称“这些事等一切尘埃落定后再具体聊吧，不然我又得面临风险了”。

![](https://pics5.baidu.com/feed/b8389b504fc2d562c68174ac183623fe77c66c9b.jpeg@f_auto?token=7311fe52e9b5ee2d1c6e5885976370ae)

该博主还谈到苹果 iPhone 数字 Pro 系列的后续路线，表示苹果内部比谁都清楚 iPhone 17 Pro 这代开始的铝合金是个妥协产物，等找到能维持重量和散热平衡点的材料后一定会换材料。

1、液态金属。但要实现苹果级的大规模量产难度很大，但只要 iPhone 折叠屏用上了，就等于这套工艺跑通了，那么成本也就会下来，最后数字 Pro 系列就有机会采用。

2、钛。刹那之前也一直跟你们说苹果内部对手机用上钛金属是引以为傲的，17 Pro 用铝完全是被逼的妥协。这是真的，所以苹果至今也没有放弃钛，似乎在研究改良版，目的就是要改变原先钛合金导热差的问题，同时在保持同等体积下把重量再压一压。具体我还不太清楚，但新配方成熟后，我相信苹果还会用回钛金属。

![](https://pics7.baidu.com/feed/e7cd7b899e510fb3cfaa3108d91b7b84d0430cb3.jpeg@f_auto?token=908647bbd7737dba5660973e01eebbb5)

### 丰富供应链 苹果正在英特尔测试18A芯片量产

*2026 年 5 月 16 日｜来源：PChome科技*

5 月 16 日消息，据知名分析师郭明錤最新发布的行业报告证实，苹果公司已正式与英特尔展开芯片生产合作，在美国本土工厂测试基于英特尔 18A-P 制程工艺的苹果硅芯片，这标志着苹果长期以来高度依赖台积电的芯片供应链多元化战略迈出实质性一步。

本月初已有行业消息传出，苹果正积极寻求将芯片制造业务从单一供应商台积电分散，英特尔和三星均被列为潜在合作伙伴。郭明錤的最新报告进一步确认了这一进展，并披露了更多合作细节。

![](https://pics6.baidu.com/feed/7c1ed21b0ef41bd5d538cd0bcc1731da3bdb3dc0.jpeg@f_auto?token=f724cbc78144b45f82eb923a3bd46803)

据了解，双方目前正在英特尔工厂进行基于 18A-P 工艺的苹果硅芯片小规模试生产。该工艺技术水平与台积电用于制造 A18 Pro 芯片的制程相当，此次生产的主要是面向入门级市场的芯片产品，将广泛应用于 iPhone、iPad 和 Mac 产品线。郭明錤估算，其中约 80% 的芯片将用于 iPhone 系列机型，所有芯片均由英特尔在美国本土工厂制造。

报告同时公布了双方合作的时间规划，2026 年全年将维持小规模测试生产状态，计划于 2027 年至 2028 年逐步扩大产能规模，随后在 2029 年根据测试结果和市场需求逐步缩减产能。此外，苹果还在同步评估英特尔后续推出的更先进制程节点，为未来更深层次的合作预留空间。

尽管苹果加速推进供应链多元化，但台积电仍将在相当长一段时间内保持其核心供应商地位。郭明錤预测，未来几年台积电仍将占据苹果硅芯片总供应量的约 90% 份额。

行业分析认为，苹果此举主要是为了降低地缘政治风险和供应链过度集中带来的潜在隐患，同时也为英特尔重振其半导体代工业务提供了重要机遇，或将对全球半导体代工市场格局产生深远影响。

## 提案


## Swift论坛

### 1、`Iterable` 修订提案：从 `BorrowingSequence` 到通用借用迭代

作者：Nate Cook ｜ 发布日期：2026 年 5 月 20 日
[阅读原帖](https://forums.swift.org/t/revision-pitch-iterable-formerly-borrowingsequence/86834 "[Revision/Pitch] Iterable (formerly BorrowingSequence)")

核心内容：SE-0516 的修订版将原来的 **BorrowingSequence** 重命名为 **Iterable**，目标是为同步迭代提供一个更通用的协议基础。新协议允许类型本身、元素类型和迭代器是 **noncopyable** 或 **nonescapable**，并且支持在迭代过程中抛出具体错误类型。

动机说明：现有 **Sequence** 诞生较早，默认围绕可复制元素和 `IteratorProtocol.next() -> Element?` 建模，难以自然表达 **Span**、**InlineArray** 以及非复制元素的借用式遍历。提案希望通过按批返回 `Span<Element>`，减少复制需求，并让连续内存场景有更好的优化空间。

主要修改包括：协议名改为 **Iterable**；迭代器协议改为 **IterableIteratorProtocol**；新增 `Failure: Error = Never` 关联类型；核心入口从 `makeIterator()` 变为 `makeIterableIterator()`，迭代器通过 `nextSpan(maximumCount:)` 返回一段元素。

```swift
public protocol Iterable<Element, Failure>: ~Copyable, ~Escapable {
  associatedtype Element: ~Copyable
  associatedtype Failure: Error = Never
  associatedtype IterableIterator: IterableIteratorProtocol<Element, Failure>

  @_lifetime(borrow self)
  func makeIterableIterator() -> IterableIterator
}
```

讨论亮点集中在 **for-in** 如何对 **Iterable** 进行语法脱糖、抛错迭代是否需要 `for try`、以及泛型算法在元素生命周期受限时能否实现类似 `first(where:)`、`elementsEqual` 等操作。简要点评：这是一项面向 Swift 所有权模型长期演进的基础设施改造，短期会增加标准库协议层复杂度，但能为 **Span**、**~Copyable** 和高性能容器打开更自然的迭代接口。

### 2、用 `Disconnected` 在类型系统中表达断开隔离的值

作者：Franz Busch ｜ 发布日期：2026 年 5 月 19 日
[阅读原帖](https://forums.swift.org/t/pitch-disconnected-type-for-modeling-disconnected-values/86815 "[Pitch] Disconnected type for modeling disconnected values")

核心内容：该 pitch 提议在标准库中加入 **Disconnected<Value>**，用于把一个值标记为处于断开隔离区域，从而在容器、队列等数据结构中保存并传递这种属性。它尤其面向 **region-based isolation**、**sending** 和非 **Sendable** 值跨隔离域转移的场景。

动机说明：SE-0414 和 SE-0430 让函数边界可以要求或返回 `sending` 值，但 `sending` 是函数签名属性，无法被普通存储属性、集合或泛型容器长期保留。例如一个队列既可能存储普通非 **Sendable** 值，也可能存储可跨隔离域移动的断开值，直接把容器 API 都改成 `sending` 会限制其他合法用法。

提案中的包装类型大致如下：

```swift
@frozen
public struct Disconnected<Value: ~Copyable>: ~Copyable, Sendable {
  public init(_ value: consuming sending Value)
  public var value: Value { borrow }
  public consuming func take() -> sending Value
}
```

使用时，容器保存的是 `Disconnected<NonSendable>`，取出后通过 `take()` 消费包装并得到 `sending` 值，再把它移动到新的任务或隔离区域。

讨论亮点在于：`Disconnected` 无条件符合 **Sendable** 是否足够直观、借用访问器 `value` 如何维持断开不变量、以及它与 SE-0519 的容器借用访问器如何组合。简要点评：这个类型把并发隔离中的一个隐含状态显式建模，对编写异步算法和通用容器很有价值，但它也要求开发者更准确地区分“值可发送”和“值已断开”这两层语义。

### 3、SE-0531：Literal Expressions 进入审查

作者：Ben Cohen ｜ 发布日期：2026 年 5 月 19 日
[阅读原帖](https://forums.swift.org/t/se-0531-literal-expressions/86794 "SE-0531: Literal Expressions")

核心内容：SE-0531 进入正式审查，审查期为 2026 年 5 月 19 日至 5 月 29 日。提案引入 **Literal Expressions**，允许编译器在特定上下文中对整数文字、标准库整数运算符以及可编译期求值的整数常量引用进行常量折叠。

动机说明：当前 **enum raw values**、`@section` 变量初始化和 **integer generic arguments** 等位置往往只能写裸整数，开发者需要手工计算并维护“魔法数字”。提案希望让意图直接保留在源码中，例如页大小、位标志和 `InlineArray` 长度都可以由表达式推导。

典型示例如下：

```swift
let pageSize = 4 * 1024
let bufferSize = 16 * pageSize

enum Permissions: Int {
  case read = 1 << 0
  case write = 1 << 1
  case execute = 1 << 2
}

let buffer: InlineArray<(2 * pageSize), UInt8>
```

主要限制是：表达式结果必须是标准库整数类型；支持算术、位运算、移位和部分一元运算；用户自定义运算符不会被当作 literal expression；公开可见常量引用暂不允许参与折叠，以避免把初始化表达式变成 ABI 承诺。

讨论亮点包括 Jordan Rose 对“literal expressions”命名的质疑，认为该特性更像受限的编译期整数表达式；也有人建议称为 **Integer Literal Expressions**。简要点评：这项改动非常务实，能明显改善底层、嵌入式和泛型值参数代码的可读性；争议主要不在能力本身，而在命名和未来扩展边界。

### 4、SE-0526 第二轮审查：`withDeadline` 简化错误与取消语义

作者：Frederick Kellison-Linn ｜ 发布日期：2026 年 5 月 18 日
[阅读原帖](https://forums.swift.org/t/second-review-se-0526-withdeadline/86791 "[Second Review] SE-0526: withDeadline")

核心内容：SE-0526 **withDeadline** 开启第二轮审查，审查期至 2026 年 5 月 31 日。该 API 为异步操作提供基于绝对时间点的截止期限，过期时取消操作，并按照操作自身的返回或抛错结果继续传播。

动机说明：手写超时逻辑通常需要任务组、时钟 sleep、取消传播和竞态处理，代码冗长且难以组合。使用绝对 **deadline** 而不是相对 timeout，可以让多层调用共享同一个截止时刻，避免时间在调用链中逐层漂移。

本轮修订删除了 `Task.currentDeadline`，移除了跨时钟 deadline 组合约束，取消了包装用的 `DeadlineError`，改为直接转发 body 抛出的错误；同时 **CancellationError** 增加 `reason`，用于在 deadline 过期触发取消时携带原因。

```swift
let clock = ContinuousClock()
let deadline = clock.now.advanced(by: .seconds(5))

let result = try await withDeadline(deadline, clock: clock) {
  try await fetchDataFromServer()
}
```

讨论亮点包括：`withDeadline` 命名是否足够准确、`throws(Failure)` 与取消错误的关系、`CancellationError.reason` 的精确定义，以及 `custom(String)` 是否会带来额外成本或滥用空间。简要点评：第二轮修订明显收敛了 API 表面，错误传播更符合 Swift 的类型化错误方向；剩余关键问题是取消原因的模型需要足够严谨，否则会影响并发运行时的实现和使用预期。

### 5、Typed throws 下 `rethrows` 不能保留具体错误类型的讨论

作者：Tiago Canto ｜ 发布日期：2026 年 5 月 20 日
[阅读原帖](https://forums.swift.org/t/rethrows-does-not-seem-to-work-correctly-with-typed-throws/86843 "Rethrows does not seem to work correctly with typed throws")

核心内容：帖子讨论 **typed throws** 与 **rethrows** 的交互。发帖者发现一个 `transaction(operation:) rethrows` 包装函数虽然只调用传入闭包，但编译器并不会把闭包的具体错误类型 `DatabaseError` 保留下来。

原始示例中，`transaction` 的闭包声明为 `() throws(DatabaseError) -> Void`，但函数本身使用 `rethrows`：

```swift
struct Database {
  func transaction(operation: () throws(DatabaseError) -> Void) rethrows {
    try operation()
  }

  func saveUser() throws(DatabaseError) {
    try transaction {
      throw .connectionLost
    }
  }
}
```

讨论中指出，`rethrows` 只表达“只有当参数抛错时才抛错”，并不承诺“抛出同一种错误”。在 **typed throws** 可用后，更推荐把错误类型写成泛型参数，并让函数显式 `throws(E)`。

```swift
func transaction<E>(
  operation: () throws(E) -> Void
) throws(E) {
  try operation()
}
```

讨论亮点来自 Slava Pestov 的说明：有了 **typed throws** 后，许多 `rethrows` 场景可以改为泛型 `throws(E)`，其中 `Never` 也符合 `Error`，可表示非抛错路径。但后续回复也指出，可选闭包默认值、错误类型推断和“只有回调抛错时才改抛另一种错误”等场景仍让 `rethrows` 有残余价值。简要点评：这次讨论很好地澄清了 `rethrows` 的语义边界，也提醒库作者在迁移到 **typed throws** 时不要机械替换，而要检查错误类型推断和默认参数对调用体验的影响。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[iOS全栈开发最新技术动态与工程实践指南](https://blog.csdn.net/a1062051470/article/details/161105594/ "iOS全栈开发最新技术动态与工程实践指南")

**摘要：** 这篇技术指南全面梳理了2026年iOS生态的核心技术栈。文章从开发工具与语言层面切入，系统介绍了Xcode 26.5内置的AI智能编程助手、Swift 6.3.2的并发安全强化与泛型改进，以及模块编译优化在包体积和启动速度方面的显著收益。在SwiftUI 6生产级普及方面，文章详细阐述了类型安全路由导航、原生液态玻璃效果、3D数据图表等核心特性，明确指出现代iOS开发正进入以SwiftUI为主、UIKit兜底的商业项目最佳实践阶段。全文为iOS开发者提供了一份涵盖性能优化、端侧AI集成、隐私合规等环节的工程能力升级路线图，兼具技术前瞻性与生产指导价值。

[Swift-Testing 项目对WASI平台支持的探索与实践](https://blog.gitcode.com/6fefb3ba362b886d34c121a79655fc38.html/ "Swift-Testing 项目对WASI平台支持的探索与实践")

**摘要：** 这篇实践探索文章，系统梳理了苹果官方新一代测试框架 Swift-Testing 向WASI（WebAssembly System Interface）平台移植过程中遇到的技术挑战与解决方案。文章指出，核心障碍出现在编译器插件系统的标准库兼容性层面：标准文件描述符操作函数（如dup、dup2等POSIX 调用）在 WASI 环境中不可用，标准输入输出重定向机制存在差异，同时 Swift Package Manager 在传递编译目标三元组时存在缺陷，这些都直接影响了 Swift-Testing 依赖的 SwiftSyntax 编译器插件在 WASI 环境下的正常构建。解决方案需要工具链各组件（WASI SDK、SwiftPM、编译器）的协同改进，而非单一项目能够独立完成。目前项目已通过实验性方式初步支持 WASI 平台，主要得益于SPM对WASI目标三元组处理的改进与社区开发者持续的适配测试。全文指出，随着 Swift 生态向 WebAssembly 扩展， WASI 支持将成为Swift跨平台能力的重要指标，而 Swift-Testing 框架在这一领域的探索为整个生态系统提供了宝贵的参考经验。

[使用 SyntaxKit 创建宏](https://swiftpackageindex.com/brightdigit/syntaxkit/0.0.3/documentation/syntaxkit/creating-macros-with-syntaxkit/ "使用 SyntaxKit 创建宏")

**摘要：** 这篇官方文档教程，通过构建一个完整的#stringify宏从零到一的实战流程，系统介绍了如何使用SyntaxKit（Swift宏开发辅助库）的声明式语法创建自定义 Swift 宏。教程涵盖了宏开发的全生命周期：创建宏包结构、配置 Package.swift 依赖、编写宏实现逻辑、创建宏插件、暴露公共 API 、建立客户端测试示例以及完整的测试与运行。文章指出， Swift 宏开发需要两个独立的包——一个用于宏声明，一个用于宏实现——并通过 #stringify 宏具体展示了如何接收两个表达式、返回包含其求和结果与源代码的元组。全文为希望利用 Swift 宏系统精简重复逻辑、提升编译时安全性的开发者提供了一份零门槛的实操指南。




## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
