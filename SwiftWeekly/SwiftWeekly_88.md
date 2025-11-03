## 前言

嗨，Swift 社区的小伙伴们～👋

欢迎来到 **第 88 期 Swift 周报**！每次写到这个数字，总有种陪大家一起成长的感觉。过去几周，Swift 社区依然热闹非凡：苹果又一次站上市值高峰、Swift 官方提案频出、论坛讨论异常活跃，还有不少开发者分享了很棒的实践文章。

**送给大家**：“生活从不是一条按部就班的路，而是一次主动出击的冒险。慢一点没关系，只要在前进，就离惊喜更近一步。👊👊👊”

> **周报精选**
>
> * 新闻和社区：苹果市值破 4 万亿、AI 服务器提前交付、iOS 广告业务加速扩张
> * 提案：`@inline(always)` 正式通过审查
> * Swift 论坛：类型检查器性能优化路线图、`defer` 异步支持提案、Swift SDK for Android 公告
> * 推荐博文：SwiftUI 视图通信机制详解

**上期话题投票结果**

![](https://files.mdnice.com/user/47553/e67d985d-aa78-49d5-aa68-0c40bd4bb46a.jpg)

根据投票结果可以看出，**塑造能凝聚人心的精神内核，而非束缚手脚的思想枷锁**。

## 本期话题讨论

在中国科技股中，人工智能（AI）板块正在吸引大量资金和市场关注，但也伴随估值攀升、监管变化、国际竞争等不确定因素。在你看来，中国科技股中人工智能（AI）板块面临的最大风险或挑战是什么？

1. 国际技术出口控制与芯片受限
2. 国内监管政策、反垄断或科技审查压力
3. 估值过高、市场泡沫风险
4. 商业模式尚未完全变现、盈利能力弱

欢迎留言参与投票，我们将在下期公布结果。

## 新闻和社区

### 苹果市值首破 4 万亿美元，美股“4 万亿俱乐部”齐聚三巨头

![](https://files.mdnice.com/user/47553/e9bd2e87-fef4-4571-a16a-1049c991b6ca.png)

2025 年 10 月 29 日，苹果正式成为继英伟达、微软之后，全球第三家突破 **4 万亿美元市值** 的公司。
Counterpoint 数据显示，iPhone 17 在中美市场开售后销量增长超 14%，成为拉动苹果股价的核心动力。

与此同时，微软与 OpenAI 签署了新一轮协议，进一步扩大 Azure 云服务合作；英伟达则在 GTC 大会上发布 NVQLink 技术，向“AI + 量子计算”生态迈进。

AI 三巨头正式组成“4 万亿俱乐部”，全球科技版图再次被重新定义。

### 苹果加速 iOS 广告布局，地图广告最快明年上线

![](https://files.mdnice.com/user/47553/d303718e-c31c-4284-8dd2-2b89b2a0b539.png)

据 Mark Gurman 爆料，苹果计划在 **iOS 26.4 / 26.5** 版本中为地图引入广告系统，采用类似 App Store 的搜索竞价机制。
初期广告将聚焦于餐厅、商户等本地服务，未来可能扩展至图书与博客应用。

这一举措显示，苹果正逐步将“广告”纳入核心营收版图。但部分用户对此并不买账——他们质疑花两千美元买的 iPhone，却越来越像“苹果广告牌”。

### Apple 智能的心脏：美国制造 AI 服务器提前交付

苹果 COO Sabih Khan 确认，**休斯顿工厂生产的 AI 服务器** 已提前发往全美数据中心。
这些设备将成为 “Apple Intelligence” 的计算骨干，用于执行安全云端推理任务。

![](https://files.mdnice.com/user/47553/b76da090-af04-44bc-93f7-03967ffd31c0.png)

这批服务器不仅采用高能效架构，还被纳入苹果的碳中和计划，预计 2030 年全面实现零排放。
苹果的 AI 版图不止在端侧，更在“自建云”中悄然重构。

![](https://files.mdnice.com/user/47553/552f71f8-3d5f-4c28-9464-aaa95167ea07.jpg)

## 提案

### 通过的提案

[SE-0496](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0496-inline-always.md "SE-0496") **`@inline(always)`属性** 提案通过审查。该提案已在 **第八十七期周报** 正在审查的提案模块做了详细介绍。

## Swift论坛

### 1、改进类型检查器的路线图

作者：Slava Pestov ｜ 发布日期：2025 年 10 月 30 日
[阅读原帖](https://forums.swift.org/t/roadmap-for-improving-the-type-checker/82952 "提议改进类型检查器的路线图")

这篇来自编译器团队核心成员 Slava Pestov 的长帖，详细介绍了 Swift 表达式类型检查器（expression type-checker）的现状、已完成的优化，以及未来的性能提升计划。目标直指老生常谈的痛点——**编译太慢**。

**核心要点：**

* 类型检查的底层逻辑：通过为子表达式创建类型变量、构造约束、并在求解阶段（constraint solving）确定类型。
* 性能瓶颈主要来自“类型重载（type-based overloading）”引发的指数级组合。为防止卡死，编译器限制了“分支尝试次数”和“内存分配规模”。
* **Swift 6.2 已完成优化：** 改良回溯机制与内存管理，典型慢表达式从 10 秒降到 6 秒左右。
* **Swift 6.3（进行中）：** 提升 disjunction 选择算法，进一步压缩类型求解耗时。
* **未来规划：**

  * 优化绑定子系统，减少复杂度。
  * 清理硬编码性能 hack。
  * 改进诊断模式（salvage mode），让“类型错误提示”不再拖慢编译。
  * 从语言层面探索减少指数复杂度触发条件。

**小结：**

如果你的项目包含大量泛型、重载或链式调用，这些改进将直接缩短编译时间，让类型系统更智能、更可预期。

### 2、在 `defer` 中支持异步调用（SE-0493）

作者：Frederick Kellison-Linn（Jumhyn） ｜ 2025 年 8 月 23 日
[查看提案](https://forums.swift.org/t/support-async-calls-in-defer-bodies/81790 "在 defer 语句中支持异步调用")

这个提案提出一个看似小、却非常实用的特性：**允许在 async 函数的 `defer` 块中执行 await 调用**。

以前即使函数是 async，`defer` 中也不能写 await，开发者不得不手动在多个退出点重复清理逻辑，非常繁琐。

```swift
func f() async {
  await setUp()
  defer { await performAsyncTeardown() }   // 新支持
  try await doSomething()
}
```

**亮点解析：**

* **兼容性好：** 完全新增语义，不破坏现有 defer 行为。
* **简化异步清理：** 特别适合异步释放资源、日志上传、外部状态回收等场景。
* **社区反馈积极：** 多位开发者认为“终于等到这一刻”，主张保持 defer 的 LIFO 顺序与串行 await 语义。

**小结：**

这项特性能让异步清理逻辑更安全、更自然，也能减少使用 `Task { ... }` 这种不受控的 workaround。未来在 Swift 并发体系中，它会成为“好用不显眼”的日常利器。

### 3、Swift SDK for Android 正式登场

发布方：Swift Android Workgroup ｜ 2025 年 10 月 24 日
[阅读原帖](https://forums.swift.org/t/announcing-the-swift-sdk-for-android/82845 "介绍Swift SDK for Android")

一个令人振奋的消息——**Swift 正式支持 Android！**

**亮点速览：**

* 可在 Windows、Linux、macOS 下载 SDK。
* 提供 “Getting Started” 与官方示例仓库。
* 已有约 25% 的 Swift Package 能构建在 Android。
* 集成 `swift-java` 桥接库，实现 Swift ↔ Java/Kotlin 双向调用。
* 工作组已制定未来路线图与 CI 计划。

**小结：**

Swift 正从“苹果生态语言”走向“跨平台通用语言”。
对于已有 iOS 项目，这意味着业务逻辑层可复用到 Android —— 如果你正在做多端统一逻辑，不妨提前关注这个方向。

### 4、Swift Configuration 初版发布

作者：Honza Dvorsky ｜ 2025 年 9 月 25 日
[阅读原帖](https://forums.swift.org/t/introducing-swift-configuration/82368 "介绍Swift Configuration")

Swift Configuration 的出现，让配置管理终于有了“官方解法”。

```swift
let config = ConfigReader(providers: [
    EnvironmentVariablesProvider(),
    try await JSONProvider(filePath: "/etc/config.json")
])
let httpTimeout = config.int(forKey: "http.timeout", default: 60)
```

**主要特性：**

* 支持组合多种配置源（env / CLI / JSON / YAML / 内存）。
* 提供同步、异步与热重载访问方式。
* 支持命名空间、访问日志与敏感值遮蔽。
* 可自定义 Provider，灵活扩展。

**社区观点：**

* 多数开发者认为这是服务端 Swift 生态的重大补足。
* 与 Argument Parser 可形成互补：前者用于 CLI，后者用于通用配置。
* 已被 Swift 官方月度精选纳入“生态亮点”。

**小结：**

在后台服务、命令行工具或多环境应用中使用 Swift Configuration，可统一配置逻辑、降低出错率，是 2025 年后 Swift 工程化的重要一环。

### 5、Swift Collections 1.3.0 发布

作者：Karoy Lorentey ｜ 2025 年 9 月 29 日
[阅读原帖](https://forums.swift.org/t/swift-collections-1-3-0/82429 "Swift Collections 1.3.0")

Swift Collections 1.3.0 带来了对系统编程友好的“拥有权感知”容器。

**新增模块与类型：**

* **`UniqueArray<Element>`**：非可复制数组，取消写时复制机制。
* **`RigidArray<Element>`**：固定容量数组，初始化后不可扩容。
* **`TrailingArray`**：用于与 C 风格尾部存储结构互操作。
* **实验性 `Box<T>`**：堆分配、非可复制包装类型。

**社区讨论：**

* 命名“UniqueArray”引起歧义，但暂定保留。
* 作者强调目标是验证语义正确性，而非极限性能。
* 一些开发者更青睐 `RigidArray`，因其行为更可预测。

**小结：**

对于系统编程、游戏引擎、图形处理等性能敏感场景，`UniqueArray` 与 `RigidArray` 提供更可控的内存模型。虽然主流 App 仍以 `Array` 为主，但这类类型正在为 Swift 打开“系统级开发”的新篇章。

## 推荐博文

[SwiftUI 中 View 之间的通信 【macOS App】](https://juejin.cn/post/7406641064914944052/ "SwiftUI 中 View 之间的通信 【macOS App】")

**摘要：** 文章系统梳理了 SwiftUI 中父子视图与多层通信的几种方式：
`@Binding`、闭包回调、`ObservableObject` 以及 `Environment`。
作者还拿 Vue 与 React 对比，指出 SwiftUI 在复杂通信场景下仍需借助 Combine 扩展。

[iOS - 渲染原理](https://juejin.cn/post/7078881864030617607 "iOS - 渲染原理")

**摘要：**  文章详细介绍了 iOS 中的渲染原理。首先，讲解了图像渲染流水线的步骤，包括应用处理阶段、几何处理阶段、光栅化阶段和屏幕成像。接着，讨论了渲染流水线可能引发的问题，如屏幕撕裂和掉帧，并提出了解决方法。
  
然后，介绍了 iOS 中的渲染框架，包括 CALayer 和 Core Animation ，以及它们在渲染流程中的作用。最后，详细解释了 Core Animation 渲染的全流程，包括事件处理、布局、绘制、打包和显示等步骤。整篇文章深入浅出地介绍了 iOS 中的渲染原理和相关框架，对理解iOS应用的图像渲染过程具有一定的帮助。

[优先级翻转 (Priority Inversion) ](https://juejin.cn/post/7394788843206721587/ "优先级翻转 (Priority Inversion) ")

**摘要：**  本文深入探讨了多线程编程中的优先级翻转现象，特别是在 Swift 中通过 Quality of Service (QoS) 管理任务优先级的重要性。优先级翻转可能导致高优先级任务被低优先级任务阻塞，从而影响系统性能和稳定性。

文章通过案例分析和解决方法提供了应对优先级翻转的实用建议，强调了合理使用锁和同步机制的重要性，以及如何通过调整任务优先级来优化多线程应用的设计。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
