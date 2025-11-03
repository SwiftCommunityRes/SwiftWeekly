## 前言

> 写给每一位还在坚持的开发者

你好，欢迎来到 **Swift 社区周刊第 87 期**。

这里是属于所有 Swift 开发者的精神角落 —— 我们用代码记录变化，也用热爱连接彼此。

这一期，我们为你整理了：

> **Swift Weekly 精选速览**
>
> * **苹果重磅发布**：M5 芯片正式亮相，AI、本地计算与 GPU 性能全线进化。
> * **Swift 论坛热帖**：一个“未赋值变量”竟能拥有神秘默认值？编译器 Bug 现场复盘。
> * **提案聚焦**：可等待赋值（Awaitable Assignment）提案引发热议，Swift 并发语法或迎重大简化。
> * **精选博文**：为什么 SwiftUI 不再需要 MVVM？一文读懂声明式 UI 的范式转向。
> * **话题讨论**：企业文化是凝聚人心的精神内核，还是束缚思想的无形枷锁？

我们知道，写代码的日子有时孤独、焦虑、也有点倦。

但“成功就是多一点的坚持，这一分钟不放弃，下一分钟就会有希望。生活的温柔，就藏在每一个日出日落里，藏在每一步的挣扎努力中！👊👊👊”

Swift 周报已在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，
欢迎提交 issue、推荐内容或加入我们，一起让 Swift 社区更有温度。

**上期话题结果**

![](https://files.mdnice.com/user/47553/6e9ae3a1-cd14-4616-a683-fea9f9592078.png)

## 话题讨论

**企业文化，是凝聚精神还是束缚思想?**

1. 精神内核派：优秀的文化能带来认同感与归属感，让员工在共同价值中找到方向。
2. 思想枷锁派：过度强调统一与服从，容易压制个性和创造力，创新因此被束缚。

## 新闻和社区  

### 动摇索尼独供地位：三星为 iPhone 18 系列在美建厂

*2025 年 10 月 16 日*

苹果正在为 **iPhone 18 系列** 相机重构供应链：
三星电子将时隔近十年重返苹果相机传感器供应体系，并计划在 **美国德州奥斯汀新建生产线**，预计 2027 年投产。

**关键点速览**

* Doosan Tesna 投资 1713 亿韩元扩充测试产能（约 8.58 亿元人民币）
* 测试设备从 Teradyne 转向 **Advantest 系统**，暗示传感器复杂度提升
* 苹果此举意在 **分散索尼供应风险**、提高链路韧性
* 2027 年量产，或影响 iPhone 18 / 19 系列相机质量走向

**背景简析**

Doosan Tesna 作为三星体系半导体测试主力，约 90% 收入来自三星 System LSI 部门。
此次投产标志三星重新拿下苹果关键相机组件订单，也预示苹果在高端影像链上的「双源布局」正式成型。

![](https://files.mdnice.com/user/47553/5d0d3cbc-f78d-4092-8bea-27155a95bd69.png)

### 苹果发布 M5 芯片：AI、GPU、续航全线升级

*2025 年 10 月 16 日*

苹果正式推出自研 **M 系列第五代芯片——M5**，并同步发布三款首发设备：
**14 英寸 MacBook Pro、iPad Pro 与 Vision Pro。**

![](https://files.mdnice.com/user/47553/dd6f27d7-bfb0-4453-9cdc-393d4595be77.png)

#### M5 核心参数亮点

* 台积电 **N3P（第三代 3nm）工艺**
* 10 核 GPU，每核带神经加速单元
* 图形性能较 M4 提升 **最高 45%**
* 统一内存带宽：120GB/s → **153GB/s**

#### 各设备升级一览

**MacBook Pro (14")**

* AI 任务处理速度提升 3.5 倍
* 图形与游戏性能最高提升 1.6 倍
* 起售价：12,999 元

**iPad Pro (M5)**

* 存储读写速度翻倍
* 256GB/512GB 版标配 12GB 内存
* 支持 Wi-Fi 7、蓝牙 6、自研 C1X 蜂窝芯片
* 起售价：8,999 元

**Vision Pro (M5)**

* 渲染像素提升 10%，刷新率最高 120Hz
* 电池续航延长至 2.5 小时
* 起售价：29,999 元
* 新头带设计提升佩戴稳定性，但重量上升至 750–800g

![](https://files.mdnice.com/user/47553/c9a7ef1b-8dc8-4f4f-90cc-92873df2a96e.png)

> 小结：
> 
> M5 不仅是性能升级，更是苹果 AI 芯片布局的关键节点。
> 
> GPU 加速 + 神经单元融合，正在让 Mac 和 iPad 逐步进入「本地 AI 计算」时代。

### 政企动态 | 李乐成会见苹果 CEO 蒂姆·库克

*2025 年 10 月 15 日*

在北京，工业和信息化部部长 **李乐成** 会见了苹果公司 CEO **蒂姆·库克**。
双方围绕苹果在华业务、产业链合作与电子信息领域创新进行了深入交流。

![](https://files.mdnice.com/user/47553/9d495584-4452-403b-bf10-f3ca4d9388a6.jpg)

> 李乐成：“中国拥有完备的产业体系和巨大消费潜力，将坚定推进智能产业化。”
>
> 库克：“苹果将继续加大在华投资，与中国产业链协同创新，实现互利共赢。”

## 提案

> Swift Evolution 提案更新：3 项通过，4 项审查中。
>
> 以下为重点摘要与开发者关注点👇

### 通过的提案

[SE-0491](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0491-module-selectors.md "SE-0491") **用于名称消歧义的模块选择器** 提案通过审查。该提案已在 **第八十六期周报** 正在审查的提案模块做了详细介绍。

[SE-0492](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0492-section-control.md "SE-0492") **部分安置控制** 提案通过审查。

本提案通过 `@section` 与 `@used` 属性控制全局变量在二进制文件的布局位置，适用于系统与嵌入式场景。

[SE-0494](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0494-add-is-identical-methods.md "SE-0494") **添加 `isIdentical(to:)` 方法，用于与具体类型快速比较** 提案通过审查。

我们针对具体类型提出了新的 `isIdentical(to:)` 实例方法，以快速确定两个实例是否必须相等的边值。

### 正在审查的提案

[SE-0493](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0493-defer-async.md "SE-0493") **`defer` 体中支持 `async` 调用** 提案正在审查。

为 `defer` 语句引入 `await`，支持异步清理逻辑。

[SE-0495](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0495-cdecl.md "SE-0495") **C 兼容函数和枚举** 提案正在审查。

新增 `@c` 属性，让 Swift 函数和枚举可直接暴露给 C 调用，取代实验性 `@_cdecl`。

> 注意：本提案旨在正式化和扩展长期实验 `@_cdecl`。虽然是实验，但这个属性已被广泛使用，因此我们将根据需要参考它，以便在本文档中澄清。

[SE-0496](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0496-inline-always.md "SE-0496") **`@inline(always)`属性** 提案正在审查。

指示编译器**始终内联**指定函数，给予开发者更明确的性能控制。

[SE-0497](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0497-definition-visibility.md "SE-0497") **客户端中的控制功能定义可见性** 提案正在审查。

扩展 `@inlinable` 的能力，平衡构建依赖与跨模块优化。

## Swift论坛

### 1、未赋值变量的“神秘默认值”Bug

论坛讨论帖：[未赋值变量出现神秘默认值](https://forums.swift.org/t/mysterious-default-value-for-un-assigned-variable/82670 '未赋值变量的“神秘默认值”Bug')

用户 **MojtabaHs** 发现 Swift 出现诡异行为：未初始化的变量在闭包捕获后似乎“自动拥有”了默认值。

```swift
func foo(date: Date, action: () -> Void) -> Date {
    action()
    return date
}

var actionDate: Date!

let resultDate = foo(date: Date.now) {
    actionDate = resultDate
    print("Assigned")
}

print(actionDate == resultDate)  // false
print(actionDate)                // Optional(2001-01-01 00:00:00 +0000)
```

现象：
即使 `actionDate` 未初始化，它被捕获后出现了奇怪的默认值。
类似现象也出现在 `Int`、`Bool`、`Double` 等类型上（分别变为 0、false、0.0）。

**社区分析：**

* **bbrk24**：怀疑是“零初始化”导致的比特模式误读（`Date` 的内部存储 0 会映射为 2001-01-01）。
* **jamieQ**：问题在于“闭包捕获顺序错误”，在局部作用域中会被编译器检测到错误。
* **xwu**：确认是 Swift 顶层脚本模式的旧 Bug，不会出现在普通作用域中。
* **Slava Pestov**：指出问题可能来自编译器处理 resilient struct 存储属性的系统性缺陷。

**结论：**

* 属于编译器 Bug，而非语言特性。
* 避免在闭包中捕获尚未初始化的变量。
* 若遇到类似问题，应提交最小重现场景给 Swift 项目组。

### 2、Approachable Concurrency 示例编译失败

原帖：[帮助理解 Approachable Concurrency 示例代码编译失败](https://forums.swift.org/t/help-with-approachable-concurrency-sample-code/82634 'Approachable Concurrency 示例编译失败')

作者 **ibex10** 在 Swift 6.2 的“Approachable Concurrency”示例中遇到编译错误：

```swift
struct Image {
  static var cachedImage: [URL: Image] = [:]

  static func create(from url: URL) async throws -> Image {
    if let image = cachedImage[url] { return image }
    let image = try await fetchImage(at: url)
    cachedImage[url] = image
    return image
  }

  @concurrent
  static func fetchImage(at url: URL) async throws -> Image {
    let (data, _) = try await URLSession.shared.data(from: url)
    return await decode(data: data)
  }
}
```

错误提示：

```txt
Static property 'cachedImage' is not concurrency-safe because it is nonisolated global shared mutable state
```

**社区排查：**

* **EngOmarElsayed**：建议检查语言版本；命令行编译通过，说明 Xcode 构建设置问题。
* **Dmitry Kozhinov**：提醒要启用严格并发检查 `SWIFT_STRICT_CONCURRENCY = Complete`。
* **Robert Ryan**：指出部分设置仅作用于特定 target；Intel 与 Apple Silicon 行为可能不同。

**结论：**
该问题与构建配置和 actor 隔离设置有关，非语法错误。可通过确保语言模式和严格并发设置一致来解决。

### 3、提案：Awaitable Assignment（可等待赋值）

原帖：[Awaitable Assignment 提案](https://forums.swift.org/t/pitch-awaitable-assignment/82627 '提案：Awaitable Assignment（可等待赋值）')

提案希望允许在赋值语句中自然使用 `await`，让跨隔离域赋值更直观：

```swift
await self.storage = produceValue()
```

目前语法要求必须在隔离上下文内，否则报错：

```swift
@MainActor
class IsolatedTest {
  var storage: Int = 5

  nonisolated func performAssignment() async {
    // 错误：Main actor-isolated property 不能从非隔离上下文修改
    await self.storage = produceValue()
  }
}
```

**提案目标：**

* 放宽限制，允许 `await prop = expr` / `await obj[key] = expr`。
* 减少 `MainActor.run` 等样板代码。

**社区反馈：**

* 优点：可读性更高、异步代码更自然。
* 担忧：可能鼓励跨 actor 的零散修改，破坏并发安全性。

**结论：**
该提案聚焦于语法一致性改进，尚处草案阶段，未来可能进入正式 SE 流程。

### 4. 已接受提案 SE-0494：`isTriviallyIdentical(to:)`

原帖：[SE-0494：Add isIdentical(to:) methods for quick comparison](https://forums.swift.org/t/accepted-with-modifications-se-0494-add-isidentical-to-methods-for-quick-comparison-to-concrete-types/82695 '已接受提案 SE-0494：isTriviallyIdentical(to:)')

Swift 新增实例方法 `isTriviallyIdentical(to:)`，用于**常量时间**判断两个对象是否“显然相同”。

**核心说明：**

* 原名 `isIdentical(to:)`，审核后改为 `isTriviallyIdentical(to:)`。
* 用于**快速对象比较**（如缓存、memoization）。
* 不做深度比较，仅判断是否“显然相同”。

**设计理由：**

* “Trivially” 表示快速、底层、非语义层的恒等性判断。
* 命名平衡了技术表达与直观可读性。

**最终决定：**

* 提案已修改通过。
* `Span` 类型也将加入该方法。
* 目标是提供一种**性能优化型比较手段**。

### 5、讨论 TaylorTorch：Swift 封装 LibTorch 的新尝试

原帖：[TaylorTorch：现代 Swift 封装 LibTorch](https://forums.swift.org/t/taylortorch-a-modern-swift-wrapper-for-libtorch/82630 "TaylorTorch：Swift 封装 LibTorch 的新尝试")

作者 **Pedro N. Rodriguez H** 推出 **TaylorTorch** —— 一个结合 Swift 自动微分与 PyTorch C++ 引擎（LibTorch）的新框架。

**主要特性：**

* 纯 Swift API，采用协议导向与 Sequential 构建方式。
* 支持常见层（Linear、Conv、Multi-Head Attention、BatchNorm、GNN 等）。
* 支持图神经网络（GNN），提供 MNIST、Seq2Seq、Karate Club 等示例。

**项目链接：**

* GitHub：[github.com/pedronahum/TaylorTorch](https://github.com/pedronahum/TaylorTorch)
* Swift Package Index：[swiftpackageindex.com/pedronahum/TaylorTorch](https://swiftpackageindex.com/pedronahum/TaylorTorch)

**未来规划：**

* 扩展更多算子与层类型。
* 引入 GPU / Metal 支持。
* 构建丰富的模型库，推动 Swift 深度学习生态复兴。

## 推荐博文

[Swift 并发编程中的全局执行器详解](https://juejin.cn/post/7562024713381855242/ "Swift 并发编程中的全局执行器详解")

**亮点摘要：**
全局执行器让 Swift 并发更结构化。通过 `@MainActor` 或自定义执行器划分领域，开发者能自然定义线程边界，避免陷入锁管理。

这是从“写并发”到“设计并发”的一次思维转变。

[SwiftUI 为什么弃用 MVVM？拥抱声明式 UI 的新范式](https://juejin.cn/post/7560558010063618086/ "SwiftUI 为什么弃用 MVVM？拥抱声明式 UI 的新范式")

**亮点摘要：**
SwiftUI 的声明式特性让 MVVM 显得多余。
UI 应该响应状态，而非由中间层驱动。

SwiftData、编程式导航的出现，意味着「更轻、更直观」的架构正在成为主流。

[Swift Approachable Concurrency (易用并发)](https://juejin.cn/post/7551726019867607079/ "Swift Approachable Concurrency (易用并发)")

**亮点摘要：**
Swift 6.2 引入默认主线程执行、自动推断隔离域等机制，让多线程开发更安全、更接近自然逻辑。

`@concurrent` 标记后台任务，其余代码自动主线程安全执行。对 UI 项目尤为友好。

## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
