## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百零二期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

余生很长，愿你拥抱自己，努力成长，眼中裹满阳光，笑里尽是坦荡。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：多方消息证实苹果首款触屏MacBook即将问世，预计2026年底亮相
> * **提案**：
> * **Swift 论坛**：
> * **推荐博文**：

上期话题投票结果如下：




## 话题讨论




欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### 多方消息证实苹果首款触屏MacBook即将问世，预计2026年底亮相

*2026 年 6 月 12 日｜来源：动静新闻*

6 月 12 日消息，据 macworld 报道称，苹果公司首款搭载触摸屏的 MacBook 产品已“100%确认”正在筹备当中。近期，来自供应链、知名分析师及市场研究机构的多个独立消息源高度一致地指出，这款打破苹果多年传统设计理念的触屏笔记本即将面世。

![](https://pics3.baidu.com/feed/1c950a7b02087bf4c01482165472843d13dfcf8d.jpeg@f_auto?token=85a1ec5ea08ba816473f1d9013be994b)

近日，一位名为“Instant Digital”的爆料者在社交平台上发布了极具确定性的消息，称苹果首款配备触摸屏的 MacBook 现已“百分之百确认”。尽管该爆料者过往在苹果新品预测方面鲜有准确记录，且此次使用了极为罕见的绝对措辞，但这一说法与近期其他多方可靠报道形成了强有力的印证。

从供应链端来看，触控版 MacBook 的硬件生产正在稳步推进。供应链消息人士透露，用于触控式 MacBook Pro 的 OLED 屏幕生产已克服关键技术障碍，三星显示器预计最快于 6 月即可向苹果供货。在市场预期方面，市场研究公司 Omdia 指出，这款被外界称为“MacBook Ultra”的新机型有望在今年第三季度发布。

苹果分析师郭明錤（Ming-Chi Kuo）与彭博社资深记者马克·古尔曼（Mark Gurman）均表示，苹果首款配备 OLED 触控屏的 MacBook Pro 预计将在 2026 年进入量产阶段，并大概率于 2026 年底至 2027 年初正式上市。考虑到全球存储芯片可能存在的供应短缺问题，2027 年初面世的可能性同样存在。

### 苹果高管：Siri不会发展为AI女友 专注打造效率助手

*2026 年 6 月 12 日｜来源：CNMO科技*

在 WWDC 结束后的最新采访中，苹果软件工程负责人 Craig Federighi 与全球市场营销负责人 Greg Joswiak 围绕 iOS 27 中的 Siri 升级、人工智能发展方向以及隐私保护等话题进行了交流。对于外界关注的 AI 陪伴功能，两位高管给出了明确回应：苹果并不希望将 Siri 打造成为情感型 AI 产品。

![](https://pics2.baidu.com/feed/7c1ed21b0ef41bd590bcab821e8b52da38db3dbf.jpeg@f_auto?token=626b3f346c26854cd6f9bfbbda824eda)

Siri

采访中，有媒体提问未来用户是否能够把 Siri 塑造成“AI 男友”或“AI 女友”。对此，Craig Federighi 直接表示不会。按照苹果的设计理念，Siri 的核心职责是帮助用户完成任务、获取信息以及提升日常效率，而非建立情感依赖关系。他指出，目前部分聊天机器人产品会通过持续互动提升用户黏性，甚至鼓励用户分享更多个人信息，以此建立更深层次的连接，但这并非苹果希望发展的方向。

Craig Federighi 表示，Siri 更希望告诉用户“我是来帮助你的”，无论是处理事务还是了解世界，而不是成为情感陪伴对象。他强调，Siri 不会以恋爱伙伴或虚拟伴侣的身份与用户互动。

Greg Joswiak 则进一步解释了苹果对于AI的整体思路。他表示，苹果并不追求为了 AI 而 AI，而是希望通过人工智能技术优化现有产品体验，让技术尽可能融入用户日常使用场景，而不是让用户专门学习复杂的提示词技巧。他认为，AI 应该成为提升产品能力的工具，而不是喧宾夺主的新概念。

在隐私方面，Craig Federighi 同样进行了重点说明。他强调，苹果始终坚持以用户隐私为核心，用户数据主要保存在个人设备之中，由用户自行掌控。Siri 调用这些信息是为了更好地服务用户，而并非让苹果获取相关数据。他认为，这种设备侧的数据管理方式，是苹果AI战略的重要组成部分。

## 提案


## Swift论坛

### 1、Swift 6.4 类型检查器近期改进

作者：Slava Pestov ｜ 发布日期：2026 年 6 月 2 日
[阅读原帖](https://forums.swift.org/t/recent-improvements-to-the-type-checker/87048 "Recent improvements to the type checker")

这篇帖子系统介绍了 **Swift 6.4** 中 **类型检查器** 的性能优化。核心变化包括 **disjunction pruning** 和更精确的 **binding inference**：前者在重载解析时不只区分“优先/非优先”，还会直接剪掉“不可能成功”的重载选择；后者从“收集候选绑定”转向分析类型变量可取值的域，从而更早发现唯一解或死路。

这些改动的动机很明确：减少大型表达式、泛型、闭包、字面量集合和大量重载组合带来的组合爆炸。帖子给出了多个 Swift 6.3 中过慢、Swift 6.4 中可快速通过的例子，例如位运算和 SIMD 运算：

```swift
func f() {
  let u = SIMD2<Float>(0, 1)
  let v = SIMD2<Float>(1, 2)
  let r = [2*u + 3*v, 4*u + 5*v, 5*u + 6*v, 6*u + 7*v]
}
```

讨论亮点在于，这些优化还让编译器能移除一些更窄、更硬编码的旧启发式逻辑，测试集也扩充了更多“快/慢表达式”基准。简评：这类改进不如新语法显眼，但对日常 Swift 开发体验非常关键，尤其能减少“表达式过复杂无法在合理时间内类型检查”的痛点。

### 2、讨论 Swift 中的字节容器类型

作者：Jeremy Schonfeld ｜ 发布日期：2026 年 5 月 29 日
[阅读原帖](https://forums.swift.org/t/discussion-bag-of-bytes-types/86983 "[Discussion] Bag of Bytes Types")

Jeremy Schonfeld 发起讨论，收集社区对 Swift 中 “bag of bytes” 类型的使用经验，包括 **Data**、`Array<UInt8>`、`UnsafeRawBufferPointer`、`ByteBuffer`、`DispatchData`、**Span** 等。背景是 Swift 6.4 已对 **Data** 做了不少性能优化：减少不必要的 exclusivity 检查，在无 ABI 稳定的平台采用新 ABI，并改善常见操作的 specialization 与 fast path。

帖子列出的基准显示，一些操作收益非常明显，例如 `Data.bytes` 在新 ABI 下快 787%，`Data.count` 快 363%，`Data.==` 快 74%，并显著减少客户端二进制体积。作者希望在此基础上形成一份长期愿景文档，指导未来关于字节容器、借用字节和不可复制类型的演进。

讨论中，社区成员分享了 C 互操作场景：二进制或非 UTF-8 数据常用 **Data**，而文本且保证 UTF-8 时会选择 **String**；跨 C API 时常需要 `withUnsafeBytes` 这类作用域借用模式：

```swift
try data.withUnsafeBytes { bytes in
  guard let baseAddress = bytes.baseAddress else { return }
  c_api(baseAddress.assumingMemoryBound(to: CChar.self), bytes.count)
}
```

讨论亮点集中在空 `Data` 的语义、稳定地址与生命周期、避免隐式复制、以及 **~Copyable** 和 **Span/RawSpan** 是否能减少 unsafe pointer 使用。简评：这是 Foundation、系统编程和服务端 Swift 都会受益的基础设施讨论，重点不只是让 **Data** 更快，而是为 Swift 的字节模型建立更清晰的分层。

### 3、修订提案：`Iterable` 取代 `BorrowingSequence`

作者：Nate Cook ｜ 发布日期：2026 年 5 月 20 日
[阅读原帖](https://forums.swift.org/t/revision-pitch-iterable-formerly-borrowingsequence/86834 "Revision/Pitch: Iterable (formerly BorrowingSequence)")

这是一版对 **SE-0516 BorrowingSequence** 的重要修订。提案将主协议重命名为 **Iterable**，以表达它作为同步迭代通用抽象的定位；同时加入 **typed throws** 风格的 `Failure: Error` 关联类型，使借用迭代也可以抛错。其目标是补足现有 **Sequence** 难以支持 **~Copyable**、**~Escapable**、**Span**、**InlineArray** 等新所有权模型类型的问题。

设计上，`Iterable` 不再像 `IteratorProtocol.next()` 那样一次返回一个元素，而是通过迭代器返回一段 `Span<Element>`，把元素生命周期绑定到迭代器和原始容器：

```swift
public protocol Iterable<Element, Failure>: ~Copyable, ~Escapable {
  associatedtype Element: ~Copyable
  associatedtype Failure: Error = Never
  associatedtype IterableIterator: IterableIteratorProtocol<Element, Failure>

  @_lifetime(borrow self)
  func makeIterableIterator() -> IterableIterator
}
```

动机在于，非复制元素通常更适合“借用迭代”而非“消费迭代”。提案还解释了 `for` 循环可能如何被展开为 `nextSpan(maximumCount:)` 调用，并指出 `InlineArray`、`Span`、`RawSpan`、`MutableSpan` 等将成为标准库优先采用对象。

讨论亮点包括：`Iterable` 是否应与 `Sequence` 共存、抛错迭代如何影响泛型算法、以及某些算法在非复制元素下无法安全返回或跨 span 保存元素。简评：这项设计把 Swift 所有权系统从“类型能力”推进到“标准库抽象”，是非复制类型真正进入日常泛型编程的重要一步。

### 4、SE-0529：`FilePath` 接受并带有修改

作者：John McCall ｜ 发布日期：2026 年 6 月 5 日
[阅读原帖](https://forums.swift.org/t/accepted-with-modifications-se-0529-filepath/87125 "Accepted with modifications: SE-0529: FilePath")

语言指导小组宣布 **SE-0529 FilePath** 被接受并带有修改。该提案把表示当前系统文件路径的 **FilePath** 类型加入标准库，社区总体支持这一方向，但审查中围绕平台差异、`resolve` 方法、安全语义和阻塞 I/O 展开了较长讨论。

主要修改之一是让一些非可移植 API（例如特定平台才有意义的 `driveLetter`）先保持平台条件化，避免可移植代码无意依赖目标系统细节。争议最大的部分是 `resolve`：它会触及文件系统，因此既可能阻塞，也可能在高权限程序中诱发 TOCTOU 类安全误用。LSG 的结论是保留该 API，但依靠文档明确说明正确使用方式，因为缺少标准能力反而会促使开发者手写更危险的路径解析。

典型用法大致如下：

```swift
let path = FilePath("/usr/bin/swift")
let resolved = try path.resolve()
```

讨论亮点在于，社区继续追问 `resolve()` 返回普通 `FilePath` 是否足以表达“已解析路径”的特殊行为，尤其在新 Darwin 系统上追加组件可能表现不同。简评：**FilePath** 进入标准库是跨平台 Swift 的基础补强，但路径解析牵涉安全和平台语义，后续文档与可能的类型细分会非常重要。

### 5、SE-0531：Literal Expressions 进入审查

作者：Ben Cohen ｜ 发布日期：2026 年 5 月 19 日
[阅读原帖](https://forums.swift.org/t/se-0531-literal-expressions/86794 "SE-0531: Literal Expressions")

**SE-0531 Literal Expressions** 进入审查，提案希望扩展 Swift 中若干必须使用整数字面量的场景，包括 **integer generic arguments**、`@section` 变量初始化器和枚举 raw value。核心思想是允许由标准库整数类型、整数 literal、算术/位运算/一元运算以及可编译期折叠的 `let` 常量组成的表达式，并在编译期折叠为单个整数值。

动机是减少“魔法数字”和手工预计算。例如权限位枚举、页大小、缓冲区大小等场景，今天常常只能写最终数字，意图容易丢失：

```swift
let pageSize = 4 * 1024
let buffer: InlineArray<(2 * pageSize), UInt8>

enum Permissions: Int {
  case read = 1 << 0
  case write = 1 << 1
  case execute = 1 << 2
}
```

提案限制也很清晰：目前只覆盖标准库整数类型和指定运算符，不支持函数调用、属性访问、闭包、浮点或字符串；引用的变量必须是可折叠的 `let`，并且公开可见常量暂不允许参与跨模块折叠，以避免无意扩大 ABI 承诺。

讨论亮点包括 Jordan Rose 对 “literal expression” 命名的质疑，认为它容易混淆 Swift 中既有的 literal 概念；也有人建议叫 “Integer Literal Expressions”。简评：这不是完整的 compile-time programming，但它把最常见、最机械的整数常量计算交还给编译器，是向更强编译期表达能力迈出的谨慎一步。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[用Swift手写LLM训练内核（第一部分）：将矩阵乘法从Gflop/s优化到Tflop/s](https://www.swift.org/blog/whats-new-in-swift-may-2026/ "用Swift手写LLM训练内核（第一部分）：将矩阵乘法从Gflop/s优化到Tflop/s")

**摘要：** 这篇来自 Matt Gallagher 的硬核性能探索文章，在 Swift 中从零开始手写矩阵乘法，通过一系列系统级优化将基础实现的性能从2.8 Gflop/s一路提升至1.1 Tflop/s，实现了约382倍的加速。文章通过一个完整的优化迭代过程，展示了高性能Swift的现实面貌：Swift并非天生不够快，但当你逐渐逼近硬件极限时，将不可避免地进入 UnsafeBufferPointer、SIMD 指令、并发切片、内存布局与GPU tile优化等底层领域。作者详细阐述了每个优化阶段的关键技术——从编译器优化选项调整、循环展开、向量化，到利用 Swift 6.2 引入的 MutableSpan 和 InlineArray 实现零开销内存访问，再到使用 DispatchQueue.concurrentPerform 进行并行化，并最终对接 AMX 和 Metal shader 利用GPU算力。文章同时反复强调，生产环境应优先使用 Accelerate、BNNS、CoreML、MPSGraph 等成熟框架，手写优化仅适用于理解底层原理或在极端场景下突破框架限制。

[ Swift 社区动态：2026年5月版]( https://www.swift.org/blog/whats-new-in-swift-may-2026/ " Swift 社区动态：2026年5月版")

**摘要：** 这篇来自Swift官方团队的月度社区动态，系统梳理了2026年5月 Swift 生态的多个重要进展。文章开篇聚焦全球各地的Swift本地线下聚会，特别提到 SF Swift meetup关于“Agentify Your Swift Repo”（构建CI与代码审查的自动化代理）的演讲，以及新成立的MLX India meetup关于在iOS应用中使用MLX Swift的分享。技术层面，文章重点推介了 Temporal Swift SDK 1.0正式版——该SDK为Swift 带来了“持久化工作流”能力，使长时间运行的任务能够在崩溃、重试和重启后不丢失状态。在社区项目方面，Matt Gallagher 的 LLM 训练优化文章被列为月度亮点，展示了 Swift 6.2 新特性在极致性能场景中的应用。此外，文章还介绍了 Swift Evolution 中正在审阅的多个提案，包括 SE-0532（改进不可复制类型的Optional支持）和SE-0528（安全的async/continuation桥接），以及已接受的 SE-0519（Ref/MutableRef 引用类型）。全文为关注 Swift 跨平台、服务端和语言演进方向的开发者提供了全面的月度资讯汇总。 。

[丢掉包袱，硬刚 Rust：WWDC26 前瞻与 Swift 6.4 的底层革命](https://blog.csdn.net/mydo/article/details/161724273/ "丢掉包袱，硬刚 Rust：WWDC26 前瞻与 Swift 6.4 的底层革命")

**摘要：** 这篇前瞻文章敏锐地捕捉到 Swift 演进的核心转向：不再讨论花哨的语法糖，而是将目光聚焦于所有权（Ownership）、借用（Borrowing）等系统级语言特性，向着Rust开辟的高性能领域迈进。这一变革背后，是Swift的应用场景从应用层拓展至大模型AI推理、空间计算等对性能极致渴求的领域，传统 ARC 的运行时开销成为瓶颈。为此，Swift 6.4 正酝酿着两大核心利器：一是被正式接受的 Ref<T> 与 MutableRef<T> ，它们能在编译期保证引用安全，安全地借用值而无需 Class 的额外开销，性能可直逼 C 语言；二是全新的 Continuation 机制，旨在从根源上终结withCheckedContinuation 模式下“忘记恢复”或“重复恢复”的异步崩溃惨案。全文清晰地描绘了 Swift 正从一门“写App的高级语言”，转变为有能力涉足系统编程底层的通用语言的宏大图景。


## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
