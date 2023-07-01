## 前言

**本期是 Swift 编辑组自主整理周报的第二十三期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

骚年，努力去成为你期待已久的自己吧，就像**Swift社区**一样，时刻心怀梦想，不断向前！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果已提供新的设计资源
> 
> 提案：本期提案没有最新内容
> 
> Swift 论坛：讨论 Non-Reentrant Actors
>
> 推荐博文：AngularGradient 在 swiftUI 中的使用
>
> **话题讨论：** 
> 
> 你认为 vision pro 是否会加速虚拟现实技术的发展？

**上期话题结果**

![](https://files.mdnice.com/user/17787/976e8f1f-d753-438d-8117-a58b5a020286.jpeg)

根据投票结果，小编认为企业应根据自身情况和员工需求，平衡薪资保密与透明的利弊，制定适合的薪资政策。

## 新闻和社区

### 现已提供新的设计资源

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/7DD13ED0-F50B-4568-813A-2C89D0D8DB25/2048.jpeg)

为方便开发者在 Apple 平台上构建 App，我们现在提供了全新及更新后的设计资源，让你可以更便捷、更准确地设计 App。

visionOS 设计资料库以及适用于 Figma 和 Sketch 的模板 (英文)。

适用于 Figma 和 Sketch 的 iOS 17 和 iPadOS 17 设计套件 (英文)。

适用于 Figma 和 Sketch 的 macOS Sonoma 设计套件 (英文)。

适用于 Sketch 的 watchOS 10 设计套件 (英文)。

SF Symbols 5 Beta 版，包含 700 多个新符号 (英文)。

更新后的《人机界面指南》(英文)，现提供简体中文和日文版本。

SF 脚本扩展，现已支持亚美尼亚语、格鲁吉亚语和希伯来语 (英文页面)。

### visionOS SDK 现已发布

Apple Vision Pro 提供了一幅无边的画布，你现在就可以开始为这幅画布打造前沿的空间计算 App。下载 Xcode 15 Beta 版 2，其中包含 visionOS SDK 和 Reality Composer Pro — 这是一种新的工具，可让你轻松地预览和准备适用于 visionOS 的 3D 内容。将 visionOS 目标添加到你的现有项目中或构建一个全新的 App，然后在 Xcode 预览中迭代你的 App。你可以在全新的 visionOS 模拟器中与你的 App 互动，探索各种房间布局和光线条件，并创建测试和可视化效果。此外，我们还提供了新的文档和示例代码，帮助你完成整个开发过程。

## 提案

本期提案没有最新内容，期待下期更新～～

## Swift论坛

1) 提议[使用部分不可复制类型的字段](https://forums.swift.org/t/request-for-feedback-partial-consumption-of-fields-of-noncopyable-types/65884 "使用部分不可复制类型的字段")

**介绍**

当前给定一个类似于 var 的构造（例如：var、inout），Swift 不允许部使用耗该类型的存储字段：

```Swift
struct E : ~Copyable {}

struct S : ~Copyable {
    var first: E
    var second: Klass
}

var s = S()
let _ = s.e // Error! Cannot partially consume s
```

**不可复制类型的部分使用**

在设计空间中考虑以下几个不同的轴：

1. 关于带有 deinit 的类型
2. 启用 Library Evolution 时
3. 当 Library Evolution 被禁用时
4. 无论哪种情况，是否应该只允许方法中的部分消耗。

具有 Deinits 的类型的部分消耗

禁止使用 deinits 部分消耗不可复制类型，因为当字段被部分消耗，允许该类型被销毁

例如：

```Swift
struct E : ~Copyable
struct S : ~Copyable {
   var first: E
   var second: E
   deinit {}
}

var s = S()
let _ = s.first // s.first is destroyed here
doSomething()
// s.second is destroyed here
```

由于这里的 s 已被部分消耗，因此永远不会将其全部销毁，这意味着永远不会调用它自己的 deinit，这意味着不能允许发生。 

**请注意**，即使不允许这样做，仍然允许使用方法的作者使用丢弃运算符来关闭值的 deinit，然后部分解构该值。

2) 提问[一组弱引用可以符合Collection吗？](https://forums.swift.org/t/can-a-group-of-weak-references-conform-to-collection/65899 "一组弱引用可以符合Collection吗？")

问题陈述：

有一个收集弱引用的类型，可以对其进行迭代并追加。 

希望它符合 RangeReplaceableCollection，但是不能做任何比 Sequence 更具体的事情。

该类型本身是一个经典的指针长度容量三元组，其中指针指向弱引用缓冲区。 一旦长度==容量，在尝试重新分配之前，会扫描缓冲区以查找可以丢弃的 nils。 仅当无法删除足够的 nil 来为新元素腾出空间时，才会执行重新分配。

使其符合 Collection 的问题是下标(`_:`)。 如果索引类型只是缓冲区中的索引，则其他线程可能会导致弱引用从下面删除，因此索引可能会变得无效，而不会对集合进行明显的更改。

可以想到两种方法来解决这个问题，但都不能令人满意。

第一个是使索引类型也持有对该对象的强引用。 但是担心当用户没有意识到他们通过索引持有强大的参考时，可能会产生问题。

第二个是使元素类型为T？ 而不是 T。这是一种误导，因为迭代器会跳过 nils，但会使下标可实现。

第三个选项是在不实际遵守协议的情况下实现许多（但不是全部）收集操作。 担心这是我必须做的，除非能证明其他两种行为之一是合理的。 

有没有一种方法可以在不改变类型语义的情况下实现协议？

回答：

不是集合似乎是所提供的数据结构的固有属性，而不是实现限制。 如果序列中的第 n 个项目可以从 x 更改为 y，因为 x（或序列中较早的某个其他对象）已被收集，则序列没有稳定的索引。

3) 提问[swift Macro 中没有这样的模块“UIKit”](https://forums.swift.org/t/no-such-module-uikit-in-swift-macro/65885 "swift Macro 中没有这样的模块“UIKit”")

在 swift Macro 中导入 UIKit 时，报错 No such module 'UIKit' 。

宏包有以下平台

平台：[.macOS(.v10_15)、.iOS(.v13)、.tvOS(.v13)、.watchOS(.v6)、.macCatalyst(.v13)]

回答：

在构建过程中，宏在编码的计算机（可能是 Mac/Windows/Linux）上运行。 它不在 iOS 上运行，因此无法访问 UIKit。

为什么在宏中需要 UIKit（而不是在声明宏的包中）？

可以尝试创建一个可以导入 UIKit 的“Mac Catalyst”宏，但即使有可能，也可能没有用

4) 提议[低级联动控制属性：@used 和@section](https://forums.swift.org/t/pitch-low-level-linkage-control-attributes-used-and-section/65877 "低级联动控制属性：@used 和@section")

**动机**

动机有两个目标：

提供低级构建块来构建更多高级 API，例如 “链接器集”（见下文）或自定义每种类型元数据，如 SE-0385 中所述（swift-evolution/proposals/0385-custom-reflection-metadata.md，位于 main·apple/swift-evolution·GitHub 2）。

尽管这个推介/提案实际上并没有尝试添加或设计高级 API，只是提供了一条单独解锁设计的路径。

为系统编程用例提供低级机制（这些用例是针对具体系统的定制案例），并构建一个通常可重用的高级 API 是没有意义的（项目作者可以自由地构建这样一个高级 API，例如项目的内部机制）。

“链接器集”机制是 Swift 已经在使用的一种方法：几乎任何类型的编译器发出的元数据都被放入二进制文件中专门命名的部分中，并给出固定布局的记录。 

然后，想要查找某些信息时（例如，在二进制文件中查找协议一致性），要求加载器（Darwin 上的 dyld）为我们提供每个加载的该部分的起始/结束地址。 图像，然后可以迭代这些部分中的所有记录。 

还可以从进程外部提取一些元数据，或者从二进制文件本身中挖掘它。使用现有的反射库来完成此操作，例如 `swift-inspect` 和 `swift-reflection-dump`。

在 Swift 语言中添加功能来表达该机制的第一部分：将固定布局记录放入专门命名的部分。

**提议**

其中一些已经在功能标志下实现为 main 中的下划线属性（ `@_section`、`@_used`），通过 https://github.com/apple/swift/pull/65901 实现。 总之：

@used 属性，通过 llvm.used 将全局变量或顶级函数标记为“不要死区”，大致相当于 C/C++ 中的 __attribute__((used)) 。

@section("...") 属性，将全局变量或顶级函数放入具有该名称的节中，大致相当于 C/C++ 中的 __attribute__((section("..."))) 。

这些注释只能应用于保证最终“静态初始化”（而不是通过 init_once 运行时调用延迟初始化）的全局变量，因为否则注释没有任何意义。

这就提出了一个有趣的问题：当用于初始化全局时，哪些表达式可以保证“静态初始化”？ 建议从一组非常基本的表达式开始，并在将来对其进行改进。

强制优化管道已经使整数文字、元组和简单算术表达式进行“静态初始化”，如果存在任何具有 `@section` 属性的全局变量，可以在 SIL 管道末尾明确拒绝编译 这不是静态初始化的。 

然后，作为后续改进，应该考虑允许 POD 结构类型也在强制优化管道中处理，并允许与 `@section` 一起使用。

虽然超出了本次推介的范围，但以下是“链接器集”API 的运行时端的草图：

```Swift
 // in Module1
@used @section("__DATA,mysection") private let my_entry: Int = ...

// in Module2
@used @section("__DATA,mysection") private let my_entry: Int = ...

for entry in SwiftRuntime.section("__DATA,mysection", as: Int.self) { // this uses the loader's APIs to locate and iterate over the section
  ...
}
```

最终，将其包装到基于宏的解决方案中可能是有意义的，这样就根本不会公开低级属性：

```Swift
@LinkerSet(name: "myLinkerSet") private let myEntry: Int = 42

for entry in SwiftRuntime.linkerSet("myLinkerSet", as: Int.self) {
  ...
}
```
或者，在想要将元数据附加到类型的情况下（由 SE-0385 推动）：

```Swift
@Registered(name: "My Favorite Type") // this creates a hidden global in a named section
class MyType { }

for regType in allRegisteredTypes { // queries over the entries in the section
  ...
}
```

5) 提问[在构建期间启用预处理器标志](https://forums.swift.org/t/enable-preprocessor-flags-during-build/65892 "在构建期间启用预处理器标志")

有一个 C++ 头文件，仅在设置了预处理器标志时才公开一个类：

```Cpp
#ifdef UNIX_ENABLED

class Some_Class {
...
}
#endif // UNIX_ENABLED
```

当调用 swift 编译器时：

swiftc MyApp.swift -cxx-互操作性模式=默认-Xcc -std=c++17 -I cxx -c -parse-as-library

并尝试在 MyApp.swift 中使用 Some_Class ，但显然找不到该类。 尝试使用 -D UNIX_ENABLED 但这没有帮助。

有什么想法可以进行此编译吗？

回答：

可以尝试将 -Xcc -D -Xcc UNIX_ENABLED 传递给 swiftc 以确保它将 -D 转发给 clang

6) 讨论[Non-Reentrant Actors](https://forums.swift.org/t/non-reentrant-actors/65888 "Non-Reentrant Actors")

每当编写涉及 Actor 的代码时，发现自己想要对 Actor 进行有意义的工作，但最终会在此过程中引入难以捕获的错误。 以这个简单的例子为例：

```Swift
actor HeavyLifting {
    var cachedResult: String?
    func doHeavyLifting() async throws -> String {
        if let cachedResult { return cachedResult }
        let result = try await // load some resource and process it.
        cachedResult = result
        return result
    }
}
```

开发人员可能会认为这是确保只执行一次“繁重工作”并缓存结果的完全足够的方法。然而，更精明的审阅者可能会注意到，虽然这不会导致灾难性的失败，实际上也不会保护繁重的工作不被多次完成，因为对此方法的多个并发请求虽然不是“ 一旦达到每个负载的暂停点，每个负载就会开始繁重的工作负载。

更具冒险精神的开发人员的工具带中确实有一个工具可以解决这个问题 - 非结构化任务：

```Swift
actor HeavyLifting {
    var heavyLiftingTask: Task<String, Error>?
    var heavyLiftingResult: String {
        get async throws {
            if let heavyLiftingTask { return try await heavyLiftingTask.value }
            let task = Task { try await // load some resource and process it. }
            heavyLiftingTask = task
            return try await task.value
        }
    }
}
```

现在引入了不完整样板的微妙平衡，更不用说缺乏对取消传播的适当支持，所有这些都是以防止死锁的名义，而实际上并没有阻止富有冒险精神的开发人员编写可能会导致死锁的代码。

代码中到处都是这样的样板文件，最终肯定会弄错，当一天结束时，希望并假设在错误的等待最终潜入之前所做的事情，是为了 Actor 的方法在进行过程中不可调用，而 Actor 的其余部分则继续其业务。

已经使用过 Actor 一段时间，重新审视不可重入性，因为它是比较有用的工具。可以看到单独的方法或函数是希望以某种能力强制执行串行访问的东西，但是也可以看到将其应用于对整个参与者的所有访问的好处。

回答：

在未来方向（有任务链重入的奖励积分，但没有任务链重入绝对非常有用）将如那里所描述的那样非常棒。不希望应用于整个 Actor。

会有助于避免现在很容易变得脆弱的模式来解决缺乏此功能的问题。

可选的参与者“发送”对 Void 返回函数的支持一起将释放参与者的很大一部分潜力。

7) 讨论[宏扩展后访问源代码](https://forums.swift.org/t/accessing-source-code-after-macro-expansion/65881 "宏扩展后访问源代码")

当构建一个使用 SwiftSyntax 遍历 Swift 源代码的工具时，是否有一种直接的方法来遍历宏扩展后的源代码？

这是否需要通过尝试扩展每个源文件来手动完成？

正在构建的工具中，复制源文件并对其进行操作，但这是直接来自文件系统和预扩展的。 具体来说，该工具会遍历有效的 .swift 文件并捕获符合给定协议的所有类型。使用宏来添加对该协议的一致性，但是构建插件无法仅通过阅读非扩展源代码来了解最终的一致性。 使用 `Target.directory` 来确定给定目标的源文件所在的位置，但是是否有更好的方法来访问扩展源所在的构建目录？

回答：

如果对宏扩展的工作原理感到好奇，可以在[这个文档](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/macros/#Macro-Expansion)中阅读。

Swift 中的宏扩展基于语法的内存表示，这意味着无法在不手动执行扩展的情况下直接从源文件中检索扩展的代码。

可能会考虑尝试使用此方法扩展所有宏：[SyntaxProtocol.expand(macros:in:)](https://github.com/apple/swift-syntax/blob/b556ac7c099539ed058f6fcfd978d66cb133176e/Sources/SwiftSyntaxMacros/MacroSystem.swift#L576)

## 推荐博文

[AngularGradient 在swiftUI中的使用](https://swdevnotes.com/swift/2023/angulargradient-in-swiftui/ "AngularGradient 在swiftUI中的使用")

**摘要：** 本篇文章讲解了如何在 swiftUI 中使用  AngularGradient，用于从一种颜色过渡到另一种颜色，可选地通过围绕指定中心点的放射状图案中的一系列颜色。本文探讨了设置不同中心点以及指定渐变的起始角度和结束角度范围的效果。 AngularGradient 可用于在 SwiftUI 视图中创建引人注目的视觉效果，尤其是在圆形或弧形中使用时。

[字节跳动 DanceCC 工具链系列之Swift 调试性能的优化方案](https://juejin.cn/post/7095940115532349454/ " 字节跳动 DanceCC 工具链系列之Swift 调试性能的优化方案")

**摘要：**  本篇文章讲解了大型 Swift 项目如何通过开关，以及自定义 LLDB ，优化 Swift 开发同学的调试速度，提高整体的研发效能。其中讲解了 LLDB 的部分工作流程，以及针对性优化的技术细节，以及实际效果。

[Swift 的可选值优化](https://juejin.cn/post/7244809939839434808/ "Swift 的可选值优化")

**摘要：** 在 Swift 中，nil 的语义与 Objective-C 中的 nil 不同，它代表没有值的概念。为了表示没有值，Swift 引入了 nil 关键字，但在内存中的表示方式与 Objective-C 不同。文章通过代码展示了 nil 在内存中的真正表示，发现可选的 Int? 类型比普通的 Int 类型多占一个字节，用来表示是否有值。然而，Swift 编译器已经进行了优化，例如 Bool? 类型只占用一个字节，用2来表示 nil 。 String 类型也可以在内存中用0表示没有值。对于 Class 类型和 Enum 类型，空指针或越界值可以表示没有值，也没有内存浪费。总之， Swift 编译器会尽可能地优化可选值的内存占用，但仍建议在某些情况下尽量少使用可选值，特别是在结构体中连续多个可选的 Int 的情况下，可以使用非可选值并用0初始化它们。

## 话题讨论

**你认为vision pro是否会加速虚拟现实技术的发展？**

1. 会
2. 不会
3. AI发展才是王道

欢迎在文末留言参与讨论。


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
