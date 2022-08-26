
## 前言

在 199 期的 Swift 周报中，负责人 [Kristaps Grinbergs](https://twitter.com/fassko) 向所有读者发出邀请，内容如下：
> 大家好！ 我真心希望你们享受完感恩节，并且能够和你所爱的人一起度过这个假期。 也许你们中的一些人甚至玩过钱德勒发明的在 6 分钟内命名所有 50 个州的游戏。

> 感恩节之后的这段时间对 Swift 团队来说收获颇丰，今天有很多活动要讨论。 但在我们开始之前，我想利用这个机会说下一期将是我的最后一期，也许是这个项目的最后一期。 如果有人有兴趣接替我的职责，请告诉我。 我很想看到这个项目在我离开后继续存在并蓬勃发展。


> 为了 Swift 社区周报持续稳定的发布更新，我们希望邀请 Swift 爱好者参与**周报编辑**，同时邀请赞助商对我们平台赞助支持。

## 新闻和社区

**Keith Smiley** 分享了有关 Swift 5.5 的更新及其[精选分类过程](https://forums.swift.org/t/5-5-cherry-pick-triage-process/53574 "5.5 cherry pick triage process")。

**John Sundell** 写了[一篇文章](https://www.swiftbysundell.com/articles/count-vs-isEmpty/ "Using count vs isEmpty to check whether a collection contains any elements")，探讨如何使用 `count` 与 `isEmpty` 来检查集合是否包含任意元素。

**Will Lisac** 在推特上表示，适用于 `Raspberry Pi` 的 [Swift 5.5 Docker 镜像](https://github.com/wlisac/swift-on-balena "Swift on Balena") 现已可用。

由 **Feli** 创作的精彩[插图](https://fbernutz.github.io/images/summaries-ios-interview-topics/swift-evolution.jpg)。 她在各种会议上的[绘画作品](https://fbernutz.github.io/sketchnotes/)值得一看。

**Max Desiatov** 宣布 [SwiftWasm 5.5.0](https://blog.swiftwasm.org/posts/5-5-released/ "SwiftWasm 5.5.0 is now available") 现已可用。


## 同意的提案
**SE-0328** `Structural opaque result` 类型已被[接受并进行了修改](https://forums.swift.org/t/accepted-with-modifications-se-0328-structural-opaque-result-type/53789 "[Accepted with Modifications] SE-0328: Structural opaque result type")。 

  在审核期间，主要讨论了两个方面：
    - 可选类型的拼写。 提案将其保留为 ` (some P)? `，尽管 `some P?` 更简洁，可能被作为语法糖。 核心团队更同意这种保守的方法，稍后可以在对该功能有更多经验后重新考虑。
    - 当返回函数类型即 `f() -> (some P) -> Void` 时，在“消费”而不是“生产”位置使用 `some`。 `some` 关键字的其他用途正在讨论中，并且担心与某些未来特性存在潜在冲突。 由于在消费位置使用 `opaque result` 类型不是特别有用（这种函数在所有情况下都是不可调用的），因此核心团队决定将这种使用子集化，目前仅在返回函数类型的返回值中要求 `opaque result` 类型。



## 正在审查的提案

**SE-0332**：[包管理器命令插件](https://forums.swift.org/t/se-0332-package-manager-command-plugins/53769 "Package Manager Command Plugins")正在审查中。
  
  **SE-0303** 引入了在 SwiftPM 中定义构建工具插件的能力，允许在构建过程中自动调用自定义工具。 该提案扩展了该插件支持以允许定义自定义命令插件——用户可以直接从 SwiftPM CLI 或从支持 Swift 包的 IDE 调用的插件，以便对其包执行自定义操作。 

**SE-0331**: [从不安全的指针类型中删除 `Sendable` 一致性](https://forums.swift.org/t/se-0331-remove-sendable-conformance-from-unsafe-pointer-types/53768 "Remove Sendable conformance from unsafe pointer types")正在审查中。
  
  **SE-0302** 引入了 `Sendable` 协议，包括对各种语言结构的 `Sendable` 要求，各种标准库类型对 `Sendable` 的一致性，以及非公共类型隐式符合 `Sendable` 的推理规则。

  `Sendable` 的使用经验表明，这种表述是不必要的危险，并且会对隐式一致性产生意想不到的负面影响。

**SE-0333**：正在审查 [`withMemoryRebound` 的扩展可用性](https://forums.swift.org/t/se-0333-expand-usability-of-withmemoryrebound/53799 "Expand usability of withMemoryRebound")。

  函数 `withMemoryRebound(to:capacity:_ body:)` 执行一个闭包，同时将一定范围的内存临时绑定到与被调用者绑定的类型不同的类型。 我们建议解除 `withMemoryRebound` 的一些显着限制，并允许重新绑定到更大的类型集，以及从原始内存指针和缓冲区重新绑定。

  请注意，此提案与 **SE-0334** 同时运行，这也与不安全的指针可用性有关。

**SE-0334**：正在审查[指针可用性改进](https://forums.swift.org/t/se-0334-pointer-usability-improvements/53800 "Pointer Usability Improvements")。

该提案为 `UnsafePointer` 及其 `Mutable` 和 `Raw` 变量引入了一些质的改进。
  1. 添加一个 API 以获取一个 `UnsafeRawPointer` 实例，该实例从其起点前进到给定的对齐方式。
  2. 在给定 `UnsafePointer<T>` 的情况下，添加 API 以获取指向聚合 `T` 的存储属性的指针。
  3. 添加比较任意两种类型的指针的能力。
  
请注意，此提案与 **SE-0333** 同时运行，这也与不安全的指针可用性有关。

## Swift 论坛

### I
**Ethan Kusters** 开始讨论[在静态托管环境中支持托管 DocC 档案](https://forums.swift.org/t/support-hosting-docc-archives-in-static-hosting-environments/53572 "Support hosting DocC archives in static hosting environments")。

  这篇文章讨论了 Swift-DocC 和 Swift-DocC-Render 的增强功能，这将允许开发人员构建无需自定义路由即可托管的 DocC 档案。 这是专门为使 DocC 能够在其他静态托管环境中使用而设计的，最显着的是 GitHub Pages。

  此更改旨在作为解决紧迫需求的快速解决方案，并提供普遍的好处。 但请注意，我们已经听到社区的反馈，他们希望 Swift-DocC 直接发出静态 HTML，并且此功能在优先级列表中居高不下。

### II
**Sam Deane** 提出了一个想法来[实现一个默认的可初始化协议](https://forums.swift.org/t/default-initable-protocol/53723 "Default-initable Protocol")。 

**Kristaps Grinbergs** 遇到过工厂类型的情况，最终制定了一个协议来表示“可以使用不带参数的默认 `init` 构造这种类型”。

**Kristaps Grinbergs** 发现他感到惊讶： **(a)** 这个协议是否已经存在于标准库中的某个地方，以及 **(b)** 如果 `init()` 存在，Swift 是否可以自动使任何类型符合它。

### III
一个好的[提醒](https://forums.swift.org/t/a-built-in-angle-type/53726 "A built-in Angle type")， [库 Swift Numerics](https://github.com/apple/swift-numerics) 确实存在。

**Guillaume Lessard** 提出了使缓冲区切片更有用的[提案](https://forums.swift.org/t/pitch-buffer-partial-initialization-better-buffer-slices/53795 "[Pitch] Buffer Partial Initialization / Better Buffer Slices")，尤其是在缓冲区的部分初始化方面。

  `UnsafeBufferPointer` 系列的子序列具有 `UnsafeBufferPointer` 的所有 `[Mutable]Collection` API，但没有它们特定于缓冲区的 API。 这使得缓冲区的部分初始化以及其他任务变得困难。
  
## 推荐博文

### LeetCode 系列

该系列的文章中有 **5 篇 Top 100 高频题**

[LeetCode - #1 两数之和](https://mp.weixin.qq.com/s/BwUa6IN4O3DWLmoMAzoFeg) 

难度水平：**容易**，公司面试使用频率如下：

公司 | 频率 
----|------
Amazon | ★★★★★★ 
Facebook | ★★★★★ 
Airbnb | ★★★★★  
Microsoft | ★★★★★
LinkedIn | ★★★★ 

[LeetCode - #2 两数相加](https://mp.weixin.qq.com/s/wFUafzkwiLe7GtP7Uyz9Eg) 

难度水平：**中等**，公司面试使用频率如下：

公司 | 频率 
----|------
Microsoft | ★★★★
Amazon | ★★ 
Airbnb | ★★  

[LeetCode - #3 最长未重复子字符串](https://mp.weixin.qq.com/s/bHLoloSfGphlBQsPXkH6pg) 

难度水平：**中等**，公司面试使用频率如下：

公司 | 频率 
----|------
Amazon | ★★ 

[LeetCode - #4 求两个有序数组的中间值](https://mp.weixin.qq.com/s/QKO2sD2T1H-tFUcakgHUwA) 

难度水平：**困难**

[LeetCode - #5 求最长的镜像字符串](https://mp.weixin.qq.com/s/XUY2DCQfRVPmt-5cXRvRag) 

难度水平：**中等**，公司面试使用频率如下：

公司 | 频率 
----|------
Amazon | ★★ 

>难度水平：容易、中等、困难
公司使用频率：1 ～ 6 颗 ★

### iOS 系列

[戴铭的 Swift 小册子](https://mp.weixin.qq.com/s/AW1PmRU8xKXORuEDJMTNOg)

本篇是面向 Swift 零基础的同学，内容主要是一些直接可用的小例子，例子可以直接在工程中用或自己调试着看。

[SwiftUI 属性包装器如何处理结构体](https://mp.weixin.qq.com/s/Uy2VY7vjFeKMU2yjh8ftsw)

更改 @state 包装的属性时是如何自动让 SwiftUI 重新调用结构体的 body 属性？

[2021 互联网公司时薪排行榜出炉！微软、美团很强！](https://mp.weixin.qq.com/s/mBtydsEv3nRvNzxdV_ikcQ)

分享一个对于选择公司非常有用的参考："**互联网时薪**"。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的各种交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量，排名不分先后：
* [张安宇@微软](https://blog.csdn.net/mobanchengshuang "张安宇")
* [倪瑶@Trip.com](https://github.com/niyaoyao "倪瑶")
* [戴铭@快手](https://ming1016.github.io "戴铭")
* [展菲@ESP](https://github.com/fanbaoying "展菲")
* [杜鑫瑶@新浪](https://weibo.com/u/3878455011 "杜鑫瑶")

周报仓库：https://github.com/SwiftCommunityRes 文章中外引链接较多，可以点击 **阅读原文** 更加方便阅读。
