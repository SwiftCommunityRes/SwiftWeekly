## 前言

**本期是 Swift 编辑组自主整理周报的第十五期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

TODO

> **周报精选**
>
> 新闻和社区：
> 
> 提案：围绕 `Macros` 提出多个提案
> 
> Swift 论坛：
>
> 推荐博文：使用 `async/await` 完成后台任务管理
> 
> **话题讨论：** 
> 
> 

## 新闻和社区

TODO

## 提案

### 正在审查的提案

[SE-0382](https://github.com/apple/swift-evolution/blob/main/proposals/0382-expression-macros.md "SE-0382") **Expression Macros** 提案重新恢复审查。该提案已在 **二十期周报** 正在审查的提案模块做了详细介绍。

[SE-0388](https://github.com/apple/swift-evolution/blob/main/proposals/0388-async-stream-factory.md "SE-0388") **增加 Async[Throwing]Stream.makeStream 方法** 提案正在审查。

改天建议引入辅助方法来创建 `AsyncStream` 和 `AsyncThrowingStream` 实例，使开发者使用起来更加方便。

[SE-0389](https://github.com/apple/swift-evolution/blob/main/proposals/0389-attached-macros.md "SE-0389") **Attached Macros** 提案正在审查。

`Attached Macros` 是 Swift 中 `Macros` 愿景的一部分，该提案以 SE-0382 `Expression Macros` 的思想和动机为基础，涵盖了大量新的用例，将参考该提案以了解 `Macros` 如何集成到语言中的基本模型。

[SE-0390](https://github.com/apple/swift-evolution/blob/main/proposals/0390-noncopyable-structs-and-enums.md "SE-0390") **引入 @noncopyable ** 提案正在审查。

该提案引入了 `@noncopyable` 类型（也称为 `move-only` 类型）的概念。 `@noncopyable` 类型的实例始终具有唯一所有权，这与可以自由复制的普通 Swift 类型不同。

[SE-0391](https://github.com/apple/swift-evolution/blob/main/proposals/0391-package-registry-publish.md "SE-0391") **Package Registry 公开发布** 提案正在审查。

`Package Registry` 公开发布后，可以对外公开可用。 从 Swift 5.7 开始，SwiftPM 支持使用任何实现与 SE-0292 一起提出的服务规范的注册表的依赖项解析和包下载。

## Swift论坛

TODO

## 推荐博文

[使用 async let 在 Swift 中并行运行后台任务](https://juejin.cn/post/7197970175478464571 "Use async let to run background tasks in parallel in Swift")

**摘要：** 本文介绍了如何在后台执行长期运行的任务并保持 UI 响应。`async/await` 提供了执行异步任务的干净机制。允许并行执行多个后台任务。

[如何在 Swift 中取消后台任务](https://swdevnotes.com/swift/2023/how-to-cancel-a-background-task-in-swift/ "How to cancel a background task in Swift")

**摘要：** Swift 5.5 中引入的 `async/await` 语法允许以可读的方式编写异步代码。异步编程可以提高应用程序的性能，同时很重要的一点是要取消不需要的任务，以确保暂时不需要的后台任务不会干扰应用程序。本文演示了如何取消任务，并解释了如何自动取消子任务。

[如何在 Flutter 中使用 async/await](https://sarunw.com/posts/how-to-use-async-await-in-flutter/ "How to use async/await in Flutter")

**摘要：** 在本文中展示了一系列异步实现示例，并在最后给出三个组件（`Future`，`async` 和 `await`）的使用说明。

## 话题讨论

**TODO**

123

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
