## 前言

```text
万物本末终终(In every end, there is also a beginning.)
```

这一期(200期)将是我最后一期以主要贡献者身份参与项目。我想要感谢开启这个项目的[Jesse Squires](https://twitter.com/jesse_squires)，以及相信我并接替我继续运营这个项目的[Bas Broek](https://twitter.com/BasThomas)。同样我还要感谢所有帮助撰写、审阅或提供内容的贡献者。这确实是一个社区运行的项目。谢谢！

## 播客

在Sundell 播客 Swift 的[第 110 集中](https://www.swiftbysundell.com/podcast/110/ "第 110 集")，[Tim Condon](https://twitter.com/0xTim)与[John Sundell](https://twitter.com/johnsundell)一起讨论客户端和服务端 Swift 开发人员如何利用新的内置并发系统，以及分布式和其他即将推出的语言功能如何继续下去让 Swift 在服务器上更加强大。

## 新闻和社区

六年前，即 2015 年 12 月 3 日，Swift 语言[开源](https://www.swift.org/blog/welcome/ "开源")了。

Xcode 13.2 已经发布。该版本略有下降，但具有一些显著的[Swift 特性](https://developer.apple.com/documentation/xcode-release-notes/xcode-13_2-release-notes#Swift "Swift 特性")。

[Swift Playgrounds 4 现已推出。](https://developer.apple.com/news/?id=v868vy6e "Swift Playgrounds 4")Swift Playgrounds 是学习如何编码的最佳和最简单的方法。借助 Swift Playgrounds 4，您可以使用工具直接在 iPad 上构建 iPhone 和 iPad 应用程序，并将它们直接提交到 App Store Connect。

亚马逊网络服务[宣布](https://twitter.com/awsdevelopers/status/1466476358389874704)[Swift版本的AWS SDK](https://t.co/0x27sFTE3p "Swift版本的AWS SDK")目前可以开发者预览。

[Vincent Pradeilles](https://twitter.com/v_pradeilles)发布了一段关于 Swift 标准库[的视频](https://www.youtube.com/watch?v=Ii1mDtDr3xo "Swift 标准库")。

## 提交和拉取请求

[Alejandro Alonso](https://github.com/Azoy)合并了一个删除 ICU[的拉取请求](https://github.com/apple/swift/pull/40340 "ICU")。

## 同意的提案

[SE-0331](https://github.com/apple/swift-evolution/blob/main/proposals/0331-remove-sendable-from-unsafepointer.md) 从不安全的指针类型中删除`Sendable`已被[接受](https://forums.swift.org/t/accepted-se-0331-remove-sendable-conformance-from-unsafe-pointer-types/53979 "删除 Sendable")。

[SE-0332](https://github.com/apple/swift-evolution/blob/main/proposals/0332-swiftpm-command-plugins.md) 包管理器命令插件已[接受修改](https://forums.swift.org/t/accepted-with-modifications-se-0332-package-manager-command-plugins/54074 "包管理器命令插件")。

## 正在审查的提案

[SE-0335](https://github.com/apple/swift-evolution/blob/main/proposals/0335-existential-any.md)：介绍存在 `any` 的[审查](https://forums.swift.org/t/se-0335-introduce-existential-any/53934 "any")。

Swift 中的存在类型有一个非常轻量级的拼写：类型上下文中的协议名称意味着存在类型。多年来，这已经通过引起混乱上升到**主动危害**的程度，导致程序员走上错误的道路，一旦他们遇到[值级抽象](https://forums.swift.org/t/improving-the-ui-of-generics/22814#heading--limits-of-existentials "值级抽象")的基本[限制](https://forums.swift.org/t/improving-the-ui-of-generics/22814#heading--limits-of-existentials "限制")，通常需要他们重新编写代码。该提案通过使用 `any` 明确存在类型的巨大影响。

[SE-0336](https://github.com/apple/swift-evolution/blob/main/proposals/0336-distributed-actor-isolation.md)：分布式 actor 隔离的[审查](https://forums.swift.org/t/se-0336-distributed-actor-isolation/53939 "分布式 actor 隔离")。

随着最近在语言中引入了[actors](https://github.com/apple/swift-evolution/blob/main/proposals/0306-actors.md "actors")，Swift 获得了用于编写*线程安全*并发程序的强大而基础的构建器。该提案是一系列通过*分布式 actor*的概念扩展 Swift 的 actor 运行时的提案中的第一个，让开发人员不仅可以在本地环境中，还可以在分布式环境中利用 actor 模型。

对于分布式参与者，我们承认我们生活的世界越来越多地围绕分布式系统构建，我们应该为开发人员提供更好的工具方便在这些环境中工作。我们的目标是简化和推动 Swift 中分布式系统编程的最新技术，就像我们把利用`local actors`来并发编程和`Swift's structured concurrency`方法嵌入到Swift语言中。

该提案侧重于扩展分布式actors的`actor隔离`和类型检查。

[SSWG-0018](https://github.com/swift-server/sswg/blob/main/proposals/0018-mqtt-nio.md)：MQTTNIO建议是[审查](https://forums.swift.org/t/sswg-0018-mqttnio-proposal/54004 "MQTTNIO")。

有许多 Swift MQTT 库，但很多都不是建立在 SwiftNIO 之上的。许多只支持一个版本的协议或不提供 WebSocket 或 TLS 连接。MQTTNIO 提供了所有这些。该库最近还新增了新的的 Swift 并发 API。

[SE-0327](https://github.com/apple/swift-evolution/blob/main/proposals/0327-actor-initializers.md)：关于 Actors 和初始化正在[接受第二次审查](https://forums.swift.org/t/se-0327-second-review-on-actors-and-initialization/54093 "关于 Actors 和初始化")。

针对[第一次审查 1 的](https://forums.swift.org/t/se-0327-on-actors-and-initialization/53053 "第一次审查")反馈，该提案经历了多次修改，作者总结为：

1. 与 actor 无关的 actor 初始值设定项现在允许您从 `nonisolated` 方法中执行通常可以执行的任何操作。作为交换，Swift 会自动拒绝可能不安全的存储属性的访问。这是[问题描述](https://github.com/apple/swift-evolution/blob/main/proposals/0327-actor-initializers.md#overly-restrictive-non-async-initializers)和[建议的解决方案 3](https://github.com/apple/swift-evolution/blob/main/proposals/0327-actor-initializers.md#initializers-with-nonisolated-self)。
2. Actor 的析构器不能再访问实例的不可发送的存储属性。这是[问题描述](https://github.com/apple/swift-evolution/blob/main/proposals/0327-actor-initializers.md#data-races-in-deinitializers)和[建议的解决方案 1](https://github.com/apple/swift-evolution/blob/main/proposals/0327-actor-initializers.md#deinitializers)
3. 类型的存储属性的默认值在非隔离上下文中进行评估。这是[问题描述](https://github.com/apple/swift-evolution/blob/main/proposals/0327-actor-initializers.md#stored-property-isolation)和[建议的解决方案](https://github.com/apple/swift-evolution/blob/main/proposals/0327-actor-initializers.md#global-actor-isolation-and-instance-members)
4. 不再需要定义一个 `actor` 的委托初始化器时候加上 `convenience` 关键字。这是其委托初始化程序的[问题描述](https://github.com/apple/swift-evolution/blob/main/proposals/0327-actor-initializers.md#initializer-delegation)和[建议规则](https://github.com/apple/swift-evolution/blob/main/proposals/0327-actor-initializers.md#delegating-initializers)，仍在 `Sendability` 部分。

## Swift论坛

[Evan Wilde](https://forums.swift.org/u/etcwilde) 提出了[一个建议](https://forums.swift.org/t/pitch-unavailability-from-asynchronous-contexts/53877 "@unavailableFromAsync 属性") `@unavailableFromAsync`属性。

Swift 并发模型允许任务在不同的线程上挂起和恢复。虽然这种行为允许计算资源的更高效用，但有一些令人讨厌的陷阱可能会出现在毫无戒心的程序员身上。一个陷阱是`pthread_mutex_t`从与持有锁的线程不同的线程解锁的未定义行为。跨暂停点读取和写入线程本地存储也可能导致意外行为，因为操作可能会在不同的线程上恢复。

[Tom Doron](https://twitter.com/tomerdoron)提出了[一个想法](https://forums.swift.org/t/pitch-package-manager-statically-link-swift-runtime-libraries-by-default-on-supported-platforms/53900 "静态链接 Swift")，即默认情况下在支持的平台上静态链接 Swift 运行时库。

Swift 5.3.1 引入[了在 Linux 上静态链接 Swift 运行时库](https://forums.swift.org/t/static-linking-on-linux-in-swift-5-3-1/)。使用此功能，用户可以 `--static-swift-stdlib` 在调用 SwiftPM 命令（或长格式 `-Xswiftc -static-stdlib`）时设置标志，以便将 Swift 运行时库静态链接到程序中。

在某些平台上，例如 Linux，这通常是链接程序的首选方式，因为程序更容易部署到目标服务器或以其他方式共享。

该提案探索了在此类平台上构建可执行程序时使其成为 SwiftPM 的默认行为。

[Frederick Kellison-Linn](https://forums.swift.org/u/jumhyn)[提议](https://forums.swift.org/t/swift-6-reconsider-escaping-for-optional-function-type-parameters/53932 "可选函数")重新考虑`@escaping`可选函数型参数。[
Kavon Farvardin](https://swiftweeklybrief.com/issue-200/)更新[了](https://forums.swift.org/t/pitch-2-on-actors-and-initialization/53972)关于 Actors 和 Initialization[的提案](https://forums.swift.org/t/pitch-2-on-actors-and-initialization/53972 "Actors 和 Initialization")。

由于提案与第一次审查有很大不同，所以这类似于竞标。下面是所提议的主要功能的非常非正式且不完整的摘要，以及一些指向文档本身的链接以获取更多详细信息：

1. 与actor 无关的actor 初始值设定项现在允许您从`nonisolated`方法中执行通常可以执行的任何操作。作为交换，Swift 会自动拒绝对可能不安全的存储属性的访问。这是[问题描述 2](https://github.com/kavon/swift-evolution/blob/actor-initializers-review2/proposals/0327-actor-initializers.md#overly-restrictive-non-async-initializers)和[建议的解决方案 1](https://github.com/kavon/swift-evolution/blob/actor-initializers-review2/proposals/0327-actor-initializers.md#initializers-with-nonisolated-self)。
2. Actor 的析构器不能再访问实例的不可发送的存储属性。这是[问题描述 1](https://github.com/kavon/swift-evolution/blob/actor-initializers-review2/proposals/0327-actor-initializers.md#data-races-in-deinitializers)和[建议的解决方案](https://github.com/kavon/swift-evolution/blob/actor-initializers-review2/proposals/0327-actor-initializers.md#deinitializers)
3. 如果类型的隔离与其初始值设定项不兼容，则类型的存储属性不能具有默认值。这是[问题描述](https://github.com/kavon/swift-evolution/blob/actor-initializers-review2/proposals/0327-actor-initializers.md#stored-property-isolation)和[建议的解决方案](https://github.com/kavon/swift-evolution/blob/actor-initializers-review2/proposals/0327-actor-initializers.md#global-actor-isolation-and-instance-members)
4. 不再需要定义一个`actor`的委托初始化器时候加上`convenience`关键字。这是其委托初始化程序的[问题描述 3](https://github.com/kavon/swift-evolution/blob/actor-initializers-review2/proposals/0327-actor-initializers.md#initializer-delegation)和为其委托初始化器[提出的规则 2](https://github.com/kavon/swift-evolution/blob/actor-initializers-review2/proposals/0327-actor-initializers.md#delegating-initializers),仍在`Sendability`部分。

## 推荐博文

### LeetCode 系列

[LeetCode - #11 盛最多水的容器（前100）](https://mp.weixin.qq.com/s/EGBbg43Rz79mP5LbVn8GUA)

[LeetCode - #12 整数转罗马数字](https://mp.weixin.qq.com/s/PylM9mU7K_XxeyvRyqZBUQ)

[LeetCode - #13 罗马数字转整数](https://mp.weixin.qq.com/s/QU3LR1OKqgqMhIIV_TyTzA)

[LeetCode - #14 最长公共前缀](https://mp.weixin.qq.com/s/9ClkaKPjv1zNp72NPh9-9Q)

### iOS 系列

[解决 iOS 15 上 APP 莫名其妙地退出登录](https://mp.weixin.qq.com/s/_a5DddYgQHKREi5VoEeJyg)

[使用 Swift 搭建一个 HTTP 代理](https://mp.weixin.qq.com/s/PtSVTLlnmUDMDnJB4URnHQ)

[TCA - SwiftUI 的救星？(一)](https://mp.weixin.qq.com/s/EIHVrg55ChAeDfxuxSDgeg)

[TCA - SwiftUI 的救星？(二)](https://mp.weixin.qq.com/s/67pMqZQ4FNhLns9lF_wBXg)

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的各种交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量，排名不分先后：
[张安宇@微软](https://blog.csdn.net/mobanchengshuang "张安宇")、[戴铭@快手](https://ming1016.github.io "戴铭")、[展菲@ESP](https://github.com/fanbaoying "展菲")、[倪瑶@Trip.com](https://github.com/niyaoyao "倪瑶")、[杜鑫瑶@新浪](https://weibo.com/u/3878455011 "杜鑫瑶")、[韦弦@Gwell](https://www.jianshu.com/u/855d6ea2b3d1 "韦弦")、[张浩@讯飞](https://github.com/zhanghao19920218 "张浩")、[张星宇@ByteDance](https://github.com/bestswifter "张星宇")、[郭英东@便利蜂](https://github.com/EmingK "郭英东")

周报仓库：https://github.com/SwiftCommunityRes 文章中外引链接较多，可以点击 **阅读原文** 更加方便阅读。
