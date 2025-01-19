## 前言

**本期是 Swift 编辑组自主整理周报的第七十期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

天地风霜尽，乾坤气象和，历添新岁月，春满旧山河。春节将至，**Swift社区**邀您一起，举杯赏月，福醉烟火！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果(AAPL.US)2024年四季度在华销量暴跌 25% 华为距离登顶仅一步之遥！
> 
> 提案：SwiftPM @testable 构建设置
> 
> Swift 论坛：讨论发送 var 可能会引发数据竞争
>
> 推荐博文：用机器学习来驱动一个 iOS 应用:如何开始使用 Create ML 和 Core ML
>
> **话题讨论：** 
> 
> 在你心里所谓的年味究竟是什么呢？
>
>**上期话题结果**

![](https://files.mdnice.com/user/47553/0900b399-10d3-4e4d-b2fa-1ea9a4143fad.jpeg)

根据投票结果可以看出，几乎所有人都希望能上 4 休 3，让我们拭目以待，希望早日能普及执行。

## 新闻和社区  

### 苹果(AAPL.US)2024 年四季度在华销量暴跌 25% 华为距离登顶仅一步之遥！

2025 年 1 月 16 日

智通财经 APP 获悉，研究公司 Canalys 的数据显示，2024 年第四季度，苹果(AAPL.US)在中国的智能手机出货量暴跌 25%，iPhone 制造商在其全球最大的市场之一面临着华为复苏带来的越来越大的压力。

根据 Canalys 周四发布的数据，苹果在此期间在中国的出货量为 1310 万台，以 17% 的份额勉强保持市场领先地位。

Canalys 的数据显示，华为占据了 17% 的市场份额，出货量为 1290 万台，与苹果并列市场领先地位。

华为第四季度出货量增长了 24%，自 2023 年 8 月凭借本土制造的芯片组重返高端市场以来，它已成为一个特别强劲的挑战者。

在竞争压力不断加大的情况下，苹果采取罕见的折扣措施来刺激销售。该公司于 1 月 4 日至 7 日在中国开展了为期四天的促销活动，通过官方渠道对 iPhone 16 机型进行最高 500 元人民币(68.5 美元)的降价。

中国各大电商平台也纷纷效仿，推出了各自的促销活动。阿里巴巴旗下的天猫商城宣布，iPhone 15 系列设备最高可享受 1,000 元人民币(137 美元)的折扣。

Canalys 分析师 Amber Liu 表示：“虽然苹果及其 iPhone 15 系列在第四季度保持了领先地位，但面临着来自国产旗舰设备越来越大的压力。”

除了季节性促销之外，苹果还通过改善零售体验、以旧换新计划和扩大免息分期付款计划来增强其在中国高端市场的竞争地位和用户保留率。”

2024年中国智能手机年出货量将同比增长4%至2.85亿部。（来源：智通财经网）

### Apple Card 成“烫手山芋”？高盛被曝寻求提前结束与苹果合作

2025 年 1 月 16 日

路透社今天（1 月 16 日）发布博文，报道称高盛首席执行官 David Solomon 暗示，该公司和苹果公司在 Apple Card 信用卡方面的合作，可能会在 2030 年合同到期前终止。

Solomon 在财报电话会议上表示，尽管合同期限到 2030 年，但存在提前终止的可能性，但未透露具体原因。

![](https://files.mdnice.com/user/47553/223d1c78-e552-4d51-83e0-d66a3c847078.png)

Solomon 认为苹果 Apple Card 信用卡业务，拖累了高盛 2024 年的股本回报率 75 至 100 个基点，不过预估将在 2025 年和 2026 年有所改善。

苹果公司和高盛合作推出 Apple Card 和 Apple Savings 账户服务，在结束和高盛合作前，苹果需要找到新的合作伙伴才能继续提供这些服务。

此前消息称，苹果接触过美国运通、Synchrony Financial 和 Capital One 等公司，不过 2024 年 9 月最新消息称，苹果正在与摩根大通就 Apple Card 接管事宜进行谈判，但达成协议可能需要数月时间。（来源：IT之家）

### 苹果公司接连传出“坏消息”

2025 年 1 月 13 日

苹果公司（AAPL.O）的“坏消息”接连不断。

2025 年开年的 8 个交易日，有 6 个交易日在下跌，今年以来股价已经跌超 5%，最新市值 3.58 万亿美元。

英国针对科技巨头的反垄断集体诉讼浪潮的首场庭审将于 1 月 13 日开始。苹果公司面临 15 亿英镑司法索赔，被指“滥用市场支配”，对从其 App Store 下载的软件收取“过高且不公平”的费用，佣金最高达 30%。除非在最后一刻达成和解，否则苹果将在英国竞争上诉法庭迎接一场法律战。

美东时间上周五，Meta CEO 扎克伯格接受了一次播客采访。在这场采访中，扎克伯格可谓“畅所欲言”：他大胆抨击了 Meta 在硬件方面的竞争对手——科技巨头苹果公司，指责他们创新乏力和压榨其他人的利益。

在节目中扎克伯格指出， 苹果公司对 App Store 上的应用程序收取 15-30% 的费用，是该公司掩盖 iPhone 销售放缓的一种方式。他还表示， 苹果公司已经有一段时间没有真正发明任何伟大的东西，仅仅依赖 iPhone 的销售来维持业绩。

扎克伯格认为，目前人们甚至不确定 iPhone 的销量是否有所增加，部分原因是每一代机型并没有变得更好，因此人们更换手机的周期比以前更长。如果销售数量总体上持平甚至下降， 苹果作为一家公司如何赚更多的钱呢？

![](https://files.mdnice.com/user/47553/42c130aa-86b0-4877-b8d2-7c2e6316d00d.png)

扎克伯格认为，苹果公司为了掩盖硬件销售下滑，基本上是通过压榨开发者并收取 30% 的“苹果税”来实现的。他“乐观”地认为， 苹果公司总有一天会被某个科技厂商击败，因为苹果公司在产品创新这方面已经偏离了正轨。

知名苹果公司分析师郭明錤近日发文预测，2025 年 iPhone 的出货量将在 2.2 亿至 2.25 亿部之间，远低于市场共识预期的 2.4 亿部或以上。这一预测引发了业界对苹果未来市场表现的担忧，尤其是在 iPhone 标准版销量持续疲软的情况下。

他还表示，据供应链调查显示， 大部分 iPhone 用户对 Apple Intelligence 不感兴趣，对推动用户换机没有任何帮助。

此前，苹果公司的评级被机构罕见下调至“卖出”评级。 　　

美国独立研究公司 MoffettNathanson 将苹果公司的评级从“中性”下调，并给出 188 美元的目标价，这意味着苹果公司股价将较当前水平下跌约 22%。

MoffettNathanson 的高级分析师 Craig Moffett 在降级报告中表示，虽然苹果公司仍然是一家“真正伟大的公司”，但由于有关苹果公司的坏消息铺天盖地，它的股价出现了毫无根据的上涨。（来源：新浪财经）

## 提案

### 正在审查的提案

[SE-0454](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0454-memory-allocator.md "SE-0454") **工具链的自定义分配器** 提案正在审查。

Swift 工具链中的工具需要分配数据结构来编译代码。不同的内存分配器具有不同的性能特征。如果分配器更好地调整到编译器的分配模式，将默认内存分配器从默认（系统）分配器中更改为可以产生好处。

[SE-0455](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0455-swiftpm-testable-build-setting.md "SE-0455") **SwiftPM @testable 构建设置** 提案正在审查。

当前的 Swift Package Manager 构建系统目前是硬编码的，在调试模式下构建时，将 `-enable-testing` 标志传递给Swift编译器以启用 `@testable import`。

[SE-0456](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0456-stdlib-span-properties.md "SE-0456") **向标准库类型添加 Span 提供属性** 提案正在审查。

我们最近引入了 Span 和 RawSpan 类型，但没有提供从现有类型中获取实例的方法。该提案添加了从各种标准库类型中提供终身依赖 Span 的属性，以及在底层元素类型支持时提供终身依赖的 RawSpan。

[SE-0457](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0457-duration-attosecond-represenation.md "SE-0457") **公开秒表 Duration** 提案正在审查。

本提案引入了公共 API，以便将 `Int128` 无缝集成到 `Duration` 类型中。具体来说，它支持通过新可用的 `Int128` 类型直接访问 `Duration` 的 attosecond 表示，并简化了从 attoseconds 创建 `Duration` 值。

[SE-0458](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0458-strict-memory-safety.md "SE-0458") **选择严格的内存安全检查** 提案正在审查。

Swift 通过语言承受能力和运行时检查的结合来提供内存安全。然而，Swift 还故意包含一些不安全的结构，例如标准库中的 `Unsafe` 指针类型、`nonisolated(unsafe)` 等语言功能，以及与C等不安全语言的互操作性。对于大多数 Swift 开发人员来说，这是一个实用的解决方案，在不妨碍的同时提供适当级别的内存安全性。

然而，一些项目希望需要比 Swift 默认提供的更强的内存安全保证。这些项目希望更密切地关注其代码中不安全结构的使用，并在存在安全替代方案时不鼓励随意使用不安全结构。**本提案引入了选择加入的严格内存安全检查，以识别 Swift 代码中使用不安全语言结构和 API 的地方。在这个严格安全子集中编写的任何代码也作为“正常” Swift 工作，并且可以与现有的 Swift 代码互操作。**

## Swift论坛

1) 讨论[Non-suspending 替代是 await?](https://forums.swift.org/t/non-suspending-alternative-to-await/77059/1 "Non-suspending 替代是 await?")

讨论的是 Swift 社区中关于非挂起的替代方案，用于处理异步任务时的一些问题和可能的解决方式。核心点包括：

1.	当前的实现方式：通过 `Task.detached` 启动异步任务，但忽略其结果和错误处理，这样的用法虽然简单，但可能会导致代码中额外的噪音。
2.	潜在改进建议：提出了可能使用 try? 或引入新的关键字（如 concurrent）来优化语法，以更清晰地表达“运行但不等待”的语义。
3.	任务分组的作用：在某些情况下，任务分组（withTaskGroup）可以更好地组织并行任务，但需要具体用例中有多个并行任务，单任务场景下未必有优势。
4.	反思并优化并发模型：作者提出要更仔细地考虑是否真正需要非结构化并发，因为合理的并发模型可以避免不受控的任务悬而未决的问题。

总结：整个讨论旨在优化 Swift 异步任务管理的语法和使用方式，使得开发者可以更高效地处理异步操作，同时避免潜在的任务管理问题。新的建议（如 try? concurrent 或改进任务分组的使用）虽然具有一定潜力，但需要权衡其复杂性和适用场景。

2) 讨论[发送 var 可能会引发数据竞争](https://forums.swift.org/t/sending-a-var-risks-causing-data-races/77051 "发送 var 可能会引发数据竞争")

讨论主题是在 Swift 并发编程中如何避免由 actor 引发的数据竞争问题，具体情境和解决方案如下：
用户分享了一段代码，描述了如何通过 actor 管理一个 Updater 实例以实现线程安全。然而在调用异步方法 stopUpdates() 时，编译器报错，提示：

```swift
Error: Sending 'self.updater' risks causing data races
```
```Swift
actor Pipeline {
    let updater = Updater()
    
    func startUpdates() {
        updater.startUpdates()
    }
    
    func stopUpdates() async {
        await updater.stopUpdates() //Error: Sending 'self.updater' risks causing data races
    }
}

final class Updater {
    func startUpdates() {
        print("started updates")
    }
    
    func stopUpdates() async {
        print("stopped updates")
    }
}
```

错误原因

* actor的隔离规则：

Swift 中，actor 提供了线程安全的隔离。任何被 actor 管理的属性（如 updater）都默认是隔离的，跨线程访问时需要满足 Sendable 协议。如果不符合 Sendable，系统会提示潜在的数据竞争风险。

* Updater不符合Sendable：

默认情况下，final class Updater 不符合 Sendable，因为它可以被多个线程同时访问，进而引发数据竞争问题。

尝试的解决方法与限制

1.	将 Updater 标记为 Sendable
    * 将 Updater 明确标记为 Sendable 是一种解决方案，但会引入以下限制：
    * 不能添加可变的成员变量：因为 Sendable 的要求是类的实例在并发场景中必须是不可变的，任何可变成员都会导致编译器报错。
2.	使用 nonisolated 修饰符
    * 另一种尝试是在 Pipeline 中将 updater 声明为 nonisolated

可能的解决方案

1.	改为使用 actor 管理 Updater
    * 将 Updater 转换为一个 actor，使其本身具有线程安全的特性。例如：
    
```Swift
actor Updater {
    func startUpdates() {
        print("started updates")
    }
    
    func stopUpdates() async {
        print("stopped updates")
    }
}
```

2.	将 Updater 的功能封装在 Pipeline 内
    * 如果 Updater 只在 Pipeline 中使用，可以直接将其功能整合到 Pipeline 中，避免跨隔离的调用。
3.	重构以满足 Sendable
    * 通过避免可变状态或使用不可变的数据类型，使 Updater 符合 Sendable 协议。

总结：这段讨论展示了 Swift 中 actor 的隔离规则和 Sendable 协议的作用。主要挑战在于如何在并发环境中既避免数据竞争，又保留灵活性。常见解决方案包括将共享状态转换为 actor，或在设计时减少对跨线程共享状态的依赖。

3) 提议[Valued break](https://forums.swift.org/t/pitch-valued-break/76995 "Valued break")

提出了一种新方案，旨在改进多行 switch 表达式的实现，提供更灵活的值生成和控制流逻辑。核心内容包括：

* 问题描述：现有的条件分支（如 if-else）无法将块内生成的值用于块外，现有解决方法如三元运算符、提前声明变量、或滥用闭包（IIFE）均存在局限性。
* 解决方案：通过引入带标签的 break，使其既能中断控制流，又能返回值。例如：

```swift
let value = mylabel: if condition {
    break mylabel(3)
} else {
    break mylabel(4)
}
```

* 支持更复杂的逻辑（例如嵌套循环和 do 块）。
* 保持语法兼容性，不引入新关键字。

其他建议：可通过冒号明确返回值的表达式，减少语法歧义和冗余。例如：

```swift
let value = inner: do {
    if test1(element) {
        break: 1
    }
    break inner: 2
}
```

优点：
1.	不引入新关键字，保持语言简洁。
2.	与现有语法完全兼容。
3.	提供更灵活的表达式控制和值返回方式。

总结：该提案旨在提供一种灵活且兼容的方式，解决条件分支和控制流中值生成的限制，为 Swift 开发者带来更多的表达能力。

4) 讨论[Swift 6 传递发送闭包的并发错误](https://forums.swift.org/t/swift-6-concurrency-error-of-passing-sending-closure/77048 "Swift 6 传递发送闭包的并发错误")

在 Swift 6 的并发环境中，问题的核心是闭包隐式捕获了 self，导致不易察觉的错误。以下是主要内容和建议：

* 问题描述：由于 self 被隐式捕获（如未显式写 await self.writer...），可能导致意外行为，尤其是在并发上下文中。
* 快速修复：通过显式捕获列表，确保只捕获必要的变量。例如：

```swift
Task { [writer] in
    // 使用 writer 进行操作
}
```

因为 Writer 是一个 actor，因此可以安全地在闭包中传递。

* 潜在问题：如果 writer 是 var，在 start 和 stop 方法调用之间发生了切换，可能会导致调用错位或遗漏。
* 对 Recorder 的讨论：
   1. Recorder 是一个非 Sendable 类型。
   2. 它参与了并发操作（如使用 Task）。
   
这种类型在并发环境中可能非常复杂，使用时需要特别谨慎。因为方法是非隔离的，所以调用顺序无法保证。例如：

```swift
recorder.startRecording()
recorder.stopRecording()
```

在上述代码中，stop 可能在 start 之前发生。

* 解决方法：
 1.	推迟创建 Task，并将调用改为异步。
 2.	如果 Recorder 与 UI 直接关联，可将其标注为 `@MainActor`。这可以：
    * 提供静态隔离，确保更好的调用顺序（在 Swift 6 编译器中）。
    * 使类型变为 Sendable。

总结：要安全、高效地在并发环境中使用非 Sendable 类型，需明确捕获范围，并考虑使用 `@MainActor` 或将并发逻辑上移，以减少复杂性和潜在错误。

5) 讨论[适用于非 Apple 平台（如 Android、Web、Windows）的 SwiftUI](https://forums.swift.org/t/swiftui-for-non-apple-platforms-like-android-web-windows/25455 "适用于非 Apple 平台（如 Android、Web、Windows）的 SwiftUI")

SwiftUI 的声明式 UI 模型展现了其跨平台潜力，可用于 Web、Windows 和 Android 等非 Apple 平台。然而，SwiftUI 并非开源项目，因此实现这一愿景需要特殊努力。以下是主要内容和建议：

* 现状：Apple 的目标是通过 SwiftUI 提供“学习一次、应用到处”的开发体验，但目前局限于 Apple 平台。
* 潜力：SwiftUI 的声明式和抽象特性（如 Text、Button、VStack）适用于所有类型的用户界面，扩展到其他平台将极大促进 Swift 的普及和应用。
* 挑战与建议：

   1.	Apple 主导：最佳方案是 Apple 开源 SwiftUI 的基础算法和 API，允许社区和公司在其他平台上进行实现。
   2.	中间层支持：Apple 提供中间层算法，用于将声明式代码转换为最终 UI 表现，并实现基于数据的 UI 更新逻辑。
   3.	社区贡献：由开源项目（如 Vapor）或公司（如微软和 Canonical）负责在非 Apple 平台上的具体实现。
   
* 实现的可能性：虽然当前看似遥远，但 Apple 可能早已考虑了跨平台支持。例如，命名为 SwiftUI 并使用 Swift 标志表明其与 Swift 语言的深度关联，或暗示潜在的开放意图。
* 愿景：如果 SwiftUI 成为真正的跨平台 UI 框架，它将成为开发者对抗 Dart/Flutter 等框架的有力武器，大幅提升 Swift 作为通用编程语言的吸引力。

总结：SwiftUI 的跨平台潜力巨大，但需要 Apple 的支持与社区的协作。开源基础框架和算法是实现这一目标的关键，而 SwiftUI 成为通用跨平台开发工具将是 Swift 生态的革命性进展。

## 推荐博文

[用机器学习来驱动一个 iOS 应用:如何开始使用 Create ML 和 Core ML](https://zhuanlan.zhihu.com/p/90919163/ "用机器学习来驱动一个 iOS 应用:如何开始使用 Create ML 和 Core ML")

**摘要：** 这篇文章全面介绍了在 iOS 应用中实现机器学习的方法，重点讲解了 Create ML 和 Core ML 这两个框架的应用实践。文章通过图像分类和情感分析两个具体实例，展示了机器学习在移动应用中的实际应用场景。在图像分类部分，详细说明了如何训练一个识别猫狗图片的模型，并将其整合到 iOS 应用中实现实时视频分类；在情感分析部分，则展示了如何处理文本数据，训练模型来分析电影评论的情感倾向。

文章同时深入探讨了这些技术的优势与局限性，指出 Create ML 虽然适合快速原型开发，但在生产环境中可能存在一些限制。文章特别强调了数据质量对模型训练的重要性，以及在实际应用中需要考虑预测可信度的关键性。

最后，文章指出移动设备上的机器学习技术尽管仍处于早期阶段，但已经展现出巨大的创新潜力，并鼓励开发者探索将机器学习技术整合到应用中的各种可能性。


[端智能：面向手机计算环境的端云协同 AI 技术创新](https://juejin.cn/post/7340481613144473619/ "端智能：面向手机计算环境的端云协同 AI 技术创新")

**摘要：** 摘要：随着移动端设备软硬件能力的提升，端智能技术在电商领域逐渐得到应用，并且在京东等企业中取得了显著进展。端智能将 AI 模型推理计算迁移至移动端，具备实时性高、隐私合规性强和离线服务能力等优势，突破了云端智能的延迟、高成本和隐私问题。

然而，在端智能的开发过程中，仍面临计算性能、灵活性、稳定性和安全性等多重挑战。京东通过创新的端智能系统架构，结合云-边-端三层结构，在模型训练、部署和推理计算等方面提供了高效支持。

同时，通过超实时数据流处理、高效事件调度、兼容性强的PythonVM端计算容器和高性能推理引擎等技术，确保了端智能的快速响应和稳定运行。京东的端智能技术已经在流量分发和图像识别等业务中成功落地，提升了用户购物体验。

未来，端智能将进一步扩展到更多算法场景，并通过平台能力建设和多端场景覆盖提升开发效率和算法应用效果。

[以 iOS 开发者的视角去看鸿蒙的 struct](https://juejin.cn/post/7459983789729824779/ "以 iOS 开发者的视角去看鸿蒙的 struct")

**摘要：**  这篇文章从一名 iOS 开发者的视角，对比了 Swift 和鸿蒙系统的 ArkTS 中的 `struct`，探讨了它们的相似之处和不同之处。文章首先解释了 `struct` 的定义及其在两种语言中的应用。它指出，尽管 Swift 和 ArkTS 的 `struct` 都是轻量级的值类型数据结构，但它们在语言定位、UI 绑定、状态管理、序列化支持和实例化方式等方面有所不同。特别是 ArkTS 的 `struct` 更加专注于声明式 UI 开发，并通过装饰器管理组件状态，与 SwiftUI 中的 `@State` 和 `@Binding` 有相似之处。

文章总结了两者在不同应用场景下的适用性，并指出 ArkTS 的 `struct` 适用于鸿蒙应用的 UI 开发，而 Swift 的 `struct` 更适合通用编程。

## 话题讨论

日月交替，时光轮转，又到了我们中华儿女的盛世佳节，然而越来越多的人感觉到年味变淡了，那么在你心里所谓的年味究竟是什么呢？

1. 备年货、送年礼、年夜饭。
2. 守岁、祭祀、拜年。
3. 糖果、美食、新衣裳。
4. 烟花、爆竹、红包。
5. 亲朋齐聚，嘘寒问暖。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
