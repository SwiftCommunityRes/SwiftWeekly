## 前言

**本期是 Swift 编辑组自主整理周报的第二十一期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

渺小不可怕，可怕的是比你优秀的强者还比你更加努力。**Swift社区**不会辜负每一位努力的勇士，优秀终将与你不期而遇！👊👊👊

> **周报精选**
>
> 新闻和社区：
> 
> 提案：
> 
> Swift 论坛：
>
> **话题讨论：** 
> 
> 有博主在视频社交平台说，2023年已然迎来了经济危机，只是有些人不愿意相信而已，那么你认为国内2023年是否真的进入了经济危机？

>**上期话题结果**

## 新闻和社区


## 提案


## Swift论坛

1) 讨论[查找符号是如何导入的？](https://forums.swift.org/t/find-how-a-symbol-was-imported/68052 "查找符号是如何导入的？")
我有一个使用特定 API 的源文件，但没有导入定义它的包。据我所知，在该文件的导入中，即使是传递性的，也不会导入该包。 然而，该文件在构建时“正确”编译（尽管 Xcode 15 的实时编译同意我的观点，即 API 不应该可见并生成实时错误）。

我正在使用 Xcode，该文件是一个测试，如果其中任何一个对答案有任何影响。

有没有办法可以调试此 API 的导入方式？ 除了 import 之外，是否还有其他机制可以让 swift API 可供 swift 源文件使用？

**回答**

从技术上讲，只有当您想要使用类型的名称时，才需要将其导入到该文件中。 您可以使用该类型的实例，无需：
```Swift
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

2) 讨论[@backDeployed 作为override运行，而不是仅用于不受支持的平台版本](https://forums.swift.org/t/backdeployed-is-operating-as-an-override-instead-of-only-for-use-in-unsupported-platforms-versions/68071 "@backDeployed 作为override运行，而不是仅用于不受支持的平台版本")
自 Xcode 15 和 iOS 17 发布以来，我们最近一直面临很多令人头痛的问题，因为我们 @backDeployed 的 API 的意外行为。 长话短说，我发现我们 @backDeployed 的任何 API 不仅在平台部署版本“之前”的操作系统上被调用，而且也在平台部署版本“之后”的操作系统上被调用。

这可以通过单元测试或playground来重现：
```Swift
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
实际上，我们使用 @backDeployed 来override任何我们喜欢的 API，而不仅仅是向后部署。

这是否可以在 Swift 的错误修复修订版中解决（最好在退出 beta 之前部署到 Xcode 15.1）？

**回答**
我认为您误解了 @backDeployed 属性的作用以及它的用途。 @backDeployed 设计用于实现操作系统附带的框架。 该属性的设计目的不是为您提供一种为 SDK 中的任意函数提供您自己的 polyfill 的方法，因此，如果我正确解释了您想要完成的任务，我认为它不会达到您想要的效果 。

在您的示例中，您已为 Locale.LanguageCode 声明了自己的计算属性 debugDescription。 您的声明不会“覆盖”基金会中的声明； 它只是作为可以调用的不同函数同时存在于您的模块中。 是否在任何给定的调用站点调用您的实现取决于编译器将 debugDescription 静态解析为哪个声明。 如果编译器解析对您的声明的调用，而不是来自 SDK 的调用，那么您的实现上的 @backDeployed 属性将导致编译器发出对中间 thunk 的调用，该中间 thunk 调用您的原始函数或函数的副本 ，它不会完成任何有用的事情，因为它是同一模块中的函数，并且原始副本和后备副本将始终具有相同的实现。

3) 讨论[新的 SwiftNIO 异步 API](https://forums.swift.org/t/new-swiftnio-async-apis/68056 "新的 SwiftNIO 异步 API")
我很高兴与大家分享，我们刚刚发布了一些软件包的新版本，其中包括全新的异步 API。

* swift-nio : [2.60.0](https://github.com/apple/swift-nio/releases/tag/2.60.0)
* swift-nio-transport-services : [1.20.0](https://github.com/apple/swift-nio-transport-services/releases/tag/1.20.0)
* swift-nio-http2 : [1.29.0](https://github.com/apple/swift-nio-http2/releases/tag/1.29.0)
一段时间以来，我们一直致力于新 API 的开发，让它们在 AsyncChannel SPI 后面进行烘焙。 在最新版本中，我们将 SPI 升级为稳定的 API。

新异步 API 的目标是让开发人员能够轻松、安全地在 NIO Channels 和 Swift Concurrency 之间建立桥梁。 新 API 的一个重要部分是它们携带有关 ChannelPipeline 的类型信息，同时保持灵活性，这是通过利用泛型的强大功能实现的。 您可以在我们全新的 [NIO 和 Swift Concurrency 文章](https://swiftpackageindex.com/apple/swift-nio/2.60.0/documentation/niocore/swift-concurrency)中找到有关新 API 的更多文档。如果您有兴趣阅读更多有关新 API 背后的想法并查看跨包的 API 添加的概述，请随时查看 我们的[开发者文档](https://github.com/apple/swift-nio/blob/main/docs/public-async-nio-apis.md).

我想指出的一件重要的事情是，新的 API 在业务逻辑和网络之间提供了明确的关注点分离。 网络协议存在于通道管道中，业务逻辑应直接在通道管道之外的 Swift Concurrency 中实现。 许多现有应用程序都驻留在通道管道内，我们强烈建议将业务逻辑移出。

我们迫不及待地想看看社区使用新 API 构建了什么，并期待您的反馈！

4) 讨论[使用 ArgumentParser 创建命令行工具的正确方法是什么？ `swift package` 或 Xcode 创建 Mac 命令行工具项目？](https://forums.swift.org/t/what-s-the-right-way-to-create-a-command-line-tool-using-argumentparser-swift-package-or-xcode-create-mac-command-line-tool-project/68050 "使用 ArgumentParser 创建命令行工具的正确方法是什么？ `swift package` 或 Xcode 创建 Mac 命令行工具项目？")
我相信创建 ArgumentParser 命令行工具的正确方法是：
```Swift
swift package init --type tool --name MyTool
```
然后在 Xcode 中打开 Package.swift。 但是我无法添加这个包：https://github.com/dominicegginton/spinner

添加依赖项后，“My Mac”target消失了。

当我从 Xcode 内部创建 macOS 命令行工具项目时，我可以找到 spinner 包并使用它。 如果我添加 ArgumentParser，运行崩溃。

我应该怎么办？

**回答**
您可以尝试分叉 Spinner，更新其软件包清单以使用 Rainbow 4+ ，取决于您的fork，而不是原始fork，然后看看有什么问题......

如果没有任何问题，您可以将该更改作为 PR 提交到 Spinner 项目。

5) 讨论[performSelector(“retainCount”)](https://forums.swift.org/t/performselector-retaincount/68055 "performSelector(“retainCount”)")
另一个线程提示我一个调用禁止的保留计数的问题——可能对调试目的有用。 我知道一些获取对象的保留计数的技术（例如，通过驻留在非 ARC obj-c 文件中的 C 帮助程序进行调用，因此能够调用保留计数，即引用线程中显示的技术）或阅读 通过“withUnsafeBytes”直接从 Swift 中保留 Swift 对象的原始位。 那么这个基于performSelector 的其他方法呢？
```Swift
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
可以对其进行调整以使其工作吗？ 它似乎工作正常，返回正确的 UnmanagedObject，我可以通过“print”命令在调试器中看到它，但如何从应用程序中获取它？ 我是否需要使用一些 unsafeBitCast 来读取该值？

**回答**
PerformSelector: 返回一个对象； 它名义上仅用于返回对象的方法，而不是基元。

在 Objective-C 中，您可能可以通过将结果转换为原始类型来滥用它，但如果它不是指针大小或平台的调用约定使用不同的寄存器来返回指针与整数，您将得到垃圾（或更糟）。

我不确定你是否可以在 Swift 中执行此转换，因为 Unmanaged 假设它确实包含有效的对象引用，并且会尝试适当地保留和释放它。

6) 讨论[为什么 CaseIterable 比 Set 更快](https://forums.swift.org/t/find-how-a-symbol-was-imported/68052 "为什么 CaseIterable 比 Set 更快")
```Swift
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
为什么V1比V2慢？

**回答**
V2 确实还有一项工作要做：从 String 到 enum case。 但这可以优化（在 init(rawValue:) 实现中），因为编译器知道可能的有效字符串的完整集合，因此它最终比哈希查找更快。 （事实上，由于所有字符串都很短，它甚至可以作为整数开关来完成，在检查长度后将字符串内容视为多字节整数。）

## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
