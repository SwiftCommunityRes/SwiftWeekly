## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百零五期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

万物在暑气里沸腾，我们在平淡里藏着热忱。愿晚风为你送来清凉，让夏夜的梦，温柔又绵长。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：苹果与 OpenAI 反目成仇：400 人挖角与商业机密之争；库克收官财报在即
> * **提案**：SE-0537 函数部分放置控制、SE-0538 Disconnected 类型正在审查；SE-0533 宏生成同步重载被拒绝
> * **Swift 论坛**：AliasedSpan/Ref 类型提案、UserDefaults 的 Sendable 谜团、Vapor 最小 Docker 镜像、SwiftUI 导入机制、IP 地址与端口标准 API 征集
> * **推荐博文**：Swift 6.4 新特性与 XCTest 互操作、SwiftUI Document 协议性能提升、Swift 6.4 底层革命前瞻

## 话题讨论

**Apple 对 OpenAI 提起商业机密诉讼，引发外界讨论：这场官司究竟只是法律战，还是会真正影响 OpenAI 与 Jony Ive 的 AI 硬件计划，甚至未来 IPO？目前双方各自坚持自己的立场，案件仍在审理中。**
**如果 OpenAI 真的推出 AI 硬件（据报道可能是无屏幕、便携式 AI 设备），你会买吗？**

1、第一时间尝鲜
2、等评测再决定
3、手机 + ChatGPT 已经够用了
4、除非 Apple 自己推出 AI 硬件，否则不会考虑

欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

**上期投票结果：**

![](https://files.mdnice.com/user/38782/3a5cc6f1-d245-454b-a437-76ce60308ad2.jpg)

**DeepSeek 以 33.33% 的得票率领先，读者对国产大模型的期待更多聚焦于性价比和技术突破潜力，而非品牌或生态因素。**

## 新闻和社区

### 苹果与 OpenAI 从盟友到对簿公堂：400 人挖角战背后的商业机密之争

*2026 年 7 月 23 日｜来源：新浪财经*

![](https://files.mdnice.com/user/38782/dcb12985-b0e1-494e-b76c-082a363f450f.png)

7 月 10 日，苹果向法院提交长达 41 页诉状，正式起诉 OpenAI、两位前苹果员工及 io Products（OpenAI 子公司），指控对方系统性挖走 400 名前苹果员工，借此窃取商业机密。具体手法包括：要求应聘者携带未发布的硬件零部件到 OpenAI 面试讲解；前员工利用离职后的系统漏洞下载机密文件；用苹果内部"Need to Know"离职安全文件指导员工躲避离职检查。

![](https://files.mdnice.com/user/38782/80bba597-b625-46f1-b790-65e4c3cb9a60.png)

苹果在诉状中强调，目前已有超过 400 名前苹果员工进入 OpenAI

**盟友为何反目？** 2024 年 WWDC 上苹果宣布与 OpenAI 合作，将 ChatGPT 嵌入苹果系统，但 OpenAI 在两年合作中发现自己并未如预期般深度进入苹果生态——ChatGPT 在 iOS 内入口藏得太深，Apple ID 等用户信息默认不共享，且苹果同时还在与谷歌、Anthropic 接触。对 OpenAI 而言，这只是一次"信任之跃"式的失败合作；但真正引爆矛盾的，是 2025 年 OpenAI 收购 io Products 后，组建起一支"缩小版苹果设计团队"（Jony Ive、Evans Hankey、Tang Tan 等），开始自研 AI 硬件，被苹果视为战略威胁。

![](https://files.mdnice.com/user/38782/d3532d08-29f4-4443-8bab-d4120c717fd4.png)

2024 年苹果全球开发者大会（WWDC）上，苹果宣布和 OpenAI 合作，把 ChatGPT 嵌入到苹果系统中

值得注意的是，6 月 29 日苹果印度代工伙伴塔塔电子刚遭遇 630GB 泄密，但苹果仅对 OpenAI 提起诉讼。投资人王倾分析，差异在于：塔塔泄密是安全意外，而 OpenAI 挖角是赤裸裸的战略威胁。

![](https://files.mdnice.com/user/38782/8afceca7-5343-46e4-a65e-fb63450f7dc3.png)

Apple 控告 Open AI 泄密案：关键前员工指控

![](https://files.mdnice.com/user/38782/faf25a34-bed3-4776-a230-e6933809f9ea.png)

Tang 通过利用一份标注"Need to Know"的苹果内部管理人员离职安全文件，与 OpenAI 团队一起，指导苹果离职员工躲过苹果的离职检查

![](https://files.mdnice.com/user/38782/ee6cbe63-6228-4777-af17-c2dd37f0d177.png)

OpenAI CEO 山姆·奥特曼(Sam Altman)

2026 年苹果 AI 战略常被批评落后，承诺的"更个性化 Siri"最终以搭载 Gemini 模型的形式呈现——OpenAI 这面镜子，让苹果看到了自己在 AI 新竞争中的被动。

![](https://files.mdnice.com/user/38782/c33ba477-24ac-403a-b9bb-3d226168e850.png)

当 Siri 判断问题应该交由 ChatGPT 处理时，会先弹窗请求用户授权

![](https://files.mdnice.com/user/38782/652013ae-4c9f-448f-961e-5e7c449b53aa.png)

2026 年 6 月下旬，一个黑客组织声称从印度塔塔电子（Tata Electronics）窃取了超过 630GB 的内部数据，涉及超过 20.4 万个文件，其中包含苹果和特斯拉的机密工程文档

![](https://files.mdnice.com/user/38782/73856c14-0d1e-48d8-86b7-276722be93a9.png)

OpenAI 的硬件业务"看起来"还没有颠覆苹果的能力

![](https://files.mdnice.com/user/38782/0edbacac-dc95-49eb-98ca-ad42fd279040.png)

2026 年 7 月 9 日，Sam Altman 发帖称 OpenAI 发布了全新的 GPT Live 语音模型

### 库克迎来离任收官财报 美银称芯片涨价压制苹果短期毛利率

*2026 年 7 月 9 日｜来源：环球市场播报*

7 月 30 日将是蒂姆·库克以苹果 CEO 身份主持的最后一场财报电话会议。届时库克将执掌苹果满 15 年，9 月 1 日起转任执行董事长，由硬件工程负责人约翰·特尔纳斯接任 CEO。

美银维持苹果买入评级，目标价 380 美元，预计 Q3 营收 1090 亿美元、EPS 1.89 美元，均高于市场一致预期；本季度 iPhone 营收同比涨幅超 20%，服务业务保持两位数增长，整体毛利率 48.2% 处于指引区间正中。

**短期毛利率承压** 受存储芯片涨价影响，6 月财季硬件毛利率环比下滑约 190 个基点，9 月财季将再降 280 个基点；美银判断这是阶段性现象，秋季新机（含折叠屏）上市后 12 月财季将大幅修复，且苹果有望收回约 30 亿美元关税相关款项。

**iPhone 分批次发布** 苹果今年首次打破秋季同步发售惯例：Pro、Pro Max 与折叠屏 9 月推出，标准版与全新 iPhone Air 推迟至 2027 年 3 月上市。这一调整将重塑季节性营收规律——9 月、12 月财季低于预期，2027 年 Q1 则迎来增长红利。

## 提案

### 正在审查的提案

[SE-0537](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0537-function-sections.md "SE-0537")
**功能的部分放置控制** 提案正在审查。

此提案扩展了 SE-0492 中引入的 `@section` 属性，也允许用 `@section` 注释函数。这在嵌入式系统中很有用，因为一些代码（例如固件的启动代码）需要放在二进制文件的特定部分。

[SE-0538](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0538-disconnected.md "SE-0538")
**Disconnected** 提案正在审查。

本提案引入了一种 `Disconnected`，该类型通过存储（如在数据结构或演员中）保留值的断开属性，允许通用类型在隔离区域之间安全地传输不可 `Sendable` 的值，而无需这些类型对 `sending` 效果进行推理。

### 拒绝的提案

[SE-0533](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0533-reasync-macros.md "SE-0533")
**使用宏生成 async 函数的同步重载** 提案被拒绝。该提案此前已在 **第一百零一期周报** 的「正在审查的提案」模块中做过详细介绍。

## Swift论坛

### 1、[提案：支持别名访问的 Span 与 Ref 类型]

作者：Douglas Gregor ｜ 发布日期：2026 年 7 月 24 日
[阅读原帖](https://forums.swift.org/t/pitch-aliased-span-and-ref-types/88529 "[Pitch] Aliased Span and Ref types")

**核心内容：**
该提案计划引入一组 **AliasedSpan**、**AliasedMutableSpan**、**AliasedRef** 与 **AliasedMutableRef** 类型。它们保留现有 **Span**、**Ref** 家族的内存安全能力，同时放宽 Swift 独占访问规则，以适配共享内存以及 C、C++ 等语言的互操作场景。API 整体沿用现有类型的设计，但针对内存可能存在别名的事实限制借用和修改方式。

**动机说明：**
讨论重点落在安全边界与生态采用策略上。社区指出，可变别名引用若跨并发任务共享，普通读写可能发生撕裂并破坏值的不变量；Douglas 因此倾向于让这些类型永远不遵循 **Sendable**。对于公共库 API，他仍建议优先使用非别名 **Span**，以保留独占访问带来的优化空间，仅在共享内存或 C 互操作等必要场景使用别名类型。

**简要点评：**
该提案填补了安全视图与现实互操作之间的重要缺口，但最终设计必须明确并发与类型转换的约束。

### 2、[为什么 UserDefaults 不遵循 Sendable？]

作者：Ben Pious ｜ 发布日期：2026 年 7 月 25 日
[阅读原帖](https://forums.swift.org/t/why-isnt-userdefaults-sendable/88531 "Why isn't UserDefaults Sendable?")

**核心内容：**
虽然文档说明 **UserDefaults** 本身是线程安全的，可同时用于多个线程或任务，但它没有遵循 **Sendable**。原因在于 **UserDefaults** 可以被继承：基类的线程安全并不能保证所有子类同样安全，而实际项目中确实存在并非线程安全、且并不少见的子类，因此 Foundation 无法为整个类层次提供 **Sendable** 保证。

**动机说明：**
讨论还提到，开发者可以用 `@retroactive @unchecked Sendable` 绕过检查，但这会把正确性责任完全交给自己，不适合作为通用方案。一个可能的改进方向是将 **UserDefaults** 标记为 `~Sendable`，让经过审慎设计的子类自行声明 **Sendable**，而不是彻底禁止。

**简要点评：**
这一案例提醒我们：线程安全描述的是具体实现，并不自动等价于可继承类型在 Swift 并发模型中的可发送性。

### 3、[运行 Vapor 应用的最小 Docker 镜像是什么？]

作者：Lars Sonchocky-Helldorf ｜ 发布日期：2026 年 7 月 24 日
[阅读原帖](https://forums.swift.org/t/what-is-the-smallest-docker-container-to-run-a-vapor-app/88507 "What is the smallest Docker container to run a Vapor app?")

**核心内容：**
讨论聚焦如何缩小 **Vapor** 应用的生产容器。默认生成的部署配置以 Ubuntu 为基础，但在镜像体积敏感的场景中，可以使用 Swift 的 **Static Linux SDK**（Musl SDK）编译应用，再部署到更精简的 Alpine 镜像；这是讨论中给出的最小化方向。

**动机说明：**
另一种选择是使用经过裁剪的 **chiseled container**，它同样能显著减少运行时内容。关键不只是替换 `FROM`：构建产物必须针对目标 C 标准库和运行环境生成，尤其要避免把 glibc 构建的二进制直接放进 musl 环境。

**简要点评：**
对于追求极致体积的服务，静态 Linux SDK 加 Alpine 值得优先验证；若更看重兼容性与维护成本，chiseled 镜像通常更稳妥。

### 4、[为什么 Swift Package 无需声明依赖就能导入 SwiftUI？]

作者：Bit By A Vampire ｜ 发布日期：2026 年 7 月 24 日
[阅读原帖](https://forums.swift.org/t/why-is-swiftui-always-available-in-swift-package-without-needing-to-declare-dependency-on-it/88518 "Why is SwiftUi always available in Swift Package without needing to declare dependency on it?")

**核心内容：**
**SwiftUI** 并不是由 Swift Package Manager 构建和下载的包依赖，而是随 macOS、iOS 等 Apple 平台 SDK 与操作系统提供的系统框架。因此，只要目标平台的 SDK 包含 SwiftUI，源码就可以直接 `import SwiftUI`，无需在 `Package.swift` 的 `dependencies` 中声明它；应用启动时会动态链接对应框架。

**动机说明：**
如果包没有导入 SwiftUI，就不会产生使用成本。讨论进一步指出，即使导入，由于 Apple 平台使用 **dyld shared cache**，其额外运行时成本也接近于零。需要注意的是，"可以导入"并不代表跨平台可用：面向 Linux 或不支持 SwiftUI 的 Apple 系统版本时，仍应通过平台声明、可用性检查或条件编译约束代码。

**简要点评：**
理解 SwiftUI 的导入机制有助于避免不必要的依赖声明，同时也要注意跨平台兼容性。

### 5、[征集 IP 地址与端口标准 API 的设计需求]

作者：Tommy Pauly ｜ 发布日期：2026 年 7 月 24 日
[阅读原帖](https://forums.swift.org/t/requirements-for-ip-address-and-port-apis/88514 "Requirements for IP address and port APIs")

**核心内容：**
Swift **Networking Workgroup** 正在规划标准化的 IP 地址与端口"通用交换类型"，希望解决 URLSession、SwiftNIO、中间件、配置、日志和高性能数据通路各自采用不同表示的问题。首阶段聚焦 **IPv4**、**IPv6** 与端口，并征集所有权模型、内存视图、解析与序列化、类型转换、地址属性查询以及与 **Span** 协作等需求，目标是建立高性能且可被各网络库共同使用的基础 API。

**动机说明：**
社区重点推荐了 `swift-endpoint` 的现有设计，其中包含 `IPv4Address`、`IPv6Address`、`AnyIPAddress`、`CIDR`、`DomainName`、`ConnectionTarget` 与 `Port` 等类型，并支持无分配的 **Span** 解析、C 互操作和 RFC 地址分类。讨论亮点还包括 ByteBuffer 与 `[UInt8]` 间的复制成本、IDN 表带来的二进制体积、旧系统对 `UInt128` 的可用性限制、Unix Domain Socket、模糊测试及未来协议扩展。

**简要点评：**
标准类型若能兼顾这些现实约束，将明显降低 Swift 网络生态的桥接成本。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[Swift 6.4 带来了新的语言特性以及 Swift 与 XCTest 之间的互操作性](https://www.infoq.cn/article/MrNN9S3ZTFiCaoaU3h4i/ "Swift 6.4 带来了新的语言特性以及 Swift 与 XCTest 之间的互操作性")

**摘要：** 这篇报道详细梳理了 Xcode 27 中 Swift 6.4 Beta 版的全新特性。语言层面包括 weak let与~Sendable、defer 支持 await 异步任务、anyAppleOS 简化可用性检查、以及通过 @diagnose 实现更精细的警告控制。测试方面，Swift Testing 与 XCTest 实现了双向互操作—— XCTest 断言失败可在 Swift Testing 中报告，Swift Testing API 也可在 XCTest 中运行。此外， @C 属性支持将 Swift 函数暴露给 C 语言，Foundation 继续向纯 Swift 迁移，URL 解析速度最高提升4倍。

[SwiftUI 新增文档协议，性能全面提升](https://www.infoq.com/news/2026/07/swiftui-wwdc26/ "SwiftUI 新增文档协议，性能全面提升")

**摘要：** 这篇报道系统梳理了 WWDC 2026 上 SwiftUI 的核心更新。新的 Document 协议通过快照差异比较和异步读写，让文档型应用高效处理大量数据。工具栏 API 新增 visibilityPriority ，可控制按钮显示优先级，自动将不常用操作收进溢出菜单。滑动操作现已支持任意视图而不仅是列表；AsyncImage 获得自动 HTTP 缓存支持， @State 实现惰性初始化，全新的 ContentBuilder 则终结了"编译器无法在合理时间内类型检查此表达式"的经典编译错误。

[丢掉包袱，硬刚 Rust：WWDC26 前瞻与 Swift 6.4 的底层革命](https://kinds.blog.csdn.net/article/details/161724273/ "丢掉包袱，硬刚 Rust：WWDC26 前瞻与 Swift 6.4 的底层革命")

**摘要：** 这篇前瞻文章敏锐捕捉到 Swift 演进的核心转向——从"写App 的高级语言"向着高性能"系统级语言"狂奔。随着 Swift 的战场拓展至大模型 AI 推理、空间计算、嵌入式开发等领域， ARC 带来的 retain/release 和写时复制已成为"性能刺客"。为此，Swift 6.4 酝酿了两大利器：一是已被正式接受的 Ref<T>与MutableRef<T>，通过编译期生命周期和所有权检查实现安全借用，性能直逼 C 语言；二是全新的 Continuation 机制，旨在终结 withCheckedContinuation 模式下"忘记恢复"或"重复恢复"的异步崩溃。


## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 "进群" 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
