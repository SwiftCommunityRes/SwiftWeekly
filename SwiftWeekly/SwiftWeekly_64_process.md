## 前言

**本期是 Swift 编辑组自主整理周报的第五十期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

间歇性的努力和蒙混过日子，都是对之前努力的清零。时间永不停歇，社会时刻发展，**Swift社区**也在华丽蜕变！👊👊👊

> **周报精选**
>
> 新闻和社区：
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


## 提案


## Swift论坛
1) 讨论[在所有平台上改进加密](https://forums.swift.org/t/improving-crypto-on-all-platforms/75330 "在所有平台上改进加密")
**内容大概**
首先澄清一下：本文并非要批评 Swift Crypto，而是希望引发讨论并提供一些建设性的反馈。

Swift Crypto 推出之前，非 Apple 平台上的加密方案极为麻烦。要么依赖系统提供的 OpenSSL（还得确保正确版本且不会被突然更新），并使用复杂的编译器标志；要么自己构建 LibreSSL 等库，承担编译时间的代价。没有一个统一推荐的选项，最终往往是混合使用，导致编译时间极长。

如今的情况有所改善，大多数生态系统中的库都已使用 Swift Crypto，并且随着 Crypto Extras 的加入，许多库可以切换到一个加密库上，享受其带来的好处。

然而，Swift Crypto 似乎受到作为客户端库的限制，并被 Apple 平台的开发速度拖累，这在服务器领域显得格格不入。一些简单功能（例如 Sendability 注解）尚未实现（问题提出已有一年半之久），而 Apple 服务需要的 API（如 Sign in with Apple 和 PassKit）因平台限制无法添加。

此外，Apple 平台有 OS 优化实现，其他平台却各自为战，进一步加强了 Swift 在 Apple 和非 Apple 平台间的不平等感。Swift 作为跨平台语言，应该提供在所有平台上统一的加密库。

其他问题还包括 Crypto Extras API 的可发现性、文档不全，以及 CryptoKit 的实现细节，这些都是使用体验上的小痛点。本周，遇到一个客户在实现 Cloudfront 3 的签名时，因为不知 RSA 操作存在于 CryptoExtras 中而受阻。

提议以下讨论阶段：

	1.	将 _CryptoExtras 重命名为 CryptoExtras ——下划线表示 API 不稳定且可能变化。应为新 API 设定一个明确的标准，支持被广泛使用的 API。
	2.	降低向 CryptoExtras 添加新 API 的门槛 ——历史上，即便是添加 API 到 CryptoExtras 也门槛很高，导致许多现有于 BoringSSL 的 API 没有暴露，因为其不提供版本保证。
	3.	将 CryptoExtras 整合到 Crypto 中 ——库的分离让人困惑，不清楚没有 iOS 经验的用户应使用哪个 API。这可以通过改进文档来解决，但这仍然是个麻烦。
	4.	与 CryptoKit 脱钩 ——尽管它对生态系统贡献很大，但越来越多问题涌现。理想情况下不再提供 RSA API，因为它不安全且不应再使用。然而服务器上仍需要此类 API。脱离 CryptoKit 的限制将允许更快的开发、改进的 API 和更好的生态系统。对于仅构建 Apple 平台的用户可以使用 CryptoKit，而构建跨平台库和应用的用户则使用 Swift Crypto，使其成为 Swiftlang 下的标准库。

希望看到第 1 和 2 点在不久的将来得到解决，尽管第 3 和 4 点可能不会很快变动。希望其他人也能提供他们的看法和观点，补充可能忽略的细节。

Swift.org 的 Packages Community Showcase 提名

在使用 swift-crypto 时有相似的体验，并能感受到许多相同的困扰。

希望第 1 和 2 点能尽早得到解决，并不期望第 3 和 4 点能迅速改进，但希望有更多人能参与讨论并提出他们的观点和见解。

为了使这些讨论有效，需要在讨论中加入资金方面的考虑。花了大量时间考虑生态系统的不足，感觉大家已经对缺失的内容及改进需求有了很大的共识。

限制是人力——如今整个服务器生态系统几乎全部由无偿志愿者维护，他们每周抽出一点时间来维持项目正常运转。这些人中有很多希望能获得资源，以便兼职甚至全职投入到这些项目中。

提一个稍微激进的建议：Apple 应开始为库维护者提供资助，让他们可以兼职维护这些库。当然，Apple 是否对此感兴趣尚不确定——也欢迎对替代资金来源的建议。但在没有讨论最重要的成功要素——资金的情况下，谈论短期内解决这些问题是不现实的。

2) 讨论[包访问级别反馈](https://forums.swift.org/t/feedback-on-package-access-level/75415 "包访问级别反馈")
**内容大概**
这个项目是一个包含多个库和一套应用程序的系统。这些应用程序是部署在一组管理设备上的专用应用程序，同时们希望将部分技术作为SDK发布。目标是保持SDK库和内部应用程序之间的实现细节共享，而不需要对外公开API。此外，们希望尽量减少开发环境的改变，保持工作流程的简便性。

反馈1：包级访问控制效果良好

使用package访问控制来替代public效果非常好。它可以在模块之间共享实现细节，而不需要对外部SDK客户公开。在代码中，可以像这样定义包内部访问：
```Swift
public struct Country {
  package init(rawISOCode: String)
}
```
这种方式避免了以往需要大量使用#if条件编译的复杂情况，简化了工作流程。建议，即使你没有类似的需求，也可以考虑使用package来定义包内部接口，而不是默认使用public。

反馈2：类的使用存在问题

包级别访问控制在类的使用上存在局限。package类无法在声明包的其他模块中被继承。虽然协议没有这个限制，但对于需要继承的类，必须将其声明为open，这会导致该类变成public，从而对外做出不必要的API承诺。

结论

总体来说，对package访问控制非常满意，但在类的继承上还有改进空间。建议Swift社区考虑为包内部的类继承提供更多支持。

3) 提议[引入 do-let-catch 实现更清晰的错误处理](https://forums.swift.org/t/pitch-introducing-do-let-catch-for-cleaner-error-handling/75348 "引入 do-let-catch 实现更清晰的错误处理")
**内容大概**
个人认为，try ... catch并不比guard ... else的差异大多少，实际上你的提议要求catch跳出当前作用域，这与guard ... else的语义类似：
```Swift
enum RequestError: Error { case failedToLoadData(any Error) }
func test(request: URLRequest) async throws {
    let data: Data
    let response: URLResponse
    do {
       (data, response) = try await URLSession.shared.data(for: request)
    } catch {
        print("trust me, I handled it") // 这里不抛出 RequestError.failedToLoadData(error)
    }
    print(data, response) // 编译错误：常量 `data` 在初始化之前被使用
}
```
并不完全赞成你的请求。实际上，可以使用现有语法完成大部分需求，如果剩下的10%确实必要（认为不必要），那么可能最简单的路径会是这样。但也不推荐这样做，在catch块中隐式绑定错误可能是个错误决定，但目前就是这样。

建议考虑你真正想要实现的目标，以及将错误包装成另一种包含原错误的错误类型是否真的帮助实现该目标。

从的角度来看，有以下几种可能性：

	1.	处理某一特定类型的错误，例如不良的HTTPS证书。在这种情况下，do / catch的语法糖可能不是限制因素。
	2.	处理一类通用错误，例如CouldNotLoadData。在这种情况下，你可能并不关心错误是否因为DNS配置错误或用户断开了Wi-Fi，这时try?可能是最简单的选择。
	3.	处理特定类型的错误，但不想在此处处理：这种情况下，你可以将函数标记为throws并使用try，这相当于guard ... else { throw(error) }。
	4.	上述几种情况的组合，但在实践中这种情况较少。一个可能的场景是有两个HTTP请求（例如一个用于获取会话令牌，另一个用于运行RPC调用），如果不能在本地处理错误，可能希望对request1Failed(with: baseError)和request2Failed(with: otherbaseError)有不同的处理规则。在这种情况下，do / catch几乎肯定是你需要的。

实际中，可能需要原始错误信息以便记录日志或展示给用户，这种情况下，实现起来确实不够方便，因为上述情景都不是真正的“处理”错误。

并不是要争论想写的代码是否对所有人都适用。每个人对错误处理有不同的看法，这完全没问题。有自己的编码风格，深受Swift设计的影响，能让写出认为既聪明又可维护的代码，并提供详细的错误信息，这在长期内减少了维护问题。

Swift 6中引入的类型化throws是一个重大改进。它终于允许明确指定在特定API（例如网络调用）中可能发生的错误类型，以便针对不同的失败原因进行相应处理。的代码示例展示了网络调用可能失败的方式之一，希望返回一个特定的RequestError（枚举类型）。由于网络调用可能因多种原因失败，希望确保这些细节能被传递，以便的错误处理代码（位于其他地方）能够更细致地管理常见的失败情况。

遇到这种语法，它让想起了if-else的情景，而guard-let增强了代码的写法和可读性，提升了语言的清晰度。很感谢反馈，但当别人建议“可能想做”的事情或说的请求“不是绝对必要”时，这些反馈帮助不大。这确实是用例的必要需求，至少还有16人同意的看法（基于该帖子中的点赞）。并不是每个人都需要使用语言中的每个特性，这没问题。但语言应当足够灵活，能满足不同需求。如果某个特性对你而言并非必要，你可以不使用它——但这并不意味着它对他人没有价值。

4) 讨论[Swift 中Class的回归：为什么我们需要虚拟、抽象和受保护](https://forums.swift.org/t/the-resurgence-of-classes-in-swift-why-we-need-virtual-abstract-and-protected/75395 "Swift 中类的回归：为什么我们需要虚拟、抽象和受保护")
**内容大概**
近年来，Swift 社区经历了令人惊叹的演变。早期，许多人认为类最终可能会完全被结构体和协议所取代。然而，随着 Swift 语言的成熟，类在现代 Swift 开发中仍然扮演着至关重要的角色。从 @Observable 等强大特性到 SwiftData 等框架，类仍然是构建稳健、灵活应用的核心部分。

今天，我想再次提出一种方法，通过引入 virtual、abstract 和 protected 关键词来进一步增强基于类的开发。这些概念对于其他面向对象语言的开发人员来说很熟悉，我相信它们可以为 Swift 语言带来显著的价值。

引言

在 Swift 的早期，人们普遍认为类将被结构体和协议所取代。这一想法得到了 Swift 对安全性、不可变性以及避免引用类型常见问题（如 ARC 相关的内存管理问题）的重视的支持。使用值类型（结构体）和行为契约（协议）来模拟大多数行为类型似乎是一条很有前途的路径，许多开发人员转向了以协议为导向的设计。

然而，随着 Swift 生态系统的成熟，我们逐渐意识到类不仅仍然相关，而且在许多现代 Swift 应用程序中不可或缺。Apple 平台的一些核心功能（如 @Observable、Core Data 和 SwiftData）依赖于类及其继承机制。类在引用语义、共享状态以及子类化的灵活性方面具有不可替代的作用。

鉴于此，我建议重新审视一些与继承和封装相关的核心概念，建议引入三个在许多其他语言中常见的重要面向对象特性：virtual、abstract 和 protected。

关于 virtual 的必要性

在面向对象编程中，virtual 关键字用于显式标记可以在子类中被重写的方法。这将向开发人员清楚地表明方法是为了在子类中重写的，而不是简单地依赖默认继承，避免了误解或意外行为。

Apple SDK 中的实际示例：

	•	UIViewController 的 viewWillAppear(_:) 方法：通常重写该方法以自定义视图出现前的行为。如果有 virtual 关键字，可以明确表明允许重写，从而区分设计为可定制的方法和不应重写的方法。
	•	UIView 中的 layoutSubviews() 方法：子类经常重写此方法以定义自己的布局逻辑。如果将此方法标记为 virtual，就能明确布局定制的子类化意图。

关于 abstract 的必要性

抽象类或方法无法直接实例化，必须由子类重写或完成。Swift 目前缺乏一种正式的方式来声明这种意图。抽象类或方法将为 API 设计者提供一种更明确和结构化的继承层次。

Apple SDK 中的实际示例：

	•	UITableViewDataSource 和 UITableViewDelegate 协议：这些协议要求实现者定义某些方法（如 tableView(_:cellForRowAt:)）。尽管 Swift 使用了协议，但在类层次结构中应用抽象方法的概念，将有助于更清晰地区分子类必须实现的方法。
	•	NSDocument（AppKit）：在 macOS 开发中，NSDocument 常被子类化，其中 write(to:ofType:) 等方法需要自定义。如果这些方法是抽象的，任何 NSDocument 的子类都必须提供自己的数据序列化逻辑。

通过将某些类和方法显式声明为抽象，可以帮助开发人员避免混淆，并明确哪些 API 部分是可扩展的、哪些是供定制的。

关于 protected 的必要性

protected 方法和属性可以被子类重写或访问，但不能被这些子类的实例或其他外部代码访问。Swift 目前缺乏正式的 protected 访问控制级别，这将在设计大型框架或复杂继承层次时改善封装。此访问控制级别在 Java 和 C# 等语言中存在，提供了灵活性而不暴露类的内部工作。

Apple SDK 中的实际示例：

	•	UIView 中的 layoutSubviews() 方法：子类经常重写此方法，但不应由这些子类的用户直接调用。如果标记为 protected，它可以防止开发人员在子类之外误用它。
	•	UIView 和 NSView 中的 draw(:) 方法：自定义绘图逻辑通常通过重写 draw(:) 提供，但不应直接从类外调用。protected 将允许子类化定制，同时防止外部代码误用。
	•	UIResponder 中的 touchesBegan(_:with:) 方法：用于子类处理触摸事件，此方法标记为 protected 可以避免外部代码直接调用它。

为什么选择现在？

随着 Swift 社区的成长，我们对不同编程范式的平衡也有了更深入的理解。协议和结构体是非常强大的工具，但在许多领域（尤其是 Apple 自身的框架中）类是不可或缺的。

鉴于 Swift 的演变以及其在不同平台（iOS、macOS、服务端 Swift 等）上的应用范围的扩展，现在正是通过引入这些核心面向对象特性（virtual、abstract 和 protected）来丰富 Swift 类模型的绝佳时机。它们将为设计稳健、灵活且可维护的 API 提供明确性、清晰性和控制力。

Swift 一直致力于清晰性和安全性，引入这些关键字将继续推动语言在这些方面的进步。我们将保留语言当前的所有优势，同时在类的优势领域中拥抱其全部潜力。

总结

	•	virtual：为开发人员提供一种显式方式来标记在子类中预期重写的方法，避免混淆，使继承更具可预测性。
	•	abstract：清晰地定义不可实例化或直接使用的类和方法，子类必须实现这些方法。
	•	protected：提供更好的封装，允许方法和属性在子类中重写或访问，但不被外部代码访问。

这篇文章旨在通过 Apple SDK 的实际示例，将 Swift 的历史背景与实际需求联系起来，提出改善 Swift 继承模型的建议，通过引入这些特性来增强 Swift 的类模型。

5) 提议[建议在闭包中使用“safe”关键字来简化“weak”捕获模式](https://forums.swift.org/t/pitch-proposal-for-safe-keyword-in-closures-to-simplify-weak-capture-pattern/75374 "建议在闭包中使用“safe”关键字来简化“weak”捕获模式")
此提案建议在 Swift 的闭包语法中引入 safe 捕获类型，以简化常用的“弱引用 self”模式。在 Swift 闭包中，开发人员通常使用 [weak self] 将 self 弱引用捕获，并通过 guard let self 检查 self 是否已被释放。虽然这种模式有效地防止了循环引用，但在代码中频繁使用时会显得冗长和重复。

当前方法：
标准模式涉及将 self 弱引用捕获，然后在闭包中检查是否为 nil：
```Swift
class DataManager {
    private let service = NetworkService()
    private var data: [String] = []

    func fetchData() {
        service.fetch { [weak self] result in
            guard let self = self else { return }
            self.data = result
        }
    }
}
```
使用 safe 的提案改进：
提案引入了一个新的 safe 捕获类型，将 [weak self] 和 guard 语句替换为更简洁的语法：
```Swift
class DataManager {
    private let service = NetworkService()
    private var data: [String] = []

    func fetchData() {
        service.fetch { [safe self] result in
            self.data = result
        }
    }
```
通过 [safe self]，safe 关键字会自动处理弱引用或无主引用，使代码更加简洁。

优势：

	1.	提高可读性：safe 关键字省去反复书写 guard let self = self 的需求，使代码更简洁，易于阅读。
	2.	自动优化：safe 关键字让 Swift 的编译器或运行时根据闭包上下文来决定是以弱引用还是无主引用的方式捕获 self，从而在安全性和性能方面可能带来优化。
	3.	灵活适用：除了 self，safe 关键字还可以应用于闭包中其他可能需要弱引用或无主引用的变量，扩大了其实用性。

总体而言，该语法改进提案旨在减少样板代码，提高生产效率，支持潜在的性能优化，使涉及闭包的 Swift 代码更加简单、易维护。

## 推荐博文


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
