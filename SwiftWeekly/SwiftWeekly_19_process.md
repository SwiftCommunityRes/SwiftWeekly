## 前言

前几期周报内容是同步翻译的英文版周报，目前英文版停更，周报停滞半年多。经过多次讨论，我们决定**重启周报**，分模块整理内容同步给大家。

周报内容模块分为：**新闻**、**提案**、**Swift论坛**、**推荐博文**。初期计划每两周发布一期，欢迎志同道合的朋友一起加入周报整理。

昨日的生活与工作是否也曾迷茫？对新技术渴望突破的心是否依旧执着？**Swift社区**，为你的技术栈添砖加瓦，你，准备好了吗？

## 新闻和社区


## 提案

### 通过的提案


### 正在审查的提案


## Swift论坛
1)讨论[`Comparable`下`==`的危险默认实现](https://forums.swift.org/t/dangerous-default-implementation-of-under-comparable/61928 "`Comparable`下`==`的危险默认实现")

2)提议[Mach Port API](https://forums.swift.org/t/mach-port-api/61930 "Mach Port API")
简介:
Mach Port API 是一种难以安全使用的神秘技术。
但是，作为我们操作系统的一个组成部分，它们有时需要处理。

该提案广泛使用了mach port术语。
如果您想复习基础知识，[请查看端口、端口权限、端口集和端口命名空间](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Mach/Mach.html#//apple_ref/doc/uid/TP30000905-CH209-TPXREF104)。

动机:
Mach ports 很难正确设置，主要是由于管理 mach port 权限的方式。 程序员需要在头脑中跟踪类型、生命周期和其他状态。

Swift的高级类型系统，最近增加了[move-only types](https://github.com/apple/swift-evolution/blob/main/proposals/0366-move-function.md)，提供了一个新的机会来创建一个能够在编译时防止整个类错误的 Mach port接口。

建议的解决方案:
建立不同的类型来表示接收、发送和发送一次的权利。
提供 Mach port权限的自动生命周期管理，这与普通的 OOP 对象不同。

3)议案[Noncopyable (或者 “move-only”) 结构和枚举](https://forums.swift.org/t/pitch-noncopyable-or-move-only-structs-and-enums/61903 "Noncopyable (或者 “move-only”) 结构和枚举")

4)议案[@globalConstructor](https://forums.swift.org/t/pitch-globalconstructor/61901 "@globalConstructor")
简介:
@globalConstructor 属性提供了一种在启动可执行文件或加载动态库时自动调用函数的方法。

动机:
在许多用例中，您可能想要执行代码而不必直接调用它。 例如：

在您希望将库插入应用程序的位置进行调试，而无需手动调用库重建应用程序
包含可选库的插件系统将自己注册到主应用程序以更改行为
希望在启动时进行 1 次设置而不要求开发人员显式调用其配置的第三方库作者
如今，在这些情况下，开发人员不得不回退到 Objective-C/C++/C（使用 __attribute__((constructor)))，即使他们只需要调用一个 Swift 函数。

建议的解决方案:
添加一个新的 @globalConstructor 属性，该属性可以添加到顶级函数，以便在启动可执行文件或加载包含该函数的动态库时自动调用它们。

5)讨论[SE-0380：`if` 和 `switch` 表达式](https://forums.swift.org/t/se-0380-if-and-switch-expressions/61899 "SE-0380：`if` 和 `switch` 表达式")

6)议案[使用较新的 macOS 版本生成 `Package.swift` 文件](https://forums.swift.org/t/pitch-generate-package-swift-files-with-newer-macos-versions/61925 "使用较新的 macOS 版本生成 `Package.swift` 文件")
简介:
目前，没有明确定义支持的最低平台版本的 Swift Package Manager 包会自动默认为第一个支持的版本，对于许多平台来说，这是 2017 年的版本。这在某些情况下会增加新生成的包的摩擦。

动机:
当前，在 macOS 上构建全新的 Swift Package Manager 包时，构建目标是 2017 年的 macOS 10.13。当他们添加诸如 swift-syntax 之类的具有更高最低支持版本的依赖项时，这可能是一种令人沮丧的新用户体验，导致他们必须立即弄清楚如何配置此选项。

建议的解决方案:
我建议我们自动将 macOS 上生成的新包的最低支持版本添加到用户当前的 macOS 版本中。 例如，不是生成这个 Package.swift 内容：
```Swift
let package = Package(
    name: "name",
    ...
)
```
目前在 macOS 上我们将生成以下内容：
```Swift
let package = Package(
    name: "name",
    platforms: [.macOS("13.0")],
    ...
)
```

7)讨论[“withUnsafeBytes”已弃用](https://forums.swift.org/t/withunsafebytes-is-deprecated/61891 "“withUnsafeBytes”已弃用")

8)讨论[Linux 上标准库的自动编译是否损坏？](https://forums.swift.org/t/is-auto-compilation-of-the-standard-library-on-linux-broken/61918 "Linux 上标准库的自动编译是否损坏？")

9)讨论[Read/modify, yield, 和 non-escaping closures](https://forums.swift.org/t/read-modify-yield-and-non-escaping-closures/61902 "Read/modify, yield, 和 non-escaping closures")

10)议案[Swift 中的 Objective-C 实现](https://forums.swift.org/t/pitch-objective-c-implementations-in-swift/61907 "Swift 中的 Objective-C 实现")
我们提出了 @objc 类的替代方案，其中 Objective-C 标头 @interface 声明由 Swift 扩展实现。 生成的类将在 Swift 中实现，但与 Objective-C 类没有区别，完全支持 ObjC 子类化和运行时技巧。
使用@objcImplementation，您可以像编写 Objective-C 类一样手写头文件，但不是在 Objective-C 中实现方法和属性，而是在 Swift 中实现它们。

## 推荐博文

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
