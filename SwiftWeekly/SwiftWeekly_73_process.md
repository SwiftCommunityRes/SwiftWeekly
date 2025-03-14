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
1) 提议[values的交换性观察](https://forums.swift.org/t/pitch-transactional-observation-of-values/78315 "values的交换性观察")

在 Swift 论坛的提案“values的交换性观察”中，提出了一个新的机制，旨在通过可组合的 @Observable 数据源，提供一个 AsyncSequence，以便安全、简洁地观察模型的变化。该机制在第一个 willSet 时启动事务，并在事务结束时于第一个一致性点发出值，与 Swift 并发性进行交互。

此提案的动机在于，虽然最初的观察工具与 SwiftUI 无缝集成，但其目标更为广泛。通过引入一个闭包初始化的 Observed 类型，作为一个序列来跟踪闭包返回的值，当闭包中的某些内容发生变化时，该序列会发出新值。这使得编写异步序列来跟踪变化变得简单，同时确保访问在并发性方面的安全性。

例如，考虑一个使用 @Observable 标记的简单 Person 类型，其中包含 firstName 和 lastName 属性，以及一个组合属性 name。通过创建一个 Observed 异步序列，可以在每次更新 name 属性时获取新值。此外，如果 Person 类型包含一个可选的 Pet 属性（同样使用 @Observable 标记），则可以创建一个更复杂的表达式，在 person 或其 pet 发生变化时，异步序列会发出相应的问候语。

这一提案为非 SwiftUI 系统提供了与 SwiftUI 相同级别的“恰到好处的魔法”，使开发者能够避免在确保 UI 随值变化而更新时所固有的复杂性。

2) 提议[解除函数调用中显式专门化的限制](https://forums.swift.org/t/pitch-lifting-restriction-on-explicit-specialization-in-function-calls/78231 "解除函数调用中显式专门化的限制")

在提案中，建议解除当前对函数调用中显式类型专门化的语法限制。目前，Swift 不允许在调用泛型函数时显式指定类型参数，开发者需要通过传递元类型参数或依赖类型推断来实现。例如，对于一个解码函数，通常需要传递类型的元类型参数：
```Swift
func decode<T>(_ type: T.Type, from data: Data) throws -> T
```
调用时需要提供 MyType.self，这对于新手来说可能并不直观。提议允许在函数调用中直接指定类型参数，如：
```Swift
let value = decoder.decode<MyType>(from: data)
```
这种语法在其他编程语言（如 C++、Java、Rust、C#）中已被广泛采用。Haskins 还提交了一个实验性的拉取请求，展示了解除此限制的可行性。

总而言之，这一提案旨在使 Swift 的泛型函数调用更加直观，减少对类型推断的依赖，提高代码的可读性和可维护性。

3) 提议[宣布成立测试工作组](https://forums.swift.org/t/announcing-the-testing-workgroup/78336 "宣布成立测试工作组")

在 Swift 论坛的公告“宣布成立测试工作组”中，Stuart Montgomery 宣布成立一个新的 Swift 测试工作组，旨在指导 Swift 代码的测试体验、库和工具的发展。该工作组由 Swift 测试的核心贡献者和社区中倡导质量与测试工具的成员组成。有关该工作组的章程、成员以及参与方式的详细信息，请参阅 Swift.org 上的测试工作组页面。  ￼

创建测试工作组的想法最初出现在语言指导小组去年夏天审查测试愿景文档期间，并在其批准公告中提到：

	将创建一个新的 Swift 测试工作组，负责监督 Swift 项目内的测试工作，最终归属于生态系统指导小组。

总而言之，Swift 测试工作组的成立标志着 Swift 社区在提升代码质量和测试工具方面迈出了重要一步，期待更多开发者的参与和贡献。

4) 提议[在 Linux 上的 Swift System 中支持 io_uring](https://forums.swift.org/t/pitch-io-uring-support-in-swift-system-on-linux/78340 "在 Linux 上的 Swift System 中支持 io_uring")

“在 Linux 上的 Swift System 中支持 io_uring”中，提议为 Linux 的 io_uring 提供一个低级 Swift API，以解决可伸缩性和线程池枯竭问题。  ￼

io_uring 是 Linux 于 2019 年引入的异步和批量系统调用解决方案，特别关注 IO 操作。传统的 Unix 平台主要使用同步文件 IO 系统调用，例如 read(2)，这在高并发场景下可能导致内存和 CPU 开销增加。io_uring 通过允许批量提交和完成 IO 操作，减少了系统调用的开销，提高了性能。

提案中介绍的 IORing 结构体提供了以下功能：
* 注册和注销资源（文件和缓冲区），这是一种 io_uring 特有的高效处理文件描述符的方式。
* 注册和注销事件文件描述符（eventfd），允许异步等待完成事件。
* 将 IO 请求加入队列。
* 从队列中取出已完成的 IO 操作。

此外，IOResource<T> 类表示注册的文件描述符和缓冲区，IORequest 结构体表示可以加入内核执行的 IO 操作。这些设计旨在使 Swift 开发者能够直接或通过中间层（如 Swift NIO）利用 io_uring 的优势，从而提升在 Linux 服务器上的可伸缩性和效率。

该提案旨在通过在 Swift System 中引入对 io_uring 的支持，提升 Swift 在 Linux 平台上的异步 IO 能力，满足高性能和高并发应用的需求。

5) 提议[UTF8Span——对连续字节的安全 UTF-8 处理](https://forums.swift.org/t/se-0464-utf8span-safe-utf-8-processing-over-contiguous-bytes/78307 "UTF8Span——对连续字节的安全 UTF-8 处理")

在 Swift 论坛的提案“SE-0464: UTF8Span: Safe UTF-8 Processing Over Contiguous Bytes”中，提出了引入 UTF8Span 类型，以便在连续内存中高效且安全地处理 UTF-8 编码的数据。  ￼

UTF8Span 旨在提供一种轻量级的视图，使开发者能够直接在连续的 UTF-8 编码字节上进行操作，而无需将其转换为 String 类型。这对于需要处理大量文本数据且关注性能的应用程序尤为重要。

该提案目前正处于审查阶段，审查期从 2025 年 3 月 5 日开始，至 2025 年 3 月 19 日结束。社区成员被鼓励在此期间提供反馈，以改进该提案并决定其在 Swift 中的未来方向。

总而言之，UTF8Span 的引入将为 Swift 开发者提供一种高效且安全的方式来处理连续内存中的 UTF-8 数据，提升文本处理的性能和灵活性。

## 推荐博文


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
