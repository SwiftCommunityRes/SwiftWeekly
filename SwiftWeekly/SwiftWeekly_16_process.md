## 前言

前几期周报内容是同步翻译的英文版周报，目前英文版停更，周报停滞半年多。经过多次讨论，我们决定**重启周报**，分模块整理内容同步给大家。

周报内容模块分为：**新闻**、**提案**、**Swift论坛**、**推荐博文**。初期计划每两周发布一期，欢迎志同道合的朋友一起加入周报整理。

昨日的生活与工作是否也曾迷茫？对新技术渴望突破的心是否依旧执着？**Swift社区**，为你的技术栈添砖加瓦，你，准备好了吗？

## 新闻和社区


## 提案

### 通过的提案


### 正在审查的提案


## Swift论坛
1) 提议[隔离函数Value和Sendable](https://forums.swift.org/t/pitch-isolated-function-values-and-sendable/61046 "隔离函数Value和Sendable")

2) 提议[Swift Distributed Actors (Cluster)](https://forums.swift.org/t/pitch-swift-distributed-actors-cluster/61061 "Swift 分布式 Actors (集群)")
提议动机: 在 Swift 5.7 中，分布式 Actor 被引入为名义类型。 与Actors类似，它们可以使用`distributed actor`关键字对来声明。 就它们自己而言，它们不能真正做任何事情， 所有分布式的行为比如actor的行为实际上都由给定actor类型相关联的 ActorSystem 处理。具体来说，一个actor必须声明它将与什么类型的actor系统一起使用，如下所示：
```Swift
import Distributed
import DistributedCluster
distributed actor Greeter {
    typealias ActorSystem = ClusterSystem
    distributed func hello(name: String) -> String {
        return "Hello \(name)!"
    }
}
```
这样的 Greeter 声明可以在集群分布式actors系统中使用此类。 也可以声明一个模块范围的默认分布式 actor 系统类型。有关更多信息，可以参考 [Swift Distributed Actor Runtime](https://github.com/apple/swift-evolution/blob/main/proposals/0344-distributed-actor-runtime.md) 和 [Swift Distributed Actor Isolation](https://github.com/apple/swift-evolution/blob/main/proposals/0336-distributed-actor-isolation.md) 这是大多数用户可能使用此功能的方式，如下所示：
```Swift
typealias DefaultDistributedActorSystem = ClusterSystem
```
为了避免在每个分布式actor模块中重复声明 ActorSystem 类型别名。这里提出的包提供了 ClusterSystem 的实现。
解决方案: DistributedCluster 中包括 ClusterSystem 类型，它是库的核心部分。 创建之后，它会绑定到主机/端口对并开始监听传入连接:
```Swift
@main
struct Main {
    static func main() async throws {
        let system = await ClusterSystem("FirstSystem") { settings in
            settings.endpoint.host = "127.0.0.1"
            settings.endpoint.port = 7337
        }
        
        try await system.terminated
    }
}
```

3）提议[Package Registry Authentication](https://forums.swift.org/t/pitch-package-registry-authentication/61047 "Package Registry Authentication")
在[SE-0292](https://github.com/apple/swift-evolution/blob/main/proposals/0292-package-registry-service.md)（API 规范）中提出的package registry服务可能需要对其部分或全部 API 进行身份验证，以便识别执行操作的用户并相应地授权请求。
提议动机：Web服务中常见的身份验证方法包括基本验证(authentication), access token和 OAuth。 SwiftPM 目前仅支持基本验证，这限制了它与包注册服务交互的能力。
建议的解决方案: 建议修改 swift package-registry 指令和 registry 的配置并且加入token authentication的支持。 这些更改还应确保将来可以灵活地添加其他验证方法。

4）提议[方便的 AsyncThrowingStream.makeStream 方法](https://forums.swift.org/t/pitch-convenience-async-throwing-stream-makestream-methods/61030 "方便的 AsyncThrowingStream.makeStream 方法")
在[SE-0314](https://github.com/apple/swift-evolution/blob/main/proposals/0314-async-stream.md)中介绍了 AsyncStream 和 AsyncThrowingStream，它们充当标准库提供的 AsyncSequence。
提议动机：在使用 Async[Throwing]Stream 一段时间后，我们发现一个常见的用法是将 continuation 和 Async[Throwing]Stream 传递到不同的地方。这需要将 Async[Throwing]Stream.Continuation excaping并且出传递给初始化程序的闭包。Escaping continuation使用起来不方便，因为它需要对隐式optional value进行格外的操作。
建议的解决方案：为了填补这个不足，建议在 AsyncStream 和 AsyncThrowingStream 上添加一个新的静态方法 makeStream ，它返回stream 和 continuation。

5) 讨论[围绕Swift 6 lock展开的讨论](https://forums.swift.org/t/what-does-use-async-safe-scoped-locking-instead-even-mean/61029 "围绕Swift 6 lock展开的讨论")
6) 讨论[围绕leetcode 2259 题 Remove Digit From Number to Maximize Result 展开的讨论](https://forums.swift.org/t/remove-digit-from-number-to-maximize-result/61049 "围绕leetcode 2259 题 Remove Digit From Number to Maximize Result 展开的讨论")

## 推荐博文

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
