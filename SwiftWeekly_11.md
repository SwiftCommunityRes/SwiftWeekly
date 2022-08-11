## 前言

**本期是 Swift 编辑组自主整理周报的第二期**，每个模块还在调整磨合期。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

平凡的八月，不平凡的世界，你若落后，必定挨打，你若前进，方得始终！**Swift社区**，给你最新的指引，给你最真的铠甲！

> **周报精选**
>
> 新闻和社区：已消失 5 年 iPhone 电量百分比为何现在回归
> 
> 提案：和脚本语言相媲美的字符串算法
> 
> Swift 论坛：你是否希望支持在 Windows 上构建 Swift
>
> 推荐博文：Swift社区 成立文章仓库

## 新闻和社区

### 已消失 5 年 iPhone 电量百分比为何现在回归？

2017年，iPhone X 以后，电量百分比一直隐藏在下拉通知栏，而现在，在最新测试版的 iOS 16系统中，电量百分比以数字形式被写入电池图标内。

如果苹果在下一代 iPhone 上增加一个常亮显示功能，那么这种电池百分比调整也会很有用，因为用户可以在不碰手机的情况下就可查看电池状态。还有传言称，iPhone14 系列将会在 Pro 机型上采用挖孔屏，顶部更大的显示面积或许也是苹果复活百分比显示的原因之一。

苹果发言人没有立即透露这个电池百分比调整是否会延续到 iOS 16 的最终版本。这次更新目前只出现在开发者版和公测版。新iOS系统将于今年秋天发布，可能是在 9 月份，届时苹果预计将发布iPhone 14。@凤凰网科技

### 线上讲座：App 内购买的新功能
诚挚邀请您参加我们于 2022 年 8 月 18 日(周四)在线举办的“线上讲座：App 内购买的新功能”。 

建议参会对象：开发人员。

注册成功并收到活动确认函后方可参会。名额有限，报满即止。
设计开发加速器活动注册指南：
https://essentials.applesurveys.com/WRQualtricsControlPanel_rel/File.php?F=F_a4rFfRXziNGhoAm

请持续关注 Apple 开发者官网：https://developer.apple.com/cn/accelerator/
我们会不定期地发布下期活动信息，届时可自行申请，获得批准后即可参加活动。 

了解如何使您的 App 内购买体验更加完美, 并探索 StoreKit 2 和 App Store Server API 的增强功能和 App Store Server 通知的改进。了解如何利用 App Transaction API 验证 App 的购买，为 StoreKit 模型添加属性，并在交易中保留 App 的 applicationUsername。如果您是服务器端开发人员，我们将向您展示如何充分利用 App Store 服务器通知、检索用户交易历史的其他方法，以及当您的服务器出现故障时如何进行恢复。了解如何迁移到最新的 App Store Server API 并整合 App Store 服务器通知。

在线活动议程：
10:00-10:30 StoreKit 2 的新功能
10:30-11:00 App Store 服务器 API 和服务器通知新功能 

### 外媒：苹果要供应商从台湾地区向中国大陆供货时严格遵守中方规定

【环球时报综合报道】在美国众议院议长佩洛西窜访台湾遭谴责之际，美国科技巨头苹果公司已要求其供应商从台湾地区向中国大陆供货时严格遵守中国海关有关规定。截至记者 5 日发稿时，苹果方面尚未就有关报道予以置评。

《日经亚洲》5 日引述消息人士的说法报道称，苹果公司告诉其供应商，中国海关要求台湾地区生产的元件进入大陆时必须标注产地为“中国台湾”或“中国台北”。苹果公司敦促供应商严肃对待此事，避免因违规导致供货受影响。报道称，苹果公司供应商目前正在为新款iPhone和今秋其他苹果新品的元件供货做准备。消息人士称，如在进口文件、表格中或包装箱上将商品生产地标注为“台湾”，中国海关可能将商品扣留检查，违规商品将被处以 4000 元人民币罚款，或被拒绝通关。

### Apple Entrepreneur Camp 已开放申请，欢迎女性、黑人和西班牙裔/拉丁裔创业者参加

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/ED9294F6-B739-4265-B6F1-78314C028500/2048.jpeg)

Apple Entrepreneur Camp 旨在为 App 驱动型组织中的少数群体创业者及开发者提供支持，助力其研发新一代的前沿 App 并开拓全球网络，鼓励这些创业者在技术领域不断探索并取得持续发展。

三组面向女性、黑人以及西班牙裔及拉丁裔创业者的在线课程将在 2022 年 10 月开展，欢迎选择合适的一组提交申请。课程期间，Apple 工程师将为学员提供编程指导，Apple 高层也将作为导师分享见解、启发灵感。申请截止日期为 2022 年 8 月 24 日。

## 提案

### 通过的提案

[SE-0365](https://github.com/apple/swift-evolution/blob/main/proposals/0365-implicit-self-weak-capture.md "SE-0365") **在 `self` 被解包后，允许为`weak self`捕获隐式`self`** 提案已通过。

从 **SE-0269** 开始，当 `self` 在捕获列表中显式写入时，允许在闭包中使用**隐式 self**。 应该将这种方式支持扩展到 `weak self` 捕获，并且只要 `self` 已解包，就允许**隐式 self** 。

```Swift
class ViewController {
    let button: Button

    func setup() {
        button.tapHandler = { [weak self] in
            guard let self else { return }
            dismiss()
        }
    }

    func dismiss() { ... }
}
```

[SE-0362](https://github.com/apple/swift-evolution/blob/main/proposals/0362-piecemeal-future-features.md "SE-0362") **即将到来的语言改进的逐渐采用** 提案已通过。该提案已在上期周报正在审查的提案模块做了详细介绍。

[SE-0357](https://github.com/apple/swift-evolution/blob/main/proposals/0357-regex-string-processing-algorithms.md "SE-0357") **基于正则表达式的字符串算法** 提案已通过。

与其他比较常用的编程语言或者脚本语言相比，Swift 标准库处理字符串算法的功能明显不足。其中一些功能可以在 `NSString` 中找到，但是这些基础的功能应该在 Swift 标准库中完善。

**本提案中的建议如下：**

1. 新增加到标准库的正则表达式字符串算法，功能性和实用性要和脚本语言相媲美
2. 就子序列而言，这些算法与通用 `Collection` 相同
3. `CustomConsumingRegexComponent` 协议允许第三方库提供 `industrial-strength` 作为正则表达式的可混合组件

### 正在审查的提案

[SE-0368](https://github.com/apple/swift-evolution/blob/main/proposals/0368-staticbigint.md "SE-0368") **StaticBigInt** 正在审查

Swift 源代码中的整数文字可以表示任意大的值。但是符合 `ExpressibleByIntegerLiteral` 协议的标准库之外的类型，在实际使用过程中受限于使用多大的文字值来构建。

因为传递给 `init(integerLiteral:)` 的值必须是标准库支持的类型，因此很难在标准库之外编写新的整数类型。

[SE-0367](https://github.com/apple/swift-evolution/blob/main/proposals/0367-conditional-attributes.md "SE-0367") **优化新属性的条件编译** 正在审查

随着时间的推移，Swift 引入了一些新的属性来优化性能，提供更多的表达能力和编译检查等功能。但是在现有的源码中增加新属性意味着旧的编译器无法进行编译。

可以使用条件编译来解决这个问题，但是实现代码冗长很不方便。例如，使用 #if 检查编译器版本确定是否可以使用 `@preconcurrency` 属性，代码如下：

```Swift
#if compiler(>=5.6)
@preconcurrency protocol P: Sendable {
  func f()
  func g()
}
#else
protocol P: Sendable {
  func f()
  func g()
}
#endif
```

通过上面的代码可以看到，这样实现会有很多重复的代码。另外 `Swift 5.6` 编译器是第一个包含 `@preconcurrency` 属性的编译器，但是有可能这个属性在 5.6 以前就被启用，或者在 `Swift 5.6` 的开发过程中启用，通过判断版本号就会有误差。建议采用下面的代码方式来规避这些问题。代码如下：

```Swift
#if hasAttribute(preconcurrency)
@preconcurrency
#endif
protocol P: Sendable {
  func f()
  func g()
}
```

[SE-0366](https://github.com/apple/swift-evolution/blob/main/proposals/0366-move-function.md "SE-0366") **代码上下文新增敏感关键字 move** 正在审查

在代码中使用 `move` 关键字，可以结束 `let`、`var` 或者 `consuming` 函数参数的生命周期。并通过编译器实时做出判断强制执行此操作。示例代码如下：

```Swift
useX(x) // do some stuff with local variable x

// Ends lifetime of x, y's lifetime begins.
let y = move x // [1]

useY(y) // do some stuff with local variable y
useX(x) // error, x's lifetime was ended at [1]

// Ends lifetime of y, destroying the current value.
move y // [2]
useX(x) // error, x's lifetime was ended at [1]
useY(y) // error, y's lifetime was ended at [2]
```

## Swift论坛

1) [关于支持在 Windows 上构建 Swift 的讨论](https://forums.swift.org/t/swift-as-a-cross-platform-language-and-windows-support/12547/9 "Swift as a cross-platform language and Windows support")

2) [如何从数据中读取 UInt32](https://forums.swift.org/t/how-to-read-uint32-from-a-data/59431 "How To Read UInt32 from a Data?")

3) [有什么方法可以显示依赖发生的原因](https://forums.swift.org/t/any-way-to-show-what-led-to-a-dependency/59512 "Any way to show what led to a dependency?")

是否有 `SPM` 命令来显示依赖项是如何产生的？可以显示指定 Swift 包在构建中生成的所有依赖路径。

4) [如何延迟对异步方法的响应](https://forums.swift.org/t/how-do-delay-the-response-to-an-async-method/59504 "How do delay the response to an async method?")

有一个网络请求，源码如下：

```Swift
func downloadRequested(_ request: DownloadRequest) async throws -> Response {
    let download = try await self.download(for: request)
        
    self.transferIdMap[download.transferId] = download.itemId
        
    let size = try Int64(download.dataProvider.size())
        
    return (download.transferId, size, download.originalFilename, download.dataProvider.mimeType)
}
```

对这个网络请求的速率进行限制。当有很多的请求未完成时，希望延迟此方法的执行，并将异步回调返回给方法调用者。维持 `async/await` 流程。

5) [在 Linux 上使用 swift Package 中的动态库](https://forums.swift.org/t/use-a-dynamic-library-in-a-swift-package-on-linux/59510 "Use a dynamic library in a swift package on Linux")

在 Apple 平台上，使用 swift Package 中的动态库非常容易。只需要创建一个 `.xcframework` 其中包含 `.dylib` 文件和头文件，并使用 `binaryTarget` 将其添加到 Package 中。在 Linux 上，没有这么简单的解决方案。

6) [提议成立 Swift Tooling 工作组](https://forums.swift.org/t/pitch-swift-tooling-workgroup/59515 "Swift Tooling Workgroup")

目前有许多工具类领域处于无人管理的状态。应该需要有一个小组来监督、推动和指导工作。这些领域包含：**SwiftPM、SourceKit-LSP**、**VSCode 扩展**、**LSP、Swift Format**、**API Breaking Change checker**、**Swiftly**、**Docker 镜像**、**DocC**、**SwiftMarkdown** 等等。

7) [通过 JS 调用 Swift 方法](https://developer.apple.com/forums/thread/711772 "Call Swift functions from JS")

8) [如何对 NavigationLink 中的 tag 和 selection 进行转换](https://developer.apple.com/forums/thread/711841 "NavigationLink")

```Swift
List(workoutTypes) { workoutType in
    NavigationLink(
        workoutType.name,
        destination: SessionPagingView(),
        tag: workoutType,
        selection: $workoutManager.selectedWorkout
    )
}
```

在 iOS 16中 `init(_:destination:tag:selection:)` 方法被弃用。Apple 建议在` NavigationStack` 或者 
`NavigationSplitView` 的列表中使用 `NavigationLink(_:value:)`。

## 推荐博文

[Swift 社区文章仓库](https://mp.weixin.qq.com/s/U1Uw7Ze9Bsmzx0Of4hh1gw)

**摘要：** 给大家推荐一下 Swift社区 的文章仓库，里面整理了公众号中的文章，并进行分类（**Swift 进阶**、**Swift 基础**、**SwiftUI 进阶**、**SwiftUI 基础**、**Tips**、**iOS**、**面试**）。方便大家查找阅读。以后会同步更新维护。

[解决 Flutter 引起的 iOS 内存崩溃问题](https://mp.weixin.qq.com/s/exaRmdUnpzSvlJ2BGSODgw)

**摘要：** 业界首发，很多开发者会被这个问题困扰。如果你的 Flutter 版本号小于等于 `2.5.3` 或大于等于 `3.0.5`，以下描述的问题将不会发生在你的应用中，但是我相信大部分应用都会命中此区间。

[swift-5.5.1-RELEASE源码编译（Xcode）](https://mp.weixin.qq.com/s/3emjAHwr7GDExBiB2cAqWQ)

**摘要：** 使用 ninja 构建 `swift-5.2.4-RELEASE` 版本，然后通过 vscode 和 `lldb` 插件来调试 swift 源码。

[货拉拉 iOS 司机端线程治理总结](https://juejin.cn/post/7129391597967376415 "货拉拉 iOS 司机端线程治理总结")

**摘要：** 经常会收到司机反馈手机发烫，耗电，crash等等问题。线程治理专项应运而生，目的就是降低crash，手机发烫，耗电等问题，尽量给原本并不富裕的内存，雪中送炭。

[使用 Swift Package 插件生成代码](https://mp.weixin.qq.com/s/0ZHfaTiJXAXrWj5qTunhLg)

**摘要：** 在 Xcode 14 的公告中说明，允许在 Xcode 项目中使用 Swift Package 插件，以及一些架构更改。例如本文的Swift Package 插件生成代码。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
