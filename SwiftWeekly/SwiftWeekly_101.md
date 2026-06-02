## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百零一期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

也许走遍了全世界，最后才会发现，美丽的风景就在你我的脸颊，让嘴角微微上扬，便收获了最灿烂的笑容。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：iOS 27 将「彻底重做」Siri，系统级整合 AI + Gemini 混合推理；苹果加码端侧 AI；MacBook Neo 或受台积电 3nm 涨价冲击
> * **提案**：SE-0527 正式通过；SE-0531～SE-0533 正在审查
> * **Swift 论坛**：`Iterable` 修订、`Disconnected` 类型、SE-0531 字面表达、SE-0526 `withDeadline` 二轮审查、typed throws 与 `rethrows`
> * **推荐博文**：Swift 并发调度真相、300 界面 SwiftUI 迁移复盘、Swift 手写 LLM 矩阵乘法优化

上期话题投票结果如下：

![](https://files.mdnice.com/user/38782/e81fff28-034e-4945-9485-7dc0041693e0.jpg)

**「看价格和续航」以约 32% 居首，「完全没兴趣」与「AI 真的好用才考虑」合计近半——读者对 AI 智能眼镜普遍持理性观望态度，苹果若入局需先证明实用价值，而非仅靠品牌号召力。**

## 话题讨论

**WWDC 2026 即将发布「彻底重做」的 Siri，你最期待哪一点？**

1. 真正好用的对话与任务执行能力
2. 端侧运行 + 隐私保护
3. 与 iOS 系统深度整合（相机、搜索、灵动岛等）
4. 独立 App 形态与多模态交互
5. 先观望，等实际体验再说

欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### iOS 27 爆料：苹果「彻底重做」Siri，系统级整合 AI

*2026 年 5 月 29 日｜来源：华尔街见闻*

据彭博援引知情人士，苹果计划在 **6 月 8 日 WWDC** 发布 **iOS 27**，对 **Siri** 进行近 15 年来最大规模重构：重新设计界面、引入 **Google Gemini** 底层模型、AI 驱动网页搜索，以及对标 ChatGPT 的**独立 Siri 应用**；预计最早 **9 月**随 iPhone 18 Pro 系列及首款折叠屏 iPhone 面向消费者推送。美银将苹果目标价从 330 美元上调至 380 美元，估算全新 Siri 到 2030 年或带来最高 **650 亿美元**增量收入；成败也将影响苹果在与 OpenAI、谷歌、三星竞争中的位置。这可能是库克 CEO 任内最后一次重大发布，此后领导权将移交给 **John Ternus**。

**系统级执行层：** 新版 Siri 以「常驻代理」形式内嵌**灵动岛**，可调用设备个人数据、网页与屏幕信息；支持语音/长按电源键启动，或从屏幕顶部中央下滑唤出「搜索或提问」界面（打字 + 语音双模），通知中心入口调整至左上角下滑。独立 Siri App 含对话历史、多轮会话与文档/图片附件，结果页继续下滑可进入完整对话视图。

![](https://files.mdnice.com/user/38782/c7a1eb5a-db01-421e-9f88-0e28244f1dac.png)

**Gemini + 混合推理：** 苹果将用完整 Gemini 对本地小模型**蒸馏**以实现端侧推理；万亿级 Gemini 仍部分依赖谷歌云，苹果已批准在谷歌云采用英伟达**机密计算**保护隐私，并可能继续沿用 Private Cloud Compute 品牌表述；同时考察收购端侧 AI 初创 **Liquid AI** 等以压缩模型体积。

**相机与照片：** Siri 首次整合进相机（与照片、视频并列），取代「视觉智能」，支持第三方 AI 分析与谷歌图片反向搜索；相机可定制快捷栏；相册新增 **Reframe**（调整视角）与 **Extend**（AI 延伸画面）工具。

![](https://files.mdnice.com/user/38782/8472a9b8-92f4-4b0f-8cfc-db3c3083914f.png)

**估值逻辑：** 2025 财年服务收入占约 26%、毛利占约 42%，AI 入口若提升服务使用频率，对利润杠杆显著；潜在增量含 Apple Intelligence Pro 订阅、模型路由费、代理式电商抽成等。最大不确定性仍是 Siri 曾多次令市场失望，若用户习惯已迁移至 ChatGPT / Gemini / Claude，苹果可获取的 AI 价值将大幅缩水。**以官方发布为准**。

### 苹果加码端侧 AI，发力脱离云端运行模式

*2026 年 5 月 28 日｜来源：新浪财经*

WWDC 上延期已久的 iPhone AI 功能升级将是重头戏；苹果有望亮出自研芯片十五年来在**终端本地运行 AI** 的积累——全球数十亿台设备汇聚的算力，据分析师估算相当于价值 **500 亿美元**的算力资源，且由用户共同承载。相较 Meta / 微软动辄数百亿至千亿美元级数据中心资本开支（苹果 2025 财年仅约 127 亿美元），苹果选择将更多推理下放至端侧，兼顾隐私、企业降本（减少云端 token）与资本效率。

部分复杂查询仍走云端：新版 Siri 部分指令将调用谷歌 Gemini，并采用英伟达机密计算；苹果正用 Gemini **蒸馏**训练本地轻量化模型，并考察收购 **Liquid AI** 等。行业观点分化：有人曾批评苹果 AI 投入保守，也有从业者认为「绝大多数运算终将转移至边缘终端」，苹果或押对方向；webAI 等企业已在 iPad / Mac 上离线运行行业专属模型。**以官方发布为准**。

![](https://files.mdnice.com/user/38782/60f571ac-ccd7-44f9-860b-b783525c0b1f.png)

### MacBook Neo 或受冲击：台积电 3nm 连续涨价

*2026 年 5 月 28 日｜来源：科创板日报*

**MacBook Neo** 基础款（599 美元）使用 iPhone 16 Pro 产线筛选余留的 **A18 Pro** 芯片以压低成本；随着余料耗尽，苹果需向台积电追加订单，而 3nm 产能紧张（Fab 18 月产能已从约 13 万片升至 16–17.5 万片，仍难满足 AI 芯片需求）。消息称台积电下半年 3nm **涨价 15%**、明年再涨 **10%**，苹果或面临停产 599 美元基础款（等效涨价约 100 美元）的抉择。另有传闻苹果可能将部分制造转交 **Intel**（如下一代 Neo 用的 A27），以分散供应链风险。**以官方信息为准**。

![](https://files.mdnice.com/user/38782/31d15388-bbd5-4fce-9982-b88a9401c43d.png)

## 提案

### 通过的提案

[SE-0527](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0527-rigidarray-uniquearray.md "SE-0527")
**RigidArray 和 UniqueArray** 提案已通过审查。

该提案此前已在 **第九十九期周报** 的「正在审查的提案」模块中做过详细介绍。

### 正在审查的提案

[SE-0531](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0531-literal-expressions.md "SE-0531")
**字面表达（Literal Expressions）** 提案正在审查。

在 **enum raw values**、**@section** 变量初始化、**integer generic arguments** 等位置，允许使用整数文字、标准库整数运算符及可编译期求值的整数常量引用进行常量折叠，减少「魔法数字」维护成本；建立在 SE-0492「常量表达式」概念之上。

[SE-0532](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0532-optional-noncopyable-improvements.md "SE-0532")
**Optional 不可复制类型的改进与泛化** 提案正在审查。

在 `Optional` 上新增 `borrow()`、`mutate()`、`insert()`，并泛化 `map`、`flatMap`、`unsafelyUnwrapped` 以更好支持 `~Copyable` 包装值；该提案此前已在 **第一百期周报** Swift 论坛模块中作为 Pitch 介绍过。

[SE-0533](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0533-reasync-macros.md "SE-0533")
**使用宏生成 async 函数的同步重载** 提案正在审查。

新增 **`@Reasync`** 宏，为 async 函数自动生成同步重载，使必须以同步与异步两种形式存在的 API 保持单一实现来源。

## Swift 论坛

### 1、Pitch：`Iterable` 修订——从 `BorrowingSequence` 到通用借用迭代

作者：Nate Cook ｜ 发布日期：2026 年 5 月 20 日
[阅读原帖](https://forums.swift.org/t/revision-pitch-iterable-formerly-borrowingsequence/86834 "Revision Pitch: Iterable (formerly BorrowingSequence)")

SE-0516 修订版将 **BorrowingSequence** 重命名为 **Iterable**，为同步迭代提供更通用的协议基础，允许类型、元素与迭代器为 **noncopyable** / **nonescapable**，并支持抛错迭代。

**动机：**
现有 **Sequence** 围绕可复制元素与 `next() -> Element?` 建模，难以自然表达 **Span**、**InlineArray** 及非复制元素的借用式遍历。

**核心设计：**

```swift
public protocol Iterable<Element, Failure>: ~Copyable, ~Escapable {
  associatedtype Element: ~Copyable
  associatedtype Failure: Error = Never
  associatedtype IterableIterator: IterableIteratorProtocol<Element, Failure>

  @_lifetime(borrow self)
  func makeIterableIterator() -> IterableIterator
}
```

迭代器通过 `nextSpan(maximumCount:)` 按批返回 `Span<Element>`。

**讨论亮点：**
集中在 **for-in** 脱糖、抛错迭代是否需要 `for try`、以及生命周期受限时泛型算法（如 `first(where:)`）的可行性。

**简要点评：**
面向所有权模型长期演进的基础设施改造，短期增加协议层复杂度，但为 **Span** 与 **~Copyable** 容器打开更自然的迭代接口。

### 2、Pitch：用 `Disconnected` 在类型系统中表达断开隔离的值

作者：Franz Busch ｜ 发布日期：2026 年 5 月 19 日
[阅读原帖](https://forums.swift.org/t/pitch-disconnected-type-for-modeling-disconnected-values/86815 "Pitch: Disconnected type for modeling disconnected values")

提议在标准库加入 **`Disconnected<Value>`**，把值标记为处于断开隔离区域，便于在容器、队列中保存并传递 **region-based isolation** 与 **sending** 语义。

**动机：**
`sending` 是函数签名属性，无法被普通存储属性或集合长期保留；队列等容器需要区分「普通非 Sendable 值」与「可跨隔离域移动的断开值」。

**核心设计：**

```swift
@frozen
public struct Disconnected<Value: ~Copyable>: ~Copyable, Sendable {
  public init(_ value: consuming sending Value)
  public var value: Value { borrow }
  public consuming func take() -> sending Value
}
```

**讨论亮点：**
`Disconnected` 无条件符合 **Sendable** 是否直观、借用访问器如何维持不变量、与 SE-0519 容器借用访问器的组合方式。

**简要点评：**
把并发隔离中的隐含状态显式建模，对异步算法与通用容器很有价值，也要求开发者区分「值可发送」与「值已断开」两层语义。

### 3、SE-0531：Literal Expressions 进入审查

作者：Ben Cohen ｜ 发布日期：2026 年 5 月 19 日
[阅读原帖](https://forums.swift.org/t/se-0531-literal-expressions/86794 "SE-0531: Literal Expressions")

SE-0531 进入正式审查（至 2026 年 5 月 29 日），引入 **Literal Expressions**，在特定上下文对整数表达式做编译期折叠。

**动机：**
enum raw value、`@section` 初始化、integer generic arguments 等位置往往只能写裸整数，意图难以保留在源码中。

**核心设计：**

```swift
let pageSize = 4 * 1024
enum Permissions: Int {
  case read = 1 << 0
  case write = 1 << 1
}
let buffer: InlineArray<(2 * pageSize), UInt8>
```

限制包括：结果须为标准库整数类型；用户自定义运算符不参与；公开可见常量引用暂不允许参与折叠。

**讨论亮点：**
Jordan Rose 质疑「literal expressions」命名，建议 **Integer Literal Expressions**；争议主要在命名与扩展边界，而非能力本身。

**简要点评：**
务实改动，能明显改善底层、嵌入式与泛型值参数代码的可读性。

### 4、SE-0526 第二轮审查：`withDeadline` 简化错误与取消语义

作者：Frederick Kellison-Linn ｜ 发布日期：2026 年 5 月 18 日
[阅读原帖](https://forums.swift.org/t/second-review-se-0526-withdeadline/86791 "Second Review: SE-0526 withDeadline")

SE-0526 **withDeadline** 开启第二轮审查（至 2026 年 5 月 31 日），为异步操作提供基于**绝对时间点**的截止期限。

**动机：**
手写超时逻辑涉及任务组、sleep、取消传播与竞态，冗长难组合；绝对 deadline 可让多层调用共享同一截止时刻。

**核心设计：**
本轮删除 `Task.currentDeadline`、移除跨时钟组合约束、取消 `DeadlineError` 包装，改为直接转发 body 错误；**CancellationError** 新增 `reason` 携带 deadline 过期原因。

```swift
let deadline = ContinuousClock().now.advanced(by: .seconds(5))
let result = try await withDeadline(deadline, clock: clock) {
  try await fetchDataFromServer()
}
```

**讨论亮点：**
命名准确性、`throws(Failure)` 与取消错误关系、`CancellationError.reason` 精确定义及 `custom(String)` 滥用空间。

**简要点评：**
API 表面明显收敛，错误传播更符合 typed throws 方向；取消原因模型仍需足够严谨。

### 5、Typed throws 下 `rethrows` 不能保留具体错误类型的讨论

作者：Tiago Canto ｜ 发布日期：2026 年 5 月 20 日
[阅读原帖](https://forums.swift.org/t/rethrows-does-not-seem-to-work-correctly-with-typed-throws/86843 "Rethrows does not seem to work correctly with typed throws")

讨论 **typed throws** 与 **rethrows** 的交互：`rethrows` 只表达「参数抛错时才抛错」，并不承诺「抛出同一种错误类型」。

**动机：**
`transaction(operation:) rethrows` 包装闭包时，编译器不会保留闭包的具体错误类型 `DatabaseError`。

**核心设计：**
更推荐泛型 `throws(E)`：

```swift
func transaction<E>(operation: () throws(E) -> Void) throws(E) {
  try operation()
}
```

**讨论亮点：**
Slava Pestov 指出 `Never` 符合 `Error` 可表示非抛错路径；但可选闭包默认值、错误推断等场景下 `rethrows` 仍有残余价值。

**简要点评：**
澄清了 `rethrows` 语义边界，提醒库作者迁移 typed throws 时不要机械替换。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[一个偶发性测试失败，揭开了 Swift 并发调度的真相](https://www.swift.org/blog/whats-new-in-swift-january-2026/ "一个偶发性测试失败，揭开了 Swift 并发调度的真相")

**摘要：** 从一个偶发测试失败切入，拆解 Swift 并发中任务、Actor 与执行器的关系：`nonisolated async` 会跳离调用者 Actor、`Task.yield()` 只让出当前执行器、`#isolation` 参数可让工具函数随调用者运行而无需跳转——适合想真正理解而非仅会使用 Swift 并发的开发者。

[将 300 个界面迁移到 SwiftUI 后所学到的](https://iosdevweekly.com/issues/751/ "将 300 个界面迁移到 SwiftUI 后所学到的")

**摘要：** 300 界面从 UIKit 渐进迁移至 SwiftUI 的实战复盘：SwiftUI 负责 UI、导航保留 UIKit；梳理 body 副作用、滥用 `onAppear`、嵌套 `ObservableObject` 等典型坑，最终沉淀 MVVM + 枚举驱动状态 + Use Case 分离业务的架构方向。

[用 Swift 手写 LLM 训练内核（第一部分）：将矩阵乘法从 Gflop/s 优化到 Tflop/s](https://iosdevweekly.com/issues/751 "用 Swift 手写 LLM 训练内核（第一部分）：将矩阵乘法从 Gflop/s 优化到 Tflop/s")

**摘要：** 在 Swift 中从零手写矩阵乘法，经循环展开、SIMD、**Span** / **InlineArray**、Metal shader 等优化，将性能从约 2.8 Gflop/s 提升至约 1.1 Tflop/s；强调生产环境仍应优先 Accelerate / BNNS / CoreML 等成熟框架。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 "进群" 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
