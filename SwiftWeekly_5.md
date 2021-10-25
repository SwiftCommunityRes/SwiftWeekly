## 前言

Apple 举办了 `Unleashed` 活动发布了新品，借助超强的 `M1 Pro` 或 `M1 Max` 芯片，不管是基于新款的 `MacBook Pro` 开发应用，还是开发 `MacBook Pro` 下的应用，新机都将给我们带来突破性的性能和惊人的电池使用时长。

再加上强大的神经引擎，用于增强机器学习和升级的支持 `ProRes` 的媒体引擎，新款 `MacBook Pro` 能让我们的 App 做前所未有的事情。

> 为了 Swift 社区周报持续稳定的发布更新，我们希望邀请 Swift 爱好者参与**周报编辑**，同时邀请赞助商对我们平台赞助支持。

## 入门任务
**SR-15312** [Swift-DocC] [添加 “version” 命令到 docc 命令行工具中](https://bugs.swift.org/browse/SR-15312 "Add 'version' command to docc command line tool") 

**SR-15312** [Swift-DocC] [当浏览器 URL 不是小写时，主教程导航下拉菜单无法将当前教程字体加粗](https://bugs.swift.org/browse/SR-15313 "Primary tutorial navigation dropdown fails to bold the current tutorial when browser URL is not lowercased") 

## 新闻和社区
**Franklin Schrans** 宣布 [Swift-DocC](https://swift.org/blog/swift-docc/ "Swift-DocC is Now Open Source") 将要开源.

**Marin Todorov** 终于披露了他关于 [`Swift Markdown`](https://github.com/apple/swift-markdown "Swift Markdown") 的工作.

**Federico Zanetello** 写了一篇[文章](https://www.fivestars.blog/articles/warn_unqualified_access/ "warn_unqualified_access")来说明 `@warn_unqualified_access` 的使用.

**Dave DeLong** 解释了如何[简化 Swift 中的向后兼容性](https://davedelong.com/blog/2021/10/09/simplifying-backwards-compatibility-in-swift/ "Simplifying Backwards Compatibility in Swift")。

`Swift-DocC` 的文档现在已经发布在 [Swift.org](https://swift.org/documentation/docc/ "Docc") (使用 [Swift-DocC!](https://forums.swift.org/t/documentation-for-swift-docc-is-now-on-swift-org/52914 "Documentation for Swift-DocC is now on Swift.org")).

## 正在审查的提案
**SE-0325** [附加包插件 API](https://github.com/apple/swift-evolution/blob/main/proposals/0325-swiftpm-additional-plugin-apis.md "Additional Package Plugin APIs") 正在审查中。

**SE-0303** 在 `SwiftPM` 中引入了定义构建工具插件的能力, 允许自定义工具在构建打包时被调用。为了支持该特性， **SE-0303** 引入了最小初始 API，插件能够通过该接口获取那些被唤起构建的 Target 的相关信息。

该提案扩展了插件 API 以提供更多上下文，包括更丰富的包图表示。 这是为将来支持新类型的插件做准备。

## Swift 论坛

**1. Nuri Amari** 提出了[改进 ClangImporter](https://forums.swift.org/t/pitch-improved-clangimporter-diagnostics/52687 "Improved ClangImporter Diagnostics") 的建议。

提出对 `ClangImporter` 的改进建议，当导入 `C` 或 `Objective-C` 实体发生错误时提供更详细的反馈。 就目前而言，当 `ClangImporter` 无法完全或部分导入实体（函数、类型、宏等）时，出现错误是不会提示的。当前的 Swift 编译错误大部分情况下会提示**从未定义过实体**。

**2. Frederick Kellison-Linn** 提出了[关键路径到函数转换](https://forums.swift.org/t/pitch-generalize-keypath-to-function-conversions/52681 "Generalize keypath-to-function conversions")的想法。

该提案介绍了在允许 `(Root) -> Value` 函数的情况下使用键路径表达式 `\Root.value` 的能力。

`Swift-evolution` 线程：[关键路径表达式作为函数](https://forums.swift.org/t/key-path-expressions-as-functions/19587 "Key Path Expressions as Functions")

**3. Patrick Pijnappel** 提出了为 [non-open 类实现详尽模式匹配](https://forums.swift.org/t/pitch-exhaustive-pattern-matching-for-non-open-classes/52718 "Exhaustive pattern matching for non-open classes")的建议。

由于现在区分了开放类和非开放类，非开放类层次结构应该能够完全匹配。对于添加新子类，不需要添加任何语法就可以完成。

**4. Guillaume Lessard** 提出了对[指针可用性](https://forums.swift.org/t/pitch-pointer-usability-improvements/52736 "Pointer Usability Improvements")的改进。

该提案为 `UnsafePointer`、`Mutable` 和 `Raw` 引入了一些 quality-of-life 改进。

1. 添加 API 获取一个 `UnsafeRawPointer` 实例，这是一个从起点推进到给定对齐的实例
2. 在给定 `UnsafePointer<T>` 的情况下，添加一个 API 获取指向聚合的存储属性的指针 T
3. 将`Unsafe[Mutable]Pointer` 未选中的下标重命名为包含 `unchecked` 标签
4. 添加比较任意两种类型的指针的能力

**5. Pavel Yaskevich** 提出了改进[相同类型约束语法](https://forums.swift.org/t/pitch-light-weight-same-type-constraint-syntax/52889 "Light-weight same-type constraint syntax")的建议。

为了实现改进泛型 UI 的目标，我们提出几项改进措施，为了解决协议和泛型类型之间的语法差距，在**关联类型**和**泛型类型**参数相同类型的约束上，隐藏了一些复杂性（视觉上和认知上）。

**6. Holly Borla** 开始讨论如何[简化引入泛型参数的学习曲线](https://forums.swift.org/t/discussion-easing-the-learning-curve-for-introducing-generic-parameters/52891 "Easing the learning curve for introducing generic parameters")。

Swift 的泛型系统具有很强的表达能力，但是要理解具有相关类型的协议、带有 where 子句的泛型签名以及其他泛型特性的完整通用性，是将泛型引入 Swift 项目的一个重大障碍。泛型系统的主要目标是通过改进在 Swift 中编写泛型代码的人体工程学，将具体API抽象为泛型API的学习曲线。本次讨论目的是就实现这一目标的可能方向征求意见，并收集在社区中提出的其他想法。欢迎在文末留言提出问题、评论和想法！

本帖中的许多想法都是由 **@Joe_Groff** 在[改进泛型 UI](https://forums.swift.org/t/improving-the-ui-of-generics/22814 "Improving the UI of generics") 中提出的。

**7. Nate Cook** 提出了一个[用于字符串处理的字符类](https://forums.swift.org/t/pitch-character-classes-for-string-processing/52920 "Character Classes for String Processing")的想法。

[声明性字符串处理概述](https://forums.swift.org/t/declarative-string-processing-overview/52459 "Declarative String Processing Overview")讲述了正则表达式支持的匹配，但没有关于语法和语义的详细信息，将澄清留给后续介绍。

[正则表达式的文本](https://forums.swift.org/t/pitch-regular-expression-literals/52820 "Regular Expression Literals")提供了关于正则表达式语法的更多细节，例如分隔符和 `PCRE-syntax` 内部结构，省略了对正则表达式语义的讨论。本帖的目的旨在解决正则表达式语义的目标子集：**字符类的定义**。我们建议直接在现有的 `Character` 和 `Unicode.Scalar` 上和新提出的 API 背景下来处理。

正则表达式中的字符类包括元字符，例如匹配数字的 `\d`、匹配空格的 `\s` 和 匹配任何字符的 `.`。单个文字字符也可以被认为是字符类，因为它们至少与自己匹配，并且在不区分大小写的匹配中，与大小写切换的对应字符匹配。因此，将字符类视为正则表达式字面量的任何部分，该部分可以匹配字符串的实际组件。

## 推荐博文

[Swift 5 从零到精通 iOS 开发训练营](https://mp.weixin.qq.com/s/vjC45D5249397bfUCXfhLg)

《Swift 5 从零到精通 iOS 开发训练营》是一本从基础到 iOS 项目开发的实战教程，由资深 iOS 开发程序员珲少亲自操刀编撰而成。`文末有送书抽奖，抽奖为 Swift社区 额外福利`

[iOS UI 自动化测试原理以及在 Trip.com 的应用实践](**https://mp.weixin.qq.com/s/qM4O-wBCZgvn0oFCR7kIbA**)

来自携程 IBU 公共无线倪瑶的实战分享： iOS UI 自动化测试实战以及原理总结。

[一文带你读懂 Swift 社区最新开源的算法库](https://mp.weixin.qq.com/s/7-QlpcfhTaw4D_SmQYbmfA)

最近 Swift 社区动作频频，又是登陆 Windows，又是推出底层基础库。现在又推出了 Swift 算法库，现在让我们看看里面到底有什么内容，是否值得现在在生产中应用，面对内容丰富的 `raywenderlich/swift-algorithm-club` 是否有足够的竞争力呢。

[多角度体会 Swift 方法派发](https://mp.weixin.qq.com/s/aoQuDd58LQRSbJty5Tyjfw)

我们知道 Swift 有三种方法派发方式：静态派发（直接派发）、VTable 派发（函数表派发）、消息派发。下面我们分别从 SIL 中间语言，以及汇编的角度体会 Swift 的方法派发方式。

## 关于我们

公众号是由 Swift 爱好者共同维护，我们会分享以 Swift 实战、SwiftUI、Swift 基础为核心的技术内容，也整理收集优秀的学习资料。欢迎关注公众号：**Swift社区**，后台点击进群，联系我们获取更多内容。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">


感谢 SwiftWeekly 与我们的合作，开启 Swift 周报中文版发布之旅。周报仓库：https://github.com/SwiftCommunityRes

后续还会翻译大量资料到我们公众号，有感兴趣的朋友，可以加入我们，扫码添加微信

<img width="300" alt="fzhanfei" src="https://files.mdnice.com/user/17787/9a7911bf-75f2-40f5-866b-3171868bb92c.jpg">
