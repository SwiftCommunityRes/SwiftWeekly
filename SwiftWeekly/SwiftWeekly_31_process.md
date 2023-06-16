## 前言

**本期是 Swift 编辑组自主整理周报的第二十二期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

若目标远大，就要有大动作。若追求卓越，便须有大改变。**Swift社区**已整装待发，你要不要一起呢？👊👊👊

> **周报精选**
>
> 新闻和社区：Apple Vision Pro 和 visionOS 撼世登场
> 
> 提案：
> 
> Swift 论坛：
>
> **话题讨论：** 
> 
> 有博主在视频社交平台说，2023年已然迎来了经济危机，只是有些人不愿意相信而已，那么你认为国内2023年是否真的进入了经济危机？

>**上期话题结果**

## 新闻和社区

### 注册 WWDC23 实验室和活动

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/1AC9D4F4-43B5-4913-B149-B0486FFE64FE/2048.jpeg)

通过在线实验室和活动这种绝佳方式，你可以在一整周内与 Apple 工程师、设计师和专家进行交流沟通。

一对一实验室
从开发的基础知识到复杂概念，你都可以在这里获得个性化指导。了解如何运用全新 Apple 技术、探索 UI 设计原则、优化产品在 App Store 上的形象，以及更多主题。

活动
每日都有许多精彩的活动在 Slack 中展开。

在 Q&A 中就工程和设计主题提问。
在大家一起观看讲座视频期间加入或关注实时对话，并与演讲者进行 Q&A。
在社区暖场活动中了解其他开发者和 Apple 团队。
体验最新的框架，尝试各种设计理念，并在学习区分享你的创作。
在 6 月 6 日，与业内的佼佼者比试一下专业知识问答。
实验室和活动对 Apple Developer Program 和 Apple Developer Enterprise Program 的所有成员，以及 2023 Swift Student Challenge 参赛者开放。

### Apple Vision Pro 和 visionOS 撼世登场

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/213FE0A2-813D-404D-B093-D766AC8D7AF3/2048.jpeg)

Apple Vision Pro 是一款革命性的空间计算设备，可实现数字化内容与真实世界的无缝融合，让用户在沉浸于当下的同时还能与他人沟通交流。在 Apple Vision Pro 中，各种 App 将突破传统显示器的束缚限制，拥有一幅无边的画布。此外，Apple Vision Pro 还推出了一个全三维用户界面，而控制这个界面，仅需要用户的眼睛、双手和语音 — 最自然、最直观的输入工具。Apple Vision Pro 搭载了全球首个空间操作系统 visionOS，让用户能够以一种绝妙的方式与数字化内容互动，如同它们真的存在于现实世界之中。Apple Vision Pro 采用了突破性设计：在显示方面，采用超高分辨率显示屏系统，两块显示屏的总像素为 2,300 万；在性能方面，采用独特的双芯片设计并搭载定制的 Apple 芯片，确保每一刻的体验都真实无比，让人沉浸当下。

探索丰富实用的资源，助你通过一种全新而又熟悉的方式将空间计算方面的创意变为现实，打造出能够重新定义沟通、效率和娱乐的 App。

### App Store 中新增的隐私功能

在 Apple，我们将隐私视作每个人的基本权利。因此，我们构建了许多功能来帮助用户了解开发者在隐私以及数据收集和共享方面的做法，让用户能够自主掌控他们的数据。通过 App 跟踪透明度 (ATT)，用户可以选择 App 是否有权跟踪用户在其他公司的 App 和网站内的活动，以便投放广告或者与数据代理商共享。借助隐私标签和 App 隐私报告，用户可以查看 App 收集哪些数据以及如何使用这些数据。

许多 App 会利用第三方软件开发工具包 (SDK)，这些工具包可以提供出色的功能，但可能会对 App 处理用户数据的方式产生影响。为了让开发者可以更轻松地打造出色的 App，同时告知用户数据使用情况并尊重他们在这方面做出的选择，我们推出了两项新功能。

首先，为了帮助开发者了解第三方 SDK 如何使用数据，我们推出了新的隐私清单。隐私清单是一份文件，会以单一标准格式概述 App 中第三方代码的隐私做法。当开发者准备分发他们的 App 时，Xcode 会将开发者使用的所有第三方 SDK 中的隐私清单合并为一个简单易用的报告。这个报告内容全面，总结了 App 中的所有第三方 SDK，使开发者能够更轻松地创建更准确的隐私标签。

此外，为了向用户提供额外的隐私保护，如果 App 引用的 API 可能会被用于指纹识别（在 App Store 中被禁止的一种做法），现在需要选择合理的原因来解释为什么使用此 API 并在隐私清单中声明已使用此 App。在这个过程中，App 必须准确描述其对于这些 API 的使用情况，并且只能出于隐私清单中所述的原因而使用这些 API。

第二，我们希望帮助开发者改善软件供应链的完整性。使用第三方 SDK 时，开发者可能很难知道他们下载的代码是不是由期望的开发者编写的。为了解决这个问题，我们推出了适用于 SDK 的签名功能，这样一来，当开发者在 App 中采用新版本的第三方 SDK 时，Xcode 将验证它是否由同一开发者签名。这个功能将对开发者和用户都十分有帮助。

我们将在今年晚些时候发布更多信息，包括：

影响隐私的 SDK 列表 (对用户隐私产生重大影响的第三方 SDK)
“需要指明原因”的 API 列表，使用它们时必须给出合理的原因
开发者反馈表，用于就调用涉及的 API 提出新的原因
其他文档，详细介绍签名和隐私清单、他们的优势以及何时需要使用它们

## 提案


## Swift论坛

1) 提议[SE-0400: Init Accessors](https://forums.swift.org/t/se-0400-init-accessors/65583 "SE-0400: Init Accessors")
[SE-0400](https://github.com/apple/swift-evolution/blob/main/proposals/0400-init-accessors.md)：Init Accessors 314 的审查从现在开始，一直持续到 2023 年 6 月 26 日。

2) 提议[改进提案模板以获得更好的功能实践](https://forums.swift.org/t/pitch-improve-the-proposal-template-for-better-feature-experimentation/65604 "改进提案模板以获得更好的功能实践")
**介绍**
强制性工具链和示例项目以及 Experiment It 部分将允许开发人员在提案审查期间更轻松地进行实验并参与讨论。

**动机**
试验正在审查的功能这是评估提案的重要方式，即使是写得很好和详细的提案也可以从让开发人员试验它中受益。 提案模板可以改进，使任何人在审查期间更容易试用提议的功能。

**建议的解决方案**
将以下标题字段添加到提案模板：工具链和示例项目以及新的 Experiment It 部分。

**工具链**
该字段应指向一个链接，从中可以下载一个 swift 工具链，其中该功能是在实验性标志下实现的。

目前大多数提案只提到主分支中有一个功能可用，尽管大多数时候该功能都在 Swift.org 上可用的开发快照中 - 下载 Swift 对于新手来说了解这一点并不是那么微不足道，有时还有一个提案审查期 甚至在没有工作快照的情况下启动。

该链接应该从第一天起就可用，并在审核期间尽可能更新。

一种可能性是在网站下载页面上添加一个额外的部分，其中包含专用于正在审查的提案的工具链，这可以允许工具链可用，即使由于某种原因它不能出现在主快照中也是如此。

3) 提问[为什么我只能将结构附加到数组一次？](https://forums.swift.org/t/why-can-i-only-append-a-struct-to-an-array-once/65601 "为什么我只能将结构附加到数组一次？")
我的应用程序的目标是提醒用户与他们亲近的人互动。 因此，我的应用程序主要使用两个结构体，称为 Relation（代表一个人）和 Interaction（代表与人的一次交互）。

我构建了一个名为“NewInteractionSheet”的工作表，其目标是向关系的交互数组之一添加一个新的交互。

在添加交互时，此工作表非常有效。 但是，由于某种原因，它只能工作一次。 为什么要这样做？ 这就是我想要弄清楚的。
这是“NewInteractionSheet.swift”代码的一部分：
```Swift
import PhotosUI
import CoreLocation
import MapKit

struct NewInteractionSheet: View {
    @Binding var isPresentingNewInteractionView: Bool
    @Binding var relations: [Relation]
    
    @State private var newInteraction = Interaction.emptyInteraction
    @State private var relation: Relation = Relation.emptyRelation
    @State private var isPresentingLocationPicker: Bool = false
        
    var body: some View {
        NavigationView {
            Form {
                
                Section("You interacted with...") {
                    RelationPicker(relations: $relations, relation: $relation)
                }
                
                Section("Interaction details") {
                    InteractionDatePicker(dateToSet: $newInteraction.date)
                    
                    TypePicker(typeToSet: $newInteraction.type)
                    
                    DurationPicker(shouldShow: newInteraction.type.hasDuration,
                                   hoursToSet: $newInteraction.durationHours,
                                   minutesToSet: $newInteraction.durationMinutes)
                    
                    SummaryTextField(summaryToSet: $newInteraction.summary)
                    
                    LocationPicker(shouldShow: newInteraction.type.hasLocation,
                                   coordinatesToSet: $newInteraction.location.coordinates,
                                   locationNameToSet: $newInteraction.location.name,
                                   isPresentingLocationPicker: $isPresentingLocationPicker)
                    
                    InteractionPhotosPicker(images: $newInteraction.pictures)
                }
            }
            .toolbar {
                ToolbarItem(placement: .cancellationAction) {
                    Button("Dismiss") {
                        isPresentingNewInteractionView = false
                    }
                }
                ToolbarItem(placement: .confirmationAction) {
                    Button("Add") {
                        if let index = relations.firstIndex(where: { $0.id == relation.id }) {
                            print("\nBefore appending to relations")
                            print(relations[index])
                            print(newInteraction)
                            relations[index].interactions.append(newInteraction)
                            print("\nAfter having appended to relations")
                            print(relations[index])
                            print(newInteraction)
                        }
                        isPresentingNewInteractionView = false
                        
                        //AJOUTER LA PLANIFICATION D'UNE NOTIFICATION
                    }
                }
            }
            .navigationTitle("New interaction")
        }
    }
}
```
正如在代码中看到的，我包含了三个“打印”指令来帮助我调试它。 当我尝试添加两个交互时，以下是控制台中打印的内容：
```Swift
Before appending to relations
Relation(id: EA18AAD4-E576-49A9-90BF-CC58C5000ECE, firstName: "Johanna", lastName: "Duby", photo: nil, interactions: [], contactFrequency: 1814400.0, birthday: Optional(2023-06-15 14:34:40 +0000), notes: "", theme: Relations.Theme.blue, reminders: nil)

Interaction(id: 106CD832-1949-4800-AC75-E21B8890E580, date: 2023-06-15 14:34:43 +0000, type: Relations.InteractionType.audioCall, durationHours: 0, durationMinutes: 0, summary: "", location: Relations.Location(name: "", coordinates: nil), pictures: [])


After having appended to relations
Relation(id: EA18AAD4-E576-49A9-90BF-CC58C5000ECE, firstName: "Johanna", lastName: "Duby", photo: nil, interactions: [Relations.Interaction(id: 106CD832-1949-4800-AC75-E21B8890E580, date: 2023-06-15 14:34:43 +0000, type: Relations.InteractionType.audioCall, durationHours: 0, durationMinutes: 0, summary: "", location: Relations.Location(name: "", coordinates: nil), pictures: [])], contactFrequency: 1814400.0, birthday: Optional(2023-06-15 14:34:40 +0000), notes: "", theme: Relations.Theme.blue, reminders: nil)

Interaction(id: 106CD832-1949-4800-AC75-E21B8890E580, date: 2023-06-15 14:34:43 +0000, type: Relations.InteractionType.audioCall, durationHours: 0, durationMinutes: 0, summary: "", location: Relations.Location(name: "", coordinates: nil), pictures: [])

Before appending to relations
Relation(id: 8D3D2012-D8A2-4092-B1A9-D476F7E05B9A, firstName: "Nastassja", lastName: "Ferrari", photo: nil, interactions: [], contactFrequency: 1209600.0, birthday: nil, notes: "", theme: Relations.Theme.green, reminders: nil)

Interaction(id: 5C4EE2E1-7D2D-4E32-BC00-FCA781EC8C20, date: 2023-06-15 14:34:49 +0000, type: Relations.InteractionType.audioCall, durationHours: 0, durationMinutes: 0, summary: "", location: Relations.Location(name: "", coordinates: nil), pictures: [])


After having appended to relations
Relation(id: 8D3D2012-D8A2-4092-B1A9-D476F7E05B9A, firstName: "Nastassja", lastName: "Ferrari", photo: nil, interactions: [], contactFrequency: 1209600.0, birthday: nil, notes: "", theme: Relations.Theme.green, reminders: nil)

Interaction(id: 5C4EE2E1-7D2D-4E32-BC00-FCA781EC8C20, date: 2023-06-15 14:34:49 +0000, type: Relations.InteractionType.audioCall, durationHours: 0, durationMinutes: 0, summary: "", location: Relations.Location(name: "", coordinates: nil), pictures: [])
```

4) 提问[Swift 5.9 是否支持嵌套/递归宏？](https://forums.swift.org/t/are-nested-recursive-macros-supported-in-swift-5-9/65569 "Swift 5.9 是否支持嵌套/递归宏？")

5) 提问[如何引用不同模块中的文章？](https://forums.swift.org/t/how-to-reference-an-article-in-a-different-module/65581 "如何引用不同模块中的文章？")
查看 DocC 代码链接的语法，似乎我们有办法引用同一模块中的文章：
<doc:GettingStarted>
但是我们不能使用前导斜杠语法来指定模块相对路径，因为它已经被 tutorials 命名空间占用：
<doc:/tutorials/SlothCreator>
如何引用来自不同模块的文章？
回答：
库存 DocC 尚不支持外部 - 或者更具体地说，尚未提供公共解决方案。 早期的 DocC 代码中有一些关于允许某些过程的外部引用解析器的位，@ronnqvist 一直在研究更新的解决方案（“分层解析器”）——但我只关注了一些 PR（最近的一个 提取了很多旧代码：通过 d-ronnqvist 添加成功解析的外部引用到参考索引, [Pull Request #582](https://github.com/apple/swift-docc/pull/582)）

6) 提问[Macros包会嵌入到App中吗？](https://forums.swift.org/t/se-0400-init-accessors/65583 "Macros包会嵌入到App中吗？")
例如，当我使用 #stringify Swift 宏在我的应用程序中生成代码时，它会在编译期间用新代码替换我的一些源代码。 那么这个宏包会随我的应用程序一起提供吗？ 或者它只是在编译期间发生
回答：替换发生在编译时。 宏目标不应链接到应用该目标中包含的宏的代码。

7) 提问[哪个 Apple Networking Api 用于 UDP 多播和单播？](https://forums.swift.org/t/se-0400-init-accessors/65583 "哪个 Apple Networking Api 用于 UDP 多播和单播？")
一般而言，iOS 开发和网络的新手。 开发一个游戏节目类型的应用程序，其中“主机”设备需要多播到“参赛者”设备。 参赛者设备也需要能够响应。 实际上传递的信息很少，但速度很重要，因此使用 UDP。 我一直在研究苹果设备的一些常用网络 api：network.framework、CocoaAsyncSocket、Multipeer-Connectivity、BSD 套接字等。总的来说，我倾向于只使用高级 network.framework 但缺乏 示例和资源使决策变得困难。 任何意见，将不胜感激。
回答：[TN3151: Choosing the right networking API](https://developer.apple.com/documentation/technotes/tn3151-choosing-the-right-networking-api)

## 推荐博文

[ Swift OpenAPI Generator 的介绍](https://www.swift.org/blog/introducing-swift-openapi-generator/ " Swift OpenAPI Generator 的介绍")

**摘要：** Swift OpenAPI Generator是一个 SwiftPM 插件，它可以生成客户端代码或服务器端代码，以便处理 HTTP 调用。 OpenAPI 是一种用于记录HTTP服务的规范，可以使用YAML或JSON编写，并可被工具读取，以帮助自动化工作流程，例如生成必要的代码以发送和接收HTTP请求。Swift OpenAPI Generator 可以帮助我们通过 OpenAPI 文档描述HTTP请求和响应的结构，包括 HTTP 方法、 URL 路径和查询参数、HTTP状态码和内容类型，使用 JSON Schema 描述响应体的结构，使得我们能够在开发应用程序时生成网络代码，而不需要手动编写和维护网络代码，专注于核心业务逻辑。要使用 Swift OpenAPI Generator 插件，需要添加 SwiftPM 依赖项以及运行时库和传输实现，然后使用生成的API客户端或服务器端存根。 Swift OpenAPI Generator 支持大多数常用特性，但仍有一些特性需要实现，项目跟踪进展情况可以使用 GitHub issues 

[ Swift 宏：使用新的表达方式扩展 Swift](https://www.avanderlee.com/swift/macros/ " Swift 宏：使用新的表达方式扩展 Swift")

**摘要：**  Swift 宏是在 Swift 5.9发布的一项新功能，它允许你通过自定义编译时检查和生成新的代码，在编译时将它们写入到你的文件中，从而消除冗余的样板代码。本文讲解了宏的工作原理、如何编写自定义宏以及如何进行测试，以验证一个允许在编译时验证 URL 并在 URL 有效时返回解包值的宏的例子。本文还讨论了宏的不同角色，包括独立和附加宏，并解释了为什么你可能考虑在代码中使用宏。

[在 Swift 服务器端 Vapor 和客户端应用之间共享 Swift 代码](https://www.avanderlee.com/swift/share-swift-code-swift-on-server-vapor/ "在 Swift 服务器端 Vapor 和客户端应用之间共享 Swift 代码")

**摘要：** 这篇博客讨论了在客户端应用和后端服务器之间共享 Swift 代码的好处以及如何通过 Swift 包和 Vapor 实现这一目标。通过共享模型和端点定义，您可以确保两个侧面都使用相同的层，避免出现意料之外的请求失败。博客提供了定义软件包结构、暴露模型、共享端点定义和在后端软件包中配置端点的代码示例。此外，它提供了一个通用方法，用于请求端点并在客户端应用中使用它们。作者还提到了优化适用于所有支持的 HTTP 方法的代码的重要性。

## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
