## 前言

**本期是 Swift 编辑组自主整理周报的第二期**，每个模块还在调整磨合期。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

昨日的生活与工作是否也曾迷茫？对新技术渴望突破的心是否依旧执着？**Swift社区**，为你的技术栈添砖加瓦，你，准备好了吗？

> **周报精选**
>
> 新闻和社区：
> 
> 提案：
> 
> Swift 论坛：你是否希望支持在 Windows 上构建 Swift
>
> 推荐博文：Swift社区 成立文章仓库

## 新闻和社区

### 已消失5年#iPhone电量百分比为何现在回归# ？

2017年，iPhone X以后，电量百分比一直隐藏在下拉通知栏，而现在，在最新测试版的iOS 16系统中，电量百分比以数字形式被写入电池图标内。

如果苹果在下一代iPhone上增加一个常亮显示功能，那么这种电池百分比调整也会很有用，因为用户可以在不碰手机的情况下就可查看电池状态。还有传言称，iPhone14系列将会在Pro机型上采用挖孔屏，顶部更大的显示面积或许也是苹果复活百分比显示的原因之一。

苹果发言人没有立即透露这个电池百分比调整是否会延续到iOS 16的最终版本。这次更新目前只出现在开发者版和公测版。新iOS系统将于今年秋天发布，可能是在9月份，届时苹果预计将发布iPhone 14。@凤凰网科技

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

【环球时报综合报道】在美国众议院议长佩洛西窜访台湾遭谴责之际，美国科技巨头苹果公司已要求其供应商从台湾地区向中国大陆供货时严格遵守中国海关有关规定。截至记者5日发稿时，苹果方面尚未就有关报道予以置评。

《日经亚洲》5日引述消息人士的说法报道称，苹果公司告诉其供应商，中国海关要求台湾地区生产的元件进入大陆时必须标注产地为“中国台湾”或“中国台北”。苹果公司敦促供应商严肃对待此事，避免因违规导致供货受影响。报道称，苹果公司供应商目前正在为新款iPhone和今秋其他苹果新品的元件供货做准备。消息人士称，如在进口文件、表格中或包装箱上将商品生产地标注为“台湾”，中国海关可能将商品扣留检查，违规商品将被处以4000元人民币罚款，或被拒绝通关。

### Apple Entrepreneur Camp 已开放申请，欢迎女性、黑人和西班牙裔/拉丁裔创业者参加

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/ED9294F6-B739-4265-B6F1-78314C028500/2048.jpeg)
Apple Entrepreneur Camp 旨在为 App 驱动型组织中的少数群体创业者及开发者提供支持，助力其研发新一代的前沿 App 并开拓全球网络，鼓励这些创业者在技术领域不断探索并取得持续发展。

三组面向女性、黑人以及西班牙裔及拉丁裔创业者的在线课程将在 2022 年 10 月开展，欢迎选择合适的一组提交申请。课程期间，Apple 工程师将为学员提供编程指导，Apple 高层也将作为导师分享见解、启发灵感。申请截止日期为 2022 年 8 月 24 日。

## 提案

### 通过的提案


### 正在审查的提案

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
