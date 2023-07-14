## 前言

**本期是 Swift 编辑组自主整理周报的第二十四期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

看那碧水蓝天，波澜又壮阔。浅读**Swift社区**，充实而豁然。期许光亮，皆在其中！👊👊👊

> **周报精选**
>
> 新闻和社区：App 内购买项目和订阅即将实行价格与税率调整
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

**上期话题结果**



## 新闻和社区

### App 内购买项目和订阅即将实行价格与税率调整

App Store 的交易和支付机制旨在帮助你在覆盖全球的 175 个国家和地区的店面中，以 44 种货币为你的产品和服务便捷地进行定价与销售。当税务法规或外汇汇率变化时，App Store 中某些地区的价格有时会随之更新，且你的收入亦将调整。这些调整将根据金融数据机构提供的公开汇率信息进行，以此确保 App 和 App 内购买项目的定价在所有店面中保持平衡。

从 7 月 25 日起，App 和 App 购买项目 (不包括自动续期订阅) 在埃及、尼日利亚、坦桑尼亚和土耳其店面中的定价将会进行调整。这些调整还包含了以下税率变更：

埃及：收取 14% 的增值税 (VAT)
坦桑尼亚：收取 18% 的增值税和 2% 的数字服务税
土耳其：增值税率从 18% 上调至 20%
这些调整对定价的影响
如果你选择了埃及、尼日利亚、坦桑尼亚或土耳其作为 App 或 App 内购买项目 (不包括自动续期订阅) 的基准店面，则对应店面中的价格不会发生变化。其他店面中的价格将会进行更新，以便与你选择的基准价格保持持平。
如果你为 App 或 App 内购买项目 (不包括自动续期订阅) 选择的基准店面不是埃及、尼日利亚、坦桑尼亚或土耳其，则埃及、尼日利亚、坦桑尼亚和土耳其店面中的价格将会上调。
如果你的 App 内购买项目是自动续期订阅，或者如果你手动管理各个店面的价格，而不是使用自动均衡价格，那么你的价格不会发生变化。
App Store Connect 中“我的 App”的“价格与销售范围”部分现已更新，以显示这些即将进行的价格调整。一如既往，你可以随时更改你的 App、App 内购买项目和自动续期订阅的价格。

这些调整对收益和税务管理的影响
你从 App 和 App 内购买项目 (包括自动续期订阅) 销售中获得的收益将会发生变化，以反映新的税率和更新后的价格。《付费 App 协议》的附录 B 已更新，表明 Apple 在埃及和坦桑尼亚征收和汇付适用税款。

### 为家庭提供安全的 App 体验

App Store 的创建目的是为用户提供一个安全且值得信赖的 App 下载平台，并为开发者提供绝佳的商机。由于孩子们会使用我们的产品和服务，来探索数字世界并与家人和朋友进行交流，因此对许多家庭而言，Apple 平台和你构建的 App 变得非常重要。针对面向儿童的 App，以及那些具有用户生成内容和互动的 App，我们设立了极高的标准。为了继续为家庭打造安全的体验，谨在此提醒你，我们提供了各种工具和资源，并制定了相关要求，以帮助你保障用户在 App 中的安全。


## 提案


## Swift论坛
1) 讨论[这些是错别字吗？](https://forums.swift.org/t/are-these-typos/66118 "这些是错别字吗？")
提问：
在观看 SwifUIi 视频时，我看到两处看起来像是拼写错误的东西。 如果不是，我想知道为什么它们的表达如此含糊：
反斜杠有什么用？
```Swift
var body: some View {
    List (graphics, children: \.children) { graphic in
        GraphicRow (graphic)
    }
    .listStyle(SidebarListStyle())
}
```
美元符号有什么用？
```Swift
var body: some View {
    DocumentGroup (newDocument: SketchDocument()) { file in
        DocumentView(file.$document)
    }
}
```
回答：
不，这些不是拼写错误。 它们是用于访问特定语言功能的符号，这些功能会生成与命名属性相关的内容，而不是正常访问该属性。

Swift 在前缀运算符位置中使用 \ 来创建“关键路径”，该对象通常表示（在本例中）Graphic.children 属性，而不是特定 Graphic 的 Children 属性； 该对象可以应用于 Graphic 的任何实例以访问其 Children 属性。 在其他语言中，\ 字符在字符串文字中很常见，它开始一个“转义序列”，但它很少用作运算符，并且使用它的语言之间几乎没有一致性。 这里与“转义”的想法有某种模糊的联系，因为在这两种情况下，你都在逐步提升到更抽象的含义水平，但在大多数情况下，它被选择是因为它是一个未使用的符号，通常是 易于打字并且看起来不错。 该功能的演变提案实际上讨论了几种不同的语法，[并解释了为什么选择反斜杠](https://github.com/apple/swift-evolution/blob/main/proposals/0161-key-paths.md#spelling)。

$ 前缀意味着您正在访问相关属性的属性包装器提供的特殊功能。 在这里，该属性是 FileDocumentConfiguration.document，它[根据文档](https://developer.apple.com/documentation/swiftui/filedocumentconfiguration/document)有一个 @Binding 属性包装器。 这意味着 $document 将公开一个到文档的 Binding - 一个可用于访问和修改该文档属性的对象，而无需关心它实际存储的位置。 我们将此 $ 变量称为“投影值”而不是“绑定值”或其他任何名称，因为 $ 语法是通用语言功能，因此如果您使用 @Binding 以外的其他内容，$ 属性可能不会创建绑定； 它可能被赋予一些其他功能。

选择这两种语法并不是因为它们会立即熟悉，而是因为我们确定没有一种语法可以立即熟悉，最好选择开发人员需要学习但一旦学习后会发现易于使用的语法。

每种语言都有独特的功能并做出独特的语法决策。 这就是为什么创建一种新语言值得的部分原因：因为现有语言无法按照您希望的方式工作。 学习一门语言就像访问一个具有不同文化的国家：如果你总是批评当地文化而不是学习适应它，你会感到非常不舒服。

2) 讨论[NSLock.Lock 加 Await 加 NSLock.Unlock 导致主线程冻结](https://forums.swift.org/t/nslock-lock-plus-await-plus-nslock-unlock-leads-to-main-thread-freeze/66113 "NSLock.Lock 加 Await 加 NSLock.Unlock 导致主线程冻结")
提问：
以下代码模拟了当外部库的作者引入锁时的情况，这可能包含等待调用。 有什么办法可以防止这种情况（noasync 注释不是解决方案，因为：1）如果函数包装在另一个没有 noasync 注释的函数中，它不起作用； 2）第三方库的作者可能会忘记添加这样的注释）。
```Swift
let lock = NSLock()

func thirdPartyLibLock() {
    print("- do sum work and lock")
    lock.lock()
    /*
     I also tried to replace it with:
         await withCheckedContinuation({ c in
             lock.lock()
             c.resume()
         })
     */
}

func thirdPartyLibUnlock() {
    print("- do sum work and unlock")
    lock.unlock()
    /*
     I also tried to replace it with:
         await withCheckedContinuation({ c in
             lock.unlock()
             c.resume()
         })
     */
}

func example() {
    /*
     Console:
     - start 4
     - do sum work and lock
     - start 1
     - do sum work and lock

     And that's all. We have suspended main thread.
     Numbers 4 and 1 could differ between app launches, it's ok.
     */
    for i in 0...1000 {
        Task {
            print("- start \(i)")

            thirdPartyLibLock()
            try await Task.sleep(for: .seconds(1))
            thirdPartyLibUnlock()

            print("- end \(i)")
        }
    }

    // Won't be executed.
    DispatchQueue.main.asyncAfter(deadline: .now() + 3, execute: {
        print("- ping")
    })
}
```
回答：
由于多种原因，锁定+解锁 API 对在设计上是不安全的，这就是其中之一。 更好的设计是使用一个函数来获取锁，调用回调，然后在回调返回后释放锁。 （理想情况下，该函数还可以提供对受锁保护的资源的回调访问，否则将无法访问。）只需使整个过程同步，就可以非常巧妙地表达在锁定和解锁之间不挂起的要求。

3) 讨论[所需的 Swift 语言功能可以提升 C++ 互操作性支持的状态](https://forums.swift.org/t/desired-swift-language-features-that-can-advance-the-state-of-c-interoperability-support/66144 "所需的 Swift 语言功能可以提升 C++ 互操作性支持的状态")
内容：
Swift 5.9 可以在 Swift 中导入和使用多种 C++ 类型。 但是，并非所有类型类别都受支持。 这篇文章列出了一组所需的 Swift 语言功能，这些功能使我们能够支持 Swift 中的大多数 C++ 类型：

对不可复制类型的泛型支持。 虽然 Swift 5.9 添加了对不可复制结构和枚举的支持，但这些类型仍然不允许用作泛型类型参数。 这是阻止我们在 Swift 中完全完成对仅移动 C++ 类型的支持的一个关键问题，因为我们需要形成像 UnsafePointer<MoveOnlyCxxType> 这样没有语言限制的类型。
添加到上面的一点，像 UnsafePointer 和 UnsafeMutablePointer 这样的类型应该提供对借用和可变借用不可复制指针对象的支持。
不可移动/不可逃避的 Swift 类型类别。 不可转义和不可复制的 Swift 类型将允许我们在 Swift 中导入和建模不可复制和不可移动的 C++ 类型。
此外，以下语言功能将有助于改善 Swift 中对 C++ 类型执行的一些常见操作的人体工程学：

能够在 Swift 序列上执行借用 for 循环，这确实需要经过 IteratorProtocol，但可以使用索引迭代。 这将使我们能够自动在 std::map 等非随机访问集合上使用 for 循环。
我想提请@语言工作组注意上面列出的项目，以确保他们的 Swift 发展计划和想法也能考虑到这些请求。

回答：
这些听起来与我们计划完善不可复制类型支持的项目一致，这很好。 在此列表中包含内部导入以及支持导入 C 和 C++ 类型而不间接公开其 ABI 是否也有意义，以便允许包在内部使用 C++ 互操作而不要求依赖项了解它？

4) 讨论[将协议添加到同名模块](https "将协议添加到同名模块")
提问：
我有一个名为 HTML 的模块，其中包含同名的类型 HTML。 它的树看起来像这样：

HTML（模块）
HTML（结构）
HTML.属性（枚举）
HTML.ContainerElement（枚举）
HTML.VoidElement（枚举）
到目前为止，一切都很好。 不可能限定对该模块中的声明的引用，因为它是同名的，但这没关系，因为 HTML 类型本身在功能上是命名空间限定符。

现在我想向这个模块添加一个协议，我们称之为 HTMLOutputStreamable。 但是我们不能向未命名为 HTML 的 HTML 模块添加顶级类型，因为该模块是同名的，并且无法使用 HTML.HTMLOutputStreamable 来限定对此协议的引用。

我该如何解决这个问题？

回答：
不幸的是，我发现的唯一方法就是使用不同的名称。

从这个角度来看，Swift 仍然缺少完整的命名空间功能。 它可以是模块级命名空间，但更完整和可靠。 我更喜欢像 C++ 那样的命名空间，或者像 Rust 那样的显式模块定义，但这似乎不是 Swift 进化愿景的一部分。

5) 讨论[嵌套函数和 @ViewBuilder：奇怪的编译器错误](https "嵌套函数和 @ViewBuilder：奇怪的编译器错误")
以下代码给出了一个奇怪的编译器错误，该错误似乎不相关：
```Swift
struct ContentView: View {

    var body: some View {

        func world() -> String {
            "world"
        }

        Text("Hello, \(world())!")
    }
}
```
错误信息是：

包含声明的闭包不能与结果生成器“ViewBuilder”一起使用

有趣的是，如果我在 world() 中添加 return （即 return "world"），编译器会在其他地方显示错误并添加警告，两者也不是很相关。 这看起来更像是一个编译器错误。

有什么想法吗？

回答：
从历史上看，结果构建器对其内部运行的语法有一些限制。 其中许多限制在 [SE-0373](https://github.com/apple/swift-evolution/blob/main/proposals/0373-vars-without-limits-in-result-builders.md)：解除结果构建器中变量的所有限制中被删除，但如果仍然存在一些限制，我不会感到惊讶。

## 推荐博文

[轻量化的 iOS 动画框架实现](https://juejin.cn/post/7252586606091419708/ " 轻量化的 iOS 动画框架实现")

**摘要：** 在这篇博客中，介绍了日常开发中对视图进行动画处理的常见问题，并提供了一种解决方案。文章首先展示了普通的动画代码，并指出了其回调函数回溯的问题。接着介绍了一些流行的动画库，如 Spring ， Hero 和 TweenKit ，但它们都存在一些限制。为了解决这些问题，引入了一种简洁、易于使用和维护的动画执行方式。该方案基于 Animator 和 Animation 的封装实现，其中 Animator 定义了动画执行器的基本协议，并封装了几种不同类型的动画执行器。 Animation 定义了动画执行的参数，并为不同的 Animato r制定了不同的协议。此外，文章还介绍了类型擦除的概念，以解决参数类型不一致的问题。具体实现方面，通过扩展UIView添加了串行和并行动画的方法。最后，总结了该方案的优点和可能的改进点。 

[使用 Swift Package 插件将自定义字体加载到您的应用程序中](https://www.polpiella.dev/load-custom-fonts-with-no-code-using-swift-package-plugins/ "使用 Swift Package 插件将自定义字体加载到您的应用程序中")

**摘要：**  本文介绍了如何使用 Swift Package 插件将自定义字体加载到应用程序中。通过创建一个 Swift Package 来包含共享的字体文件和字体加载代码，可以加快新应用的发布速度，减少代码重复，并提供一个统一更新字体文件的地方。结合 Swift Package 的可重用性和 Swift Package 插件的强大功能，甚至可以在构建时从字体文件自动生成所有必要的代码。本文使用 SwiftGen 来演示如何实现这一点。首先创建一个名为 "Fonts" 的 Swift Package ，并在其中添加自定义字体资源。然后添加 SwiftGen 插件来生成加载字体所需的代码。最后，可以使用生成的代码来在 SwiftUI 和 UIKit 中使用自定义字体。

[掌握 Swift Foundation Formatter API 。自定义格式样式](https://swiftwithmajid.com/2023/07/04/mastering-swift-foundation-formatter-api-custom-format-styles/ "掌握 Swift Foundation Formatter API 。自定义格式样式")

**摘要：** 本篇博客介绍了如何使用 Swift Foundation Formatter API 中的自定义格式样式。作者分享了自己在每个项目中都使用该 API 并构建自定义格式化逻辑的经验。博客中详细讲解了 FormatStyle 协议以及如何创建符合该协议的自定义格式样式。通过示例，展示了如何创建短数字格式样式和粗体数字格式样式，并说明了如何在自定义类型中重用这些格式样式。最后，作者还提供了一种封装格式化逻辑的方法。



## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
