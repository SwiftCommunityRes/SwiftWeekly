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

[Swift 6.3 中 Codable 错误终于变得可读了](https://sarunw.com/posts/readable-codable-errors/ "Swift 6.3 中 Codable 错误终于变得可读了")

**摘要：** 这篇来自Sarunw的技术博客聚焦于 Swift 6.3 中一项看似微小却极大改善开发体验的改进：DecodingError 和 EncodingError 现在会输出带有编码路径的清晰单行摘要，而不再是过去需要费力略过的大段文本。全文为长期受困于 Codable 错误信息冗长难读的开发者，提供了一个简洁实用的版本升级理由。

[我们的WWDC 26系列现已免费开放](https://www.pointfree.co/blog/posts/226-our-wwdc-26-series-is-now-free/ "我们的WWDC 26系列现已免费开放")

**摘要：** 这篇来自Point-Free的公告宣布其WWDC 26系列共10集内容现已免费。系列深入分析了SwiftUI、UIKit和SwiftData的重大更新，并与Point-Free生态中的SwiftNavigation、SQLiteData、StructuredQueries等工具进行对比。内容从Apple新的状态驱动弹窗API讲起，覆盖UIKit对Observation框架的支持、SwiftData新的查询与持久化特性，最终通过逆向工程SwiftUI的@State宏来填补其遗留缺口，为希望深入理解WWDC 26框架更新的开发者提供了一份系统性的深度解读。

[为什么某些 Swift 类型只在你导入两个模块时才会出现](https://sarunw.com/posts/swift-cross-import-overlay/ "为什么某些 Swift 类型只在你导入两个模块时才会出现")

**摘要：** 这篇来自 Sarunw 的技术博客揭示了一个许多开发者未曾留意却频繁遭遇的编译现象：单独 import SwiftUI 时 Map 视图报“cannot find in scope”，加上 import MapKit 后立即编译通过。文章指出， Map 实际上位于一个名为 _MapKit_SwiftUI 的交叉导入覆盖层（ cross-import overlay ）模块中——只有当文件中同时导入了MapKit和SwiftUI时，编译器才会自动加载这个隐藏模块。 Apple 采用这一设计的目的是避免框架间的强制依赖：若将 Map 放入 SwiftUI，则每个导入 SwiftUI 的应用都会被迫拖入 MapKit ；放入 MapKit 则反向发生。文章还提供了通过 xcrun 命令自行查看 SDK 中覆盖层定义的具体方法，并梳理了iOS 26 SDK 中常见的36组配对关系。


## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
