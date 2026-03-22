## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第九十七期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

世上最耀眼的光芒，就是你我努力拼搏的模样，不曾辜负每个朝阳，不曾荒废每个深夜，因为平凡而奋斗，也会因为奋斗而不平凡！👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：库克成都出席苹果 50 周年庆典；否认退休传闻；苹果开发者入驻 B 站与领英迎接 WWDC
> * **提案**：SE-0501、SE-0507、SE-0512、SE-0514、SE-0515、SE-0518 正式通过；SE-0520～SE-0522 正在审查；SE-0513 被拒
> * **Swift 论坛**：UUID v7、SE-0522 源码级警告控制、RigidArray/UniqueArray、SE-0469 Task.name 修订、Pico 裸机 Swift
> * **推荐博文**：Android 瘦 LTO 与 Swift 启动优化、认证系统替换复盘、浏览器中的 Swift 应用

上期话题投票结果如下：

## 话题讨论

### 本期话题：**AI 工具在你日常 Swift / iOS 研发中的主要用途是？**

**选项：**

1. 以检索与方案调研为主（文档、报错、最佳实践），少直接生成大块代码，对齐「AI 替代常规搜索」
2. 以模块/样板代码与单测思路为主，架构与安全自分把关，对齐「分层使用、人机分工」
3. 深度使用 IDE 内 AI 贯穿编码，但有团队规范与 Review，对齐「Cursor/Kiro + 制度」
4. 会玩本地/私有模型，主要为了脱敏、内网或成本，较少用公网 API，对齐「本地 vs 云端选型」
5. 基本不用 AI 写代码，或公司/项目禁止，仅接受传统方式

欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### 库克现身成都出席苹果公司成立 50 周年庆典

*2026 年 3 月 18 日｜来源：中国新闻网*

3 月 18 日，蒂姆·库克现身成都太古里 Apple 零售店，参加苹果成立 50 周年系列庆祝活动的全球第二站、亚太首站，系库克时隔三年再度来蓉。活动邀请李宇春献唱，库克称赞成都活力与文化底蕴。报道指出，成都是苹果供应链（富士康承担 iPad、MacBook 等总装）与西部消费市场的重要节点；2026 财年一季度大中华区销售额同比增长 38% 至 255 亿美元，创历史新高，苹果高管近年亦频繁来华考察，释放持续深耕中国市场的信号。

![](https://files.mdnice.com/user/47553/3ea0767f-151f-4f79-997e-564026263ccc.png)

### 苹果 CEO 库克回应退休传闻：只是谣言，无法想象没有苹果的人生

*2026 年 3 月 18 日｜来源：PChome科技*

库克在接受专访时否认退休传闻，称相关说法均为谣言，暂无离开苹果的计划，并表示「无法想象没有苹果的人生」。《金融时报》等曾报道董事会加速遴选继任者，古尔曼则反驳该消息过早不实；库克在 2026 年 2 月股东大会上未提退休，与高管谈及长期继任规划，暗示交接不会仓促。

![](https://files.mdnice.com/user/47553/1cb1f168-a59d-4bcf-b5e7-a2310cb4ecad.png)

### 迎接 2026 年全球开发者大会 WWDC，苹果开发者账号入驻 B 站和领英

*2026 年 3 月 18 日｜来源：IT之家*

苹果为迎接 2026 年 WWDC，官方「Apple 开发者」账号已入驻 B 站与领英（LinkedIn），发布「Hello World」等视频，持续推送大会资讯、技术解析与「与苹果会面」等活动信息；账号已上线多段 2025 年 WWDC 相关内容（含 Metal 4、机器学习与 AI 框架等）。此外，苹果本月在 Instagram 推出「Hello Apple」账号，侧重品牌与产品故事传播。

## 提案

### 通过的提案

[SE-0501](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0501-swiftpm-html-coverage-report.md "SE-0501")
**HTML 覆盖报告** 提案已通过审查。

[SE-0507](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0507-borrow-accessors.md "SE-0507")
**借用和突变访问器** 提案已通过审查。

该提案此前已在 **第九十五期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0512](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0512-withlockifavailable-cannot-spuriously-fail.md "SE-0512")
**记录 Mutex.withLockIfAvailable 不能虚假失败** 提案已通过审查。

该提案此前已在 **第九十六期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0514](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0514-hashable-conformance-for-dictionarykeys-collectionofone-emptycollection.md "SE-0514")
**Hashable 符合 Dictionary.Keys 和 EmptyCollection** 提案已通过审查。

该提案此前已在 **第九十六期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0515](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0515-noncopyable-reduce.md "SE-0515")
**允许 reduce 产生不可复制的结果** 提案已通过审查。

该提案此前已在 **第九十六期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0518](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0518-tilde-sendable.md "SE-0518")
**~Sendable 用于显式标记非 Sendable 类型** 提案已通过审查。

该提案此前已在 **第九十六期周报** 的「正在审查的提案」模块中做过详细介绍。

### 正在审查的提案

[SE-0520](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0520-discardableresult-task-initializers.md "SE-0520")
**在任务初始化器中使用可丢弃的结果** 提案正在审查。

此前 `@discardableResult` 被普遍应用于所有任务初始化器，容易在无意中忽略抛出型初始化器所抛出的错误。提案建议为会抛错的任务初始化器引入新警告，帮助开发者不「漏掉」错误处理。

[SE-0521](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0521-improved-optional-opaque-and-any.md "SE-0521")
**改进了不透明和存在类型可选的语法** 提案正在审查。

允许直接书写 `some P?` 与 `any P?`，语义与带括号的 `(some P)?`、`(any P)?` 一致。

[SE-0522](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0522-source-warning-control.md "SE-0522")
**源级控制编译器警告** 提案正在审查。

引入新的声明属性，用于在源码层面控制特定代码区域的编译器警告行为：作为警告、升级为错误或抑制发出。

### 拒绝的提案

[SE-0513](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0513-commandline-executablepath.md "SE-0513")
**API 获取当前可执行文件的路径** 提案被拒绝。该提案此前已在 **第九十六期周报** 的「正在审查的提案」模块中做过详细介绍。

## Swift 论坛

### 1、Pitch: UUID v7 及其他改进

作者：Tony Parker ｜ 发布日期：2026 年 3 月 18 日
[阅读原帖](https://forums.swift.org/t/pitch-uuid-v7-other-improvements/85427 "[Pitch] UUID v7, other improvements")

本 pitch 为 Foundation 的 `UUID` 类型带来一系列改进。

**动机：**
v4 随机 UUID 在 B-tree 索引中易导致写放大；开发者需要时间有序、可排序的标识符，以及更高效的字符串与字节访问方式。

**核心设计：**

* 新增 **UUID v7**（时间有序 UUID）：Unix 时间戳编码于高位，生成单调递增、可排序的 UUID，适合数据库主键
* 新增 **`UUID.Version`** 结构体（`RawRepresentable`），支持对任意 UUID 做版本自省，兼顾源码与二进制兼容
* 新增 **`UUID.nil` / `UUID.max`** 哨兵值、**`uuidStringLower`**、`span`（`Span<UInt8>` 零拷贝访问）、基于 `OutputSpan` 的构造等

```swift
let id = UUID.timeOrdered()
switch id.version {
case .timeOrdered: print("v7 UUID，按创建时间可排序")
case .random:      print("v4 UUID")
default:           break
}
let nilID = UUID.nil
let maxID = UUID.max
```

**讨论亮点：**

* 版本命名争议：有成员建议采用 `.v4`、`.v7` 等与规范编号一致的命名
* `UUID.nil` 是否与关键字混淆：有人建议 `.zero` 或 `.min`，Tony Parker 倾向 `.min` 与 `.max` 对称
* `timeOrdered(using:at:)` 支持注入日期，便于测试

**简要点评：**
这是 Foundation `UUID` 的一次实质性升级，v7 对后端与存储场景很重要，`Span` 集成也体现 Swift 对低层零拷贝 API 的持续投入。

### 2、SE-0522：源码级编译器警告控制

作者：Tony Allevato（Review Manager）｜ 发布日期：2026 年 3 月 19 日
[阅读原帖](https://forums.swift.org/t/se-0522-source-level-control-over-compiler-warnings/85453 "SE-0522: Source-Level Control Over Compiler Warnings")

**SE-0522** 进入审查阶段（截至 2026 年 4 月 2 日），引入 **`@warn`** 属性，允许在源码层面对编译器诊断进行细粒度控制（升级为错误、保持警告或忽略）。

**动机：**
目前多依赖命令行在模块级控制警告，难以针对单个声明精细调节，易出现「要么噪音满天飞，要么整类关掉」的两难。

**核心语法示例：**

```swift
@warn(DeprecatedDeclaration, as: error)
func foo() { ... }

@warn(DeprecatedDeclaration, as: ignored)
func bar() { ... }
```

**讨论亮点：**

* 命名争议：有建议改为 `@diagnose` 并调整参数顺序
* 是否扩展至 remarks 与更小词法作用域（如 `do {}`）的讨论
* Xiaodi Wu 等对「一键忽略所有废弃警告」可能带来的滥用表示担忧

**简要点评：**
切中大型代码库维护痛点，设计方向合理，命名与作用域粒度仍是后续打磨重点。

### 3、Pitch: RigidArray 与 UniqueArray

作者：Alejandro Alonso、Karoy Lorentey ｜ 发布日期：2026 年 3 月 19 日
[阅读原帖](https://forums.swift.org/t/pitch-rigidarray-and-uniquearray/85455 "[Pitch] RigidArray and UniqueArray")

建议在标准库引入 **`RigidArray`** 与 **`UniqueArray`**，用于存放 **`~Copyable`** 元素的堆分配数组。

**动机：**
`Array` 的写时复制（CoW）在缓冲区复制时无法「克隆」不可复制元素，易导致资源重复释放等问题。

**核心设计：**

* **`UniqueArray<Element: ~Copyable>`**：动态扩容、唯一持有存储，`var b = a` 为移动语义
* **`RigidArray<Element: ~Copyable>`**：固定容量，越界 `fatalError`，适合实时/嵌入式等对分配敏感场景

```swift
var a = UniqueArray<File>()
a.append(file1)
var b = a

var r = RigidArray<Int>(capacity: 2)
r.append(1)
r.append(2)
r.append(3) // 运行时错误：超出容量
```

**讨论亮点：**

* `UniqueArray` 是否易被误解为「元素唯一」类似 Set，命名是否改为 `NoncopyableArray` 等
* 为何不直接让 `Array` 支持 `~Copyable`：与「消除 CoW、独占缓冲」等需求并不完全等同

**简要点评：**
所有权与系统编程场景的关键拼图，正式提案阶段需认真对待命名与 API 边界。

### 4、修订：SE-0469 Task 命名补充实例属性

作者：Konrad 'ktoso' Malawski ｜ 发布日期：2026 年 3 月 20 日
[阅读原帖](https://forums.swift.org/t/amend-se-0469-task-names-to-include-instance-property/85460 "[Amend] SE-0469 Task names to include instance property")

对 **SE-0469（Task 命名）** 的小幅修订：补充从 `Task` 实例读取名称的 API。

**动机：**
创建 Task 时可设名称，lldb 可展示任务树，但缺少 `task.name` 这类实例属性，属于明显遗漏。

**拟新增 API：**

```swift
extension Task {
    public var name: String?
}
```

**讨论亮点：**

* 社区多认为宜走修订快速通道；属性只读、创建后不可变
* 因缺少运行时入口，**无法向旧版运行时回溯部署**
* 与 Instruments 教学、可观测性场景结合度高

**简要点评：**
小而实用的补全，有利于调试与运维侧读取任务名。

### 5、完全用 Swift 编写的裸机 Raspberry Pi Pico 示例（零 C 代码）

作者：Kishikawa Katsumi ｜ 发布日期：2026 年 3 月 19 日
[阅读原帖](https://forums.swift.org/t/bare-metal-raspberry-pi-pico-examples-written-entirely-in-swift-no-c-code-at-all/85454 "Bare-metal Raspberry Pi Pico examples written entirely in Swift, no C code at all")

作者分享 **pico-bare-swift**：基于 **Embedded Swift** 的 RP2040 裸机示例，除链接脚本外无 C 代码，向量表与启动逻辑亦用 Swift 编写。

**动机：**
展示 Swift 在裸机、无 C 运行时场景下的完整链路，供嵌入式开发者参考。

**关键技术：**

* **`@section`（SE-0492）**：放置向量表等到指定段
* **`@_extern`**：引用链接脚本符号（如 `__data_start`）
* **`@c`（SE-0495）**：导出 C 可调用符号（如 `Reset_Handler`）

**讨论亮点：**
PIC 与 GOT 落在 RAM 导致启动阶段「鸡生蛋」问题，可通过链接脚本将 `.got` 放 ROM 等方式规避；项目含由浅入深多个示例（LED、I2C OLED 等）。

**简要点评：**
Embedded Swift 成熟度的重要展示，`@section` / `@_extern` / `@c` 组合为「尽量不用 C 写固件」提供了可复现路径。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[Android 瘦 LTO 与 Swift 集成层启动优化实战指南](https://developer.unity.cn/projects/6985aea1edbc2a001e30c857/ "Android 瘦 LTO 与 Swift 集成层启动优化实战指南")

**摘要：** 本文探讨跨平台场景下，Android 端瘦 LTO 与 Apple 端 Swift 重写集成层协同优化启动性能：瘦 LTO 精简启动关键路径产物体积，Swift 原生集成层减少跨语言桥接开销，形成从编译到运行时的优化闭环，并给出差异化配置与扩展性思考。

[替换认证系统背后的经验教训](https://www.esri.com/en-us/software-engineering/blog/articles/lessons-from-swapping-out-our-authentication-system/ "替换认证系统背后的经验教训")

**摘要：** Esri 工程团队复盘在 Qt Maps SDK 中替换认证系统、并与 Swift、Kotlin 等 SDK 对齐 API 的过程，涉及命名冲突、防混用、网络栈重构与测试翻倍等挑战；通过新旧系统并行发布完成迁移，对大型 SDK 底层升级与跨平台复用有参考价值。

[跨平台 Swift：构建一个运行在浏览器中的 Swift 应用](https://www.pointfree.co/blog/posts/151-cross-platform-swift-building-a-swift-app-for-the-browser/ "跨平台 Swift：构建一个运行在浏览器中的 Swift 应用")

**摘要：** 以简单计数应用为例，介绍 SwiftWasm 工具链、JavaScriptKit 与 DOM 交互、Observation 做响应式更新；直面工具链与缺少 SwiftUI 等限制，同时展示「一次编写、多端运行」的潜力，适合探索 Swift 全栈或 Web 侧的开发者。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 "进群" 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
