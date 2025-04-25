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
1) 提议[引入 Swift 筹资合作社](https://forums.swift.org/t/introducing-the-swift-fundraising-cooperative/79252 "引入 Swift 筹资合作社")

Swift 论坛成员 Diana Ma（@taylorswift）宣布成立 Swift 筹资合作社（Swift Fundraising Cooperative，简称 SFC），旨在为 Swift 生态系统中缺乏资金支持的项目提供集中筹资和协调支持。 ￼

合作社的目标包括：
•	支持不在核心开发议程中的小众功能和中间层基础设施。
•	为跨平台支持（如 Android、WebAssembly、Windows 和服务器端 Swift）提供资金。
•	资助高质量的跨领域文档和培训材料的创建。

合作社的运作方式：
•	为潜在赞助商提供一个稳定的合作伙伴，协调资源分配。
•	采用延迟许可模式，鼓励首次投资者，同时希望赞助商能够立即将其资助的工作贡献给论坛。

创始成员包括：
•	Diana Ma（@taylorswift）：Swift 服务器工作组和文档工作组成员，swiftinit.org 的创建者。
•	Finagolfin：长期致力于将 Swift 移植到 Android 的开发者。
•	Sven A. Schmidt（@finestructure）：Swift Package Index 的联合创始人。 ￼

SFC 的成立旨在弥补当前以志愿者为主的开发模式在资源和安全性方面的不足，推动 Swift 生态系统的可持续发展。

2) 提议[SE-0477：字符串插值中的默认值](https://forums.swift.org/t/se-0477-default-value-in-string-interpolations/79302 "SE-0477：字符串插值中的默认值")

Swift 提议 SE-0477 引入了一种新的字符串插值语法，允许开发者在插入可选值时提供默认字符串，从而避免输出中出现“Optional(…)”或“nil”的情况。 ￼

动机：

在当前的 Swift 中，将可选值直接插入字符串会导致输出包含类型信息，例如 Optional("value")，这通常不适合用户界面显示或日志记录。 ￼

提议内容：

新增的插值语法如下：
```Swift
let name: String? = nil
print("Hello, \(name, default: "Guest")!")
```
这将输出：Hello, Guest! ￼

实现细节：

该功能通过扩展 String.StringInterpolation 实现，添加了一个新的 appendInterpolation 方法，接受一个可选值和一个默认字符串。 ￼

影响：

此更改不会破坏现有代码，属于向后兼容的新增功能。

论坛反馈：

论坛成员普遍支持该提议，认为这是一个常见需求，能够简化代码并提高可读性。

3) 提议[引入 weak let 语法](https://forums.swift.org/t/pitch-weak-let/79271 "引入 weak let 语法")

Swift 论坛成员 Nickolas Pokhylets 提出了一项提议，建议允许在 Swift 中使用 weak let 声明，以解决当前 weak 属性必须为可变（var）所带来的限制。 ￼

动机：
•	当前，Swift 要求 weak 存储属性必须是可变的（var），这使得包含 weak 属性的类无法符合 Sendable 协议，因为 Sendable 类要求其属性为不可变的（let）。
•	类似地，闭包中使用 weak 捕获的变量也被视为可变的，导致这些闭包无法标记为 @Sendable。
•	开发者通常并不打算修改被捕获的 weak 变量，但由于其隐式的可变性，导致与 unowned 或默认捕获行为不一致。 ￼

提议内容：
•	允许在局部变量和存储属性中使用 weak let 声明，使其成为不可变的 weak 引用。
•	在闭包中，weak 捕获的变量将被视为不可变的。如果需要可变的捕获，开发者需要显式地声明并捕获可变变量。

示例：
```Swift
final class C: Sendable {}

struct WeakRef {
    weak var ref: C?
}

final class User: Sendable {
    weak let ref1: C? // 提议允许的语法
    let ref2: WeakRef // 当前的替代方案
}

func makeClosure() -> @Sendable () -> Void {
    let c = C()
    return { [weak c] in
        c?.foo()
        c = nil // 错误：'c' 是不可变的捕获
    }

    weak var explicitlyMutable: C? = c
    return {
        explicitlyMutable?.foo()
        explicitlyMutable = nil // 合法：显式声明的可变变量
    }
}
```
兼容性影响：
•	允许 weak let 声明是源代码兼容的更改，使之前无效的代码变为有效。
•	将 weak 捕获视为不可变是源代码不兼容的更改，任何尝试修改捕获变量的代码将无法编译，但预计此类代码数量较少。 ￼

论坛反馈：
•	一些论坛成员担心 weak let 可能违反 let 表示值不变的直觉，尤其是在多线程环境中。
•	其他成员认为 weak 引用的行为更像是对对象生命周期的观察，而不是传统意义上的可变性，因此支持该提议。
•	总体而言，论坛对该提议持积极态度，认为它可以减少样板代码，并提高与 Sendable 协议的兼容性。

4) 提议[扩展可用性检查机制](https://forums.swift.org/t/pitch-extensible-availability-checking/79308 "扩展可用性检查机制")

Swift 论坛成员 Allan Shortlidge 提出了一项提议，旨在通过允许开发者在 Swift 源代码中声明自定义的可用性域（availability domains），扩展 @available 属性的功能，从而支持更广泛的使用场景。 ￼

动机：
•	当前，@available 主要用于限制声明在特定平台或语言版本中的可用性，但其支持的域是编译器内置的，扩展性有限。
•	随着 Swift 扩展到更多平台，开发者希望能够根据库版本、特性标志等自定义条件控制 API 的可用性。 ￼

提议内容：
•	允许开发者使用 @availabilityDomain 属性声明自定义的可用性域，其值可以是版本元组或布尔值。例如：
```Swift
@availabilityDomain(MyLibrary)
public let myLibraryVersion = (2, 1, 0)

@availabilityDomain(MyFeatureFlag)
public var myFeatureEnabled = true
```
 
•	在声明中使用自定义可用性域限制 API 的可用性：
```Swift
@available(MyLibrary, introduced: 2.1)
public func newFunctionality()

@available(MyFeatureFlag)
public func requiresMyFeature()
```

•	在代码中使用 if #available 语句根据自定义可用性域进行条件判断：
```Swift
if #available(MyLibrary 3.0) {
  // ...
}

if #available(MyFeatureFlag) {
  // ...
}
```
优势：
	•	提高了 @available 的灵活性，支持基于库版本、特性标志等自定义条件控制 API 的可用性。
	•	相比于条件编译，使用自定义可用性域可以在编译时进行更精确的类型检查和诊断。
	•	支持模块限定的可用性域名称，避免命名冲突。 ￼

论坛反馈：
	•	论坛成员对该提议表示支持，认为这将有助于管理跨平台库的可用性和特性标志的控制。
	•	一些成员提出了关于命名空间、文档生成和与现有工具链集成的建议，以进一步完善该功能。

该提议旨在增强 Swift 的可用性检查机制，使其更具扩展性和灵活性，满足日益增长的跨平台和模块化开发需求。

5) 讨论[Flappy Swift：一个用 Swift 编写的约 100 KB 的 WebAssembly 游戏](https://forums.swift.org/t/flappy-swift-a-webassembly-game-written-in-swift-in-100-kb/79262 "Flappy Swift：一个用 Swift 编写的约 100 KB 的 WebAssembly 游戏")

Swift 论坛成员 Simon Leeb（@sliemeobn）发布了一个名为 Flappy Swift 的项目，这是一个用 Swift 编写并编译为 WebAssembly 的“Flappy Bird”游戏克隆，体积仅约 100 KB。 ￼

项目亮点：
•	Flappy Swift 使用完整的响应式 DOM 协调引擎进行每帧动画，并应用传统的 CSS 样式。
•	尽管尚未进行性能优化，但游戏在浏览器中的表现相当不错。
•	该项目展示了 Swift 在 WebAssembly 上的潜力，证明了 Swift 可以用于构建高性能的 Web 应用。 ￼

论坛反馈：
•	论坛成员对该项目表示赞赏，认为这是 Swift 在 WebAssembly 应用方面的一个有趣示例。
•	一些成员建议改进用户体验，例如在触摸设备上禁用文本选择，以及优化在 Safari 浏览器中的动画表现。
•	该项目在 GitHub Universe 大会上展示时，吸引了大量关注，展示了 Swift 在非传统平台上的可能性。 ￼

Flappy Swift 的发布展示了 Swift 在 Web 开发领域的潜力，为开发者探索 Swift 在 WebAssembly 上的应用提供了一个有趣的起点。

## 推荐博文


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
