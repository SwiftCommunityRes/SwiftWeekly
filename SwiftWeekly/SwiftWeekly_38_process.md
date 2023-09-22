## 前言

**本期是 Swift 编辑组整理周报的第三十八期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

三餐四季，春夏秋冬，平凡如尔，与众不同。**Swift社区**陪你苦尽甘来，笑看山河星月！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果自研调制解调器芯片受挫：速度太慢容易过热，落后高通3年
> 
> 提案：
> 
> Swift 论坛：
>
> 推荐博文：
>
> **话题讨论：** 
> 
> HUAWEI Mate 60 Pro 和 iPhone 15 你会如何选择？

**上期话题结果**

![](https://files.mdnice.com/user/17787/dc237f3b-c4d9-405f-96ef-1e913c5cfed3.jpg)

这个结果反映了人们对核污水排放问题的担忧，以及对个人健康和环境保护的重视。

## 新闻和社区

### 苹果自研调制解调器芯片受挫：速度太慢容易过热，落后高通3年

去年底的测试发现，苹果自研的调制解调器芯片速度太慢且容易过热，电路板尺寸太大，占据半个 iPhone 的面积，无法使用。这些芯片基本上比高通最好的调制解调器芯片落后 3 年。

熟悉该项目的苹果前工程师和高管透露，由于技术挑战、沟通不畅，以及高层对尝试设计芯片而不是购买芯片是否明智的问题存在分歧，苹果调制解调器芯片的工程团队工作进展缓慢，且设定了不切实际的目标。

![](https://d.ifengimg.com/w1125_q90_webp/x0.ifengimg.com/res/2023/D3966516AE536448301F83F355C2A452F896CC5C_size627_w2000_h1200.jpg)

苹果硬件技术高级副总裁约翰尼·斯鲁吉（Johny Srouji）领导了芯片研发。

据苹果公司前工程师和高管透露，该公司原计划将其自研调制解调器芯片用在最新的 iPhone 机型中，但去年年底的测试发现，该芯片速度太慢且容易过热，电路板尺寸太大，占据半个 iPhone 的面积，无法使用。

调制解调器芯片的作用是连接手机与无线运营商，iPhone 目前依赖高通公司生产的调制解调器芯片。本月上旬，高通宣布将苹果的采购合同延长 3 年，业界推测苹果自主研发调制解调器芯片的计划遇到挫折。

2018 年，苹果首席执行官蒂姆·库克（Tim Cook）下达设计和制造调制解调器芯片的命令，并招聘数千名工程师。目标是切断苹果对高通的依赖。据估计，去年苹果已向高通支付了超过 72 亿美元芯片采购费用。在 2017 年的诉讼中，苹果指控高通对其专利使用费收取过高费用。

熟悉该项目的苹果前工程师和高管告诉《华尔街日报》，由于技术挑战、沟通不畅，以及高层对尝试设计芯片而不是购买芯片是否明智的问题存在分歧，苹果调制解调器芯片的工程团队工作进展缓慢。团队被孤立在美国和国外的不同小组中，没有全球领导者。一些高管不鼓励工程师传播有关延误或挫折的坏消息，从而导致设定不切实际的目标和最后期限。

苹果在十多年前就致力于生产用于其产品的各种芯片。2010 年 1 月，苹果创始人史蒂夫·乔布斯在第一代 iPad 发布会上低调展示了自研的 A4 芯片，这枚 45nm 制程的芯片由三星代工，一开始并不被业界看好。一年之后，苹果在 iPhone 4S 发布会上展示了第二代芯片 A5，性能提升巨大。此后，苹果构建了由 A 系列（手机和平板）、M 系列（桌面电脑）、H 系列（耳机）、S 系列（手表）等多个产品线的芯片家族。特别是在 2020 年，苹果用 M1 芯片替代 Mac 电脑中使用多年的英特尔处理器芯片，震动了市场。今年 9 月发布的 iPhone 15 Pro 系列更是搭载了全球首款 3nm 工艺制程芯片—— A17 Pro。

### App Store 现已接受适用于最新版操作系统的 App 和游戏提交

iOS 17、iPadOS 17、macOS Sonoma、Apple tvOS 17 和 watchOS 10 即将面向全球用户推出。使用发布候选版 Xcode 15 和最新 SDK 构建你的 App 和游戏，通过 TestFlight 进行测试，然后提交到 App Store 以供审核。现在，你可以着手从 Xcode Cloud 将你的 App 和游戏无缝部署到 TestFlight 和 App Store。借助激动人心的新功能，以及针对各种语言、框架、工具和服务的重大改进，你可以在 Apple 平台上提供更加独特的体验。

Xcode 和 Swift：Xcode 15 提供增强的代码补齐功能、交互式预览和实时动画，可让你更快地推进 App 的编码和设计。Swift 通过引入宏解锁了多个新的 API 类型，不但表现力强，且直观易用。全新的 SwiftData 框架使用声明式代码，可轻松保留数据。SwiftUI 还支持使用相位和关键帧创建更复杂的动画，并通过新的 Observation 框架简化数据流。

小组件和实时活动：小组件现在支持交互操作，并且可以在新的位置运行，例如 iPhone 上的待机界面、iPad 上的锁定屏幕、Mac 上的桌面以及 Apple Watch 上的智能叠放。借助 SwiftUI，系统会根据情境调整小组件的颜色和间距，从而提高它在各个平台中的实用性。通过 WidgetKit 和 ActivityKit 构建的实时活动现已在 iPad 上推出，以帮助用户实时了解 App 中正在发生的事情。

Metal：借助新的游戏移植工具包，可以比以往更轻松地将游戏移植到 Mac，Metal 着色器转换器大大简化了游戏着色器和图形代码的转换过程。借助最新的光线追踪更新，可将你的游戏和产品渲染器扩展到更逼真、更细腻的场景。此外还能利用许多其他增强功能，在 Apple 芯片上更轻松地提供精彩的游戏和专业 App。

App 快捷指令：如果你适配了 App 快捷指令，App 的主要功能会自动出现在聚焦中，方便用户快速访问 App 中最重要的视图和操作。新的设计让 App 快捷指令的运行变得更加容易，新的自然语言功能让用户能够更加灵活地用自己的声音来执行你的快捷指令。

App Store：借助 StoreKit 中的全新 SwiftUI 视图，你现在可以更轻松地在所有平台上推销 App 内购买项目和订阅。利用 Xcode 中的 StoreKit 测试、Apple 沙盒环境以及 TestFlight 的最新增强功能，你还可以对更多产品内容进行测试。通过按地区预购功能，你可以在新地区提供 App 并设置不同的发布日期，让用户更期待你的 App 发布。App Store 提供极为灵活且个性化的 App 发现体验，根据用户的兴趣和偏好提供量身定制的推荐内容，帮助他们找到更多出色的 App。

## 提案


## Swift论坛
1) 讨论[结构和类型（以前是匿名联合类型）](https://forums.swift.org/t/structural-sum-types-used-to-be-anonymous-union-types/67432 "结构和类型（以前是匿名联合类型）")
从状态检查中衍生出一个关于匿名联合类型主题的新讨论[线程：类型抛出](https://forums.swift.org/t/status-check-typed-throws/66637)。

关于这个主题的衍生讨论是围绕这个[评论](https://forums.swift.org/t/status-check-typed-throws/66637/100)开始的。

类型化抛出就像类一样，是静态类型信息的重要载体。 您所说的相当于说“不应允许类实例在弹性库中具有特定的类类型，而应始终为 AnyObject”。 这显然是非常错误的。 不小心将自己锁定在特定错误类型中，然后在主要版本发布后后悔的可能性不是语言问题，而是工程无能问题。 作者应该采取预防措施，在设计错误类型时考虑到未来的扩展（例如，具有可选元数据的结构而不是裸枚举）。

当我们谈论这个话题时：

匿名联合类型 (A | B) 也是如此，它们只不过是某些通用枚举周围的语法糖（例如 Either<A, B>）。 这不是什么新鲜事，Swift 已经完全能够表达这种类型，因此我不断听到的“由于编译器复杂性而经常被拒绝的提案”显然也是非常错误的。

**结论：**

类型系统必须具有工程师认为合适的表达能力，以使他们的代码具有表达能力。 仅仅因为有人想不出保留静态类型信息的理由（通过使用特定的错误类型或使用匿名联合类型），并不意味着没有理由。

2) Swift使用[推出 Swift SDK 生成器](https://forums.swift.org/t/announcing-swift-sdk-generator/67409 "推出 Swift SDK 生成器")
我们很高兴地宣布推出新的[开源实用程序](https://github.com/apple/swift-sdk-generator)，它可以简化 Swift 包的交叉编译！

使用 Xcode 时，许多 Swift 开发人员每天都会使用从 macOS 到其他 Darwin 平台的交叉编译。 与此同时，使用命令行开发工具对 Linux 和 Swift 支持的其他平台进行交叉编译并不那么容易设置。 通过 SE-0387 35，我们希望缩小这一差距，并使交叉编译成为 SwiftPM 命令行界面中的一流功能。

虽然 [SE-0387](https://github.com/apple/swift-evolution/blob/main/proposals/0387-cross-compilation-destinations.md) 指定了 Swift SDK 捆绑包的格式和文件系统布局，但它没有规定如何生成这些捆绑包。 我们提供了此类生成器的参考实现，它支持 macOS 作为主机平台和一些主要的 Linux 发行版作为目标平台。

区分 Swift SDK 作者和 Swift SDK 用户非常重要。 新的 Swift SDK Generator 应主要由 Swift SDK 作者使用，他们可以根据自己的需求对其进行自定义并发布自己的 Swift SDK 捆绑包。 反过来，Swift SDK 用户可以依赖 Swift 5.9 中引入的 swift Experimental-sdk 命令来安装 Swift SDK 作者之前生成的捆绑包。

我们正在努力增加对 Swift 项目正式支持的所有 Linux 发行版的支持。 一如既往，欢迎所有贡献！

3) 讨论[Swift 测试的新方法](https://forums.swift.org/t/a-new-approach-to-testing-in-swift/67425 "Swift 测试的新方法")
大家好，

我很高兴地宣布一个新的开源项目，旨在探索 Swift 测试体验的改进。 我和我的同事 @briancroom、@grynspan、@chefski、@Dennis 和我最近几个月一直在致力于此工作，并取得了一些早期进展，我们很高兴与大家分享。

受到 Swift 宏的启发，我们构建了一个测试库 API，它可以：

使用名为 @Test 的附加宏提供有关各个测试的详细信息。 这使得许多新功能成为可能，例如表达需求、传递参数或添加自定义标签，所有这些都直接在代码中而不是单独的配置文件中实现。
使用拼写为 #expect(...) 的表达式宏，通过详细且可操作的故障信息验证测试中的预期条件。 它通过自动捕获传入表达式的值及其源代码来通知失败消息，并且比专门的断言函数更容易学习，因为它接受内置运算符表达式，如 #expect(a == b)。
通过向函数添加参数并在 @Test 属性中指定其参数，可以使用不同的输入轻松重复测试多次。
这是一个示例：它显示了一个测试函数，使用 @Test 表示，其中包含两个特征：自定义显示名称和决定测试是否应运行的条件。 该测试创建一辆食品卡车，在其中存放食物，然后使用 #expect 检查食物数量是否等于我们期望的值：
```Swift
@Test("The Food Truck has enough burritos",
      .enabled(if: FoodTruck.isAvailable))
func foodAvailable() async throws {
    let foodTruck = FoodTruck()
    try await foodTruck.stock(.burrito, quanity: 15)
    #expect(foodTruck.quantity(of: .burrito) == 20)
}
```
如果上述测试失败，#expect 将捕获数量(of: .burrito) 等子表达式的值以及源代码文本。 这允许在输出中包含丰富的诊断信息：
```Swift
✘ Test "The Food Truck has enough burritos" recorded an issue at FoodTruckTests.swift:8:6:
Expectation failed: (foodTruck.quantity(of: .burrito) → 15) == 20
```
使用这种方法，使用不同的输入多次重复测试（称为参数化测试 15）也很简单。 @Test 属性可以包含参数，并且该函数将被重复调用并传递每个参数：
```Swift
@Test(arguments: [Food.burrito, .taco, .iceCream])
func foodAvailable(food: Food) {
    let foodTruck = FoodTruck()
    #expect(foodTruck.quantity(of: food) == 0)
}
```
[Swift 测试的新 API 方向](https://github.com/apple/swift-testing/blob/main/Documentation/Vision.md)深入探讨了我们的愿景，描述了项目的目标，并展示了我们提出的方法的更多示例。

这些想法已在名为 [swift-testing](https://github.com/apple/swift-testing) 的新包中原型化，该包目前被认为是实验性的，尚未推荐用于一般生产用途。 如果您感兴趣，我们鼓励您克隆它，探索它的实现，并尝试使用它为您的项目编写测试。 有关说明，请参阅入门。
4) 讨论[VSCode 5.9：停止服务器失败](https://forums.swift.org/t/vscode-with-5-9-stopping-server-failed/67397 "VSCode 5.9：停止服务器失败")
自从升级到 5.9 以来，VSCode 上的 sourcekit-lsp 变得更加不稳定，我不断收到“客户端 SourceKit 语言服务器：与服务器的连接出错。 关闭服务器。” 问题，它打印的唯一日志输出是：
```
[Error - 4:44:34 PM] Stopping server failed
  Message: Cannot call write after a stream was destroyed
  Code: -32099
```
我相信，这是应该解决该问题的 PR：[Don’t crash when unregistering for change notifications of a file that isn’t watched by ahoppen · Pull Request #828 · apple/sourcekit-lsp · GitHub](https://github.com/apple/sourcekit-lsp/pull/828)

5) 讨论[对于传递到异步作用域函数的闭包来说，Sendable 是否是必需的？](https://forums.swift.org/t/is-sendable-necessary-for-closures-passed-into-asynchronous-scope-functions/67403 "对于传递到异步作用域函数的闭包来说，Sendable 是否是必需的？")
我一直在思考以下函数代码。
```Swift
public extension Database {
    func transaction<T>(_ closure: @Sendable @escaping (Database) async throws -> T) async throws -> T {
        try await self.transaction { db -> EventLoopFuture<T> in
            let promise = self.eventLoop.makePromise(of: T.self)
            promise.completeWithTask{ try await closure(db) }
            return promise.futureResult
        }.get()
    }
}
```
这是来自 Vapor 框架的实际代码。
以下是供参考的网址：https://github.com/vapor/ Fluent-kit/blob/main/Sources/FluentKit/Concurrency/Database%2BConcurrency.swift 1

在这个事务函数中，参数闭包具有@Sendable和@escaping属性。
我想知道是否可以将两者删除。

特别是，@Sendable 属性意味着传递给闭包的类型必须是 Sendable，
这施加了相当严格的限制。
因此，如果我们可以省略它，那就方便多了。

我认为它可以被删除的原因是，
虽然这个闭包确实被传递到事件循环线程，
当它离开交易功能时，
它正在等待 EventLoopFuture.get(),
确保闭包的函数调用完成。

换句话说，两个不同线程不可能同时调用闭包。

确实，理论上由于 eventLoop 类型被抽象为任何 EventLoop，
实现一种将传递给completeWithTask的闭包存储到全局变量或类似的东西中的方法是可能的，
但这对于 EventLoop 和 EventLoopFuture 来说显然是不自然的行为，我认为没有什么可担心的。

此外，我认为出于同样的原因可以消除@escaping。 闭包实际上并没有逃脱。

上面的想法可能是对的吗？
我很想听听有更多见解的人的想法来权衡。

作为参考，具体实现如下：
```Swift
public extension Database {
    func transaction<T>(_ closure: (any Database) async throws -> T) async throws -> T {
        try await withoutActuallyEscaping(closure) { (closure) in
            let closureBox = UncheckedSendableBox(closure)
            return try await self.transaction { db -> EventLoopFuture<T> in
                let dbBox = UncheckedSendableBox(db)
                let promise = self.eventLoop.makePromise(of: T.self)
                promise.completeWithTask {
                    let db = dbBox.value
                    let closure = closureBox.value
                    return try await closure(db)
                }
                return promise.futureResult
            }.get()
        }
    }
}
```
我相信这个想法可以推广。
我将这些接受值并允许使用闭包进行灵活处理的函数称为作用域函数。
这样的作用域函数确实可以是异步的，但是，即使它们是异步的，
在我看来，只要作用域函数中的闭包执行是串行完成的，
它们不一定必须是@Sendable 或@escaping。

您对此有何看法？

**回答**
这个问题很好理解，但解决方案不是放弃当前语言中的 Sendable 要求，而是让编译器可以推断出根本不需要它。 请参阅 [Pitch 跨隔离域安全发送非“可发送”值](https://forums.swift.org/t/pitch-safely-sending-non-sendable-values-across-isolation-domains/66566)，了解编译器如何增强此功能的示例。

我同意你的观点，只要我们排除异步代码中不安全的行为，这种使用模式可能是安全的，但此时我仍然不愿意删除注释。

6) 讨论[编写 TCP 客户端应用程序的推荐方法是什么？](https://forums.swift.org/t/whats-the-recommended-way-to-write-a-tcp-client-application/67433 "编写 TCP 客户端应用程序的推荐方法是什么？")
我需要为 TCP/IP 上的自定义专有协议编写一个客户端。 我希望它能够在 macOS、iOS 和 Linux 上使用。 推荐的方法是什么？

我有一组现有的 Objective-C 代码来执行此操作，并且我只使用原始 BSD 套接字。 它们很简单，并且由于不需要是高性能服务器，所以我非常乐意阻塞：我只需将代码粘贴在 NSOperation 中，在串行 NSOperationQueue 上运行它，并使用回调来传递结果。 在 Swift 中使用 BSD 套接字感觉就像我在与该语言作斗争：很多都陷入了 UnsafePointer 领域。

我查看了 Mojave 和 Swift-NIO 中引入的网络框架，但在这两种情况下，我真的不确定如何构建客户端。 我需要做很多来回操作：向事物发送命令，读回响应，发送下一个命令，读取响应等。通过单个通道读取处理程序（在 Swift-NIO 的情况下）感觉所有内容， 再次，就像我做错事一样。

有谁知道 Swift-NIO 类似的来回通信示例吗？ 或者我看错了方向？

**回答**
自从我上次查看我的代码以来已经过去很长时间了，我确信自那时起 API 已经发生了很大的变化，但对我帮助最大的是查看 Java 的 Netty 文档。 Swift-NIO 现在似乎有相当好的文档，所以我会先阅读一下。

同样，它已经很老了，而且事情可能已经发生了变化，但这里有一个简单的示例，说明 Swift-NIO 客户端和处理程序类如何[协同工作](https://github.com/jonathanwong/TCPClient/tree/master/Sources/TCPClient)。 这个默认实现会让您遇到您提到的确切问题，但是如果您在 TCP 客户端类之外声明通道、处理程序、事件循环等，您可以处理处理程序类中发生的更改，例如断开连接或接收消息， 在客户端类的其他方法中。 我不确定这是否是“正确”的处理方式，但它足以让它在我正在构建的应用程序中顺利运行。

您可能会考虑由 IBM 开发并在 macOS、iOS 和 Linux 上运行的 BlueSocket。

我向这个库添加了对 Windows 的支持，并以 GreenSocket 的名称提供。

BlueSocket 此处（macOS、iOS、Linux）：
https://github.com/Kitura/BlueSocket
https://github.com/litewrap/GreenSocket


7) 讨论[协议扩展可以定义类 API 覆盖吗？](https://forums.swift.org/t/can-protocol-extension-define-class-api-overrides/67404/3 "协议扩展可以定义类 API 覆盖吗？")
我有几个符合协议的 UIViewController 子类（它们不共享相同的父类）。 我想添加几个 UIViewController API 重写的默认实现，以避免在每个子类中重写它们。 无论如何要让这项工作成功吗？
```Swift
protocol StylingController {
        
}

extension StylingController where Self: UIViewController {
    
    override func viewDidAppear(_ animated: Bool) {
        super.viewDidAppear(animated)
        
        becomeFirstResponder()
    }
    
    override func viewDidDisappear(_ animated: Bool) {
        super.viewDidDisappear(animated)
        
        resignFirstResponder()
    }
    
}
```
**回答**
在这种情况下，只需创建两个父类而不是一个：一个基于 UIViewController，另一个基于 UITableViewController。 如果有很多重叠的功能，并且您希望它尽可能DRY，您可以进一步将通用功能提取到协议扩展中：
```Swift
class BaseViewController: UIViewController, CommonVCFunctionality {
    override func viewDidAppear(_ animated: Bool) {
        super.viewDidAppear(animated)
        commonVCFunctionality()
    }
}

class BaseTableViewController: UITableViewController, CommonVCFunctionality {
    override func viewDidAppear(_ animated: Bool) {
        super.viewDidAppear(animated)
        commonVCFunctionality()
    }
}

protocol CommonVCFunctionality: AnyObject {
    func commonVCFunctionality()
}

extension CommonVCFunctionality {
    func commonVCFunctionality() { ... }
}
```

## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
