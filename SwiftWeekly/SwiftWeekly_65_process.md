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
1) 提议[修改和读取访问器](https://forums.swift.org/t/pitch-modify-and-read-accessors/75627 "修改和读取访问器")
**内容大概**
Swift 团队在讨论访问器的改进，特别是针对 yield-once 协程访问器，建议使用“borrow”和“mutate”作为新名称，以实现对象属性的临时、直接访问。该提案详细探讨了这些新术语与传统“read”和“modify”访问器之间的区别。

1. 新访问器命名的目的：
* 提出用“borrow”和“mutate”描述基础的访问器，涉及就地访问并可能更改对象的部分（如属性），使对象保留所有权并临时提供借用访问权限。
* 这与现有的“read”和“modify”访问器不同，后者用于一次性协程，在操作期间只会短暂地将被访问的实体实现出来。“read”和“modify”表示有开始和结束的操作，允许临时访问而不转移所有权。
2. 词汇和语义上的差异：
* Swift 团队仔细考虑了词汇，旨在避免混淆。虽然“read”和“modify”更接近临时操作，不转移所有权，而“borrow”和“mutate”更准确地描述了直接、基于组件的访问，而不转移所有权。
* 这些术语避免了与现有术语“get”和“set”同义，后者暗示更直接的完成式交易，即所有权或值被直接交付。
3. 功能性和未来应用场景：
* 团队强调，这些新的访问器“borrow”和“mutate”旨在作为基础概念，与 Swift 未来的组件化访问模式对齐。
* 团队表示，这些新名称还希望解决未来可能的情况，例如“投影访问器”（设计用于借用字段而不转移所有权），并澄清目前该提案中不包含异步访问器（异步 read/modify），但未来可能会考虑。
4. 提案的时间安排：
* 该提案并不面向 Swift 6.1，尽管团队仍在继续讨论，以期在 Swift 的未来版本中进一步完善这些访问器的行为和命名。

2) 讨论[Task 和 MainActor.assumeIsolated 的等价性](https://forums.swift.org/t/equivalence-of-task-and-mainactor-assumeisolated/75671 "Task 和 MainActor.assumeIsolated 的等价性")
**内容大概**
讨论围绕 Swift 中的 Task 和 MainActor.assumeIsolated 方法的使用和文档的解释不足展开。用户认为，现有文档对这两个方法的描述虽然基本清晰，但在关键点上有所欠缺。例如，MainActor.assumeIsolated 的描述略显模糊，似乎仅涉及验证，而未明确指出它会在 MainActor 上执行操作。

用户指出，Task 方法能够创建并在当前 actor 上运行非抛出操作，但相关机制的解释在 Swift 的文档中缺乏统一性。用户希望能有一份简洁、结构清晰的文件，概述隔离、actor 和异步概念，而不必频繁查阅分散的资料。

他们还提到，现有的并发文档通常缺乏吸引力，重要信息散落在各个提案中，术语不统一且细节不足，增加了理解难度。用户建议，改进文档应首先建立一致的术语，并提供一份简洁的叙述，清晰解释并发机制的工作原理及其用法。这种优化文档的过程尽管耗时繁重，但能有效提升开发者的理解。

3) 讨论[使用手动构建的 5.10.1 在 6.0.1 上构建 lib/liblldb.so.17.0.0 时出现问题](https://forums.swift.org/t/trouble-building-lib-liblldb-so-17-0-0-on-6-0-1-using-manually-built-5-10-1/75610 "使用手动构建的 5.10.1 在 6.0.1 上构建 lib/liblldb.so.17.0.0 时出现问题")
**内容大概**
用户在尝试用手动构建的 Swift 5.10.1 版本编译 Swift 6.0.1 时遇到问题，无法成功构建 lldb-server 和 lib/liblldb.so.17.0.0，因为缺少符号。用户描述了编译过程，使用了 swift/utils/build-script --preset=buildbot_linux,no_test，但怀疑 Swift 5.10.1 的构建不完整，可能导致链接错误。

一位回复者建议，如果用户的 /usr/bin/ld 是 lld，需要在构建脚本中设置 LLVM_USE_LINKER=lld 变量，以确保 LLVM、lldb 和其他组件使用 lld，从而调整链接行为。并建议通过修改 swift/utils/build-presets.ini 文件来添加一个新的预设，以便在编译时启用该设置。

另外，回复者提供了在 Gentoo 系统上编译 Swift 6.0.1 的示例预设，并建议用户参考 buildbot_linux,no_assertions,no_test 预设，以禁用断言和测试项，简化构建过程。回复者还表达了愿意提供进一步帮助的意愿。

4) 讨论[原始标识符](https://forums.swift.org/t/se-0451-raw-identifiers/75602 "原始标识符")
**内容大概**
这篇 Swift 提案（SE-0451）评论中表示，提案的主要逻辑是合理的，允许描述性和程序生成的标识符，将对 Swift 语言有益。尽管提案已简化了对标识符中特殊字符的处理，但用户指出它在实现生成任意标识符的目标上仍存在不足：

1. 提案的局限性：
* 当前提案不支持转义字符，也禁止仅包含操作符字符的标识符，因此无法完全适用于某些编程场景，如将文件名（可能包含换行符或操作符）转换为标识符。
* 由于此限制，代码在合成标识符时仍需绕开 Swift 的语法规则，导致可能需要额外的转义方案，从而增加负担。
2. 改进建议：
* 用户建议 Swift 中引入一种通用的转义机制，以便任何字符串都能成为标识符，且标识符的内容不会影响语义。
* 例如，希望允许 foo\nbar() 等类似标识符，并能使用 Int.+ 指代常规标识符 +。
3. 支持该提案的理由：
* 用户认为，虽然提案不完美，但它为未来的改进奠定了基础，特别是在测试命名、枚举和代码生成中具有实际价值。
* 提案还获得其他开发者支持，他们认为它对工具链的额外负担是可控的，同时会显著提升开发体验。
4. 对未来改进的建议：
* 提案中还建议，未来可以通过社区贡献或一个小型工具包来减轻代码生成中的转义困难。此工具包可以包含禁用字符集的查询功能，判断字符串是否为合法的原始标识符，并提供基本的字符串转换为合法标识符的方法。这些功能可以作为未来方向来探讨。

5) 讨论[关于 Modern Swift 的主动反馈](https://forums.swift.org/t/unsolicited-feedback-on-modern-swift/75699 "关于 Modern Swift 的主动反馈")
**内容大概**
用户分享了在 Swift 中开发项目 SwiftClaude 的一些经验和反馈，特别是现代 Swift 特性如结构化并发、可变参数泛型和 SwiftSyntax 的使用。以下是主要反馈内容：

1. 正确的函数隔离模式：
* 用户分析了 Swift 中使用结构化并发的三种方式：普通的 async 函数、Actor 隔离函数以及可选的 Actor? 隔离函数。
* 最初用户尝试将所有类型标记为 Sendable，但最终认为不标记所有类型反而更适合项目需求（因为 SwiftClaude 中有很多不可传送的类型）。
* 用户指出，isolated Actor? 隔离可能是一个反模式，因为它不能保证数据安全，且容易导致崩溃。因此在 SwiftClaude 中，他们只使用非可选的 isolated Actor 以避免潜在问题。
2. withObservationTracking 的强大之处：
* 用户对 withObservationTracking 的功能表示赞赏，尤其是在将 @Observable 类型属性暴露为 AsyncSequence 时，帮助统一了异步和 SwiftUI 数据处理。
* 用户建议改进 withObservationTracking，在对象析构时也能触发 onChange，以便更好地跟踪对象的生命周期。
3. 重塑 Codable：
* 为实现 SwiftClaude 的功能，用户创建了自己的序列化系统，因为 Codable 类型中的 init(from:) 无法提供静态数据形状推断。
* SwiftClaude 使用自定义的 ClaudeToolInput 系统和可变参数泛型，以确保每个 ToolInput 类型都有静态已知的结构。用户可以利用这些信息生成 JSON 模式，从而实现与 Claude API 的交互。
* 用户希望 Swift 未来能提供更静态化的 Codable 类型，以便更直观地了解编码/解码流程。

## 推荐博文


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
