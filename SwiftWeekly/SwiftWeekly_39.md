## 前言

**本期是 Swift 编辑组整理周报的第三十九期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

梦想之所以遥不可及，是因为今天的你和昨天一样，并没有拉近与梦想的距离。**Swift社区**陪你努力每一天，一同迈向象牙塔！👊👊👊

> **周报精选**
>
> 新闻和社区：卖不动了 iPhone 在美国市场销量或陷入停滞
> 
> 提案：在导入声明上使用访问级别修饰符
> 
> Swift 论坛：讨论从头开始的基本 HTTP 客户端
>
> 推荐博文：用示例解释了 Swift 中的值和类型参数包
>
> **话题讨论：** 
> 
> 如果公司允许远程办公但要降薪，薪资降多少可以接受？

**上期话题结果**

![](https://files.mdnice.com/user/17787/4e9ccec8-5750-40b8-9a4d-93d52d0260b5.jpg)

这个投票结果反映了人们在度过假期时的不同偏好，有些人喜欢冒险和旅行，有些人更愿意宅在家里，而还有一些人则追求休闲和享受。

## 新闻和社区

### 卖不动了 iPhone 在美国市场销量或陷入停滞

10 月 8 日消息，作为苹果公司总部的所在地，iPhone 在美国当地市场的销量一直是很可观的。之前就有报告披露 iPhone 在美国市场有 1.67 亿用户，要比安卓系统用户的 1.44 亿高出 2300 万。

不仅如此，美洲市场向来也是苹果主要的营收来源，常年在占据在 40% 左右。苹果的财报显示，在截至 7 月 1 日的 2023 财年第三财季，营收的 817.97 亿美元美洲市场贡献了 353.83 亿美元，远高于欧洲等市场。而在第二财季 948.36 亿美元的营收中，美洲市场则是贡献了 377.84 亿美元。

但是这一情况或将在明年有所改变，根据 Business Insider（BI）的第三轮专项年度调查数据显示。由于经济形势的不确定以及手机更新周期延长，在美国市场许多用户将会继续使用老款手机而不是升级到 iPhone 15，预计明年 iPhone 在美销量或将陷入停滞。

不过该调查还强调，虽然 iPhone 的销量会走低，但是苹果公司的营收仍有望增加。这主要还是因为消费者更偏向购买价格更高的 Pro Max 系列，这也在一定程度上保证在面临销量压力时能保持较高收入水平。

此外调查还发现，决定转用安卓系统的用户占比远高于转用苹果的用户，也有很多用户表示计划减少 iCloud 和 Apple TV+ 等增值服务。

据多家投行预测，iPhone 15 的出货量将在 7000 万到 8000 万部之间，低于去年同期的 iPhone 14 的 9000 万部以上。而根据 IDC 最新发布的数据，2023 年全球智能手机出货量预计同比减少 4.7% 至 11.5 亿部，创十年来新低。（来源：快科技）

### 与 Apple 专家会面交流

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/053312EB-FF8B-40A6-A4D9-DCFE9BC7A628/2048.jpeg)

欢迎参加为全球开发者量身打造的各种讲座、咨询、实验室等，与我们一起探索相关问题。

Apple 开发者活动为处于开发之旅各个阶段的人士打造，全年以线上和线下的形式在世界各地举行。无论你是希望提升现有的 App 或游戏、完善设计还是启动新项目，总有活动适合你。

申请设计一对一咨询，2023 年 10 月 16 日 上午 10:00 – 下午 5:00 (GMT+8) ，30 分钟线上咨询，地点：Shanghai，与 Apple 专家远程交流，共同探索如何设计美观易用的出色 App。在时长 25 分钟的线上咨询中，你可以征询关于最新 UI/UX 设计原理、最佳实践、设计模式等方面的建议。活动语言为普通话。

App 曝光度和营销入门，2023 年 10 月 31 日 中午 11:00 – 中午 12:00 (GMT+8) ，线上讲座，地点：Beijing，在这个线上讲座中，了解如何提高你的 App 在 App Store 上的曝光度。探索人们如何在 App Store 上查找 App，了解优秀产品页应包含的要素，并学习如何提升 App 的曝光度。我们还将探讨搜索功能、推荐流量的作用以及可带来更多下载次数的推广功能。活动语言为普通话。

Apple Vision Pro 开发者实验室 - 上海，2023 年 10 月 31 日 上午 9:30 – 2023 年 11 月 2 日 下午 5:00 (GMT+8)，线下讲座，地点：上海设计开发加速器。参加为期一天的开发者实验室，体验在 Apple Vision Pro 上运行的 visionOS、iPadOS 或 iOS App。你将能够在 Apple 的帮助下测试、细化并优化你的 App 和游戏，让它们在无边的空间画布中提供卓越的体验。由于场地有限，我们会审核每个请求，然后你会收到一封告知申请状态的电子邮件。请务必详细回答所有必填问题。

## 提案

### 通过的提案

[SE-0409](https://github.com/apple/swift-evolution/blob/main/proposals/0409-access-level-on-imports.md "SE-0409") **在导入声明上使用访问级别修饰符** 提案通过审查。该提案已在 **三十八期周报** 正在审查的提案模块做了详细介绍。

[SE-0408](https://github.com/apple/swift-evolution/blob/main/proposals/0408-pack-iteration.md "SE-0408") **包迭代** 提案通过审查。该提案已在 **三十七期周报** 正在审查的提案模块做了详细介绍。

## Swift论坛

1) 讨论[Emitting 模块花费的时间是 XCode 15.1 beta 的 25 倍](https://forums.swift.org/t/emitting-module-takes-25x-the-time-in-xcode-15-1-beta/67671 "Emitting 模块花费的时间是 XCode 15.1 beta 的 25 倍")

XCode 15.0 ( Swift 5.9.0.128.108 ) 和 XCode 15.1 Beta ( Swift 5.9.2.1.6 ) 之间的构建“发出模块”阶段似乎存在一些退化。

我的 XCWorkspace 中有几个不同的框架和应用程序。 在 15.1 beta 中，大多数编译速度都差不多，或者稍快一些。 然而，我们拥有的一个框架的时间似乎是以前的 10 倍以上。 当在 Xcode 时间线中查看时，几乎所有时间都花在“Emitting Module”阶段。 

在干净的构建中，时间从约 56 秒缩短到约 1440 秒。 另外，有些文件的编译速度似乎确实慢了一些，但这是一个很大的瓶颈，除了当时的“发射模块”之外，时间线中没有其他真正发生的事情。 

如果我当时观看 Activity Monitor，我的 CPU 的 swift-frontend 进程在此期间将保持在 100%。 但除此之外似乎没有什么可疑的。 比较输出，框架的大小几乎相同，我没有看到任何其他真正值得注意的东西。

关于什么会导致这种巨大差异有什么想法吗？

**回答**

我刚刚发现并修复了 39 个案例，当模块中包含大量 Swift 文件时，我们会看到这种情况发生。 （大量宏展开也可能发生）。对于我们看到回归的项目，“发射模块”阶段从 300 秒下降到 32 秒。

它很可能与您所看到的相同。 如果您能够捕获一个旋转转储，我们可以使用旋转转储来验证这一点，或者如果您想尝试的话，我们可以启动工具链构建。

[编辑：对于那些好奇的人来说，编译器有一个线性时间算法，可以从源位置的内部表示映射到该位置所在的源文件。 该算法“永远”是线性时间的，但最近的错误修复将其置于热路径中。 解决方法是将其转换为具有单元素最近使用的缓存的对数算法。]

2) 讨论[状态检查：Int128 和 UInt128](https://forums.swift.org/t/status-check-int128-uint128/67694 "状态检查：Int128 和 UInt128")

Swift 标准库实际上包含 Int128 和 UInt128，它们只是没有作为公共 API 公开。 它们是作为 SE-0329 的先决条件添加的：时钟、即时和持续时间。 他们在公共 API 中的明显缺席甚至在该提案的[第三次]审查期间被提出，但因超出范围而被推迟。 多年来，一直有人对它们提出要求，甚至可以追溯到这些论坛存在之前。

swift-numerics（本质上）拥有自己的 128 位整数重新实现，现在基金会也正在考虑添加自己的。

更不用说各种第 3 方包，以及其他 Swift 库和程序中这些类型的大量私有重新实现。

复制粘贴扩散这样一个基本的数字类型似乎有点愚蠢，当它已经在标准库中时，只需要发布它即可。 不过，我怀疑这已经是实现这一目标的目标，所以我希望问题只是：预计到达时间？

**回答**

需要明确的是：Foundation 库不考虑添加自己的。 他们建议使用 Numerics 现有的 DoubleWidth 测试支持来进行测试。 我们很快就会为 stdlib 推荐 Int128，但即使它可用，由于可用性限制（至少在中期），Foundation 和 Numerics 仍应使用双宽度类型进行测试。 所以无论如何，这都是正确的前进道路。

3) 讨论[我是否必须手动检查宏参数是否为文字？](https://forums.swift.org/t/do-i-have-to-manually-check-macro-parameters-to-be-literals/67687 "我是否必须手动检查宏参数是否为文字？")

在做了一些实验来了解如何开发一个真正的宏之后，我遇到了一个问题：我试图开发一个 `@AddCompletionHandler` 宏（如 WWDC 演讲中提到的那样），并且我尝试将完成参数名称传递为 宏的参数：

```Swift
@attached(peer, names: overloaded)
public macro AddCompletionHandler(completionName: String = "onCompletion") = #externalMacro(...)
```

我应该得到一个字符串，我将使用它来构建要添加到函数签名的新参数：

```Swift
let completionParameter: FunctionParameterSyntax = "\(raw: completionParameterName): @escaping (\(returnType)) -> Void"
```

并在新生成的函数块内调用完成：

```Swift
let newCode: CodeBlockItemListSyntax = """
    Task.detached {
        await \(raw: completionParameterName)(\(functionDeclaration.wrappedInvocation))
    }
    """
```

这样做的问题是宏声明接受任何返回字符串的表达式，因此您可以像这样调用它：

```Swift
@AddCompletionHandler(completionName: "on" + "Completion")
```

我发现自己手动检查 AttributeSyntax 树是否包含一个名为completionName 的参数，该表达式的类型为 `StringLiteralExprSyntax`，只有一个段，最后提取该值作为该唯一段的 `.content.text`。 如果这些步骤中的任何一个失败，我都会发出一条诊断消息，要求该值是一个文字。

这是应该如何工作的吗？ 对于看似常见的用例来说，这似乎是一个极其繁琐的过程。 我在这里错过了什么吗？

**回答**

这是实现它的一种迂回方式，但您可以执行以下操作：

定义符合 `ExpressibleByStringLiteral` 的自定义类型，并使用该类型作为宏的参数而不是 String。 用户仍然可以将字符串文字直接传递给宏调用，但他们无法执行任何接近但不是文字的操作，例如 “hello”+“world”。

但是，这仍然会让有人这样做，这是你不希望的，因为你无法评估 x：

```Swift
let x: YourCustomType = "onCompletion"
@AddCompletionHandler(completionName: x)
```

因此，下一个技巧是，当您在自定义类型中实现 init(stringLiteral:) 时，只需将其设置为 fatalError() 即可。 这将阻止任何人尝试创建它的实例并将其存储在某个地方。 但该类型在宏使用中仍然有效，因为在宏调用中使用宏时，该类型实际上并不调用 init(stringLiteral:) 。 它所要做的就是类型检查它是否有效，确实如此。 （如果有人确实尝试在某处创建显式实例，则直到运行时才会捕获该错误。）

使这变得更容易的是某种参数必须为常量的功能，这些功能之前已经在这些论坛上讨论过。

仅当用户尝试直接实例化新类型时才会发生运行时错误，否则除了在宏签名中命名之外，该新类型对他们是隐藏的。 将其命名为 `CompletionHandlerNameLiteral` 之类的名称，这样就不会混淆其用途。

没有编译时失败被转移到运行时，因为它严格阻止了编译器以前允许的使用：现在编译器不再允许像“hello”+“world”这样的表达式并要求宏检查它，而是 编译器会停止它，宏不再需要检查它。

这不是一个完美的解决方案，但我可以理解，用户并不都希望为“这是一个文字吗”之类的事情编写相同的检查，因此最好让编译器在可能的情况下为您完成工作。 在缺乏 const-value 强制功能的情况下，SwiftSyntax 将成为此类辅助 API 的良好家园，至少可以减轻负担。

4) 讨论[从头开始的基本 HTTP 客户端](https://forums.swift.org/t/swift-runtime-unable-to-suspend-thread-when-compiling-in-qemu/67676 "从头开始的基本 HTTP 客户端")

我想使用 Swift 从头开始创建基本的 HTTP 客户端，以达到学习目的，以了解互联网上 http 的发送者和接收者是如何工作的。 这只是出于原始学习目的，所以我只想使用套接字。 现在我正在本地主机中尝试，我在SO 1中发布了相同的内容。我尝试了下面的代码:

```Swift
import Foundation
import Darwin

final class Client {
    
    let host: String
    let port: UInt16
    
    init(host: String, port: UInt16) {
        
        self.host = host
        self.port = port
    }
    
    func get(_ completionHandler: @escaping() -> Void) {
        
        // Create a socket
        let sock = socket(AF_INET, SOCK_STREAM, 0)
 
        var serveraddr = sockaddr_in()
        serveraddr.sin_family = sa_family_t(AF_INET)
        serveraddr.sin_port = self.port
        serveraddr.sin_addr.s_addr = inet_addr(self.host)

        // Connect to the server
          
        print("Connecting....")
        
        withUnsafePointer(to: &serveraddr) { sockaddrInPtr in
          
            let sockaddrPtr = UnsafeRawPointer(sockaddrInPtr).assumingMemoryBound(to: sockaddr.self)
            let connection = connect(sock, sockaddrPtr, socklen_t(MemoryLayout<sockaddr_in>.size))
             
            if connection == 0 {
                
                // Form an HTTP GET request
                let request = "GET / HTTP/1.1\r\nHost: \(self.host)\r\n\r\n"
                let bytes = [UInt8](request.data(using: .utf8)!)

                // Send the request over the socket
                send(sock, bytes, request.count, 0)

                /*
                // Receive and print the response
                var response = [UInt8](repeating: 0, count: 1024)
                let bytesRead = recv(sock, &response, response.count, 0)
                if bytesRead > 0 {
                    if let httpResponse = String(bytes: response, encoding: .utf8) {
                        print(httpResponse)
                    }
                }

                // Close the socket
                close(sock)
                 */
                
            } else {
                
                print("not connected \(connection)")
            }
        }
    }
}
```

使用：

```Swift
let client: Client = .init(host: "127.0.0.1", port: 8080)
client.get {
                
     print("GET request successfully executed!")
}
```

我使用 python3 -m http.server 8080 作为包含一些文件的文件夹上的测试服务器。 它适用于浏览器和邮递员 GET 请求。

但问题是 cleint 退出，打印未连接 -1

我该如何解决此问题并成功请求？

**回答**

从 Swift 正确使用 BSD 套接字是一个严峻的挑战。 我自己在这个问题上反复讨论了很多次，最终选择了从 [Swift 调用 BSD 套接字中所示的方法](https://developer.apple.com/forums/thread/734124 "Swift 调用 BSD 套接字中所示的方法")。 正如那篇顶级文章中所解释的，这并不适用于生产代码，而是适用于我们在这里讨论的测试项目。

至于您是否应该使用 BSD 套接字，这是我在 TN3151 [选择正确的网络 API](https://developer.apple.com/documentation/technotes/tn3151-choosing-the-right-networking-api "选择正确的网络 API") 中介绍的内容。

哦，实现一个正确的 HTTP 客户端非常困难，即使您将自己限制为 HTTP/1.1 而没有 HTTPS。 因此，虽然为这样的测试项目编写自己的 HTTP 代码很好，但如果您打算部署它，我建议您使用现有的 HTTP 库。
需要明确的是，ATS 仅适用于 URLSession 及以上版本。 低级 API，如网络框架和 BSD 套接字，只是忽略 ATS。

应用程序沙箱适用于所有网络连接，因此这是正确的举措（-：

5) 讨论[不同平台不同的宏实现](https://forums.swift.org/t/different-macro-implementation-for-different-platforms/67693 "不同平台不同的宏实现")

我正在尝试创建一个宏，允许我在资源包中按名称引用颜色。

例如，能够执行以下操作：

```Swift
let myColor = #color("MyColor")
```

在 macOS 上，我希望将其为：

```Swift
"NSColor(named: \(argument)) ?? NSColor.clear"
```

在 iOS 上，我希望它是：

```Swift
"UIColor(named: \(argument))"
```

我写了以下宏：

```Swift
public struct ColorMacro: ExpressionMacro {
    public static func expansion(of node: some FreestandingMacroExpansionSyntax, in context: some MacroExpansionContext) throws -> ExprSyntax {
        guard let argument = node.argumentList.first?.expression else {
            throw MacroError.invalidArguments
        }

#if canImport(AppKit)
        return "NSColor(named: \(argument)) ?? NSColor.clear"
#elseif canImport(UIKit)
        return "UIColor(named: \(argument))"
#else
        #error("Unsupported platform")
#endif
    }
}
```

和

```Swift
#if canImport(AppKit)
import AppKit

@freestanding(expression)
public macro color(_ named: String) -> NSColor = #externalMacro(module: "SwatchbookMacrosMacros", type: "ColorMacro")
#elseif canImport(UIKit)
import UIKit

@freestanding(expression)
public macro color(_ named: String) -> UIColor = #externalMacro(module: "SwatchbookMacrosMacros", type: "ColorMacro")
#endif
```
在为 macOS 构建时效果很好，但在为 iOS 构建的目标中使用时，它似乎仍在尝试使用 AppKit 分支并引用 NSColor。

难道我做错了什么？ 是否使用正在构建的平台来确定可用性，而不是目标平台？

**回答**

这里的问题是 #if 块是 IfConfigDeclSyntax，而不是表达式。 不过，您可以将整个事情包装在立即执行的闭包中，使其成为一个表达式：

```Swift
return """
  {
    #if canImport(AppKit)
      NSColor(named: \(argument)) ?? NSColor.clear
    #elseif canImport(UIKit)
      UIColor(named: \(argument))
    #else
      #error("Unsupported platform")
    #endif
  }()
  """
```

但如果您打算执行所有这些操作，那么在宏的库目标中创建一个辅助函数并调用它可能会更干净、更简单：

```Swift
func __colorHelper(_ name: String) {
  #if canImport(AppKit)
    NSColor(named: name) ?? NSColor.clear
  #elseif canImport(UIKit)
    UIColor(named: name)
  #else
    #error("Unsupported platform")
  #endif
}
```

并让您的宏实现调用该函数：

```Swift
return """
  YourModuleName.__colorHelper(\(argument))
  """
```

## 推荐博文

[Swift 5.9 中的调试改进](https://www.swift.org/blog/whats-new-swift-debugging-5.9/ "Swift 5.9 中的调试改进")

**摘要：**  本篇官方文章介绍了 Swift 5.9 在编译器和 LLDB 调试器中引入了许多新的调试功能。以下是三个改变，可以帮助你在日常调试工作中更加便捷。首先，通过使用快捷命令别名 p 和 po 进行变量检查可以更快速地进行操作。

其次，LLDB 的 dwim-print 命令提供了更加用户友好的方式来打印变量。而且，在 Swift 5.9中，使用 p 命令不再会创建像 $R0 这样的持久结果变量，这些变量常常在调试会话中未被使用。最后， LLDB 现在支持在表达式评估中使用泛型类型参数，这使得在调试过程中能更好地区分不同的变量。Swift 5.9 还引入了更精确的词法作用域信息，使得调试器能够更好地区分不同的变量。

[用示例解释了 Swift 中的值和类型参数包](https://www.avanderlee.com/swift/value-and-type-parameter-packs/ "用示例解释了 Swift 中的值和类型参数包")

**摘要：**  本文介绍了 Swift 中的值和类型参数包，并结合示例进行了详细解释。类型参数包和值参数包允许你编写一个接受任意数量具有不同类型参数的通用函数。在 Swift 5.9 中，由于 SE-393、SE-398 和SE-399 的提案，这一新特性得以实现。

采用参数包的最显著影响之一是在 SwiftUI 中的10个视图限制已经不存在，这是由于在这些提案之后可实现了可变参数泛型。本文还解释了参数包的解决方案，它们帮助我们编写可重用的代码，避免编写大量的函数重载。从 Swift 5.9 开始，我们可以使用参数包重写类似的函数。本文末尾总结了参数包的优势，并提供了进一步学习 Swift 的资源链接。

[SwiftData 中的并发编程](https://juejin.cn/post/7288178532861886504/ "SwiftData 中的并发编程")

**摘要：** 该文主要介绍了货拉拉 iOS 用户端在 Crash 治理方面的经验和技术方案。文章探讨了 iOS 平台下 Crash 监控方案的优缺点，并分享了自建 Crash 监控平台的思路和经验。

随后，总结了 Crash 治理的思路和经验，包括分级治理、版本追踪、定期分析和团队合作。最后，文章分享了常见的 Crash 类型及其解决方案，并总结了长期 Crash 治理的经验和收益。

## 话题讨论

**如果公司允许远程办公但要降薪，薪资降多少可以接受？**

1. 10%以下
2. 25%以下
3. 50% 以下
4. 保持，不接受降薪
5. 应该加薪，工作量增加

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
