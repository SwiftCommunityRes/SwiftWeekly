## 前言

**本期是 Swift 编辑组自主整理周报的第六期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

果然，十一假期与新一轮疫情撞了个满怀，远方的你还好吗？**Swift社区**愿与你携手，一起尖叫一起笑，一起撑伞一起闹！👊👊👊

> **周报精选**
>
> 新闻和社区：iPhone14 车祸检测功能摆乌龙 坐过山车自动报警
> 
> 提案：申请将 sleep(for:) 添加到 Clock
> 
> Swift 论坛：Bug @available 在 literal 初始化中没有效果
>
> 推荐博文：async/await 系列代码示例详解
> 

**话题讨论：** 面对各厂新一轮裁员，你焦虑了吗？

## 新闻和社区

### Apple Entrepreneur Camp 现已开放申请

Apple Entrepreneur Camp 旨在为 App 驱动型组织中的少数群体创业者及开发者提供支持，助力其研发新一代的前沿 App 并开拓全球网络，鼓励这些创业者在技术领域不断探索并取得持续发展。

三组面向女性、黑人以及西班牙裔及拉丁裔创业者的在线课程将在 2023 年 1 月开展，欢迎选择合适的一组提交申请。课程期间，Apple 工程师将为学员提供编程指导，Apple 高层也将作为导师分享见解、启发灵感。申请截止日期为 2022 年 12 月 5 日。

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/ED9294F6-B739-4265-B6F1-78314C028500/2048.jpeg)

### iPhone14车祸检测功能摆乌龙 坐过山车自动报警

据美国有线电视新闻网等多家媒体报道，近日有游客在携带苹果公司的新款手机 iPhone14 乘坐过山车时，手机会错误检测到遭遇车祸并自动报警。目前在美国游乐园，已发生多起类似事件，而造成这一切的原因是 iPhone14 自带的车祸检测功能存在问题。

![](https://pics5.baidu.com/feed/b03533fa828ba61e24785d252e258101314e59c6.jpeg@f_auto?token=3abd6fcb688961e1336a2296b0b6744d)

苹果在９月初发布了新款手机 iPhone14，其中一项“车祸检测”新功能颇为引人关注。该功能借助加速度传感器、陀螺仪、麦克风等多种传感器来感知四种碰撞场景，包括正面、侧面、追尾和翻车。一旦检测到车祸，系统会自动弹窗询问机主是否遭遇了紧急情况，在一定时间内若未收到回应，系统将自动报警。

不过，设计人员可能没有考虑到，乘坐过山车与汽车行驶状态容易混淆。据了解，iPhone14 上市以来，在美国多家游乐园的过山车上，都发生过报警乌龙。有的游乐园无奈之下只能提醒游客，坐过山车之前关闭车祸检测功能，或把手机调成飞行模式。(看看新闻Knews)

### 苹果自研5G芯片或要等2025年

此前爆料称，苹果将为未来的 iPhone 开发自主研发的 5G 基带芯片，但据预测，高通仍将是所有 iPhone 15 和 iPhone 16 系列机型的调制解调器供应商，这表明苹果的基带芯片至少要到 2025 年才会亮相。

海通国际证券分析师 Jeff Pu 在周五的研究报告中说，他预计 2024 年发布的 iPhone 机型（暂称 iPhone 16 系列）将使用高通尚未公布的骁龙 X75 调制解调器。与骁龙 X70 一样，X75 预计将基于台积电的 4nm 工艺制造，有助于提高能效。（IT之家)

### 欧盟批准强制苹果使用USB C接口

【欧盟将统一便携智能设备充电接口】据@央视新闻 ，欧洲议会 10 月 4 日通过一项新规，要求从 2024 年底开始，所有手机、平板电脑等便携智能设备新机都使用 USB Type-C 的充电接口。

欧洲议会当天以 602 票赞成、13 票反对的投票结果通过有关统一便携智能设备充电接口的法案。所有手机、平板电脑、数码相机、耳机、便携音箱、手持视频游戏机、电子阅读器、键盘、鼠标和便携式导航系统将在两年内统一充电接口。

## 提案

### 正在审查的提案

[SE-0375](https://github.com/apple/swift-evolution/blob/main/proposals/0375-opening-existential-optional.md "SE-0375") **允许非可选非空参数传递给可选类型的参数** 提案正在审查。

在 [SE-0352](https://github.com/apple/swift-evolution/blob/main/proposals/0352-implicit-open-existentials.md "SE-0352") 提案中有一个限制，可选类型的参数不允许接受非可选参数。本提案申请更改这个限制，当非可选非空参数传递给可选类型的参数时，允许调用成功。示例代码如下：

```Swift
func acceptOptional<T: P>(_ x: T?) { }
func test(p: any P, pOpt: (any P)?) {
  acceptOptional(p) // SE-0352 does not open "p"; this proposal will open "p" and bind "T" to its underlying type
  acceptOptional(pOpt) // does not open "pOpt", because there is no "T" to bind to when "pOpt" is "nil"
}
```

[SE-0374](https://github.com/apple/swift-evolution/blob/main/proposals/0374-clock-sleep-for.md "SE-0374") **将 `sleep(for:)` 添加到 `Clock`** 提案正在审查。

Swift 5.7 中引入的 Clock 协议提供了一种方法来暂停到未来的某个时刻，但没有提供一种方法来休眠一段时间。这与 Task 上的静态 sleep 方法不同，后者提供了一种方法来休眠到某一时刻或一段时间。

[SE-0373](https://github.com/apple/swift-evolution/blob/main/proposals/0373-vars-without-limits-in-result-builders.md "SE-0373") **取消 `result builders` 中对变量的所有限制** 提案正在审查。

`result builders` 转换的实现（由 [SE-0289](https://github.com/apple/swift-evolution/blob/main/proposals/0289-result-builders.md "SE-0289") 引入）对转换函数中的局部变量声明设置了许多限制。具体来说，局部变量需要有一个初始化表达式，它们不能被计算，它们不能有观察者，它们不能有附加的属性包装器。这些限制在 SE-0289 提案中都没有明确说明，但它们实际上是当前功能的一部分。

## Swift论坛

1) 讨论[苹果是否应该创造一个简单编程语言](https://forums.swift.org/t/should-apple-create-a-simple-programming-language/60746 "苹果是否应该创造一个简单编程语言")

2) **Bug** [@available 在 literal 初始化中没有效果](https://github.com/apple/swift/issues/61564 "@available 在 literal 初始化中没有效果")

```Swift
struct Foo {
    let bar: String
}

@available(*, deprecated)
extension Foo: ExpressibleByStringLiteral {
    init(stringLiteral value: StringLiteralType) {
        self.bar = value
    }
}

let a: Foo = Foo(stringLiteral: "") // warning: 'init(stringLiteral:)' is deprecated
let b: Foo = "" // no warning
```

3) 讨论[重新考虑基于 property wrappers 的全局 actor 推断](https://forums.swift.org/t/reconsider-inference-of-global-actor-based-on-property-wrappers/60821 "重新考虑基于 property wrappers 的全局 actor 推断")
内容概括：

4) 提问[拆分我的信息元素](https://forums.swift.org/t/splitting-information-elements/60835 "拆分我的信息元素")

```Swift
// Foo.swift
//
class Foo {
    var x : Int;

    init ();
    init (v: Int);

    func bar () -> Int;
    func bar (u:Int, v:Int) -> Int;
}

extension Foo {
    init () {
        ...
    }

    init (v: Int) {
        ...
    }
}

extension Foo {
    func bar () -> Int {
        ...
    }

    func bar (u:Int, v:Int) -> Int {
        ...
    }
}
```

**解决**使用 `convenience` 初始化方法, `designated` 初始化方法必须写在 class 的主体中但 `convenience` 初始化方法可以在 `extension` 中使用。

```Swift
class Foo {
    var x: Int

    // Note that this is a designated init because it doesn't have the
    // `convenience` keyword.
    init() {
        x = 0
    }
}

extension Foo {
    convenience init(v: Int) {
        self.init()
        x = v
    }
}

extension Foo {
    func bar() -> Int {
        return x
    }

    func bar(u:Int, v:Int) -> Int {
        return x + u + v
    }
}
```

5) 讨论 [iPhone 拍照和激光雷达数据采集](https://forums.swift.org/t/iphone-picture-taking-and-lidar-data-acquisition/60799 "iPhone 拍照和激光雷达数据采集")

6) 讨论[使用 @MainActor 确保在主线程上执行](https://forums.swift.org/t/using-mainactor-to-ensure-execution-on-the-main-thread/60764 "使用 @MainActor 确保在主线程上执行")

7) 讨论 [switch 语句的替代方法](https://forums.swift.org/t/an-alternative-to-the-switch-statement/60714/10 "switch 语句的替代方法")

8) 讨论[累积 HTTP 请求 body 部分：存储 ByteBuffer 是个好主意吗？](https://forums.swift.org/t/accumulating-http-request-body-parts-is-storing-bytebuffer-s-a-good-idea/60813 "累积 HTTP 请求nody部分：存储 ByteBuffer 是个好主意吗？")


## 推荐博文

[Sendable 和 @Sendable 闭包 —— 代码实例详解](https://mp.weixin.qq.com/s/IA9CgMjZf63_RFwNBB9QqQ "Sendable 和 @Sendable 闭包代码实例详解")

**摘要：** Sendable 和 @Sendable 是 Swift 5.5 中的并发修改的一部分，解决了结构化的并发结构体和执行者消息之间传递的类型检查的挑战性问题。

[Swift 中的 async/await —— 代码实例详解](https://github.com/SwiftCommunityRes/article-ios/blob/main/resource/19%20Swift%20中的async:await%20——代码实例详解.md "Swift 中的 async/await —— 代码实例详解")

**摘要：** async-await 是在 WWDC 2021 期间的 Swift 5.5 中的结构化并发变化的一部分。Swift中的并发性意味着允许多段代码同时运行。这是一个非常简化的描述，但它应该让你知道 Swift 中的并发性对你的应用程序的性能是多么重要。有了新的 async 方法和 await 语句，我们可以定义方法来进行异步工作。

[Swift AsyncSequence —— 代码实例详解](https://github.com/SwiftCommunityRes/article-ios/blob/main/resource/20%20Swift%20AsyncSequence%20——%20代码实例详解.md "Swift AsyncSequence —— 代码实例详解")

**摘要：** `AsyncSequence` 是并发性框架和 [SE-298](https://github.com/apple/swift-evolution/blob/main/proposals/0298-asyncsequence.md "SE-298") 提案的一部分。它的名字意味着它是一个提供异步、顺序和迭代访问其元素的类型。换句话说：它是我们在 Swift 中熟悉的常规序列的一个异步变体。

[Swift AsyncThrowingStream 和 AsyncStream ——— 代码实例详解](https://github.com/SwiftCommunityRes/article-ios/blob/main/resource/21%20Swift%20AsyncThrowingStream%20和%20AsyncStream%20———%20代码实例详解.md "Swift AsyncThrowingStream 和 AsyncStream ——— 代码实例详解")

**摘要：** `AsyncThrowingStream` 和 `AsyncStream`是 Swift 5.5 中由 [SE-314](https://github.com/apple/swift-evolution/blob/main/proposals/0314-async-stream.md "SE-314") 引入的并发框架的一部分。异步流允许你替换基于闭包或 Combine 发布器的现有代码。

[Swift 中的 MainActor 使用和主线程调度](https://github.com/SwiftCommunityRes/article-ios/blob/main/resource/22%20Swift%20中的%20MainActor使用和主线程调度.md "Swift 中的 MainActor 使用和主线程调度")

**摘要：** MainActor 是 Swift 5.5 中引入的一个新属性，它是一个全局 actor，提供一个在主线程上执行任务的执行器。在构建应用程序时，在主线程上执行UI更新任务是很重要的，在使用几个后台线程时，这有时会很有挑战性。使用 `@MainActor` 属性将帮助你确保你的UI总是在主线程上更新。

## 话题讨论

**面对各厂新一轮裁员，你焦虑了吗？**

![](https://raw.githubusercontent.com/SwiftCommunityRes/image/main/weekly/weekly1503.png)

欢迎留下你的想法

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
