## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百一十二期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

这世界很酷，但岁月有度，愿健康永不止步，铸人生财富之路。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：特努斯督战 AI，代理式 Siri 最快 2027 年落地
> * **提案**：基于跨度访问 Optional 存储，另有 2 个提案被拒绝
> * **Swift 论坛**：探索使用 Swift 编写 GPU 程序
> * **推荐博文**：Swift社区动态：2026年11月版、Practical Auto-Vectorization 实战、SwiftUI 中的 GlassEffectContainer

## 话题讨论

AI 正以前所未有的速度改变就业格局：有人靠它效率翻倍，也有人担心岗位被替代。**对你而言，AI 是利大于弊，还是弊大于利？**

1. 利大于弊：很多工作在 AI 协助下效率已经翻了好几倍
2. 弊大于利：AI 压缩了普通人的就业空间，基础劳动换报酬的时代正在消失
3. 利弊取决于人：能否快速掌握 AI 技能，决定你是被淘汰还是被放大
4. 不必焦虑：历史上每次技术革命，最终都创造了更多新岗位

欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

**上期投票结果：**

![](https://files.mdnice.com/user/38782/7884c9e8-484f-4154-9caf-a59710cee467.jpg)

近七成读者对触屏 MacBook Pro 持保留态度——48% 认为「不值得为触屏多花钱」，22% 更爱键盘和触控板，仅 5% 认为早就该推出。

## 新闻和社区

### 特努斯督战：代理式 Siri 最快 2027 年落地

*2026 年 11 月 9 日｜来源：太平洋科技*

据彭博社记者古尔曼在《Power On》时事通讯中爆料，苹果正推进 Siri 的全面形态升级：最早于 2027 年推出自主代理式 Siri，从“被动响应指令”转向主动管理任务、代用户完成事务。目前 OpenAI ChatGPT Dots、Meta Muse、Grok 均已向“目标驱动型代理”演进，可跟踪用户目标、自主判断下一步操作；苹果的长期规划正是让 Siri 向同一方向进化，按当前进度最快明年落地。

![](https://pics2.baidu.com/feed/7a899e510fb30f243ad07cfbfeef4551ac4b0308.jpeg@f_auto?token=ccc23a0ea6358fb93137bef3a274b96a)

**内部提速：特努斯亲自督战**

新任 CEO 特努斯上任两个多月后把火烧向 AI，已明确敦促软件工程主管克雷格·费德里吉加快节奏——“迅速超越仅对 Siri 进行必要改进的阶段”，要求 Siri 做出体验层面的本质升级。Siri 团队此前已历一次核心调整：原 AI 负责人詹南德雷亚因未能兑现升级承诺被边缘化，开发工作交由费德里吉接管，随后推出新版 Siri 与 Apple 智能体系，完成向生成式 AI 助手的第一步跨越；代理式升级将是该团队接下来的核心攻坚方向。

**从工具到代理：差距在哪**

![](https://pics4.baidu.com/feed/d52a2834349b033b339ceab423b4a2c1d439bdd0.jpeg@f_auto?token=4d292e6773b1d189cfd8f9fcb7050577)

当前 iOS 27 的 Apple 智能仍以工具属性为主，集中在文本润色、照片编辑、实时翻译等单一场景，主打端侧处理保障隐私；而代理式 Siri 将依托系统级权限打通多应用数据，自主完成日程安排、邮件处理、服务预约、行程规划等多步骤复杂任务，真正从“回答问题的助手”变成“执行事务的代理”。

**追兵四起，苹果的底牌**

AI 代理已是 2026 年全球科技行业的核心竞速赛道，谷歌、三星等终端厂商也在布局自有代理产品。苹果的迟到源于技术（大模型起步晚、AFM 3 云端能力借力 Gemini 被视为过渡方案）、组织（核心人才流失、软硬件路线之争）与战略（“不为 AI 而 AI”的克制）三重因素，如今补课明显提速：与谷歌多年合作升级 Siri、10 月底牵手阿里让国行接入千问大模型、11 月 3 日向开发者开放 Siri 调用第三方 App 执行任务，甚至公开了代号 HALO 的人形机器人研究（宇树 G1 加运行千问模型的 Mac mini，360 次测试平均成功率 91%）。

苹果的底牌是 20 多亿台活跃设备、软硬一体的系统级权限、自研芯片端侧算力与长期积累的隐私体系。资本市场态度已反转：11 月 7 日苹果市值报 5.03 万亿美元，从英伟达手中夺回全球第一。但这是一场巨大的赌注——若代理式 Siri 顺利落地，苹果很可能重塑移动端智能助手的体验标准；若迟迟拿不出可交付的“王牌”，则将失去下一个十年的主动权。

### 苹果 AI 前景几何：追赶者的窗口与代价

*2026 年 11 月 10 日｜来源：中国经营报*

**入口战争的四条路径**

当前各大巨头正沿不同路径争夺下一代人机交互：OpenAI 的 ChatGPT Dots 与 Anthropic 的 Claude 已具备“计算机操作”能力，能识别屏幕、移动光标、跨应用执行；Meta 手握 35.6 亿日活用户的社交消息流，用 Business Agent 在聊天界面内完成从种草到下单的闭环；微软让 Copilot 深度嵌入邮件、日历与工作流；谷歌则把 Gemini 贯穿搜索、Android 与 Workspace，主打“全场景智能体”。华为、小米、荣耀、vivo 等国产厂商也已围绕端侧大模型、系统级智能体展开多轮迭代。

**分析师与业内人士的判断**

业内人士认为，苹果大模型底座积累起步偏晚，通用能力、多轮复杂推理和头部 AI 厂商存在代差，跨应用智能代理的权限框架搭建进度滞后；AI 迭代节奏受硬件发布周期约束，很难像纯 AI 公司那样快速灰度试错。此外，供应链议价权的松动也在侵蚀传统护城河——AI 服务器抢走存储产能推高成本，涨价转嫁消费者又将面对销量压力；OpenAI 等纯模型厂商还在加紧自研硬件，苹果“设备+OS+芯片”的既有优势可能被重新审视。

天使投资人郭涛指出，特努斯亲自督战会压缩内部审慎评审周期，把资源向代理 Siri 项目倾斜，推动从零散功能修补转向面向 2027 智能体目标的系统性开发，但隐私合规底线不会松动，提速空间依旧存在边界。前景取决于苹果能否把“硬件特权+隐私结界”真正转化为代理时代的执行力——当其他巨头在 AI 算力上豪赌、回报尚不明朗时，风险更小的苹果反而显得安全，但留给它“慢慢来”的时间已经不多了。

## 提案

### 正在审查的提案

[SE-0561](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0561-optional-span-access.md "SE-0561")
**基于跨度访问 Optional 存储** 提案正在审查。

将 `span` 和 `mutableSpan` 计算属性添加到 `Optional`。它们以单元素 `Span` 或 `MutableSpan` 的形式提供对包裹值的就地访问，或者在没有包裹值时作为空跨度的访问。还添加了 `edit` 函数，该函数通过闭包的 `OutputSpan` 参数提供对存储的访问，允许添加、替换或删除包装值。

[SE-0562](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0562-subscript-ownership-parameters.md "SE-0562")
**下标参数的所有权** 提案正在审查。

本提案引入了对下标参数的 `inout`、`borrowing` 和 `consuming` 的支持。它使下标参数的功能与函数和初始化器保持一致。

[SE-0563](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0563-improve-interaction-between-at-main-and-top-level-code.md "SE-0563")
**改善 @main 和顶级代码之间的交互** 提案正在审查。

确定源文件是否被解析为顶级代码的当前规则很难理解，并且在采用 `@main` 时经常会导致报告令人困惑的错误。该提案描述了一个源兼容的更改，该更改禁用了用户很可能不打算使用此模式的源中的顶级代码解析。

[SE-0564](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0564-split-continuations.md "SE-0564")
**拆分 Continuation** 提案正在审查。

引入一种新的 `withContinuation` 形式，其主体是 `async`，并接收延续的两半：用于恢复的现有 `Continuation` 和用于等待的新 `ContinuationWaiter`。等待方可以安装取消和优先级升级处理程序，这些处理程序仅在任务暂停时处于活动状态。

此外，该提案在 `Continuation`、`UnsafeContinuation` 和 `CheckedContinuation` 中添加了新的 `resumeSynchronously` 方法，允许执行者向恢复的任务提供其当前执行上下文。如果任务在同一个执行器上恢复，它将内联运行，而不是排队。

最后，本提案更新了 `withTaskPriorityEscalationHandler`（在 SE-0462 中引入）的行为，为优先级升级提供一致的处理程序触发行为。优先级升级处理程序现在将在安装时始终调用一次任务的当前优先级。这关闭了在安装处理程序之前发生的升级从未报告的竞态。

[SE-0565](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0565-swiftpm-allow-deprecating-package-products.md "SE-0565")
**允许弃用软件包产品** 提案正在审查。

软件包作者目前没有一流的方式来表示某个软件包产品正处于被移除的路上。SwiftPM 通过 `@available(*, deprecated, ...)` 支持 Swift 源码 API 的丰富弃用语义，但 `Package.swift` 清单无法为 `.library`、`.executable` 或 `.plugin` 产品表达相同的意图。

本提案引入直接在清单中将产品标记为弃用的方法：作者用单个工厂方法 `.unsupported(message:replacement:)` 描述弃用，其中可选的 `replacement:` 定位器指向消费者应采用的另一个产品（同一软件包或不同软件包均可）。当消费者依赖了不受支持的产品时，SwiftPM 会在构建时发出警告，显示弃用消息及作者声明的替代品信息；配套的 `swift package report` 命令可按需在软件包图中列出每个不受支持的产品，并以退出状态支持 CI 判定失败。

[SE-0566](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0566-infer-result-builder-generics.md "SE-0566")
**推断结果生成器属性的通用参数** 提案正在审查。

启用通用结果生成器用作属性时无需显式指定通用参数，而是允许推断它们。

### 拒绝的提案

[SE-0554](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0554-deployment-target-conditional-compilation.md "SE-0554")
**部署目标条件编译** 提案被拒绝。

该提案此前已在 **第一百一十期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0542](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0542-package-manager-conditional-plugin.md "SE-0542")
**包管理器的条件化插件** 提案被拒绝。

该提案此前已在 **第一百零八期周报** 的「正在审查的提案」模块中做过详细介绍。

## Swift论坛

### 1、在包清单中按目标环境设置构建条件

作者：Franz Busch ｜ 发布日期：2026-11-13
[阅读原帖](https://forums.swift.org/t/target-environment-conditions-in-package-manifests/90725 "Target environment conditions in package manifests")

该提议为 **SwiftPM** 的构建设置与目标依赖条件 `.when(...)` 新增 **targetEnvironments** 参数，用于区分模拟器、Mac Catalyst、musl 等环境，解决仅按操作系统筛选时无法选择不同库或实现的问题。例如，仅在使用 musl 的 Linux 上引入兼容目标：

```swift
.target(
    name: "CFTS",
    condition: .when(platforms: [.linux], targetEnvironments: [.musl])
)
```

平台与环境条件必须同时满足；环境名称精确匹配，无环境的目标三元组不匹配。提议还计划扩展源码中的 `#if targetEnvironment(...)`，使其与清单规则一致。讨论重点是自定义 **Swift SDK** 的适配，以及条件如何融入包解析与 SwiftBuild 的构建模型。点评：这能减少手动传递 traits 的负担，但仍需明确条件在构建流程中的求值方式。

### 2、让 Never 遵循字符串描述协议

作者：Dmitriy Ignatyev ｜ 发布日期：2026-11-10
[阅读原帖](https://forums.swift.org/t/conform-never-to-customstringconvertible/90617 "Conform Never to CustomStringConvertible")

作者建议为 **Never** 添加 **CustomStringConvertible** 和 **CustomDebugStringConvertible** 遵循，使以 `Never` 表示不可能分支的泛型枚举也能满足字符串描述的条件遵循。由于该类型没有实例，属性可通过空 `switch` 实现：

```swift
extension Never: CustomStringConvertible {
    public var description: String {
        switch self {}
    }
}
```

讨论的主要分歧在于动机：作者希望用协议约束限制日志 API 的输入，Xiaodi Wu 则指出，该协议只是字符串表示的定制点，不保证输出质量或稳定性；一般格式化可直接使用 `String(describing:)`，特定业务保证应由自定义协议表达。点评：补齐遵循有利于泛型组合，但不宜把描述协议当作日志内容质量的保证。

### 3、第二轮提议：区分恰好一次与至多一次的函数类型

作者：Allan Shortlidge ｜ 发布日期：2026-11-05
[阅读原帖](https://forums.swift.org/t/pitch-2-called-once-function-types/90515 "[Pitch #2] Called-once function types")

第二轮提议引入 **@once** 表示恰好调用一次，并将至多调用一次的标注更名为 **@callable(once)**。这些信息让编译器能够允许闭包消耗不可复制值，或重新发送非 **Sendable** 值，避免因潜在的重复执行而拒绝安全代码：

```swift
func callOnce(_ body: @once () -> Void) {
    body()
    body() // 错误：闭包已被消耗
}
```

本轮还引入编译器内部的 **Deinitable** 协议，并补充互操作与标准库采用规则。讨论聚焦属性命名、逃逸闭包和 `withoutActuallyDeiniting` 的保证边界：逃逸的 `@once` 并不保证在某个时间点前执行；非逃逸形式可在作用域正常结束时提供更强检查。点评：将调用次数纳入类型系统能改善所有权与并发体验，但应准确理解其对程序进展的保证范围。

### 4、探索使用 Swift 编写 GPU 程序

作者：Drecothedev ｜ 发布日期：2026-10-26
[阅读原帖](https://forums.swift.org/t/swift-on-the-gpu/90299 "Swift on the GPU")

作者正在尝试将 **Swift** 转译为 **Metal** 的小型编译器，希望探索类似 Mojo 的 GPU 编程体验，并询问其他实现路径。这是一场早期探索，尚未形成正式语言设计。

讨论中，Jonathan Wight 分享了使用 Swift 语法编写着色器的 **schmetal** 实验；另有参与者建议研究 LLVM 层的 GPU 支持，并与 **Embedded Swift** 社区交流。实际开发痛点则涉及渲染管线、CPU/GPU 数据传输和着色器绑定，单纯更换着色器语言难以全部解决。后续还涉及 **MetalSprockets** 的组合式封装，以及通过 **MetalCompilerPlugin** 缓解 SwiftPM 对 Metal 目标支持不足的问题。

点评：Swift GPU 编程的价值既取决于编译能力，也取决于资源管理、类型安全与包工具链能否形成完整体验；帖中的 API 构想仍属探索，不能视为已支持的 Swift 功能。

### 5、为固定布局值类型提供回部署能力

作者：Douglas Gregor ｜ 发布日期：2026-11-04
[阅读原帖](https://forums.swift.org/t/pitch-back-deployment-for-fixed-layout-value-types-3571/90446 "Pitch: Back-deployment for fixed-layout value types - #3571")

Douglas Gregor 与 Allan Shortlidge 提议将 **@backDeployed(before:)** 扩展至固定布局的 **@frozen struct** 和 **enum**，让部分新类型可用于较旧的系统运行时，降低新标准库 API 的采用门槛。候选包括 **Span** 系列、**Int128/UInt128**、**UniqueArray** 和 **Mutex** 等；不同类型仍可能有各自的运行时下限。

实现复用现有的外来类型及协议见证表唯一化机制。讨论涉及动态布局能否支持、多个依赖中的元数据副本合并，以及元数据访问成本。值得关注的是，作者在 11 月 14 日更新中明确撤回了最初对弹性协议追溯遵循的限制，表示已找到解除方案，最新草案已移除该限制。

点评：这有望缩短新类型发布与应用实际采用之间的等待，但回部署范围仍受类型布局及所需运行时能力约束，不代表所有新 API 都能自动用于旧系统。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[Swift社区动态：2026年11月版](https://www.swift.org/blog/whats-new-in-swift-november-2026/ "Swift社区动态：2026年11月版")

**摘要：** 这篇官方月度动态由 Swift Package Index 联合创始人 Dave Verwer 与 Apple 高级产品经理 Dave Lester 共同主笔，开篇即是给 CocoaPods 用户的提醒：历经两年过渡期后，CocoaPods 将于 2026 年 12 月 2 日停止接受新的 pod 与版本，现有仓库转为只读，尚未迁移到 SwiftPM 的项目应当抓紧行动。社区亮点部分提到 John Sundell 分享的 Optional `take()` 等实用技巧、Sindre Sorhus 用 Swift 重写个人网站让链接错误变成编译错误，以及 EPAM 团队用 Hummingbird 与 Vapor 构建后端的经验对比。包发布方面，Swift Kafka Client 达到 1.0.0，swift-ros2 新增机器人网络的话题图 API。提案板块涵盖正在审查的 SE-0559 与 SE-0560，以及近期通过的 SE-0552、SE-0545、SE-0553、SE-0551。

[Practical Auto-Vectorization：让单线程循环快上好几倍](https://blog.mahdibm.com/posts/practical-auto-vectorization/ "Practical Auto-Vectorization：让单线程循环快上好几倍")

**摘要：** 这篇技术文章以优化 Base64 编码为例，讲解如何通过调整源码形态来适配 LLVM 的成本模型、让编译器自动把单线程循环转换成 SIMD 向量代码。作者在 Apple M6 上实测，朴素实现仅 0.34 GB/s，加上查找表后达到 4.6 GB/s，而去掉阻碍向量化的查找表与分支后，自动向量化版本跃升至 16.0 GB/s；最终手工 SIMD 配合 64 字节查找表更是达到 29.2 GB/s，较最初实现提升约 90 倍，甚至略快于 Daniel Lemire 的 C++ 实现。文中给出的技巧包括：使用 Span 等连续内存接口、通过预计算候选结果做 If-Conversion 以生成条件移动指令、用 `&+` `&-` 避免溢出检查路径、用 `unsafe bytes[unchecked:]` 消除下标边界检查，以及借助 `-emit-ir` 搜索 `vector.body` 来确认循环确实已被向量化。

[SwiftUI 中的 GlassEffectContainer 是什么](https://sarunw.com/posts/swiftui-glasseffectcontainer/ "SwiftUI 中的 GlassEffectContainer 是什么")

**摘要：** 这篇来自 Sarunw 的技术博客解读了 iOS 26 引入的 GlassEffectContainer：默认情况下每个玻璃视图各自独立绘制，互不知晓彼此，而容器的作用正是把 Liquid Glass 形状归拢到一处，让它们彼此产生反应。文章详细讲解了如何用容器的 spacing 参数控制形状靠近后融合的程度、用 glassEffectUnion(id:namespace:) 让相距较远的形状合并为同一块玻璃，以及用 glassEffectID 配合 @Namespace 与 withAnimation 实现形态间的生长与收缩过渡。作者还实测指出玻璃效果过渡的三种形态——.matchedGeometry、.materialize 与 .identity——各自的适用场景，并提醒标准控件如工具栏和标签栏已自带该行为，无需重复包裹。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
