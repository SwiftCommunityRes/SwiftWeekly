## 前言

**本期是 Swift 编辑组自主整理周报的第六十期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

野心太大，才华甚少。于是，回忆间遗憾，梦境中恐惧，时光里迷惘。**Swift社区**于流年里筑基，岁月间化形，恍惚中蜕变。所以，千日苦修，终成不朽！👊👊👊

> **周报精选**
>
> 新闻和社区：消息称苹果仍在研发更大尺寸的iMac 屏幕超过30英寸
> 
> 提案：
>
> Swift 论坛：
>
> 推荐博文：
>
> **话题讨论：** 
> 
> 
>
>**上期话题结果**




## 新闻和社区  

### 消息称苹果仍在研发更大尺寸的iMac 屏幕超过30英寸

2024 年 8 月 15 日

据外媒报道，在转向自研的M系列芯片之后，苹果公司 2021 年 4 月份推出的搭载 M1 芯片和 2023 年 10 月份推出的搭载 M3 芯片的 iMac，都是 24 英寸的屏幕，而随着 iMac Pro 和搭载英特尔芯片的 2020 年款 iMac 的下架，iMac 也就有一段没有了 27 英寸版可买，只有 24 英寸屏幕可选。

![](https://upload.techweb.com.cn/s/1080/imgs/2024/0815/1723691769808.jpg)

虽然苹果目前在售的 iMac 只有 24 英寸屏幕，但从去年开始，多次有外媒在报道中称苹果在研发更大尺寸的 iMac，在去年年中，就曾有消息称一款更大尺寸的 iMac，已在研发的早期阶段。不过到目前为止，尚未有更大屏幕的 iMac 推出，去年年底推出的仍是 24 英寸屏幕。

但长期关注苹果的一名资深记者透露，苹果公司仍在探索屏幕尺寸更大的 iMac。

不过，这名长期关注苹果的资深记者，目前还不确定更大尺寸的 iMac 是否会搭载苹果自研的 M4 芯片，也就是 5 月份推出的新一代 iPad Pro 率先搭载的那一款芯片。

此外，基于不同的芯片，外媒目前在更大尺寸的 iMac 的推出时间上也还有不同的看法，搭载 M4 芯片，可能就会同 MacBook Air、Mac Pro、Mac Studio 一样，在明年推出，但苹果也有可能等待 M5 芯片，推出时间可能就是在 2026 年或之后。

值得注意的是，在去年 10 月份，知名苹果产品分析师郭明錤，曾预计苹果在 2025 年将推出 32 英寸屏幕的 iMac，搭载 mini-LED 显示屏。

至于苹果是否会推出及何时推出屏幕超过 30 英寸的 iMac，要在他们正式发布之后才会揭晓，保密传统浓厚的他们，在发布之前不会公布相关的消息。(来源：TechWeb)

### 最新！苹果大动作

2024 年 8 月 14 日

面对欧盟等地监管方多年的压力，苹果公司终于低头。

美东时间 8 月 14 日周三，苹果宣布，从新版操作系统 iOS 18.1 开始，开发者将可使用 iPhone 内的安全元件（SE），不通过苹果旗下支付和钱包 Apple Pay 和 Apple Wallet，在开发者自行开发的 iPhone 应用程序 App 中，提供 NFC 无接触数据交换功能。

要使用这些 App 内的新功能，用户可以直接打开 App，也可以在 iOS 设置中将该 App 设置为默认支持，然后双击 iPhone 侧边按钮，即可发起交易。

![](https://pics4.baidu.com/feed/9e3df8dcd100baa1df51bee82aa1c01cc9fc2ea7.jpeg@f_auto?token=7227780230c2c2effeb08f3b9e9e4351)

苹果称，通过新的 NFC 和 SE API，开发者将能提供 App 内的无接触数据交换，可用于闭环公交、企业工牌、学生证、家门钥匙、酒店钥匙、商家积分和回馈卡，甚至活动门票等，未来还将支持身份证件。这些 API 将首先通过即将发布的 iOS 18.1 开发者资源向澳大利亚、巴西、加拿大、日本、新西兰、英国和美国的开发者提供，未来将落地更多地区。

同时苹果指出，若要在 iPhone App 中纳入上述新的无接触数据交换功能，开发者需要同苹果签订一份商业协议，申请并得到NFC和SE授权，且支付相关费用。这将确保开发者符合特定行业及监管的要求，并遵守苹果的安全和隐私标准。

上述苹果公告意味着，苹果将开始允许第三方使用 iPhone 的支付芯片来处理交易，等于允许银行和其他服务方与 Apple Pay 平台竞争。有消息称，到目前为止，只有 Apple Pay 和 Apple Wallet 可以使用 iPhone NFC 芯片的许多功能，这种“独家”优势将随着 iOS 18.1 上线而改变。

值得一提的是，今年苹果在欧盟反垄断压力下作出了一系列让步。

今年 1 月苹果宣布，对其在欧盟的 iOS、Safari 和 App 应用商店产品进行一系列历史性的大幅改革。改革将首次允许客户从苹果应用商店 App Store 以外下载软件。人们还将能够使用其他的支付系统，并且更容易地选择新的默认网络浏览器。

另据新华社报道，欧盟委员会 7 月 11 日宣布已同美国苹果公司达成和解，苹果承诺向竞争对手免费开放基于近场通信（NFC）技术的移动支付功能。相关承诺将具法律约束力，为期 10 年，适用于整个欧洲经济区。

2022 年，欧盟委员会指控苹果公司限制第三方移动支付应用开发者使用 NFC，这使苹果支付在和其他同类产品竞争中获得不公平的优势。

据欧盟委员会介绍，此前苹果提出初步承诺，向第三方移动支付应用开发者免费开放在苹果设备上的 NFC 访问权限，无需通过苹果支付或苹果钱包等。此后，欧盟委员会对苹果承诺的措施进行了市场测试，苹果也根据测试和反馈结果修改了其承诺。

欧盟委员会认可了这些承诺并表示，苹果的最终承诺将有助于消除该委员会对相关领域市场竞争的担忧。

美国媒体援引苹果公司一份声明说，该公司将为欧洲经济区的开发者在他们的相关应用程序中提供多种使用场景下启用 NFC 非接触式支付和交易的选项。(来源：每日经济新闻)

### Apple Entrepreneur Camp 现已开放申请

2024 年 8 月 13 日

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/99A1800C-E399-41AB-9A95-F58AEA6B28F9/2048.jpeg)

Apple Entrepreneur Camp 旨在为少数群体创业者和开发者提供支持，并鼓励这些企业家在技术领域不断探索并取得持续发展。课程期间会提供一对一编程指导以及与 Apple 工程师和专家沟通的宝贵机会，参与者也将成为持续扩大的全球 Apple Entrepreneur Camp 营友网络中的一员。

申请通道现已面向女性*、黑人、西班牙裔/拉丁裔和原住民创业者及开发者开放。今年，我们很高兴能再次在库比提诺的 Apple 园区举办现场活动。对于无法亲赴现场参加的人员，我们仍将提供完整的在线课程。欢迎经营 App 驱动型企业的成熟企业家进一步了解资格要求并提交申请。

申请截止日期为太平洋时间 2024 年 9 月 3 日。

## 提案


## Swift论坛
1) 提议[并发安全通知](https://forums.swift.org/t/pitch-concurrency-safe-notifications/73713 "并发安全通知")
**内容大概**
该提案旨在将 Swift 并发引入到 NotificationCenter 中，以提高代码的安全性和健壮性。目前，NotificationCenter API 通过发布和观察通知的模式，使代码解耦。这种模式在 macOS、iOS 以及其他基于 Darwin 的系统中的框架中得到了广泛集成。通知的发布者通过 Notification.Name 标识发送通知，并可以选择性地包括 object 和 userInfo 作为负载。观察者则通过注册代码块或闭包来接收通知，并可以选择指定 OperationQueue 来执行这些观察者的代码。

然而，目前的 NotificationCenter 存在一些问题。首先，通知的并发性依赖于隐式约定，观察者的代码块通常会在与发布者相同的线程上运行。为了确保并发性，客户端通常需要查阅文档或使用并发机制，这可能会导致问题。此外，现有的通知类型和负载类型并不够强，使用字符串作为标识符容易导致拼写错误，且客户端在处理通知负载时，可能需要频繁地进行类型转换。

为了解决这些问题，提案提出了一个新协议 NotificationCenter.Message，该协议允许创建可以通过 NotificationCenter 发布和观察的类型，并提供对 Swift 并发的支持，同时保留与现有 Notification 类型的互操作性。通过定义 Notification.Name，NotificationCenter.Message 可以与现有的 Notification 类型兼容。默认情况下，符合 NotificationCenter.Message 的类型的观察者将在 MainActor 上运行，并且可以指定其他的隔离上下文。

提案还介绍了如何在 NotificationCenter.Message 与现有的 Notification 类型之间进行转换，例如通过定义 makeMessage(_:) 方法将通知转换为 NotificationCenter.Message，或通过 makeNotification(_:) 方法将 NotificationCenter.Message 转换为现有的 Notification 类型，以支持现有的 Objective-C 代码中的观察者。

提案的一个示例展示了如何将现有的 NSWorkspace.willLaunchApplicationNotification 通知适配为使用 NotificationCenter.Message，并展示了如何在客户端代码中观察和发布这样的通知。

该提案不仅增强了类型安全性和并发支持，还通过平滑的过渡路径确保了与现有代码库的兼容性。

2) 讨论[真实应用中的 Swift 并发](https://forums.swift.org/t/swift-concurrency-in-real-apps/73790 "真实应用中的 Swift 并发")
**内容大概**
在实际应用中使用 Swift 并发可能会带来一些复杂性和挑战。作者分享了一个自定义 NSTableColumn 的代码示例，该示例使用图片而不是字符串作为列头。在实现过程中，作者遇到了与 Swift 并发相关的问题，特别是在 Xcode 16 beta 5 中，某些以前可行的方法突然失效了。

代码示例如下：
```Swift
final class LockTableColumn: NSTableColumn {
    lazy private var _headerCell: NSTableHeaderCell? = nil

    override var headerCell: NSTableHeaderCell {
        get {
            if _headerCell != nil { 
               return _headerCell 
            }

            _headerCell = super.headerCell // 保留父类提供的默认样式
            if let image = NSImage(systemSymbolName: "lock.fill", accessibilityDescription: nil) {
                image.size = CGSize(width: 14, height: 14)
                Task { @MainActor [_headerCell] in
                    _headerCell!.image = image
                 }
            }
            return _headerCell
        }
        set {
            // 空操作
        }
    }
}
```
作者提到，NSTableColumn 并没有被标记为可发送（sendable），而 NSCell 则被绑定到 MainActor 上，这使得这两者的结合使用变得困难。特别是，当尝试在代码中使用 Task { @MainActor in } 来设置图片属性时，编译器会抛出错误，提示任务或 actor 隔离值无法发送。为了解决这个问题，作者必须使用捕获列表 [ _headerCell ]，但这一点并不直观，特别是对于初学者来说。

作者还指出，Swift 并发的严格性导致了一些简单任务的实现变得异常复杂，并质疑当前 Swift 并发的成熟度和苹果框架的准备情况。不断变化的开发环境（如 beta 版本之间的差异）进一步增加了学习和采用 Swift 并发的难度。

此外，作者讨论了在大型、旧项目中使用 Swift 并发的挑战，特别是在尝试迁移到 Swift 6 时遇到的困难。虽然迁移可能是一个长期的过程，但作者认为，尽早采用新特性比等待其完全成熟更为可取。

总之，尽管 Swift 并发在理论上提供了更好的安全性，但在实践中，它可能会增加开发的复杂性，特别是在现有代码库中。

3) 提议[未实现函数的占位符](https://forums.swift.org/t/pitch-a-placeholder-for-unimplemented-functions/73624 "未实现函数的占位符")
**内容大概**
讨论了对未实现函数的占位符进行改进的提案。提案的核心思想是引入一种新的语法，用于明确标记未实现的函数或方法。这种语法将帮助开发者在编写和维护代码时更清楚地识别出哪些部分尚未完成，从而减少遗漏和错误。

提案中提出了以下几个关键点：

1. 建议添加一个新的关键字或标记，来表示一个函数或方法尚未实现。这种标记可以使代码在编译时产生警告或错误，提醒开发者注意未完成的部分。

2. 通过这种标记，开发者可以在代码中添加详细的注释或文档，说明该函数将来会实现的功能。这有助于团队成员之间的沟通，并且在代码审查过程中提供更多的信息。

3. 提案中提供了几个具体的语法示例，展示如何使用这种新语法标记和处理未实现的功能。这些示例展示了不同情况下的用法，并说明了这种方法如何提高代码的可读性和可维护性。

总的来说，这项提案旨在提高代码的清晰度和可靠性，帮助开发者更有效地管理未实现的功能。

4) 讨论[测试基于闭包的异步 API](https://forums.swift.org/t/testing-closure-based-asynchronous-apis/73705 "测试基于闭包的异步 API")
**内容大概**
在XCTest中，当设置一个非零超时时间时，fulfillment(of:timeout:) API 会旋转运行循环并等待最长指定时间，直到XCTestExpectation被满足。相对而言，Swift Testing中的confirmation() API不会等待，它要求Confirmation在闭包返回之前得到确认。

在实际应用中，start()函数创建了一个无结构的Task，但没有等待其值，这意味着当start()返回时，任务中的异步操作可能尚未完成。为了解决这个问题，可以修改代码，让start()函数返回一个Task，并在confirmation()闭包中等待该任务完成。具体做法是：
```Swift
@MainActor
@discardableResult
func start() -> Task<...> {
    Task {
        // 异步操作
    }
}
```
然后在confirmation闭包中等待任务完成：
```Swift
await confirmation { confirmed in
    env.analytics.trackEventMock.whenCalled { _ in
        confirmed()
    }
    let startingTask = await sut.start()
    await startingTask.value
}
```
虽然这种方法在理论上可行，但实际应用中受到限制，特别是当需要创建与并发模型无关的ViewModel时。在这种情况下，ViewModel通常具有一个同步接口，并且只从视图层访问。视图通过该接口向ViewModel发送信号，ViewModel启动一个Task，或者在旧代码中使用Combine或传统的闭包API。当异步操作完成时，ViewModel会更新状态并通过@Published属性或Observation框架将其传递到视图层。

由于Swift Testing的确认机制无法正常工作，这使得采用该框架变得困难。工程师们可能只能在新项目中使用该框架，而不能在现有项目中轻松集成。

5) 讨论[ShapedArray 中 4D 及更高维度的下标](https://forums.swift.org/t/subscript-for-4d-and-higher-dimensions-in-a-shapedarray/73735 "ShapedArray 中 4D 及更高维度的下标")
**内容大概**
讨论中，有关`ShapedArray`的子脚本功能的扩展请求涉及了几个关键方面：

1. 当前，`ShapedArray`可以处理一维、二维和三维数组的索引和子脚本操作。这意味着对于这些维度的数据，用户可以通过索引轻松地访问和修改元素。然而，对于四维及更高维度的数组，现有的`ShapedArray`实现尚不支持直接的子脚本操作。

2. 用户希望能够对更高维度的数组进行类似的一维、二维、三维数组那样的子脚本操作。这种需求通常来源于需要处理复杂的数据结构，如多维矩阵或张量，这在科学计算、机器学习和图像处理等领域非常常见。

3. 讨论中建议通过扩展`ShapedArray`的子脚本功能，允许对四维及更高维度的数组进行直观的访问。例如，能够通过多个索引进行访问，如`array[x][y][z][w]`，其中每个索引对应数组的不同维度。这将使得操作这些复杂数据结构变得更加简洁和高效。

4. 扩展子脚本功能以支持更高维度数组面临一些技术挑战，包括：
   - API设计: 需要设计一个易于理解和使用的API，同时支持灵活的维度访问。
   - 性能考虑: 高维数组的操作可能会涉及大量数据，如何优化性能以确保高效的访问和操作是一个重要问题。
   - 兼容性: 确保新的功能不会破坏现有的`ShapedArray`实现，并且能够与现有代码库兼容。

综上所述，扩展`ShapedArray`以支持四维及更高维度的子脚本操作被认为是一个有价值的改进，能够显著提升处理复杂数据结构的灵活性和效率。然而，实施这一改进需要解决若干技术挑战，并考虑如何设计一个用户友好的API。

## 推荐博文


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
