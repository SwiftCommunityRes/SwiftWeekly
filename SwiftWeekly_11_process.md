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
