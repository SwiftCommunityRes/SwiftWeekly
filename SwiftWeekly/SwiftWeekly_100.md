## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百期周报**。从第一期到第 100 期，离不开每一位编辑的辛勤付出，以及每一位读者的留言、投稿与转发。**感谢一路同行 👏👏👏**——周报会继续把社区生态、Swift 演进与工程实践的最新动态稳定、克制地带给大家。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

一朵花凋零荒芜不了整个春天，一次跌倒也荒废不了整段人生。坚持走下去，凭着耐心和拼搏，生活自会给予你全部答案。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：新版 Siri 大升级，独立应用形态 + 集成 Google Gemini，新增聊天记录自动删除；iPhone Fold / Ultra 试产受阻于铰链；苹果在 Intel 18A 试产 Apple Silicon
> * **提案**：SE-0517、SE-0519、SE-0525、SE-0528、SE-0530 正式通过；SE-0479 被拒
> * **Swift 论坛**：高性能埋点用 Task 标识、`Optional` 对不可复制类型的改进、`nonisolated(nonsending)` 陷阱、SourceKit 暴露并发信息、Swift 6.3.2 发布
> * **推荐博文**：iOS 全栈技术动态、Swift-Testing 的 WASI 适配、用 SyntaxKit 创建宏

上期话题投票结果如下：

![](https://files.mdnice.com/user/38782/915420ad-dfa3-4ab6-abd9-69f88e380680.png)

## 话题讨论

### 本期话题：**如果 Apple 在 2026–2027 推出 AI 智能眼镜，你会买吗？**

**选项：**

1. 会，首发必买
2. 看价格和续航
3. AI 功能真的好用才考虑
4. 我更想要真正的 AR 眼镜
5. 完全没兴趣

欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### 新版 Siri 大升级：独立应用 + 集成 Gemini，支持聊天记录自动删除

*2026 年 5 月 18 日｜来源：TechWeb*

据古尔曼爆料，苹果将在 **WWDC 2026** 推出全面改版的 **Siri**，首次以**独立应用**形态出现，并深度集成 **Google Gemini** 大模型，采用「苹果设计 + 谷歌算力」的混合架构：前端交互由苹果把控，后端复杂多轮对话与任务规划由 Gemini 承担；强调**私有云端计算**与隐私，用户数据不用于谷歌模型训练，新增**聊天记录自动删除**（如 30 天 / 1 年）。新版 Siri 还将带来类 ChatGPT 的对话界面与仿短信样式的对话列表，计划随 **iOS 27 / iPadOS 27 / macOS 27** 正式推送。**以官方发布为准**。

![](https://files.mdnice.com/user/38782/4101c16a-a2a6-4e46-a050-04e039d4792b.png)

### iPhone Fold / Ultra 折叠屏试产受阻：铰链可靠性成卡点

*2026 年 5 月 18 日｜来源：IT之家*

近日爆料显示，**iPhone Fold / Ultra** 在试产阶段卡在**铰链**——长期高频开合的可靠性尚未达到苹果品控标准；屏幕**折痕**侧已可做到长期稳定接近无折痕。报道还提到 iPhone 数字 Pro 系列后续可能从 17 Pro 起步的铝合金材质过渡：**液态金属**若在折叠屏先打通量产，或反哺 Pro 系列；**钛合金**侧苹果在持续探索改良配方，目标兼顾轻量与导热表现。具体节奏与材料路线仍以苹果官方信息为准。

![](https://files.mdnice.com/user/38782/bf9f7e23-9926-41d4-9cb2-48940083eb53.png)

### 丰富供应链：苹果在 Intel 18A 试产 Apple Silicon

*2026 年 5 月 16 日｜来源：PChome 科技*

郭明錤报告确认，苹果已在 **Intel** 美国本土工厂以 **18A-P** 制程试产 **Apple Silicon**，工艺水平与台积电 A18 Pro 制程相当；当前为面向入门级产品的小批量试产，约 **80%** 计划用于 iPhone 系列。时间线：**2026 年**维持小规模测试，**2027–2028** 逐步扩产，**2029** 视市况调整；苹果也在同步评估 Intel 后续更先进制程节点。预计未来数年 **TSMC 仍占苹果硅片约 90%**，本举更多用于分散供应链与地缘风险。

![](https://files.mdnice.com/user/38782/6d6cc052-b5d2-4bd7-879d-fcfe5e87a5bb.png)

## 提案

### 通过的提案

[SE-0517](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0517-uniquebox.md "SE-0517")
**UniqueBox** 提案已通过审查。

该提案此前已在 **第九十六期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0519](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0519-borrow-inout-types.md "SE-0519")
**Borrow 和 Inout 类型，用于安全的一级引用** 提案已通过审查。

该提案此前已在 **第九十六期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0525](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0525-rawspan-safe-loading-api.md "SE-0525")
**RawSpan 安全加载 API** 提案已通过审查。

该提案此前已在 **第九十八期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0528](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0528-noncopyable-continuation.md "SE-0528")
**Continuation：安全且高性能的异步延续** 提案已通过审查。

该提案此前已在 **第九十九期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0530](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0530-async-result-support.md "SE-0530")
**Result 的异步支持** 提案已通过审查。

`Result` 是处理可抛出代码的常用工具，但缺少能直接配合 `async` 代码的初始化器；该提案补全了这一缺口，使 `Result` 与 `async/await` 的衔接更加顺畅。

### 拒绝的提案

[SE-0479](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0479-method-and-initializer-keypaths.md "SE-0479")
**方法和初始化器关键路径** 提案被拒绝。该提案此前已在 **第七十六期周报** 的「正在审查的提案」模块中做过详细介绍。

## Swift 论坛

### 1、Pitch：为高性能埋点提供低开销的 Task 标识符

作者：Joakim Hassila ｜ 发布日期：2026 年 5 月 12 日
[阅读原帖](https://forums.swift.org/t/pitch-cheap-task-identity-for-high-performance-instrumentation/86666 "Pitch: Cheap Task identity for high-performance instrumentation")

提议为 Swift 并发运行时暴露一个轻量级的**公开 Task 标识符 API**，类似线程中的 `pthread_self()`，专为高性能埋点（交易系统、游戏、音频管线等）设计。

**动机：**
作者团队的零分配、无锁埋点库追求**纳秒级**开销（如完整 span 捕获约 25 ns）。当前为关联并发任务的 span 与日志，只能通过 `@_silgen_name` 调用即将报错的私有运行时符号；公开的 `withUnsafeCurrentTask { }` + 解出标识需要数十纳秒，开销过大。

**核心设计：**

```swift
extension Task {
    /// 当前 Task 的轻量标识符，非 Task 上下文返回 nil；O(1) 且无分配
    public static var currentIdentifier: Task.Identifier? { get }
}
```

**讨论亮点：**
Franz Busch、Konrad Malawski 建议直接暴露运行时既有的 **`task_id`**（进程内单调递增的 `UInt64`）；John McCall 认为可以将其纳入 ABI，ktoso 也表达了愿意参与实现。

**简要点评：**
对始终开启、零开销可观测性的实时系统场景而言，是一个填补关键空白的实用提案。

### 2、Pitch：Optional 对不可复制类型的改进与泛化

作者：Alejandro Alonso ｜ 发布日期：2026 年 5 月 11 日
[阅读原帖](https://forums.swift.org/t/pitch-optional-noncopyable-improvements-and-generalizations/86656 "Pitch: Optional noncopyable improvements and generalizations")

针对 **`~Copyable`** 类型与 **`Optional`** 的交互痛点，提议新增方法并泛化既有 API。

**动机：**
自 Swift 6.0 起 `Optional` 部分支持不可复制值，但常见的 `if let` 会消耗所有权，难以在不消耗的前提下检查与改写。

**核心设计：**

* `borrow()` → `Ref<Wrapped>?`：以借用方式读取内部值
* `mutate()` → `MutableRef<Wrapped>?`：以 `inout` 就地修改
* `insert(_:)`：写入新值并返回可变引用，避免使用 `!` 强解包
* `map` / `flatMap` 改为 `consuming`，`unsafelyUnwrapped` 等泛化以支持 `~Copyable & ~Escapable`

**讨论亮点：**
集中在 `insert` 命名（`put`、`place`、`replace` 等）与 `borrow()` / `mutate()` 是否应作为属性；Joe Groff 指出与未来 `if borrow x = opt` 绑定语法方向兼容。

**简要点评：**
所有权系统的关键补全，让 `~Copyable` 类型在日常编码中真正可用。

### 3、`nonisolated(nonsending)` 作为函数参数是否基本无用？

作者：BJ Homer ｜ 发布日期：2026 年 5 月 11 日
[阅读原帖](https://forums.swift.org/t/is-nonisolated-nonsending-on-a-function-parameter-mostly-useless/86649 "Is nonisolated(nonsending) on a function parameter mostly useless?")

作者尝试为自定义 actor 构建类似 `MainActor.run` 的 API 时发现：`@MainActor` 隔离的闭包会**隐式转换**为 `nonisolated(nonsending)`，导致实际仍在 `@MainActor` 执行，而非目标 actor。

**核心设计：**
Jamie（jamieQ）提出，将参数同时标记为 `sending nonisolated(nonsending)` 可阻断隐式静态隔离推断，使闭包在调用点被推断为 `nonisolated(nonsending)`：

```swift
func run(_ work: sending nonisolated(nonsending) async () -> Void) async { ... }
```

**讨论亮点：**
讨论中还揭示了一个相关 bug：`nonisolated(nonsending)` 参数同时标记 `sending` 或 `@Sendable` 时，在旧版本中无法正确跳转到调用方执行器，已在 main 修复并预计随 **Swift 6.4** 发布。作者的实际场景是为 Core Data 的 `NSManagedObjectContext` 构建支持 `async` 闭包的 `performAsyncBlock` API。

**简要点评：**
并发模型中一处微妙陷阱；`sending nonisolated(nonsending)` 的组合写法虽反直觉，但目前是有效防护手段。

### 4、通过 SourceKit 暴露并发信息

作者：Jamie（jamieQ）｜ 发布日期：2026 年 5 月 12 日
[阅读原帖](https://forums.swift.org/t/exposing-concurrency-info-via-sourcekit/86678 "Exposing concurrency info via sourcekit")

作者在原型中借助 **SourceKit-LSP** 将并发信息以可视化方式呈现给开发者：

* **隔离跨越（Isolation Crossings）**：在调用方与被调用方隔离域不同的调用点处给出图标提示
* **闭包推断隔离（Inferred Closure Isolation）**：以灰色 inlay 提示展示编译器推断结果

**讨论亮点：**
Alex Hoppen 建议两类功能拆开实现；隔离跨越可考虑 **Code Lenses** 行级标注；最终通过 `SourceKitLSPOptions`（`.sourcekit-lsp/config.json`）提供开关。Franz Busch 还建议进一步暴露编译器的**隔离区域（isolation regions）**信息。

**简要点评：**
工具层的可观测性改进，有望显著降低理解 Swift 并发代码的认知负担。

### 5、Swift 6.3.2 正式发布

作者：Mishal Shah ｜ 发布日期：2026 年 5 月 13 日
[阅读原帖](https://forums.swift.org/t/announcing-swift-6-3-2/86698 "Announcing Swift 6.3.2")

**Swift 6.3.2** 已发布，可通过 `swiftly install 6.3.2` 安装；**Xcode 26.5** 也内置该版本。主要修复：

* **编译器**：Linux 上使用 C++ 互操作时允许导入使用 C++23 头文件（如 `<expected>`）的 C++ 库
* **SwiftPM**：修复 `Bundle.module` 在 `MainActor` 之外的访问问题；多项 Package Registry 相关修复
* **Swift Testing**：修复退出测试（exit tests）在无 stdout/stderr 时返回无效结果；为 `@Test` 等宏含泛型参数时新增警告
* **libdispatch**：将 dispatch 工作线程名统一为 `"DispatchWorker"`
* **SourceKit-LSP**：修复在 Windows 上使用 `compile_commands.json` 可能崩溃的问题；新增 `forceResolvedVersions` 配置（等价于 SwiftPM 的 `--force-resolved-versions`）
* **Swift Build**：同步修复 `Bundle.module` 在 `MainActor` 之外的访问问题
* **生态**：Amazon Linux 2023 的 Docker 镜像（`6.3.2-amazonlinux2023`）已同步发布

**简要点评：**
稳定性补丁版本，C++23 互操作与 `Bundle.module` 并发访问修复尤为值得关注。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[iOS 全栈开发最新技术动态与工程实践指南](https://blog.csdn.net/a1062051470/article/details/161105594/ "iOS 全栈开发最新技术动态与工程实践指南")

**摘要：** 系统梳理 2026 年 iOS 生态：Xcode 26.5 内置 AI 编程助手、Swift 6.3.2 的并发与泛型改进、模块编译优化；SwiftUI 6 生产级普及（类型安全路由、液态玻璃、3D 数据图表等），整体上「SwiftUI 为主、UIKit 兜底」成为商业项目最佳实践，覆盖性能优化、端侧 AI、隐私合规等环节的能力升级路线。

[Swift-Testing 项目对 WASI 平台支持的探索与实践](https://blog.gitcode.com/6fefb3ba362b886d34c121a79655fc38.html/ "Swift-Testing 项目对 WASI 平台支持的探索与实践")

**摘要：** 复盘 Swift-Testing 向 WASI 适配过程：编译器插件依赖的 POSIX 接口（`dup` 等）在 WASI 不可用、stdio 重定向差异、SwiftPM 传递目标三元组等问题，需要 WASI SDK / SwiftPM / 编译器协同改进；目前已经能以实验方式初步在 WASI 平台运行，可作为 Swift 跨平台到 WebAssembly 的实践样本。

[使用 SyntaxKit 创建宏](https://swiftpackageindex.com/brightdigit/syntaxkit/0.0.3/documentation/syntaxkit/creating-macros-with-syntaxkit/ "使用 SyntaxKit 创建宏")

**摘要：** 以 `#stringify` 宏为例，演示用 **SyntaxKit** 的声明式语法从零到一构建一个 Swift 宏：包结构、`Package.swift` 依赖、宏实现与插件、对外 API、客户端测试样例、完整测试与运行，是希望用宏精简重复逻辑、提升编译期安全的开发者的实操指南。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 "进群" 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
