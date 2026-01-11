## 前言

**本期是 Swift 编辑组自主整理周报的第九十三期。**
经过持续迭代，各个模块的结构与节奏已经逐步稳定。如果你对选题方向、内容深度或呈现方式有任何建议，欢迎在文末留言，我们都会认真阅读与讨论。

Swift 周报已在 GitHub 开源维护：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly "Swift 周报开源 Link")

欢迎提交 Issue、投稿或推荐优质内容。目前计划 **每两周周一发布**，也非常欢迎志同道合的朋友加入编辑组，一起把这份社区周报长期做下去。

> 这世界或许千疮百孔，但总有一隅温柔在等待我们踏足。就仿若这世间没有真正的成长，只有不断破碎又重组的生命力在呐喊。👊👊👊

### 本期精选速览

* **新闻和社区**：苹果税全球博弈升级，谁能真正逼苹果低头？
* **提案**：成员初始化器私有属性规则调整正在审查
* **Swift 论坛**：尾随闭包、参数包、`mapValues` 能力扩展等多项语言讨论
* **推荐博文**：Swift 跨平台、内存模型、类型系统深挖

## 话题讨论

### 当 AI 能写“正确的代码”时，人类工程师的核心价值到底是什么？

随着 AI 写代码能力不断提升，一个无法回避的问题正在摆在所有工程师面前：
**如果“写对代码”不再稀缺，人类工程师还剩下什么？**

我们整理了社区中最具代表性的几种观点：

1. **系统架构与复杂度控制能力**
   能在规模、性能、可演进性之间做长期取舍，而不仅仅是把功能跑通。

2. **将模糊需求转化为“可执行规范”的能力**
   定义问题本身，往往比解决问题更重要。

3. **业务与领域理解 + 技术落地能力**
   知道“该不该做”，而不只是“怎么做”。

4. **工程判断与责任承担**
   出问题时，AI 不背锅，人要。

5. **人与 AI 的协作与编排能力**
   会用 AI 写代码不重要，会“指挥 AI”才重要。

6. **以上都重要：工程师角色正在重构**
   从“写代码的人”，转向“系统设计者 + 决策者”。

欢迎在评论区投票或分享你的答案。

## 新闻和社区

### 罚款或达 380 亿美元，印度监管机构就反垄断新法与苹果交锋

*2026 年 1 月 8 日｜来源：财联社*

印度竞争委员会（CCI）正与苹果就反垄断新法展开正面博弈。新法允许监管机构 **基于企业全球营业额** 而非印度本地收入计算罚款，苹果认为这一规则可能带来 **高达 380 亿美元** 的风险。

争议核心仍然是 App Store 抽成与平台支配地位问题。印度监管机构明确表示，仅以本地营业额计算罚款，对全球性数字平台缺乏足够威慑力。

案件预计于 **1 月 27 日** 在德里高等法院审理，结果或将对全球“苹果税”博弈产生连锁影响。

### 苹果设计师持续流失，iPhone Air 设计师加入 AI 初创公司

*2026 年 1 月 8 日｜来源：海蓝*

继多名 AI 工程师与 UI 设计高管被 Meta 挖走后，苹果再度流失关键设计人才。
曾参与 **iPhone Air** 设计的 Abidur Chowdhury，于 2025 年 11 月离开苹果，加入 AI 初创公司 Hawk，担任设计主管。

![](https://files.mdnice.com/user/47553/80e5790d-4695-424b-b9f7-7da371f171cd.png)

这家公司由 Figure AI CEO Brett Adcock 创立，目标是研发新一代 AI 模型。
从趋势上看，**AI 正在成为吸走苹果设计与工程人才的重要方向之一**。

### 苹果税全球博弈升级，谁能真正逼苹果低头？

*2026 年 1 月 5 日｜来源：钛媒体*

![](https://files.mdnice.com/user/47553/01b2494e-4f1d-40b0-ab53-b12341630c40.png)

这是本期最重磅的一篇深度报道。

![](https://files.mdnice.com/user/47553/70276d00-fd54-4d63-b8f8-f444e9df4009.png)

从美国 Epic 案、欧盟 DMA、日本《特定智能手机软件竞争促进法》，到英国 15 亿英镑集体诉讼——全球监管正在围绕“苹果税”展开围剿。

![](https://files.mdnice.com/user/47553/234f7191-3653-40fd-9c4c-751213a8cae8.png)

但一个清晰的现实正在浮现：
**苹果会让步，但几乎从不真正低头。**

* 规则被放开，但费用结构被重构
* 抽成下降，但“核心技术费”悄然出现
* 合规执行，但通过复杂条款抵消实质影响

![](https://files.mdnice.com/user/47553/a1d850f0-8b68-478b-8201-c14ef9feb863.png)

文章最终将视角落回中国市场：
在全球最大 App Store 市场，中国用户与开发者仍承受着 **全球最高、选择空间最小的苹果税**。

这场博弈，远未结束。

## 提案

### 正在审查的提案

**SE-0502：从成员初始化器中排除私有初始化属性**

该提案建议调整 Swift 隐式成员初始化器规则：
当新增带默认值的 `private` 属性时，不再因为可访问性问题而强制将成员初始化器降级为 `private`。

核心目标是：
**提升类型演进的安全性，减少无意义的可见性变化对 API 的破坏。**

## Swift 论坛

### 1、为单参数 `Array / Dictionary` 初始化器支持尾随闭包

作者：Jordan Rose ｜ 发布日期：2026 年 1 月 2 日
[阅读原帖](https://forums.swift.org/t/trailing-closure-for-single-argument-array-dictionary-initializers/84201 "Trailing closure for single-argument Array / Dictionary initializers")

该讨论建议为 `Array`、`Dictionary` 等仅有一个参数的初始化器，引入 **尾随闭包（Trailing Closure）** 支持，以提升集合构造时的语法一致性与可读性。

期望支持的写法类似：

```swift
let numbers = Array<Int> {
    1
    2
    3
}

let dict = Dictionary<String, Int> {
    ("a", 1)
    ("b", 2)
}
```

支持者认为，这种写法在以下场景中尤为自然：

* DSL 风格代码
* 测试数据构造
* 与 `@ResultBuilder` 风格 API 保持一致

讨论中的主要分歧集中在：

* 是否会与现有 `Array { repeating:count: }` 等初始化器产生歧义
* 对初学者是否会造成“数组像函数”的理解成本
* 是否应仅限于 Result Builder 场景，而非裸闭包

**简要点评：**
这是一个典型的“语法一致性优化”讨论，短期内不一定推进，但长期来看与 Swift DSL 化方向高度一致。

### 2、枚举一组元类型参数包（Parameter Pack of Metatypes）

作者：Doug Gregor ｜ 发布日期：2025 年 12 月 29 日
[阅读原帖](https://forums.swift.org/t/iterating-over-a-parameter-pack-of-metatypes/84087 "Iterating over a parameter pack of metatypes")

该讨论围绕 Swift 泛型中的 **参数包（parameter pack）** 展开，核心问题是：

> 如何在编译期或运行期，枚举一组泛型参数的 `T.self`？

示例背景类似于：

```swift
func foo<each T>() {
    // 希望能够遍历 each T.self
}
```

这类能力在以下场景中非常关键：

* 序列化 / 反序列化框架
* 依赖注入容器
* 反射与类型注册系统
* 高级泛型工具库

讨论涉及到：

* 参数包展开（pack expansion）与运行时表示的关系
* 是否需要引入新的语法或标准库辅助 API
* 如何在不破坏编译期优化的前提下提供枚举能力

**简要点评：**
这是一个明显偏“语言内核”的讨论，短期难以落地，但它是 Swift 泛型能力继续演进的关键拼图之一。

### 3、在更多位置支持 `#warning` 指令

作者：Ben Cohen ｜ 发布日期：2026 年 1 月 1 日
[阅读原帖](https://forums.swift.org/t/allow-warning-directive-in-more-locations/84155 "Allow #warning directive in more locations")

当前 Swift 中的 `#warning` 只能出现在文件顶层。
该 pitch 提议允许在 **函数体、条件分支等更细粒度的位置** 使用 `#warning`。

期望支持的写法包括：

```swift
func legacyAPI() {
    #warning("This API will be removed in v2.0")
    ...
}
```

支持理由包括：

* 警告可以更贴近真实问题位置
* 比注释更容易被 CI 与编译器捕捉
* 对技术债管理更友好

反对声音主要担心：

* 警告泛滥导致编译输出噪音增加
* 与现有 lint / 静态分析工具职责重叠

**简要点评：**
这是一个非常“工程向”的提案，小而实用，若控制得当，对大型项目维护价值很高。

### 4、让 `Dictionary.mapValues(_:)` 能访问 Key

作者：Xiaodi Wu ｜ 发布日期：2025 年 12 月 31 日
[阅读原帖](https://forums.swift.org/t/mapvalues-should-have-access-to-the-key/84102 "mapValues should have access to the key")

当前 `Dictionary.mapValues` 只能访问 value：

```swift
dict.mapValues { value in
    ...
}
```

该讨论提议提供一个新重载，使其同时能访问 key：

```swift
dict.mapValues { key, value in
    ...
}
```

核心动机是：

* 避免为了访问 key 而退回到 `map { }` + 重建字典
* 在 **不重新 hash key** 的前提下完成值变换
* 提升性能与表达力

讨论中也涉及 API 命名与向后兼容问题。

**简要点评：**
这是一个典型的“补齐能力短板”的改进点，工程价值明确，社区支持度也较高。

### 5、社区推荐：《An Introduction to Programming Using Swift》

作者：Swift Community ｜ 发布日期：2025 年 12 月
[阅读原帖](https://forums.swift.org/t/an-introduction-to-programming-using-swift-beta-0-5-1/83944 "An Introduction to Programming Using Swift")

这是一本面向初学者的 Swift 系统教材，目前已发布 **Beta 0.5.1**，前 17 章内容完成初步校对。

特点包括：

* 从语言基础到控制流、集合、函数逐步展开
* 示例代码完整、循序渐进
* 非 Apple 官方，但社区维护质量较高

**简要点评：**
非常适合作为中文开发者“对照阅读”的英文学习资料。

## 推荐博文

[深入探索 Android 版 Swift SDK](https://www.swift.org/blog/exploring-the-swift-sdk-for-android/ "深入探索 Android 版 Swift SDK ")

**摘要：**
文章从工程实践角度介绍了 Swift 在 Android 平台的可行性，包括编译链路、运行时支持以及与 Kotlin / Java 的互操作方式。作者重点分析了 Swift 作为“跨平台语言”在非 Apple 生态中的现实边界与潜力，适合关注 Swift 长期生态走向的开发者阅读。

[Swift Array的写时复制](https://juejin.cn/post/7585406229150629926/ "Swift Array的写时复制")

**摘要：**
本文通过示例和内存行为分析，详细解释了 Swift Array 的 Copy-on-Write 机制，澄清了“修改一定触发拷贝”的常见误解。对于理解性能问题、避免无意识的内存放大非常有帮助，尤其适合做过性能优化但仍心存疑惑的开发者。

[swift 带有关联类型的协议不可以做类型？](https://juejin.cn/post/7584730308752654386/ "swift 带有关联类型的协议不可以做类型？")

**摘要：**
文章从编译器视角出发，解释了为什么带 `associatedtype` 的协议在 Swift 中不能直接作为类型使用，并结合 `any`、`some`、泛型等概念，系统梳理了 Swift 类型系统背后的设计取舍，是一篇“读完会恍然大悟”的底层向文章。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
