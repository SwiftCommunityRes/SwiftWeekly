## 前言

> 写给每一位还在坚持的开发者

你好，欢迎来到 **Swift 社区周刊第  期**。

这里是属于所有 Swift 开发者的精神角落 —— 我们用代码记录变化，也用热爱连接彼此。

这一期，我们为你整理了：

> **Swift Weekly 精选速览**
>
> * **苹果重磅发布**：
> * **Swift 论坛热帖**：
> * **提案聚焦**：
> * **精选博文**：
> * **话题讨论**：

我们知道，写代码的日子有时孤独、焦虑、也有点倦。

但“成功就是多一点的坚持，这一分钟不放弃，下一分钟就会有希望。生活的温柔，就藏在每一个日出日落里，藏在每一步的挣扎努力中！👊👊👊”

Swift 周报已在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，
欢迎提交 issue、推荐内容或加入我们，一起让 Swift 社区更有温度。

**上期话题结果**

## 话题讨论
“边熬夜边养生，这届年轻人到底是死是活？”——朋克养生是真有效还是自我安慰？
从“熬最晚的夜敷最贵的面膜”到“可乐泡枸杞”，从“护肝片配烧烤”到“褪黑素配手机”。一边是身体发出警告信号，一边是“道理都懂就是改不了”。**你觉得这种一边作死一边自救的生活方式，是年轻人的生存智慧还是自欺欺人？来选你的态度：**

1. 心理安慰大于实际：吃了护肝片，烧烤就能多吃两串，主打一个心安？
2. 真没办法：上班那么累，晚上那点时间不熬一下就感觉今天白过了？
3. 科学养生：保温杯里泡枸杞，该补的补该睡的睡，谁说年轻人不懂养生？


## 新闻和社区  


## 提案


## Swift论坛


## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[Swift 6.4 中 Embedded Swift 的持续进化]( https://www.swift.org/blog/embedded-swift-improvements-coming-in-swift-6.4/ "Swift 6.4 中 Embedded Swift 的持续进化")

**摘要：** 这篇官方月度动态汇聚了 Swift 项目在7月的多项进展。视频资源方面，John McCall 在 PLDI 2026 上的演讲深入探讨了为 Swift 引入显式所有权和生命周期特性时所面临的挑战；社区贡献方面，Google Summer of Code 的参与者正在为Swift并发运行时构建 Task Registry。此外，博客还特别邀请网站工作组贡献者分享了参与 Swift.org 社区建设的亲身经历。

[用 Swift 重构 Electron 会议录制引擎](https://ohmyswift.com/blog/2026/08/02/stop-burning-tokens-on-fix-my-ios-app-performance/ "用 Swift 重构 Electron 会议录制引擎")

**摘要：**  这篇实战博客记录了将 Electron 应用中的实时音视频捕获引擎从 JavaScript 迁移到Swift的全过程。团队发现浏览器渲染进程无法容忍GC暂停等干扰，于是决定走向原生方案：macOS 使用 ScreenCaptureKit，Windows 通过自研的 OBSKit 调用 libobs，中间以共享 Swift 层统一串联。更值得一提的是，团队开发了内部工具 Atomic ——借助Swift宏在编译时自动生成原生代码与 React 前端之间的类型安全桥接，让 Swift 中每个@Published属性自动变为 React 的 Jotai atom。全文呈现了一场从Web技术栈向原生Swift迁移的完整实践，为处理实时媒体场景的跨平台应用提供了极佳的参考范本。

[ Swift 社区动态：2026年7月版]( https://www.swift.org/blog/whats-new-in-swift-july-2026/ " Swift 社区动态：2026年7月版")

**摘要：** 这篇官方月度动态汇聚了 Swift 项目在7月的多项进展。视频资源方面，John McCall 在 PLDI 2026上的演讲深入探讨了为 Swift 引入显式所有权和生命周期特性时所面临的挑战；社区贡献方面，Google Summer of Code 的参与者正在为 Swift 并发运行时构建 Task Registry。此外，博客还特别邀请网站工作组贡献者分享了参与 Swift.org 社区建设的亲身经历。


## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
