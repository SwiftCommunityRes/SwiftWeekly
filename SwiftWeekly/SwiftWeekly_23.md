## 前言

**本期是 Swift 编辑组自主整理周报的第十四期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

勇敢是即便知道好结局不会每每降临在我们身上，但也依然选择热爱和坚持。**Swift社区**会伴你一起，见证每一刻勇敢的光亮！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果iPhone 15 Pro硬件细节曝光，广大网友期待USB-C接口迎来普及
> 
> Swift 论坛：讨论嵌套泛型的问题
>
> 推荐博文：iOS App 项目优化
> 
> **话题讨论：** 
> 
> 生活中遇到的问题你会使用 chatGTP 寻找答案吗？

## 新闻和社区

### 苹果iPhone 15 Pro硬件细节曝光，广大网友期待USB-C接口迎来普及

苹果在欧美市场已被多个监管施压放弃Lighting接口改为USB-C接口，最新关于苹果 iPhone 15 Pro硬件细节爆料消息，似乎透露着苹果公司将将在自家产品正式放弃Lighting接口改为 USB-C 接口。从苹果 iPhone 15 Pro 真机图片来看，苹果 iPhone 15 Pro 开始使用USB-C接口。随着安卓手机厂商普遍采用 USB-C 接口，目前来看苹果公司在自家新品上采用 USB-C 接口，也是整个手机行业的大势所趋。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2023%2F0218%2F2eca6bd0j00rqa52w001id000u000gvm.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

除此之外，苹果 iPhone 15 Pro 硬件外观部分也更加圆润，同时音量键设计也改为电容式设计，后置摄像头的镜头模组也变得更加凸起，意味着苹果公司在新的 iPhone 15 Pro 机型镜头模组进行了升级。

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2023%2F0218%2Fe1795fd6j00rqa52l000ad000sg00e8m.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

![](https://nimg.ws.126.net/?url=http%3A%2F%2Fdingyue.ws.126.net%2F2023%2F0218%2F6f5d7cdaj00rqa52n000sd000sg00e8m.jpg&thumbnail=660x2147483647&quality=80&type=jpg)

总体来说，iPhone 15 Pro 大概率也将是 iPhone 14Pro 升级产品，相较前代机型，在细节部分进行了进一步的优化完善。来源: IT极客世界。

### 苹果也要“降本增效”？步亚马逊、Meta等公司后尘，大刀砍向员工

![](https://pic.rmb.bdstatic.com/bjh/down/d572ac3a4cab7954fc5bacdf5e12aa1f.jpeg)

在亚马逊、微软、谷歌等国际科技巨头们裁员后，苹果也被曝出裁员消息。2 月 17 日，《纽约邮报》援引知情人士报道，苹果公司在过去几天裁减了数百名合同未到期的外包合同工。

作为全世界最赚钱的公司之一，苹果公司曾在 2022 年公开宣称不会裁员，但将停止招聘。但随着 2022 年四季度不及预期的财报发布后，苹果还是动了裁员的念头。

据苹果公司发布 10-12 月份的季度业绩显示，其实现总净销售额 1171.54 亿美元，同比下滑 5% ，不仅低于市场预期的 1211.04 亿元，还创造了 2019 财年来首次营收同比下滑。iPhone、Mac、可穿戴设备等业务营收均出现不同程度的下滑，仅iPad业务的营收实现了同比增长。

为挽救业务，苹果一方面加大促销力度，于 2022 年 9 月开始在中国销售的 iPhone 14 系列，在上市不到半年后即推出“全系降价 600 元- 800 元”的促销活动。搁往年，苹果最新款降价一般都在六七月份。如今，裁员也成为“降本增效”的新选择。

## Swift论坛

1) 讨论[WebURL KeyValuePairs API](https://forums.swift.org/t/weburl-keyvaluepairs-api/63164 "WebURL KeyValuePairs API")

为了更容易地从 URL 组件读取/写入键值对，WebURL 0.5.0 将包含一个新的 KeyValuePairs 类型。 当前的 formParams 视图将在下一个次要版本中弃用和删除。

2) 讨论[将反射元数据划分为运行时和调试类别](https://forums.swift.org/t/partition-the-reflection-metadata-to-runtime-and-debug-categories/63163/1 "将反射元数据划分为运行时和调试类别")

目前的情况：

* 可以完全启用或禁用反射功能。 （中间没有选项）
* 当使用 `-disable-reflection-metadata` 标志禁用时，LLDB 将无法使用反射元数据，从而导致调试功能显着降低。
* 启用后，dsymutil 将反射信息从 TEXT 复制到 dSYM 的 DWARF 段，这允许 lldb 稍后发现它。
* 通过使用 `-enable-reflection-for-debugger-only` 标志，LLDB 可以使用反射，但是，它不会链接到 NTD，这将允许链接器通过 dead-stripping 消除它。

设计：

快速编译器：

* 扩展 FieldTypeMetadataBuilder（可能还有其他构建器）并使其可从外部进行配置。

* 在 emitFieldDescriptor 中实例化两个 FieldTypeMetadataBuilder，一个将直接在 _DWARF 中发射全反射，另一个将像往常一样发射反射到 _TEXT 段。 前者将由 -g 系列标志控制，而后者将由反射标志控制。

DSYMUTIL：

* 更改 dsymutil，而不是从 TEXT 复制反射，而是将其复制到 DWRAF 段。

LLDB：

* 可能需要更改 LLDB，以教会它在没有提供 DSYM 的情况下进行调试时发现 DWARF 段中的反射。

3) 讨论[防止优化 XCFramework 所需的公共接口（又名 dyld：未找到符号）](https://forums.swift.org/t/prevent-optimizing-away-public-interfaces-needed-by-an-xcframework-aka-dyld-symbol-not-found/63162 "防止优化 XCFramework 所需的公共接口（又名 dyld：未找到符号）")

4) 提议[SE-0388：便捷 Async[Throwing]Stream.makeStream 方法](https://forums.swift.org/t/se-0388-convenience-async-throwing-stream-makestream-methods/63139 "SE-0388：便捷 Async[Throwing]Stream.makeStream 方法")

便捷 Async[Throwing]Stream.makeStream 方法”的审查现在开始，一直持续到 2023 年 2 月 26 日。

该提案可在此处获得：https://github.com/apple/swift-evolution/blob/main/proposals/0388-async-stream-factory.md

5) 讨论[Swift 开发容器模板](https://forums.swift.org/t/swift-devcontainer-template/63161 "Swift 开发容器模板")

**内容大概：**

Visual Studio Code 的优势之一是您可以在 docker 容器内开发项目。 如果你在 macOS 上开发但部署到 Linux，你不再需要在 Linux 上运行你的代码来验证它是否工作，你可以在你的 Mac 上编辑、编译、运行和调试你的项目，在 VS Code 中运行的 docker 容器中。

到目前为止，您可以通过手动编辑 devcontainer.json 文件或下载由 Microsoft 管理的快速开发模板来定义容器环境。

由 Microsoft 管理模板意味着在需要对模板进行更改时需要他们的输入（通过 PR 审查），例如添加新版本的 swift。

最近这种情况发生了变化，Swift devcontainer 模板的责任已转移到 SSWG。 devcontainer 现在存储在 swift-server GitHub 组织中。

我们做的第一件事是使模板现代化。 我们用等效的 devcontainer common-utils 功能替换了原始模板具有的 shell 脚本。 您可以在此处找到有关 `devcontainer` 功能的更多信息。原始模板有一个安装 Node.js 的选项（在大多数模板中实现的标准 MS）。 这已被删除，因为现在可以通过 devcontainer 功能完成。

**新的 devcontainer GitHub链接**：https://github.com/swift-server/swift-devcontainer-template

6) 提问[嵌套泛型的问题](https://forums.swift.org/t/nested-generic-trouble/63152 "嵌套泛型的问题")

```Swift
protocol P {}
struct S: P {}

func foo<T: P>(_ value: T) {
    print(type(of: value)) // S
    print(value) // S()
    bar(value)
}

func bar(_ value: S) { print("S call") }

func bar<T: P>(_ value: T) { print("P call") }

func test() {
    let s = S()
    bar(s) // S call
    foo(s) // P call
}
```

calling bar 直接打印出预期的“S call”，但通过“foo”调用它会打印出意外的“P call”。我的期望是错误的？
有趣的是它在 C++ 中按预期工作。

7) 提议[Swift 异步算法提案：缓冲区](https://forums.swift.org/t/swift-async-algorithms-proposal-buffer/63155 "Swift 异步算法提案：缓冲区")

**介绍：**

缓冲是一种通过临时存储元素来平衡生产和消耗率波动来平衡供需的技术。 `AsyncStream` 通过允许您控制缓冲区的大小和处理超过该大小的元素的策略来促进此过程。 但是，这种方法可能并不适合所有情况，并且它不提供一种方法来调整其他 `AsyncSequence` 类型以合并缓冲。

该提案提出了一种新类型，可以满足这些更高级的要求，并为异步序列中的缓冲提供全面的解决方案。

8) 提议[自定义 Actor 执行器](https://forums.swift.org/t/pitch-custom-actor-executors/63135 "自定义 Actor 执行器")

**介绍：**

该提案侧重于使 actor 执行程序可由库作者或最终用户配置的最小可行部分。 它基于 `@John_McCall` 的自定义执行器 16 的早期草案，我们在 Swift 并发性首次引入时分享了该草案，但我们从未正式确定它引入的想法。

在过去的几年里，我们发现了什么有效，什么需要更多的思考。 该提案侧重于标准化基本的 `SerialExecutor` 机制以及参与者如何自定义他们想要运行任务的位置。 我们也承认之前提出的未来工作领域，我们不打算在本提案中一次解决所有这些问题； 请参阅“未来方向”部分以了解更多信息。 有趣的是，这个 API 的某些部分被默默地引入并融入了 Swift 并发的 ABI——在适用的情况下，我们解释了这些关系以及我们如何使提议的 API 满足那些现有的要求。

这个推介也与最近推介的 `unsafeAssumeMainActor` 想法有一点关系，因为它打开了共享同一个串行执行器的各种参与者的领域，并引入了基于此的断言。

**附上 GitHub 链接**：https://github.com/ktoso/swift-evolution/blob/wip-custom-executors/proposals/nnnn-custom-actor-executors.md

## 推荐博文

[百度 APP iOS 端内存优化-原理篇](https://juejin.cn/post/7197970175478464571 "百度 APP iOS 端内存优化-原理篇")

**摘要：** 本文介绍了 Mach 虚拟内存的特点、内存管理的数据结构以及 Mach 内核提供的内存操作接口，同时对 OC 内存分配核心函数 alloc 做了源码分析。

[iOS 包体积优化3 - 代码管理](https://juejin.cn/post/7185083491061596219/ "iOS 包体积优化3 - 代码管理")

**摘要：** 本文是 iOS 包体积优化的系列文章中代码管理模块，主要讲述了如何做好项目中的代码管理工作。

[iOS 包体积优化5 - 编译优化](https://juejin.cn/post/7185101900303728695 "iOS 包体积优化5 - 编译优化")

**摘要：** 本文是 iOS 包体积优化的系列文章中编译优化模块，介绍了多种项目实战所用到的编译优化方法。

## 话题讨论

**生活中遇到的问题你会使用 chatGTP 寻找答案吗？**

123

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
