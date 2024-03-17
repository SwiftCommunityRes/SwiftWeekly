## 前言

**本期是 Swift 编辑组自主整理周报的第四十九期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

热麻辣烫美味，热辣滚烫美丽。**Swift社区**与你相约，一起成就更好的自己！👊👊👊

> **周报精选**
>
> 新闻和社区：143亿！苹果这个瓜真的有点大啊
> 
> 提案：解决 DistratedActor 协议
> 
> Swift 论坛：讨论 SwiftNIO 需要 noassert 模式，这个模式存在吗？
>
> 推荐博文：在 Playdate 上使用 Swift 构建小型游戏
>
> **话题讨论：** 
> 
> 你在工作中使用AI写代码吗？
>
>**上期话题结果**

![](https://files.mdnice.com/user/17787/9cd73db5-1edd-461d-b227-f1080e33c950.jpg)

根据投票结果分析，2024年购车的选择呈现出多样化的趋势。尽管传统的油车仍然占据主导地位，但混动车和电车的比例也相当可观，显示了消费者对环保和节能的关注程度在增加。

## 新闻和社区  

### 苹果公司公布重大调整

新华财经北京 3 月 13 日电当地时间 3 月 12 日，苹果公司宣布对欧盟地区的下载协议进行重大调整，将首次允许欧盟用户直接从开发者网站下载iPhone应用程序，以符合欧盟《数字市场法案》的规定。该项变更对欧盟地区的苹果用户立即生效。
 
此外，今年春季，苹果将添加一个新的 “Web Distribution” 功能，让开发者可以直接从自己的网站分发 iOS 应用程序。这意味着，iPhone 用户能够访问开发人员的网站并直接下载其应用程序，无需再使用 App Store 等应用程序市场。

不过，开发者必须选择新的 App Store 业务条款，才能使用此功能。苹果表示：“当引导用户在外部网页上完成数字商品或服务的交易时，开发者可以选择如何设计促销、折扣等。”

中国银河证券传媒互联网分析师岳铮认为，此次苹果针对欧盟地区做出一系列的开放性调整，对比以往调控力度较大，为欧盟地区开发者提供更多的灵活性，后续有望助其增加收入。建议持续跟踪全球其他地区苹果生态规则的调整，重点关注出海欧盟地区的游戏及应用发行商。(文章来源：中国证券报)

### 143亿！苹果这个瓜真的有点大啊

2024 年 3 月 11 日

两天前，欧盟对苹果公司处以 18.4 亿欧元的罚款，换算成人民币就是 143.7 亿。

作为参考，苹果 2024 财年第一季度营收为 1196 亿美元，约合人民币 8610 亿元。

罚款的原因，还是大家熟悉的那两个字——垄断。

欧盟委员会负责人表示：苹果公司滥用其在音乐流媒体 App 分发市场上的主导地位。他们限制开发者告知用户，苹果生态外有更便宜的购买选项。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2024%2F0311%2F177c3da0j00sa6je7002zd000hs006jg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

这一事件要追溯到 2019 年音乐平台 Spotify 的一次投诉，其认为苹果破坏了公平竞争。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2024%2F0311%2Fb1a17925j00sa6je7006bd000hs00mfg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

大家应该都知道苹果不允许 iPhone 用户通过侧载的方式安装 App，必须使用苹果自家的 App Store。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2024%2F0311%2F361e1299j00sa6je7000yd000hs009kg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

想充个 VIP，也必须通过苹果的渠道，苹果还得从中抽取最高 30% 的服务费。

俗称「苹果税」。

加上这笔费用，很多订阅服务在 iOS 端的价格，都会高于安卓或者网页端。

但是呢，苹果还要求开发者，不能在应用内提示用户，别的渠道可以用更低的价格开通会员。

霸道总裁了属于是。

更关键的是，苹果在这一顿骚操作的基础上，自己也开始做音乐平台。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2024%2F0311%2Fc9f55feej00sa6je7000sd000hs005kg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

既当运动员又当裁判，苹果的确会玩。

不少开发者都对此表示不满，而 Spotify 可以说是最刚的之一。一方面，刚才也有说，它去投诉了。另一方面，既然过路费无可避免，那干脆别从这过了。于是 Spotify 直接取消了 iOS 平台的内购，绝不让苹果多赚一毛钱。直到现在也是。而欧盟这次的决定，代表 Spotify 在这次对抗中已经取得了初步胜利。

为啥是初步呢？因为苹果已经明确表示，将提起上诉。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2024%2F0311%2F3e5819a7j00sa6je70034d000hs009mg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

面对如此高额的罚款，甚至还要涉及到审核规则的改动，苹果坐得住才奇怪。苹果很少在官网的文章里提到其他厂商，但这一次，将近两千多字的长文，安排上了。一字一句，都在斥责 Spotify，和欧盟的这个决定。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2024%2F0311%2Fc5b4bb98j00sa6je7001od000hs00aqg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

苹果表示，欧盟委员会未能发现任何消费者利益受损的实质证据，且忽视了这一市场繁荣兴盛、竞争充分、迅速发展的现实。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2024%2F0311%2F1fdf5f09j00sa6je70032d000hs009fg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

苹果反而认为，Spotify 占据了「支配性份额」，属于「领先者」，因为它目前已经是全球数字音乐行业最大的巨头企业，在欧洲市场占据了超过 50% 的份额。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2024%2F0311%2F602c1fdaj00sa6je7002ed000hs008tg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

苹果还用了一大段强调，自己给 Spotify 提供了诸多便利，但对方从未支付任何费用。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2024%2F0311%2Fcc4fd06bj00sa6je7002wd000hs009og.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

包括应用的分发、API /框架/测试平台的使用的便利等等。苹果还表示 Spotify 经常来催审核，自己还派工程师飞去亲自调试，都是免费的。简单来说就是，你白嫖我这么多年，竟然还有怨言？苹果还称，自己已经在几年前允许一些 App 把用户引导至其他网页，但 Spotify 并没有这样做。苹果认为 Spotify 真正想要的，就是直接嵌入订阅价格，但不向苹果支付任何报酬。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2024%2F0311%2F3ccfa540j00sa6je70038d000hs009fg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

与此同时，苹果还认为 Spotify 和欧盟委员会存在合作关系。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2024%2F0311%2F48dc4982j00sa6je70035d000hs009xg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

总而言之，这种彻底撕破脸皮的文章能直接出现在官网，可以感受到苹果确实是急了。接下来就看苹果的上诉，能不能改变一下局面喽。

不过 Spotify 这边也还没完。Spotify 在声明中表示，虽然此案「伸张了一些正义」，但全球其他市场的情况并没有改变。「直到真正公平的数字市场无处不在，我们的工作才会完成」。

其实。这两天苹果与欧盟的瓜，还不止这一个。关于侧载，也就是从第三方应用商店安装 App 这事儿，苹果和欧盟也是吵吵闹闹了好几年。目前来看，苹果还是妥协了。近期推送的 iOS 17.4 将允许用户用过「替代应用市场 alternative app marketplaces」安装 App。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2024%2F0311%2F9b737066j00sa6je70026d000hs006sg.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

不出意外，仅限于欧盟地区。如果系统检测到用户长期离开欧盟，那就没办法，只能用回 App Store 喽。不过已经下好的 App，还是可以用的。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2024%2F0311%2Fc8b6404aj00sa6je7002ad000hs0049g.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

So...之前还有不少小伙伴说买个欧版回来试试，现在应该是行不通了。那么问题来了，大伙希望苹果把这些措施带到国内吗？

## 提案

### 通过的提案

[SE-0424](https://github.com/apple/swift-evolution/blob/main/proposals/0424-custom-isolation-checking-for-serialexecutor.md "SE-0424") **自定义 SerialExecutor 的隔离检查** 提案通过审查。该提案已在 **四十八期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0425](https://github.com/apple/swift-evolution/blob/main/proposals/0425-int128.md "SE-0425") **128 位整数类型** 提案正在审查。

128 位整数是目前在“通用”代码中常用的最大固定大小类型。它们比 64 位类型要少见得多，但足够常见，因此将它们添加到标准库中是有意义的。我们已经在标准库中内部使用它们（例如，作为 Duration 的实现细节）。

[SE-0426](https://github.com/apple/swift-evolution/blob/main/proposals/0426-bitwise-copyable.md "SE-0426") **BitwiseCopyable** 提案正在审查。

我们提议引入一个新的标记协议 `BitwiseCopyable`，它可以由那些可以通过直接调用 `memcpy` 进行移动或复制且不需要特殊销毁操作的类型来遵循。当编译具有这些约束的泛型代码时，编译器可以直接发出这些高效操作，只需要在运行时进行最小的额外开销来查找值的大小。或者，开发人员可以使用这个约束来有选择地提供特定操作的高性能变体，例如容器的批量复制。

[SE-0427](https://github.com/apple/swift-evolution/blob/main/proposals/0427-noncopyable-generics.md "SE-0427") **不可复制的泛型** 提案正在审查。

SE-0390 引入的不可复制类型：不可复制结构体和枚举不能与泛型、协议或存在类型一起使用，这在语言中留下了一种表达能力的差距。本提案扩展了 Swift 的类型系统以填补这一差距。

[SE-0428](https://github.com/apple/swift-evolution/blob/main/proposals/0428-resolve-distributed-actor-protocols.md "SE-0428") **解决 DistratedActor 协议** 提案正在审查。

Swift 的分布式 actor 为开发人员提供了一种灵活的自定义运行时方法，以使用 actor 范式构建分布式系统。该功能的初始设计旨在用于所有节点共享相同二进制文件的系统（例如集群中的节点），因此所有节点都可以访问可能会被解析并进行远程调用的具体 `distributed actor` 声明。

尽管这对点对点系统非常有效，但分布式参与者也适用于需要客户端/服务器分离的系统。这种用例的示例包括将一些容易出错的逻辑隔离到另一个进程中，或在客户端和后端服务之间进行拆分，客户端缺乏实现 API 所需的库或知识，将此工作委托给后端服务。

[SE-0429](https://github.com/apple/swift-evolution/blob/main/proposals/0429-partial-consumption.md "SE-0429") **不可复制值的部分消耗** 提案正在审查。

我们建议允许在没有析构函数的聚合类型中，单独消耗当前模块中定义的或者已被冻结的不可复制字段。此外，我们建议允许在具有析构函数的聚合类型中，单独消耗该析构函数中的字段。这使得许多不可复制值可以使用常见模式。

## Swift论坛

1) 讨论[Wasm/WASI 的 Stdlib 和运行时测试现在可在 Swift CI 上使用](https://forums.swift.org/t/stdlib-and-runtime-tests-for-wasm-wasi-now-available-on-swift-ci/70385/1 "Wasm/WASI 的 Stdlib 和运行时测试现在可在 Swift CI 上使用")

**内容概括**

Swift 针对 WebAssembly (Wasm) 和 WebAssembly 系统接口 (WASI) 的标准库和运行时测试现已在 Swift Continuous Integration (CI) 上提供，这标志着 Swift 工具链中 WebAssembly 支持开发的一个重要里程碑。 

以前，对于 Wasm 和 WASI 平台来说，维护主 Swift 存储库的分支是必要的，但 SwiftWasm 团队（特别是 @kateinoigakukun 领导的团队）最近的努力已经消除了这种需求。

上游 Swift 工具链的开发快照已经启用了几个月的 Wasm 编译，WasmKit 中的性能优化允许在 CI 上运行 Swift 标准库和为 WASI 编译的运行时测试。

由 `@mishal_shah` 实现的 apple/swift 存储库主分支上的新 CI 作业允许监控 WASI 支持的稳定性。 我们鼓励贡献者在合并之前在其拉取请求 (PR) 上运行此 CI 作业。

尽管在 Swift 中增强 WebAssembly 体验仍有工作要做，但定期 CI 测试对于进步至关重要。 社区热切等待 WebAssembly 社区对 Swift 做出更多贡献。

为了将 Swift 编译为 WebAssembly，开发人员可以使用上游 Swift 编译器，该编译器在预览模式下支持 Wasm。 Wasm 的交叉编译遵循与其他平台相同的过程，使用适当的编译器开关或选项。

Swift 的标准库函数可以在 wasm32-unknown-wasi 三元组的编译过程中使用，但不能用于 wasm32-unknown-none-wasm 三元组，其中类似的限制适用于其他嵌入式 Swift 平台。

对于文件 I/O 等系统相关功能，开发人员可以利用 Swift System 或 Swift Foundation 库。 任何其他 WASI 兼容的运行时都应该能够使用 .wasm 文件运行，只要二进制文件没有除了 wasi_snapshot_preview1 标准导入之外的其他导入。

2) 提议[SE-0425：128 位整数类型](https://forums.swift.org/t/se-0425-128-bit-integer-types/70456 "SE-0425：128 位整数类型")

**内容概括**

SE-0425 提议向 Swift 添加 128 位整数类型。 这些类型可在 swift-numerics 包的一个名为 int128 的分支中进行实验。 该提案的反馈截止日期为 2024 年 3 月 19 日，审核经理为 Doug Gregor。 

该提案包括以 JSON 和 plist 格式对这些大整数类型进行编码和解码的考虑因素，提出了处理 Int128 和 UInt128 类型的编码和解码容器的协议要求。 建议默认实现将这些类型编码为 64 位整数对，从而允许特定编码人员根据需要灵活地以不同方式处理表示形式。 寻求 Swift 社区的反馈来完善该提案并确定其与 Swift 的目标和方向的一致性。

3) 讨论[SwiftNIO 需要 noassert 模式，这个模式存在吗？](https://forums.swift.org/t/swiftnio-needs-a-noassert-mode-does-this-exist/70454 "SwiftNIO 需要 noassert 模式，这个模式存在吗？")

**内容概括**

围绕 SwiftNIO 中“noassert”模式必要性的讨论深入探讨了库中前提条件的使用，强调了它们的多方面目的。 首先，先决条件用于防止调用未定义的行为，例如越界内存访问，如果不加以控制，可能会导致灾难性后果。 其次，它们充当一种防御机制，防止用户通过滥用 API 无意中导致复杂且难以诊断的问题，例如承诺泄漏。 这种主动方法旨在将无声故障转变为更明显的故障，确保及时识别和解决开发人员的错误。

然而，对话承认处理意外前提条件失败的挑战，特别是在某些条件被认为不可能的情况下。 虽然遇到先决条件通常意味着程序中存在真正的错误，但人们认识到开发人员容易犯错，曾经被认为不可能的事情实际上可能会发生。 因此，最佳实践转向采用更灵活的方法，其中对所谓不可能路径的断言与优雅的错误处理机制相结合。

此外，讨论还扩展到解决有关处理库中前提条件失败的更广泛的问题，特别是在服务器端 Swift 应用程序的上下文中。 与其他编程语言中的错误处理实践进行了比较，突出了 Swift 独特的限制和挑战。 尽管存在困难，还是提出了增强错误处理能力的建议，例如区分不同类型的前提条件失败并允许更受控的恢复机制。

总的来说，这次对话强调了 SwiftNIO 平衡安全性和灵活性的重要性，并认可了框架内为改进错误处理机制所做的持续努力。

4) 讨论[@MainActor 方法中的 Task {...} 是否保证在下一个运行循环周期中运行？](https://forums.swift.org/t/is-task-in-a-mainactor-method-guaranteed-to-run-in-the-next-run-loop-cycle/70436 "@MainActor 方法中的 Task {...} 是否保证在下一个运行循环周期中运行？")

**内容概括**

讨论围绕着理解“@MainActor”方法中任务的行为展开，特别是关于它们的执行时间以及是否保证它们在下一个运行循环周期中运行。 在解决最初的问题时，强调应该避免对当前运行循环的假设，即使是在主线程上。

参与者强调了考虑运行循环模式的重要性，但澄清说，如果开发人员知道自己所在的线程，那么他们通常不需要担心自己处于哪个运行循环中。 线程的运行循环是按需创建的，当任何线程调用某些 Core Foundation 函数时，就会创建主线程的运行循环。

尽管对运行循环的访问受到限制，但值得注意的是，后台线程可以在特定情况下运行运行循环，例如在使用某些 Core Foundation 函数时。

经过讨论，最初的问题被细化为仅关注 Swift 的行为，而没有明确提及运行循环。 参与者尝试确定 Swift 是否保证涉及“@MainActor”方法中任务的代码的特定输出行为。

总之，虽然运行循环被认为是一个重要的基础概念，但我们还是努力以与平台无关的方式解决这个问题，重点关注 Swift 在任务执行计时方面的行为。

5) 讨论[Swift Macros：构建时间开销问题](https://forums.swift.org/t/swift-macros-build-time-overhead-concerns/70443 "Swift Macros：构建时间开销问题")

**内容概括**

讨论解决了与使用 Swift 宏相关的构建时间开销的问题，该功能是为了提高代码质量并减少样板文件而引入的。 通过一系列实验，团队观察到在各种项目设置中使用宏时构建时间显着增加。

分析了三种不同的宏类型：StringifyMacro、MemberwiseInitMacro 和 ObservationMacro，每种宏类型都展示了不同的使用场景和性能影响。 对使用宏的项目和使用非宏等效项的项目进行了比较，揭示了构建时间的显着差异。

调查结果表明，使用宏时构建时间开销会大幅增加，观察结果表明宏可执行文件会增加额外的构建步骤和系统负载。 该团队向社区寻求有关潜在解决方法、优化或正在进行的 Swift 开发的见解，以解决这些问题。

此外，轶事经验强调了宏进程使系统超载的情况，可能导致构建冻结或速度减慢。 鼓励进一步测试以探索跨文件的宏进程的可扩展性、潜在的死锁、优化机会以及分析以识别瓶颈。

总之，虽然 Swift 宏有望改善开发实践，但观察到的构建时间开销构成了重大挑战，促使社区合作制定缓解策略和优化。

6) 讨论[将 String 与零拷贝 C API 一起使用](https://forums.swift.org/t/using-string-with-zero-copy-c-apis/70476 "将 String 与零拷贝 C API 一起使用")

**内容概括**

讨论围绕如何利用 Swift 的 String 类型和零拷贝 C API 展开，特别关注 Swift 的内存管理限制阻碍与此类 API 进行有效交互的场景。 Tree-sitter 的 API 提供了一个具体示例，展示了需要提供连续字符串数据而无需复制的 TSInput 闭包。

挑战在于安全地转义从 Swift 对象派生的指针，确保它们在整个 API 调用过程中的有效性，而无需诉诸手动内存管理。 现有的解决方案（例如 SwiftTreeSitter）采用缓冲区分配和清理策略来解决此问题。

参与者提出了对 Swift 闭包类型的潜在增强，以促进安全的指针转义，理想情况下允许表达对象生命周期和转义指针之间的依赖关系。 然而，人们承认，在没有手动生命周期管理的情况下实现这一目标仍然是一个挑战。

人们提出了各种想法，包括扩展 Swift 闭包来封装函数指针和上下文指针，或者利用借用或仅移动类型来表达对象和转义指针之间的依赖关系。 最终目标是直接从 Swift 与零拷贝 C API 进行高效、安全的交互，最大限度地减少不必要的内存复制和管理开销。

7) 提议[SE-0426：可按位复制](https://forums.swift.org/t/se-0426-bitwisecopyable/70479 "SE-0426：可按位复制")

**内容概括**

关于 SE-0426（BitwiseCopyable）的讨论围绕着改进所提议协议的定义和实现细节。 参与者对 BitwiseCopyable 的概念表示同意，其中包含 BitwiseMovable、NoOpDeinit 和可能 Copyable 的类型。 但是，对于 BitwiseCopyable 是否应包含可复制但不包含 BitwiseMovable 且具有 NoOpDeinit 的类型，存在不同意见。

反馈建议重新考虑 BitwiseCopyable 作为标记协议的特征，强调需要澄清语言属性，并避免与 SE-0302（可发送）中定义的标记协议概念混淆。 标记协议被概述为具有特定的属性，包括在各种情况下对其使用没有要求和限制。

人们担心运行时表示是否有必要实现 BitwiseCopyable 一致性，特别是在后端部署场景中。 在避免不必要的开销的同时，人们认识到需要一些运行时支持来查询 BitwiseCopyable 约束。

总的来说，讨论强调了完善 BitwiseCopyable 的定义和实现的重要性，以平衡 Swift 版本之间的效率、清晰度和兼容性。

## 推荐博文

[在 Playdate 上使用 Swift 构建小型游戏](https://www.swift.org/blog/byte-sized-swift-tiny-games-playdate/ "在 Playdate 上使用 Swift 构建小型游戏")

**摘要：**  这篇 swift 官方博客详细介绍了如何在 Playdate 上使用 Swift 构建小型游戏的过程。作者首先介绍了为什么选择 Swift 以及 Playdate 的背景，然后讨论了 Swift 在嵌入式系统中的应用和发展。

作者分享了他在使用 Swift和 Playdate SDK 构建 Conway's Game of Life 和 Swift Break 两款游戏的经验，包括在模拟器和真机的调试和优化过程。文章还深入探讨了如何改进 Playdate C API 的 Swift 封装以提高代码的可读性和易用性。作者最后总结了整个开发过程中遇到的挑战和解决方案，并鼓励读者尝试在非传统环境中使用  Swift 开发。

[Swift 中的全局 actors](https://swiftwithmajid.com/2024/03/12/global-actors-in-swift/ "Swift 中的全局 actors")

**摘要：**  在这篇文章中，作者探讨了如何在 Swift 中使用全局 actors 。全局 actors 允许我们保护多种类型，确保它们具有互斥访问。通过示例代码和解释，解释了如何定义和使用全局 actors ，特别是 `@MainActor` 和自定义的 StorageActor 。

这些全局 actors 有助于确保在特定情况下的线程安全性，如主线程渲染。通过在类型、函数或属性上标记 `@MainActor` 或自定义的全局 actor ，我们可以确保特定工作在相应的 actor 上独占运行。全局 actors 在特定情况下非常有用，如主线程渲染。

[Swift 类型中的 Equality, Identity 和 Hashing](https://juejin.cn/post/7340278606391869459/ "Swift 类型中的 Equality, Identity 和 Hashing")

**摘要：**  本文深入探讨了 Swift 类型中的 Equality、Identity 和 Hashing 的概念。
文章首先介绍了 Equality 的概念，以值类型和引用类型为例，介绍了如何实现 Equatable 协议以便比较对象是否相等。对于引用类型，还介绍了 Identity 的概念，使用 "===" 运算符来检查对象是否指向相同的引用。

接着讨论了 Hashable 的重要性，特别是在需要在 Dictionary 或 Set 中进行快速查找时。文章解释了 Hashable 的原理，如何为自定义类型实现 Hashable 协议，并提到了哈希碰撞可能会影响性能的问题。文章最后强调了正确实现 Hashing 的重要性，展示了如何在 Swift 中实现 Hashable 协议来生成有效的哈希值，并提到了好的哈希值的必要性以防止潜在的安全漏洞。

## 话题讨论

你在工作中使用AI写代码吗？

1. 从不，自己手动搜索
2. 不经常使用
3. 如果遇到了困难会使用
4. 用AI生成初始代码然后自己往里面加东西
5. 一直在用，自己只是修改很少的一部分

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
