## 前言

**本期是 Swift 编辑组自主整理周报的第九期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

蝴蝶的生命之所以如此短暂，因为它的翅膀太过精致了。Swift社区之所以浩瀚汹涌，因为它总想牵动起每一位读者的心！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果 70 亿收购曼联消息不实
> 
> 提案：Package 注册表认证
> 
> Swift 论坛：讨论数组的悬空指针
>
> 推荐博文：灵动岛开发
> 
> **话题讨论：** 
> 
> 世界杯你赚钱了吗？
>
> 你觉得国足几年内能进世界杯？

## 新闻和社区

### 苹果 70 亿收购曼联消息不实

此前，有消息称苹果有意以 70 亿美元收购曼联。11 月 25 日消息，有多位知情人士表示，这条消息并不属实，苹果目前不准备收购英超俱乐部曼联。

![苹果公司](https://pic.rmb.bdstatic.com/bjh/news/ce99a6dd230252a9a9df8a2a37678858.jpeg)

据悉，苹果收购曼联这条消息出自英国小报《The Daily Star》，苹果公司计划斥资大约 70 亿美元用于收购曼联，但据外媒 MacRumors 直接联系多名知情人士，确认这则报道是错误的、不实的。虽然没有收购曼联的计划，但苹果一直在推动体育内容的发展。该公司与 MLB 合作，在 2022 年常规赛期间，每周在 Apple TV + 上播放“ Friday Night Baseball ”两场比赛，并且在未来10年内，它将成为 MLS 比赛的独家供应商。

虽然苹果不准备收购曼联，但确实在推进体育方面的内容。苹果与美国职业棒球大联盟（MLB）合作，2022 年每周通过 Apple TV+ 播放常规赛。该公司还将成为未来 10 年的美国职业足球大联盟（MLS）的独家提供商。另有消息称，苹果还可能从下个赛季开始购买美国职业橄榄球联盟（NFL）的流媒体转播权。

目前，世界杯正在进行中，有关足球的消息总能吸引外界，但苹果收购曼联这事确实让人摸不着头脑。

### 供应链确认 iPhone15 全系 C 口

供应链传出苹果下一代 iPhone 15 最新规格。业内人士预计，升级焦点将集中在 Pro 上，包括 3nm AP、8GB LPDDR5 DRAM 和虚拟侧键等。基本型号的配备规格则预计包括 4nm AP、开孔设计和 48MPx 主镜头。此外，iPhone 15 系列所有机型都将采用 USB Type-C 接口。（财联社）

![](https://files.mdnice.com/user/17787/d0c12b07-ba20-4345-aa0a-64013bdb9fd4.gif)

### iPhone15 或告别纯直边！效果图出炉：神似 iPhone 5C

据 AppleInsider 报道，据博主 ShrimpApplePro 掌握的早期信息，iPhone15 将采用全新的边框设计，后边缘角将变圆，不再是直边框，材料也将会是钛金属。还有网友提前带来了效果图，来看看！

![](https://files.mdnice.com/user/17787/cc52aa27-8c5c-4022-a7d1-534ba1095105.gif)

## 提案

### 正在审查的提案

[SE-0378](https://github.com/apple/swift-evolution/blob/main/proposals/0378-package-registry-auth.md "SE-0378") **Package 注册表认证** 提案正在审查。

Web 服务使用的常用身份验证方法包括基本身份验证、访问令牌和 OAuth。SwiftPM 目前只支持基本的身份验证，这限制了它与 Package 注册服务交互的能力。

Package 注册表需要对其部分或全部 API 进行身份验证，以便识别执行操作的用户并相应地授权请求。

## Swift论坛

1) 讨论[是否应该用 Codable 还是用 NSCoding](https://forums.swift.org/t/should-i-stick-with-codable-or-switch-back-to-nscoding/61604 "是否应该用 Codable 还是用 NSCoding")

2) 讨论[NSKeyedArchiver, CoreData 和其他的存储方案](https://forums.swift.org/t/nskeyedarchiver-coredata-and-other-storage-solutions/61603 "NSKeyedArchiver, CoreData 和其他的存储方案")

3) 讨论[数组的悬空指针](https://forums.swift.org/t/dangling-pointer-from-array/61609 "数组的悬空指针")

```Swift
do {
    var array = [0, 1, 2, 3, 4]
    let ptrToArray = UnsafeBufferPointer<Int>(start: &array, count: array.count)
    
    for number in ptrToArray {
        print(number)
    }
}
```

解决

```Swift
let array = [0, 1, 2, 3, 4]
array.withUnsafeBufferPointer { ptrToArray in
    for number in ptrToArray {
        print(number)
    }
}
```

4) 讨论[如何从 ReducerProtocol 中创建的alert回调中触发操作](https://forums.swift.org/t/how-to-trigger-action-from-alert-callback-created-in-reducerprotocol/61598 "如何从 ReducerProtocol 中创建的alert回调中触发操作")

5) 讨论[键路径与闭包的代码大小差异](https://forums.swift.org/t/code-size-difference-with-keypath-vs-closure/61599 "键路径与闭包的代码大小差异")

6) 讨论[将 Objective-C 代码库迁移到 Swift](https://forums.swift.org/t/migrating-an-objective-c-codebase-to-swift/61592 "将 Objective-C 代码库迁移到 Swift")
Steve Barnegren 撰写的从 Objective-C 迁移到 Swift 30 的博客文章是一本不错的读物。

7) 讨论[RawRepresentable<String> 和  LosslessStringConvertible 的区别](https://forums.swift.org/t/difference-between-rawrepresentable-string-and-losslessstringconvertible/61600 "RawRepresentable<String> 和 LosslessStringConvertible 的区别")
LosslessStringConvertible 改进了 CustomStringConvertible，这会影响其他事情，例如对 String(describing:) 的调用。 
从语义上讲，LosslessStringConvertible 意味着它可以表示为字符串（例如整数），而 RawRepresentable<String> 意味着它在底层是一个字符串（例如原始类型为 String 的枚举）。

8) 讨论[无法使用 protocol 重新创建的类 - 扩展存储属性](https://forums.swift.org/t/i-cant-recreate-my-class-using-protocols-extension-stored-properties/61589 "无法使用 protocol 重新创建的类 - 扩展存储属性")
简短的回答是“ protocol 不能定义存储的属性”。 协议一致性可以在定义类型的模块之外定义，这很自然地得出结论：这样的协议如何添加存储？
您能做的最好的事情就是让协议要求您的类型具有存储空间。 您的类型定义仍然必须实际定义该存储。

9) 讨论[状态初始化器中的 UUID](https://forums.swift.org/t/uuid-in-state-initializer/61593 "状态初始化器中的 UUID")

10) 讨论[对于金融计算用 Decimal 还是 Double](https://forums.swift.org/t/decimal-or-double-for-financial-calculations/61585 "对于金融计算用 Decimal 还是 Double")

## 推荐博文

[在 SwiftUI 中开发灵动岛](https://swiftwithmajid.com/2022/09/28/mastering-dynamic-island-in-swiftui/ "Mastering Dynamic Island in SwiftUI")

**摘要：** 本文将详细介绍使用 WidgetKit 框架中新的 API 实现灵动岛的开发配置和自定义功能。
  
[灵动岛快速入门教程](https://nemecek.be/blog/171/dynamic-island-and-live-activities-quick-start-tutorial "Dynamic Island (and Live Activities): Quick start tutorial")

**摘要：** Dynamic Island 是 `Live Activities` API 的一部分，Live Activities API 是 `Widgets` 系统的一部分。关于 Widgets 详细使用可以参考之前发布的 [SwiftUI 锁屏小组件](https://mp.weixin.qq.com/s/jYbRAJhhdE8H8xeoBnTEaA)

[iOS16 灵动岛 ActivityKit 开发](https://zhuanlan.zhihu.com/p/577728766 "iOS16 灵动岛 ActivityKit 开发")

**摘要：** iOS16.1 苹果向我们开放了 ActivityKit。 使用此框架我们可以在锁定屏幕或者灵动岛上显示实时活动。

## 话题讨论

**世界杯你赚钱了吗？**

  
14 亿人为什么选不出一支十多人的优秀团队？到底是哪里出了问题？元芳，你怎么看？国足⚽️的未来在哪里？

**你觉得国足几年内能进世界杯？**


欢迎在文末留言参与讨论。


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
