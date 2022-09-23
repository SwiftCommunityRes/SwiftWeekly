## 前言

**本期是 Swift 编辑组自主整理周报的第五期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

小时候幸福很简单，长大后简单很幸福。**Swift社区**有你未领取的小幸福，等你简简单单来开启！👊👊👊

> **周报精选**
>
> 新闻和社区：iPhone灵动岛无法适配大部分应用
> 
> 提案：Swift 5.8 实现的提案
> 
> Swift 论坛：`conformance` 关键字
>
> 推荐博文：SwiftUI 新功能 Layout 协议
> 
> **话题讨论：** 大厂养老你会选择谁

## 新闻和社区

### iPhone 灵动岛无法适配大部分应用

近日，有海外程序员小哥哥曝光了灵动岛的开发代码，并配文称原本想安装完 Xcode 14.1 Beta版（ iOS 开发程序）去了解下 iPhone 14 Pro 的灵动岛API接口情况，但没想到，苹果并未开放 API，也就是说第三方开发人员很难自行适配灵动岛这个系统级的交互功能。如果想要适配灵动岛恐怕只能向苹果官方申请开放 API 接口。这也是为什么很多 App 至今都没能适配灵动岛的情况出现。（新浪数码）

![](https://raw.githubusercontent.com/SwiftCommunityRes/image/main/weekly/weekly1401.gif)

### App 和 App 内购买项目即将实行价格和税率调整

最早于 2022 年 10 月 5 日起，下列地区 App Store 上的 App 及 App 内购买项目 (自动续期订阅除外) 价格将有所提高：智利、埃及、日本、马来西亚、巴基斯坦、波兰、韩国、瑞典、越南和所有使用欧元货币的地区。在越南，相关的价格提升反映了要求 Apple 代扣代缴适用税款的新规定，其中适用税款包括 5% 的增值税 (VAT) 和 5% 的企业所得税 (CIT)。

您的收益将随之进行调整，并会根据不含税的价格来进行计算。《付费 App 协议》的附录 B 将会更新，表明 Apple 在越南征收和汇付适用税款。

以上调整生效后，在“我的 App”中“价格与销售范围”部分会随即更新。您可以随时在 App Store Connect 中更改您的 App 和 App 内购买项目的价格 (包括自动续期订阅)。如果您有提供订阅项目，您可以选择为现有订阅者保留当前价格。
 
### 苹果确认iOS16存漏洞影响新机激活

据MacRumors看到的一份备忘录，苹果称，“iOS 16有一个已知的问题，可能会影响到使用开放的Wi-Fi网络的设备激活”。为了解决这个问题，苹果表示，用户应该在初始化iOS时，在提示连接到Wi-Fi网络时选择“用iTunes连接到Mac或PC”，然后返回到之前的屏幕，使用Wi-Fi再次尝试，直到激活成功。

### 使用 iOS 16.1 Beta 版和 Xcode 14.1 Beta 版，开发实时活动功能

新的 ActivityKit 框架现已在 iOS 16.1 Beta 版和 Xcode 14.1 Beta 版中推出，探索如何通过这一框架为您的 App 构建实时活动。借由实时更新，实时活动能帮助用户跟踪您的 App 内容。App 的实时活动会显示在锁定屏幕和灵动岛中 — “灵动岛”作为一项全新设计，可以让用户直观、愉悦地体验 iPhone 14 Pro 和 iPhone 14 Pro Max。

实时活动功能和 ActivityKit 将包含在今年晚些时候推出的 iOS 16.1 中。当 iOS 16.1 发布候选版本可用时，您即可将配置了实时活动功能的 App 提交至 App Store。

## 提案

### Swift 5.8 实现的提案

[SE-0372](https://github.com/apple/swift-evolution/blob/main/proposals/0372-document-sorting-as-stable.md "SE-0372") **更新稳定排序文档** 该提案已在[十三期周报](https://mp.weixin.qq.com/s/aoEL9z6U9jq7X_rqecKcuw)正在审查的提案模块做了详细介绍。

[SE-0369](https://github.com/apple/swift-evolution/blob/main/proposals/0369-add-customdebugdescription-conformance-to-anykeypath.md "SE-0369") **同步 CustomDebugString 协议到 AnyKeyPath** 

此提案主要目的是将 `CustomDebugStringConvertible` 的协议添加到 `AnyKeyPath`。

[SE-0367](https://github.com/apple/swift-evolution/blob/main/proposals/0367-conditional-attributes.md "SE-0367") **优化新属性的条件编译** 。该提案已在[十二期周报](https://mp.weixin.qq.com/s/IXP8PNT4aoCnyB-V2qMY_Q)已通过的提案模块做了详细介绍。


## Swift论坛

1) Swift 5.7 发布! 🥳 新增功能详见：[Swift Evolution](https://www.swift.org/blog/swift-5.7-released/ "Swift Evolution") 

2) [Swift Platform Work Group](https://forums.swift.org/t/initiative-swift-platform-work-group/60340 "Swift Platform Work Group")

Swift community 工作组将努力提高 Swift 的平台可用性

工作组内容包括：

* 拓展 Swift 可用的目标平台
* 拓展 Swift 可用的主机平台
* 提高 Swift 现有平台上的 Toolchain
* 让 Swift 编译器可以在现有的平台上工作比如 Linux 和 Windows
* 努力打造更好的跨平台 Swift 生态系统

工作组不涉及的内容有：

* 涉及 Apple 已经支持的平台
* 涉及低资源和裸机平台

3) 提议[使用 conformance 关键字的让协议符合要求](https://forums.swift.org/t/pre-pitch-explicit-protocol-fulfilment-with-the-conformance-keyword/60246 "使用 conformance 关键字的让协议符合要求")

`conformance` 关键字的意思是：**此声明由程序员定义并满足协议要求**。`conformance` 不是 protocol 必须有的关键字。 但是，当 conformance 存在时，除非声明确实符合协议要求，否则程序格式错误。

栗子🌰：

```Swift
protocol Program {
    func run()
}

struct HelloWorld: Program {
    // OK
    conformance func run() { ... }
    
    // error: function crash() does not fulfill any requirement of the protocol 'Program'.
    conformance func crash() { ... }
}
```

4) 提议[clock.sleep(for:)](https://forums.swift.org/t/pitch-clock-sleep-for/60376 "clock.sleep(for:)")

5) 框架[用于web和swift server交互的框架](https://forums.swift.org/t/html-framework-for-swift/60241 "用于web和swift server交互的框架")

* [vapor/leaf 8](https://github.com/vapor/leaf)
* [vapor-community/HTMLKit 9](https://github.com/vapor-community/HTMLKit)
* [Plot 13](https://github.com/JohnSundell/Plot)

6) 讨论[在init方法中使用async function](https://forums.swift.org/t/call-an-async-function-in-an-initializer/60396 "在init方法中使用async function")

7）讨论[PassthroughSubject 和 CurrentValueSubject](https://forums.swift.org/t/asyncsequence-stream-version-of-passthroughsubject-or-currentvaluesubject/60395 "PassthroughSubject 和 CurrentValueSubject")


## 推荐博文

[SwiftUI Layout 协议——第 1 部分](https://swiftui-lab.com/layout-protocol-part-1/ "SwiftUI Layout 协议——第 1 部分")

**摘要：** 今年 SwiftUI 新增比较实用的功能当属 Layout 协议。本篇文章主要介绍 Layout 协议的基础知识和常用功能使用。

[SwiftUI Layout 协议——第 2 部分](https://swiftui-lab.com/layout-protocol-part-2/ "SwiftUI Layout 协议——第 2 部分")

**摘要：** 本篇文章是 SwiftUI Layout 协议的第二部分介绍，主要讲述 Layout 协议的高级布局包含自定义动画、递归布局等功能。

[SwiftUI 之 HStack 和 VStack 的切换](https://mp.weixin.qq.com/s/C739cypR-npGt7F8NLtQgQ)

**摘要：** 本文介绍了当涉及到水平和垂直的变体时( HStack 和 VStack )，我们需要如何在这两者之间动态的切换。

[App Store 已上架项目打开瞬闪问题](https://mp.weixin.qq.com/s/QOB5alijsV5Gg8pi4lg03g)

**摘要：** 用户反馈 iPhone11 iOS14.7 下载安装 App Store 已上架项目后，点击图标，App 闪一下就回到了桌面。

[实现模块化应用的本地化](https://mp.weixin.qq.com/s/8fPJbPNA7kIZhnv3I8m4tg)

**摘要：** 本文详细的介绍了本地化上线的过程，建议收藏，以后新开项目作为参考。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
