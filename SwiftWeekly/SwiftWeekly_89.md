## 前言

嗨，Swift 社区的小伙伴们～👋

欢迎来到 **第 89 期 Swift 周报**！每周陪你一起跟进动态、学点新东西、再顺便聊点和 Swift 相关但不止于 Swift 的话题～

本周也一样，先送上一小段给你们的 **能量文**：“清晨的风轻轻吹过，带来的是新的希望和挑战。无论昨日有多少困惑，今天的你依然有无限的可能性。带着微笑，走向新的精彩。👊👊👊”

> **周报精选**
>
> * 新闻和社区：微信小游戏 iOS 抽成确定为 15%
> * 提案：SE-0498 开放 runtime demangle API 提案正在审查
> * Swift 社区：所有权模型（ownership model）持续推进，各协议正在适配不可复制类型
> * 推荐博文：动态布局、几何变化监听、滚动行为优化相关文章非常值得关注

**上期话题投票结果**

![](https://files.mdnice.com/user/47553/b3b09218-01f4-4632-89bf-9555c4d4097e.jpeg)

根据投票结果大家如何看待？

## 本期话题讨论

**你觉得苹果对 App Store 的抽成（15% / 30%）应该继续存在吗？你怎么看苹果抽成？**

1. 维持现状没问题，苹果提供生态与分发也值这个价
2. 应该大幅降低，比如统一 10% 或更少
3. 应该开放更多侧载渠道，抽不抽我自己选
4. 应该取消抽成，开发者时代已经变了
5. 看业务场景，不同品类不应该一刀切

欢迎在留言区说说你的理由，下期我们公布统计结果！
（别只投不说，大家都爱看你们的观点～）

## 新闻和社区

### 马斯克起诉 OpenAI 和苹果：法院驳回撤诉申请，双方必须应诉

**2025 年 11 月 14 日**

![](https://files.mdnice.com/user/47553/ed5bfa13-d1fc-4e65-be60-8ec459dc7d20.png)

美国得州联邦法官裁定，苹果与 OpenAI **必须回应** xAI 的诉讼，驳回了两家公司此前提出的撤销申请。法官要求双方提交进一步文件阐述各自立场，案件正式进入下一阶段。

马斯克指控苹果在 App Store 的“必备”类别中长期排除 X 与 Grok，并认为苹果与 OpenAI 的合作让其他 AI 公司难以竞争。他称这违反反垄断法，因此在 8 月正式提起诉讼。

苹果与 OpenAI 也公开回应：

* **OpenAI（奥特曼）**反击称马斯克自身也存在操纵 X 平台的质疑，并强调 OpenAI 将专注产品；
* **苹果**表示推荐标准客观透明，“不存在偏袒行为”，并强调保障用户安全与开发者公平机会。

诉讼文件中，xAI 指控 OpenAI 在美国生成式 AI 聊天机器人市场占比达 **80%**，苹果在智能手机市场占 **65%**，双方“合谋阻挠竞争”。

与此同时，马斯克在特斯拉股东会上获得重大利好：

* “**万亿美元薪酬方案**”以 75% 多数票通过；
* 特斯拉股东还投票同意 **投资 xAI**（虽有利益冲突疑虑，但被认为对双方协调发展有益）。

关于“xAI 完成 150 亿美元 E 轮融资”的报道，马斯克本人已否认，称消息“不实”。

### 微信小游戏抽成新进展：苹果将抽 15%，腾讯回应“保持建设性”

**2025 年 11 月 14 日**

腾讯已与苹果达成新协议：苹果将参与处理微信小游戏及应用内支付，并抽取 **15% 分成**。这被视为小游戏生态的一次重要调整。

腾讯管理层在三季度业绩会上确认：

* 双方正保持良好沟通，
* 合作推进中，
* 具体细节需等待正式公告。

事实上，腾讯去年就曾表示正在与苹果商讨让小游戏交易走 iOS 支付体系，从而开启苹果分成模式。

苹果对 App Store 的抽成机制沿用多年：

* 年收入 **>100 万美元**：抽成 30%；
* 年收入 **≤100 万美元** 的中小开发者：抽成 15%。

第三方数据显示，2023 年“苹果税”全球收入约 **223.4 亿美元**（约 1506 亿人民币），其中 **中国市场超过 400 亿人民币**。

消息发布当日，腾讯发布 Q3 财报：

* 营收 **1928.69 亿元**（+15%）
* 净利润 **631.33 亿元**（+19%）

### iPhone Pocket 发布：Apple × ISSEY MIYAKE 联名的“可穿戴口袋”

**2025 年 11 月 11 日**

![](https://www.apple.com.cn/newsroom/images/2025/11/introducing-iphone-pocket-a-beautiful-and-wearable-carrier-for-iphone/article/Apple-iPhone-Pocket-and-ISSEY-MIYAKE-hero_big.jpg.large.jpg)

Apple 与 ISSEY MIYAKE 联手推出 **iPhone Pocket** ——一个可穿戴的“一块布”设计口袋，用于随身携带 iPhone 与日常小物，采用品牌标志性的 **一体式三维编织** 工艺。

![](https://files.mdnice.com/user/47553/d6691ffb-fc13-477d-8d7c-55ba4cd484d6.png)

iPhone Pocket 亮点包括：

* 可容纳任意 iPhone，开放式纹理可透视设备屏幕；
* 可手提、挂包、佩戴在身上等多种使用方式；
* 多色可选，短带 8 色、长带 3 色；
* **日本制造**，由 ISSEY MIYAKE 开发的三维编织结构打造。

![](https://files.mdnice.com/user/47553/49e66292-dc6a-402b-aa9a-35d0458e9e3a.png)

设计团队强调：

* “让 iPhone 以更自由的方式贴近用户”；
* “少定义、留空间”是 ISSEY MIYAKE 的核心理念；
* Apple 表示其颜色和造型可以与所有 iPhone 的配色自由混搭。

![](https://files.mdnice.com/user/47553/b28f2608-5bf3-4546-9199-d7a26f5f034c.png)

价格：

* **短带款：RMB 1,299**
* **长带款：RMB 1,899**

11 月 14 日起在部分 Apple Store 及 apple.com.cn 上市，覆盖法国、大中华区、日本、新加坡、韩国、英国、美国等市场。

## 提案

### 通过的提案

[SE-0493](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0493-defer-async.md "SE-0493") **`defer` 体中支持 `async` 调用** 提案通过审查。该提案已在 **第八十七期周报** 正在审查的提案模块做了详细介绍。

[SE-0495](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0495-cdecl.md "SE-0495") **C 兼容函数和枚举** 提案通过审查。该提案已在 **第八十七期周报** 正在审查的提案模块做了详细介绍。

[SE-0497](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0497-definition-visibility.md "SE-0497") **客户端中的控制功能定义可见性** 提案通过审查。该提案已在 **第八十七期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0498](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0498-runtime-demangle.md "SE-0498") **在运行时模块中公开 demangle 功能** 提案正在审查。

当你在 Crash 回溯里看到被破坏的名称可能看起来像下面这样：

```txt
$sSS7cStringSSSPys4Int8VG_tcfC
```

这种神秘字符串的那种绝望情绪你懂的。
这个提案要做的就是：

**开放运行时 API，让你自己在 Swift 内部对符号进行 demangle（变成人类看得懂的格式）。**

例如，之前显示的标识符可以被非语为 `Swift.String.init(cString: Swift.UnsafePointer<Swift.Int8>) -> Swift.String`，这是一个很好的人类可读格式，追踪堆栈、打印调试信息都会更友好。

## Swift论坛

### 1、支持 ~Copyable、~Escapable 在标准库简单协议中

作者：Ben Cohen ｜ 发布日期：2025 年 11 月 7 日
[阅读原帖](https://forums.swift.org/t/support-copyable-escapable-in-simple-standard-library-protocols/83083 "支持 ~Copyable、~Escapable 在标准库简单协议中")

这是一项针对 Swift 标准库协议的小而关键的提案，目标是让这些协议能够兼容“非可复制（non-Copyable）”和“可逃逸（Escapable）”类型，从而进一步推动 Swift 新的所有权模型在生态中的采用。

**核心要点：**

* 提议将以下协议声明为精炼（refine） ~Copyable 与 ~Escapable：
* Equatable, Comparable, Hashable
* CustomStringConvertible, CustomDebugStringConvertible
* TextOutputStream, TextOutputStreamable
* 同时，将 LosslessStringConvertible 标记为精炼 ~Copyable。
* 此外，提案建议更新 Optional 与 Result 的 Equatable/Hashable 关联条件，使其支持元素类型满足 ~Copyable & ~Escapable 的情形。
* 提出该变更不会改变现有语义或破坏兼容性，而是扩展协议的可适用类型集合。
* 提案背景：目前标准库协议大量依赖于类型为 “可复制” 或 “不可逃逸” 的假设，这限制了将非可复制类型或资源型类型（如唯一所有权结构）用于这些协议的情况。通过该变更，可让这些类型更方便地参与如 Hashable、Equatable 等通用协议。

**小结：**

如果你的代码或库即将采用 Swift 的所有权模型（非可复制类型、借用/消耗语义）——那么这项提案是极其有意义的。它删减了因为标准协议“假定可复制／不可逃逸”而导致的障碍，让更多种类的类型能参与生态内常用协议。你可在未来项目中留意：当标准库版本支持后，可尝试将自定义非可复制类型也纳入 Equatable、Hashable、CustomStringConvertible 等协议。这将提升资源型类型的可用性与通用性。

### 2、为任意 Swift PM 包生成文档的提案

作者：Chris McGee ｜ 发布日期：2025 年11 月12 日
[查看提案](https://forums.swift.org/t/pitch-documentation-generation-for-any-swiftpm-package/83174 "为任意 Swift PM 包生成文档的提案")

这则 pitch 提出了一个简化并标准化 Swift 包文档生成流程的建议：通过新增 `swift package generate-documentation` 命令，让任何使用 DocC 的 SwiftPM 包能“一键生成” HTML API 文档，而无需手动配置插件、symbol-graph、archive 合并等繁琐步骤。

**核心要点：**

* 动机：目前虽然 DocC 能生成 API 文档，但对包作者而言，配置门槛高、流程繁琐，许多包因此缺乏优质文档。
* 提案：将文档生成流程内置于 SwiftPM，通过新命令自动发现产品／目标、生成 symbol graph、合并多个目标文档并输出为统一浏览结构。示例界面如下：

```bash
swift package generate-documentation
```
无需手动指定具体 target。

* 理想效果：包作者与使用者均能快速浏览包的 API、模块结构与文档内容，从而提升 Swift 社区中包的可发现性与可用性。
* 符合生态趋势：随着 DocC 与 SwiftPM 的深度融合，该提案希望将文档生成变为默认而非附加操作。

**小结：**

如果你或你的团队正在维护 SwiftPM 包，尤其是希望提高包的文档质量与使用友好度，这一提案值得密切关注。一旦实现，你将能更轻松地为你的库发布在线文档，而无须额外插件或复杂配置。建议在周报中提醒团队：在该命令支持后可立即评估迁移路径。

### 3、通用化 ContiguousBytes 以支持 Span 等类型

作者：Douglas Gregor ｜ 发布日期：2025 年11 月 7 日
[查看提案](https://forums.swift.org/t/pitch-generalize-contiguousbytes-to-support-span-et-al/83082 "通用化 ContiguousBytes 以支持 Span 等类型")

这篇 pitch 针对标准库中的协议 ContiguousBytes 提出了增强建议：让它能够支持新引入的“连续存储视图”（如 Span、RawSpan 等）以及“非可复制（non-Copyable）”和“不可逃逸（non-Escapable）”类型，从而提升其适用范围。

**核心要点：**

* 背景：ContiguousBytes 目前用于表示能够输出其底层字节存储（如 Data, `Array<UInt8>` 等）并提供 withUnsafeBytes 闭包访问。 
* 问题：新的 Span 类型家族设计为轻量 “借用视图”，可能是不可逃逸或非可复制类型，因此当前 ContiguousBytes 限制其 `Self: ~Copyable`， `~Escapable` 无法使这些类型符合协议。 
* 提案：修改 ContiguousBytes 定义，将其要求调整为更加通用：
  
```swift
public protocol ContiguousBytes: ~Escapable, ~Copyable {
    func withUnsafeBytes<R>(_ body: (UnsafeRawBufferPointer) throws -> R) rethrows -> R
    func withBytes<R, E>(_ body: (RawSpan) throws(E) -> R) throws(E) -> R
}
```

同时让 `Span`， `MutableSpan`， `RawSpan`， `MutableRawSpan`， `UTF8Span`， `InlineArray` 等类型都符合该协议。

* 讨论要点包括：
* 是否应优先使用 withBytes(RawSpan) 而非传统 withUnsafeBytes。
* 如何处理旧 API 与新 API 的交互、可用性注解（availability）与编译器支持。

**小结：**

对于希望在 Swift 中使用低级字节视图或固定容量/借用数组等新型存储类型的开发者而言，这项提案具有重要意义。它可让这些类型与现有标准库字节接口兼容，从而简化诸如序列化、数据解析、网络字节流等场景的 API 设计。建议项目团队关注该提案的进展，并在未来考虑采用 Span 类型及其字节访问优化。

### 4、恢复提议：为元组自动生成 Hashable 一致性（SE-0283）

作者：Joshua Cleetus ｜ 发布日期：2025 年 11 月 9 日
[阅读原帖](https://forums.swift.org/t/pitch-automatic-hashable-conformance-for-tuples-revival-of-se-0283/83105 "恢复提议：为元组自动生成 Hashable 一致性（SE-0283）")

这篇 pitch 提出了一个实用而常见的改进建议：当元组的所有元素都遵循 Hashable 协议时，让编译器自动将该元组类型识别为 Hashable。这项功能意在节省手动扩展元组协议的一致性代码，并促进元组在诸如 Dictionary 或 Set 中作为键的使用。

核心要点如下：

* 痛点描述：目前，尽管 (Int, String) 的元素类型 Int 和 String 均为 Hashable，但元组 (Int, String) 本身并不自动符合 Hashable，因此不能直接用作字典键。提案指出这是与语言可读性和生态惯例不一致之处。
* 提案方案：当元组 (T0, T1, …, Tn) 中每个 Ti 都符合 Hashable 时，自动生成如下扩展：

```swift
extension (T0, T1, …, Tn): Hashable
  where T0: Hashable, T1: Hashable, …, Tn: Hashable
{
  public func hash(into hasher: inout Hasher) {
    hasher.combine(0)         // 类型判别符，防止不同元组混淆
    hasher.combine(self.0)
    hasher.combine(self.1)
    …
    hasher.combine(self.n)
  }
}
```

注：== 运算符对于元组元件数不超过 6 已由标准库通过重载提供，无需再次生成。

* 适用规则：
* 若且仅若所有元组元素均遵循 Hashable，元组即自动符合 Hashable。
* 若任何一个元素不符合 Hashable，则该元组不自动符合。
* 嵌套元组、元素为元组、元素为数组（如 `Array<T>` 若 `T: Hashable`）等均支持。
* 兼容性与实现影响：
* 仅为新增自动一致性，不会破坏现有代码，因为没有移除任何功能；手动扩展的情形仍可用。
* 对 ABI 无影响，因为这是源级扩展，不涉及运行时布局改变。
* 历史背景：
* 原提案 SE-0283（2020）曾被接受，目标让元组同时自动符合 Equatable、Comparable 和 Hashable。
* 但因“非名义类型（non-nominal type）”自动一致性实现在运行时/编译器中存在挑战，最终被撤回。
* 该 pitch 是对 SE-0283 的“限定复兴”——聚焦仅 Hashable 且待编译器对元组一致性支持成熟。

**小结：**

这项提案虽看似“小改”，但对于许多使用元组作为复合键、缓存标识、数据结构的开发者而言，是一个极具可用价值的提升。若被采纳，将大幅减少样板代码，并提升元组类型在 Swift 生态中的整合度。但其是否会实施，仍取决于编译器对于“非名义类型自动协议一致性”底层机制的成熟度。


### 5、为什么 `removeLast(_:)` 不返回值？

作者：Matt Neuburg ｜ 发布日期：2025 年 11 月 10 日
[阅读原帖](https://forums.swift.org/t/why-doesnt-removelast-return-a-value/83116 "为什么 removeLast(_:) 不返回值？")

在这篇讨论中，用户 Matt Neuburg 提出一个长期困扰：在 Swift 中，removeLast() 会移除并返回最后一个元素，但其重载方法 `removeLast(_:)`（移除多个元素）却仅移除而不返回这些元素。他认为从“最少惊讶原则（Least Surprise Principle）”出发，`removeLast(_:)` 理应返回被移除的元素集合。讨论中标准库团队成员及其他用户给出了性能与设计层面的解释。

核心观点：

* 问题背景：虽然 removeLast() 在 Array 等可变集合类型上移除最后一个元素并返回它，但 `removeLast(_ n: Int)` 仅移除最后 n 个元素，不返回它们。Matt 指出自己每次都必须先做 `let removed = array.suffix(n)`，然后再 `array.removeLast(n)`，感觉繁琐且容易出错。 
* 标准库团队解释（Tony Allevato）：当只移除一个元素时返回值「廉价」且直观；但若移除多个元素，若要返回这些元素，就必须在移除前复制它们或生成一个切片（slice）保持原始存储。两者皆可能带来性能开销：
* 返回 slice：需保留原底层存储直到切片销毁，可能禁用 COW 优化。 
* 复制数组：若大多数用户不需要返回值，这将给所有人埋下不必要开销。 
* 社区建议与延伸思考：
* 可以通过扩展提供 `removeLastAndReturn(_:)`（或类似命名）手动实现返回值行为。 
* Ben Cohen 指出：随着 Span 等轻量视图类型引入，未来或许可以为此类方法返回“消耗视图（draining span）”——类似于 Rust 中 drain 的概念，在不额外分配的情况下返还移除元素。 

**小结：**

这个讨论虽然不是语言提案，而是 “为什么如此设计” 的反思，对日常 Swift 开发者依然有价值。若你所在项目常用 `removeLast(_:)` 移除多个元素且需要获取它们，建议采取以下实践：
* 若需要被移除元素，先做 `let removed = array.suffix(n)` 再 `array.removeLast(n)`。
* 或者封装一个自定义扩展方法（如 `removeLastAndReturn(_:)`）明确返回 `ArraySlice` 或 `Array`。
* 关注未来标准库是否会针对此情景增强 API（例如支持 Span 或类似技术）。

## 推荐博文

[Swift 6.2 性能革新](https://blog.csdn.net/qq449245884/article/details/154585510/ "Swift 6.2 性能革新")

**摘要：** 这是一篇对 Swift 6.2 版本的深度分析文章，虽然来自个人博客，但对新特性的解读非常详细。它主要讨论了以下关键更新：

Inline Arrays（内联定长数组）：允许数组数据直接存储在栈上，减少了堆分配和引用计数的开销，对于游戏、金融和媒体处理等高性能计算场景，能带来数倍的性能提升和显著的内存占用降低。

Span 类型：提供了一种安全且高效的方式来操作连续内存，类似于C语言的指针但更具安全性，非常适合处理音频、图像等缓冲区数据。

并发模型改进：优化了 Actor 隔离推断和结构化并发，使得并发代码更易于编写和维护，减少了与编译器的“角力”。

[SwiftUI 新Tab API实战](https://blog.csdn.net/qq_36478920/article/details/154802726/ "SwiftUI 新Tab API实战")

**摘要：**  这篇博客通过代码示例，手把手教你如何使用 SwiftUI 的新 API 来创建符合 iOS 18 新设计语言（Liquid Glass）的标签栏。

新旧写法对比：展示了从传统的 tabItem 写法到新的 Tab 结构体的转变，使代码层次更清晰。

状态绑定：讲解了如何结合 `@SceneStorage` 来持久化用户选择的标签页状态。

标签角色：介绍了TabRole机制，例如可以将某个标签设为.search角色，系统会为其应用特殊的样式。

[Swift 内存管理：吃透 ARC 、weak、unowned](https://juejin.cn/post/7571693273729007652/ "Swift 内存管理：吃透 ARC 、weak、unowned")

**摘要：**  Swift 的内存管理核心在于理解 ARC（自动引用计数）的自动化机制与局限性。它虽然能自动处理大部分内存，但当对象之间产生“强引用循环”时，便会陷入内存泄漏的困境。

破解此困境的关键在于正确使用 weak 和 unowned 这两把钥匙：weak 提供了一种安全的观察者模式，在对象销毁时自动退场；而 unowned 则假设了一种更紧密的生命周期绑定，性能更高但风险自担。

本质上，精湛的 Swift 内存管理是一门在“自动化便利”与“手动干预责任”之间寻求平衡的艺术，要求开发者不仅能设计对象之间的关系，更能预见它们从生到死的完整生命周期。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。