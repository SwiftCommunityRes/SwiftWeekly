## 前言

**本期是 Swift 编辑组整理周报的第四十期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

世间万般兵刃，唯有过往伤人最深。**Swift社区**邀你走出低谷，迈向山巅！👊👊👊

> **周报精选**
>
> 新闻和社区：53.5亿美元！传苹果今明两年或将采购2.3万台AI服务器！
> 
> 提案：隔离的默认值表达式
> 
> Swift 论坛：讨论为什么 CaseIterable 比 Set 更快
>
> 推荐博文：掌握 swift 中  Preview macro 的用法
>
> **话题讨论：** 
> 
> 在诸多物流行业，你最看好哪一家？

**上期话题结果**

![](https://files.mdnice.com/user/17787/b4e1d72d-e137-40ba-8792-7ee684a256a7.jpg)

投票结果显示大多数人更倾向于保持薪资不变或者期望薪资增加，而只有少数人愿意接受较小幅度的薪资降低。小编认为公司在决定远程办公政策时需要综合考虑员工的期望和需求。

## 新闻和社区

### 53.5亿美元！传苹果今明两年或将采购 2.3 万台 AI 服务器！

![](https://files.mdnice.com/user/17787/74aa9817-a2f6-4eb7-a2d3-5e7080d3596c.png)

10 月 25 日消息，根据最新的研究显示，苹果公司计划在 2023 年采购约 2000 - 3000 台 AI 服务器，2024 年或将增长至 1.8 万 - 2 万台，采购的主要目标是满足苹果对AI算力的需求，尤其是在训练和推理生成式 AI 方面。

报告称，苹果主要采购的是英伟达的 HGX H100 8-GPU 系统，由 8 个 H100 SXM5 模块加上 4 个 NVSwitch Chip 在同一个 System board 上。这款 AI 服务器以其强大的性能和稳定的表现成为业界热门选择，单台价格高达 25 万美元（约合人民币 183 万元）。

据天风国际分析师郭明錤预测，在 2023 年和 2024 年期间，苹果将分别采购约 6.2 亿美元（约合人民币 45.38 亿元）和 47.5 亿美元（约合人民币 347.7 亿元）的 AI 服务器，总投额资达 53.3 亿美元。虽然投资额巨大，但考虑到苹果的品牌影响力和技术需求，这一投入无疑是值得的。

目前各行各业对 AI 技术应用持续渗透，对于 AI 算力的需求暴增，全球 AI 服务器市场将迎来更大规模的增长。郭明錤也指出，在未来几年中，全球 AI 服务器市场将继续保持强劲增长，并为相关企业带来更多机会。因此，对于那些想要在这个领域取得成功的企业来说，关注并积极参与 AI 服务器市场的扩张至关重要。（来源：芯智讯）

### TestFlight 让管理测试员变得更加简单

![](https://files.mdnice.com/user/17787/a743075b-d7aa-48f5-a206-ac5461e7ad81.png)

2023 年 10 月 24 日

借助 TestFlight，你可轻松获取有关 App Beta 版的反馈，以便放心地在 App Store 上进行发布。现在，使用 App Store Connect 中经改进的控件，你可更有效地评估测试员的参与度并管理参与情况，以充分利用 Beta 测试。你可按状态和参与度指标 (例如会话、崩溃和反馈) 对测试员进行排序，并删除参与度较低的非活跃测试员。你还可以按设备和操作系统进行筛选，甚至选择相关测试员，以将其添加到新的群组中。

### 推送通知控制面板现已推出新交付指标

![](https://files.mdnice.com/user/17787/345f138a-5923-41ec-9c9b-613a06ffb979.png)

2023 年 10 月 19 日

推送通知控制面板现在包含在生产环境中通过 Apple 推送通知服务 (APNs) 发送的通知的指标。借助控制面板的直观界面，你可以查看交付状态的聚合视图，深入了解通知的各种统计数据 (包括基于推送类型和优先级的详细细分)。

我们在 WWDC23 (简体中文字幕) 公布的推送通知控制面板，将能帮助你轻松地通过 APNs 向 Apple 设备发送测试通知。

### Apple Vision Pro 开发者实验室现已扩展到纽约市和悉尼

![](https://files.mdnice.com/user/17787/469efa54-6995-47ae-8117-c793957ef8e7.png)

2023 年 10 月 17 日

我们非常兴奋能看到世界各地的开发者对 Apple Vision Pro 开发者实验室的期待和热情。很高兴能在此宣布，我们已在纽约市和悉尼设立新的实验室。欢迎参加我们的开发者实验室活动，直接在设备上进行测试，与 Apple 专家沟通交流以获得帮助，一起探索如何让你的 visionOS、iPadOS 和 iOS App 在这个激动人心的新平台上更进一步。我们还分别在库比蒂诺、伦敦、慕尼黑、上海、新加坡和东京设立了实验室。

## 提案

### 正在审查的提案

[SE-0410](https://github.com/apple/swift-evolution/blob/main/proposals/0410-atomics.md "SE-0410") **Low-Level Atomic Operations ** 提案正在审查。

该提案为标准库添加了一组有限的低级原子操作，包括 C++ 风格的内存排序的原生拼写。我们的目标是使编写系统级代码的勇敢的图书馆作者和开发人员能够直接在 Swift 中构建同步结构。

[SE-0411](https://github.com/apple/swift-evolution/blob/main/proposals/0411-isolated-default-values.md "SE-0411") **隔离的默认值表达式** 提案正在审查。

默认值表达式允许用于默认参数和默认存储属性值。当前默认值表达式的 actor 隔离规则存在一些问题：**存储属性的规则容许数据竞争，默认参数值的规则过于限制，而在不同的默认值表达式使用位置之间的规则相互矛盾，导致 actor 隔离模型更难理解**。

该提案统一了默认值表达式的 actor 隔离规则，消除了数据竞争，通过安全地允许默认值的隔离来提高表现力。

## Swift论坛

1) 讨论[查找符号是如何导入的？](https://forums.swift.org/t/find-how-a-symbol-was-imported/68052 "查找符号是如何导入的？")

我有一个使用特定 API 的源文件，但没有导入定义它的包。据我所知，在该文件的导入中，即使是传递性的，也不会导入该包。 

然而，该文件在构建时“正确”编译（尽管 Xcode 15 的实时编译同意我的观点，即 API 不应该可见并生成实时错误）。

我正在使用 Xcode，该文件是一个测试，如果其中任何一个对答案有任何影响。

有没有办法可以调试此 API 的导入方式？ 除了 import 之外，是否还有其他机制可以让 swift API 可供 swift 源文件使用？

**回答**

从技术上讲，只有当你想要使用类型的名称时，才需要将其导入到该文件中。 你可以使用该类型的实例，无需：

```swift
// main.swift
let calendar = myCalendar()
let currentYear = calendar.component(.year, from: now())
print("It's \(currentYear)")

// This all works fine with no errors.
// The type of `calendar` is NSCalendar, but if we had written
//   let calendar: NSCalendar = myCalendar()
// that would be an error.

// file2.swift
import Foundation

func myCalendar() -> NSCalendar {
  return NSCalendar(calendarIdentifier: .gregorian)!
}

func now() -> Date {
  return Date()
}
```

2) 讨论 [@backDeployed 作为 override 运行，而不是仅用于不受支持的平台版本](https://forums.swift.org/t/backdeployed-is-operating-as-an-override-instead-of-only-for-use-in-unsupported-platforms-versions/68071 "@backDeployed 作为 override 运行，而不是仅用于不受支持的平台版本")

自 Xcode 15 和 iOS 17 发布以来，我们最近一直面临很多令人头痛的问题，因为我们 `@backDeployed` 的 API 的意外行为。 

长话短说，我发现我们 @backDeployed 的任何 API 不仅在平台部署版本“之前”的操作系统上被调用，而且也在平台部署版本“之后”的操作系统上被调用。

这可以通过单元测试或 playground 来重现：

```swift
import UIKit

public extension Locale.LanguageCode {
  @backDeployed(before: macOS 14.0, iOS 17.0, watchOS 10.0, tvOS 17.0)
  var debugDescription: String { // <-- introduced in iOS 17
    get {
      if #available(iOS 17, macOS 14.0, *) {
        return "17"
      }
      return self.identifier
    }
  }
}

func test() {
  let locale = Locale(identifier: "en_US")
  let languageCode = locale.language.languageCode!
  
  
  let desc = languageCode.debugDescription
  // ^ This print should yield "en" on iOS 16 & 17
  // but it yields "17" on iOS 17 (proving the @backDeployed API is actually being treated as an override instead thunking to the platform deployed version).
  // You can comment out the @backDeployed `debugDescription` above to see it go back to correct behavior
}

test()
```

实际上，我们使用 @backDeployed 来 override 任何我们喜欢的 API，而不仅仅是向后部署。

这是否可以在 Swift 的错误修复修订版中解决（最好在退出 beta 之前部署到 Xcode 15.1）？

**回答**

我认为你误解了 @backDeployed 属性的作用以及它的用途。@backDeployed 设计用于实现操作系统附带的框架。

该属性的设计目的不是为你提供一种为 SDK 中的任意函数提供你自己的 polyfill 的方法，因此，如果我正确解释了你想要完成的任务，我认为它不会达到你想要的效果 。

在你的示例中，你已为 `Locale.LanguageCode` 声明了自己的计算属性 `debugDescription`。 你的声明不会“覆盖”基金会中的声明；它只是作为可以调用的不同函数同时存在于你的模块中。是否在任何给定的调用站点调用你的实现取决于编译器将 debugDescription 静态解析为哪个声明。

如果编译器解析对你的声明的调用，而不是来自 SDK 的调用，那么你的实现上的 @backDeployed 属性将导致编译器发出对中间 thunk 的调用，该中间 thunk 调用你的原始函数或函数的副本，它不会完成任何有用的事情，因为它是同一模块中的函数，并且原始副本和后备副本将始终具有相同的实现。

3) 讨论[新的 SwiftNIO 异步 API](https://forums.swift.org/t/new-swiftnio-async-apis/68056 "新的 SwiftNIO 异步 API")

我很高兴与大家分享，我们刚刚发布了一些软件包的新版本，其中包括全新的异步 API。

* swift-nio : [2.60.0](https://github.com/apple/swift-nio/releases/tag/2.60.0)
* swift-nio-transport-services : [1.20.0](https://github.com/apple/swift-nio-transport-services/releases/tag/1.20.0)
* swift-nio-http2 : [1.29.0](https://github.com/apple/swift-nio-http2/releases/tag/1.29.0)

一段时间以来，我们一直致力于新 API 的开发，让它们在 AsyncChannel SPI 后面进行烘焙。 在最新版本中，我们将 SPI 升级为稳定的 API。

新异步 API 的目标是让开发人员能够轻松、安全地在 NIO Channels 和 Swift Concurrency 之间建立桥梁。 新 API 的一个重要部分是它们携带有关 ChannelPipeline 的类型信息，同时保持灵活性，这是通过利用泛型的强大功能实现的。 

你可以在我们全新的 [NIO 和 Swift Concurrency 文章](https://swiftpackageindex.com/apple/swift-nio/2.60.0/documentation/niocore/swift-concurrency "NIO 和 Swift Concurrency 文章")中找到有关新 API 的更多文档。如果你有兴趣阅读更多有关新 API 背后的想法并查看跨包的 API 添加的概述，请随时查看 我们的[开发者文档](https://github.com/apple/swift-nio/blob/main/docs/public-async-nio-apis.md).

我想指出的一件重要的事情是，新的 API 在业务逻辑和网络之间提供了明确的关注点分离。

网络协议存在于通道管道中，业务逻辑应直接在通道管道之外的 Swift Concurrency 中实现。 许多现有应用程序都驻留在通道管道内，我们强烈建议将业务逻辑移出。

我们迫不及待地想看看社区使用新 API 构建了什么，并期待你的反馈！

4) 讨论[使用 ArgumentParser 创建命令行工具的正确方法是什么？ swift package 或 Xcode 创建 Mac 命令行工具项目？](https://forums.swift.org/t/what-s-the-right-way-to-create-a-command-line-tool-using-argumentparser-swift-package-or-xcode-create-mac-command-line-tool-project/68050 "使用 ArgumentParser 创建命令行工具的正确方法是什么？ swift package 或 Xcode 创建 Mac 命令行工具项目？")

我相信创建 ArgumentParser 命令行工具的正确方法是：

```swift
swift package init --type tool --name MyTool
```

然后在 Xcode 中打开 Package.swift。 但是我无法添加这个包：https://github.com/dominicegginton/spinner

添加依赖项后，“My Mac” target 消失了。

当我从 Xcode 内部创建 macOS 命令行工具项目时，我可以找到 spinner 包并使用它。 如果我添加 ArgumentParser，运行崩溃。

我应该怎么办？

**回答**

你可以尝试分叉 Spinner，更新其软件包清单以使用 Rainbow 4+ ，取决于你的 fork，而不是原始 fork，然后看看有什么问题......

如果没有任何问题，你可以将该更改作为 PR 提交到 Spinner 项目。

5) 讨论[performSelector("retainCount")](https://forums.swift.org/t/performselector-retaincount/68055 "performSelector("retainCount")")

另一个线程提示我一个调用禁止的保留计数的问题——可能对调试目的有用。 我知道一些获取对象的保留计数的技术（例如，通过驻留在非 ARC obj-c 文件中的 C 帮助程序进行调用，因此能够调用保留计数，即引用线程中显示的技术）或阅读 通过 “withUnsafeBytes” 直接从 Swift 中保留 Swift 对象的原始位。 那么这个基于 performSelector 的其他方法呢？

```swift
let obj = NSObject()
let x = obj.perform("retainCount")!
// p x
// (Unmanaged<AnyObject>) {
//  _value = (object = 0x0000000000000002)
// }
print(x) // crash
let y = x.toOpaque() // crash
print(y)
let z = x.takeUnretainedValue() // crash
print(z)
print(obj)
```

可以对其进行调整以使其工作吗？ 它似乎工作正常，返回正确的 UnmanagedObject，我可以通过 “print” 命令在调试器中看到它，但如何从应用程序中获取它？ 我是否需要使用一些 unsafeBitCast 来读取该值？

**回答**

`PerformSelector:` 返回一个对象； 它名义上仅用于返回对象的方法，而不是基元。

在 Objective-C 中，你可能可以通过将结果转换为原始类型来滥用它，但如果它不是指针大小或平台的调用约定使用不同的寄存器来返回指针与整数，你将得到垃圾（或更糟）。

我不确定你是否可以在 Swift 中执行此转换，因为 Unmanaged 假设它确实包含有效的对象引用，并且会尝试适当地保留和释放它。

6) 讨论[为什么 CaseIterable 比 Set 更快](https://forums.swift.org/t/find-how-a-symbol-was-imported/68052 "为什么 CaseIterable 比 Set 更快")

```swift
// V1
enum VaccineCodeSet: String {
    case covidModerna = "207"
    case covidBioNTech = "208"
    case covidAstraZeneca = "210"
    case covidNovax = "211"
    case covidJohnson = "212"
    case covidValneva = "213"
    case hepatitesB = "45"
    case whoopingCough = "11"
    case measles = "05"
    case mumps = "07"
    case rubella = "06"
    case chickenpox = "21"
    case tbe = "77"
    case hepatitesA = "85"
    case yellowFever = "184"

    static var allCases: Set<String> = [
        Self.covidModerna.rawValue,
        Self.covidBioNTech.rawValue,
        Self.covidAstraZeneca.rawValue,
        Self.covidNovax.rawValue,
        Self.covidJohnson.rawValue,
        Self.covidValneva.rawValue,
        Self.hepatitesB.rawValue,
        Self.whoopingCough.rawValue,
        Self.measles.rawValue,
        Self.mumps.rawValue,
        Self.rubella.rawValue,
        Self.chickenpox.rawValue,
        Self.tbe.rawValue,
        Self.hepatitesA.rawValue,
        Self.yellowFever.rawValue
    ]
}
printTimeElapsedWhenRunningCode(title: "VaccineCodeSet") {
    if VaccineCodeSet.allCases.contains("184") {
        true
    }
}
// Time elapsed to check: 0.006421875 s.

// V2
enum VaccineCodeCaseIterable: String, CaseIterable {
    case covidModerna = "207"
    case covidBioNTech = "208"
    case covidAstraZeneca = "210"
    case covidNovax = "211"
    case covidJohnson = "212"
    case covidValneva = "213"
    case hepatitesB = "45"
    case whoopingCough = "11"
    case measles = "05"
    case mumps = "07"
    case rubella = "06"
    case chickenpox = "21"
    case tbe = "77"
    case hepatitesA = "85"
    case yellowFever = "184"
}
printTimeElapsedWhenRunningCode(title: "Array") {
    if let code = VaccineCodeCaseIterable(rawValue: "184"),
       IllnessCodeCaseIterable.allCases.contains(code) {
       true
    }
}
// Time elapsed to check:: 0.005916875 s.
```

为什么 V1 比 V2 慢？

**回答**

V2 确实还有一项工作要做：从 String 到 enum case。 但这可以优化（在 `init(rawValue:)` 实现中），因为编译器知道可能的有效字符串的完整集合，因此它最终比哈希查找更快。

事实上，由于所有字符串都很短，它甚至可以作为整数开关来完成，在检查长度后将字符串内容视为多字节整数。

## 推荐博文

[掌握 swift 中  Preview macro 的用法](https://swiftwithmajid.com/2023/10/17/mastering-preview-macro-in-swift// "掌握 swift 中  Preview macro 的用法")

**摘要：**  本篇博客介绍了 Swift 中的新功能——预览宏（Preview macro），以及它对开发体验的改进。预览宏可以轻松地将 SwiftUI 视图、UIViewController 或 UIView 实例嵌入到预览中。文章还讨论了如何创建展示不同视图状态的多个预览，并通过传递标题参数来区分它们。此外，它还介绍了预览宏的 traits 参数，可以在预览中显示横向视图或指定尺寸。文章最后提到了如何将预览宏与 widget 结合使用来展示交互式的 widget 时间线。作者建议开发者可以利用预览宏来改善开发体验，并指出可以创建专门用于设计系统包的预览文件或示例用法的文件。

[Xcode 中使用 SPM 和 Build Configuration 的一些坑](https://onevcat.com/2022/10/spm-in-xcode/ "Xcode 中使用 SPM 和 Build Configuration 的一些坑")

**摘要：**  本文介绍了 Swift 中的值和类型参数包，并结合示例进行了详细解释。类型参数包和值参数包允许你编写一个接受任意数量具有不同类型参数的通用函数。在 Swift 5.9 中，由于 SE-393、SE-398 和SE-399 的提案，这一新特性得以实现。采用参数包的最显著影响之一是在 SwiftUI 中的10个视图限制已经不存在，这是由于在这些提案之后可实现了可变参数泛型。本文还解释了参数包的解决方案，它们帮助我们编写可重用的代码，避免编写大量的函数重载。从 Swift 5.9 开始，我们可以使用参数包重写类似的函数。

[Swift 中 User Defaults 的读取和写入](https://www.avanderlee.com/swift/user-defaults-preferences/ "Swift 中 User Defaults 的读取和写入")

**摘要：** 这篇文章讨论了在 Swift 中使用 User Defaults进行读取和写入的方法。User Defaults 是 Swift 应用程序中用于存储在应用程序启动期间保持不变的偏好设置的首选解决方案。它是一个基于属性列表（plist）文件的键值存储。文章介绍了一些与 User Defaults 工作时的最佳实践，并提供了一些特定的解决方案和建议。其中包括使用应用程序组与其他应用程序和扩展共享 User Defaults，以及类型支持和数据转换的注意事项。此外，文章还介绍了监听 User Defaults 更改的方法，并探讨了一些替代方案，如 Keychain 和 CloudKit。在文章的结尾，作者总结了使用 User Defaults 存储偏好设置的好处，并提醒读者在需要跨设备访问数据或存储敏感数据时考虑其他解决方案。。

## 话题讨论

**10月27日，起家于东南亚的极兔速递正式登陆港交所。此次IPO，发行价12港元/股,市值约1000亿港元，成为港交所2023年迄今开盘市值最高的IPO。在诸多物流行业，你最看好哪一家？**

1. 菜鸟
2. 顺丰
3. 京东物流
4. 极兔

欢迎在文末留言参与讨论。


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
