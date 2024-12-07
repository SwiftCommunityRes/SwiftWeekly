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
1) 讨论[代码来临 2024](https://forums.swift.org/t/advent-of-code-2024/76301 "代码来临 2024")
每年12月，Eric Wastl都会发布一系列有趣的编程挑战——Advent of Code。从12月1日至25日，每天发布一个新挑战，难度逐渐增加。参与者可以使用任何编程语言解决，但推荐用Swift进行。

参与步骤：
1.	（可选）克隆Swift模板：
 * 如果使用Xcode，打开模板目录即可开始。
 * 如果使用Swift CLI，运行swift run或swift test执行代码或测试。
2.	在Advent of Code官网创建账号（加入排行榜需要）。
3.	使用代码3315857-05237f97加入Swift社区排行榜（最多200人）。
4.	每天尝试挑战并提交Swift解决方案。排行榜将根据完成速度更新分数（仅供娱乐）。

建议将你的解决方案上传至GitHub，方便学习其他人的技巧与Swift使用方式。期待大家的参与！

2) 讨论[重试和截止期限简介：Swift 并发中的弹性](https://forums.swift.org/t/introducing-retry-and-deadline-resiliency-in-swift-concurrency/76290 "重试和截止期限简介：Swift 并发中的弹性")
过去几年，在多个 iOS 项目中处理硬件通信及协议集成，并尝试全面使用 Swift 并发。在此过程中，我开发了两个轻量级开源库：swift-concurrency-deadline 和 swift-concurrency-retry，目前已达到较为稳定的状态，可供他人使用。
主要特点：
* 使用结构化并发
* 支持 actor 隔离继承
* 支持自定义时钟（便于测试）
* 提供详尽文档与近乎 100% 测试覆盖率
* 无外部依赖，最小化二进制文件体积

:alarm_clock: Deadline
为异步操作提供截止时间控制，操作超时将抛出 DeadlineExceededError。
示例：
```Swift
try await deadline(until: .now + .seconds(5)) {  
  try await URLSession.shared.data(from: url)  
}  
```
更多文档与示例请见：[GitHub - swift-concurrency-deadline。](https://github.com/ph1ps/swift-concurrency-deadline)

:arrows_counterclockwise: Retry
为异步操作提供重试机制，可基于错误类型定制策略和重试间隔。支持多种回退策略（如指数回退）与错误处理。
示例：
```Swift
let (data, response) = try await retry(maxAttempts: 5) {  
  try await URLSession.shared.data(from: url)  
} strategy: { error in  
  if error.isRecoverable {  
    return .backoff(.exponential(a: .milliseconds(100), b: 2))  
  } else {  
    return .stop  
  }  
}  
```
更多文档与示例请见：[GitHub - swift-concurrency-retry。](https://github.com/ph1ps/swift-concurrency-retry)

欢迎尝试并提供反馈！希望这些工具能帮助构建更高弹性与可靠性的 Swift 应用。🎉

3) 讨论[将 Int32 数组转换为 Int 数组以进行整数运算](https://forums.swift.org/t/convert-arrays-of-int32-to-arrays-of-int-for-integer-arithmetic/76356 "将 Int32 数组转换为 Int 数组以进行整数运算")
该讨论围绕如何通过代码生成及分析评估性能展开，主要集中在 x86 汇编代码的生成和优化上。

生成汇编代码的方法：
1.	使用编译器命令生成：如 Swift CLI 的 -emit-assembly 参数。
2.	使用工具分析二进制文件：如 macOS 上的 otool -tvV 命令。
3.	使用在线工具：如 Compiler Explorer (godbolt.org)，查看生成的 LLVM IR 和最终汇编代码。

如何判断代码性能：
评估性能需结合经验和分析技巧，以下是关键点：
1.	无不必要的循环依赖： 确保每次循环迭代独立，避免引入延迟链。
2.	纯向量化代码： 除循环计数器外，尽量避免标量指令。关键指令如 movdqu (SIMD 加载/存储) 和 paddq (SIMD 加法) 应主导循环。
3.	避免不必要的加载和存储操作。
4.	适当的循环展开： 展开两倍循环（每次处理两个 SIMD 向量）以平衡加载、计算和存储操作的开销，接近硬件吞吐极限。

性能分析实例：
在现代 CPU 上，循环性能接近其加载和存储的理论极限（如 2 次加载 + 1 次存储/周期）。即使在旧设备上，该代码也可达到 80% 的峰值效率。进一步展开循环通常代价较高，除非数据长度非常大且固定为某个 2 的幂。

经验与总结：
评估性能需要对汇编指令集和硬件架构的深入理解。通过确保代码结构清晰、向量化充分，以及循环展开合理，便能实现高效执行，无需进一步优化。

4) 讨论[发送，输入输出发送，互斥](https://forums.swift.org/t/sending-inout-sending-mutex/76373 "发送，输入输出发送，互斥")
Swift 6 引入了新的 Mutex 类型及其相关功能，例如 withLock 方法，进一步完善并安全化了并发编程的特性。以下是对其工作原理及使用中遇到的问题的深入探讨。
withLock 方法的签名:
```Swift
func withLock<R>(
    _ body: (inout sending State) -> sending R
) -> sending R
```
* 作用：
 * Mutex 在调用 withLock 时，暂时放弃对 State 的所有权，将其以 inout sending 参数传递给闭包。
 * 闭包可以对状态进行分割，操作完成后，部分状态返回给 Mutex，成为新的保护状态，其余部分通过返回值传递给调用者。
* 关键点：
 * inout sending： 表示状态在闭包内可以被临时转移到其他隔离区域。
 * sending 返回值： 保证返回值可以安全地传递到其他隔离域。

实现自定义 Mutex 并使用 inout sending
尝试实现类似 Mutex 的类：
```Swift
class NotAMutex<State> {
    var state: State

    init(state: sending State) {
        self.state = state
    }

    func withNoLock<R>(
        _ body: (inout sending State) -> sending R
    ) -> sending R {
        body(&state)
    }
}
```
问题：
* 编译错误：
```Swift
sending 'self.state' risks causing data races
```
Swift 编译器提示此代码可能导致数据竞争，因为 self.state 是类的实例变量 (ivar)，而类的状态管理包含专有的隔离和排他性检查机制。

如何使用自定义 Mutex
以下示例尝试对非 Sendable 的状态对象进行操作：
```Swift
class NotSendable {
    var next: NotSendable?
}

func test() {
    let noMutex = NotAMutex(state: NotSendable())
    let next = NotSendable()

    // 尝试操作
    noMutex.withNoLock {
        $0.next = next
    }
}
```
错误：
* 编译器认为闭包捕获的 next 可能导致多次使用，而无法保证安全性。
* 因为 inout sending 参数在操作完成后仍需重新初始化为非隔离值。

解决方法和进一步尝试
分离隔离区域
尝试用 Optional 类型的扩展实现值的传递和分离：
```Swift
extension Optional where Wrapped: ~Copyable {
    static func take(_ self: inout sending Optional) -> sending Optional {
        switch consume self {
        case .none:
            self = nil
            return nil
        case let .some(wrapped):
            self = nil
            return .some(wrapped)
        }
    }
}
```
* 改进：
这种方法有效，但较复杂；编译器能够证明 Optional 的正确分离。
* 局限：
对于更复杂的容器（如 Array），由于内部元素可能有相互依赖，分离变得不直观且难以验证。

Mutex 的实现差异

相比自定义的 NotAMutex，Swift 6 的 Mutex 通过底层机制和优化规避了这些问题：
* 运行闭包仅执行一次： 通过 Swift 编译器保证闭包的执行模型不会导致多次捕获或别名问题。
* 非复制值的处理： 编译器能智能分析并优化 noncopyable 类型的值传递行为。

总结与建议
1.	原生 Mutex 是推荐方案：
通过原生 withLock 方法，可安全操作并发状态，而无需手动处理复杂的隔离区域拆分问题。
2.	使用 inout sending：
理解 sending 的语义对于编写安全并发代码至关重要。具体包括：
 * 确保闭包只运行一次。
 * 明确分离状态的生命周期和隔离域。
3.	避免对状态过度操作：
如果无法使用 Swift 6 的特性，建议在需要多次分离或复杂状态管理时简化模型或引入外部工具来帮助验证状态安全性。

5) 讨论[关于协议继承和泛型的编译器错误？](https://forums.swift.org/t/compiler-bug-w-r-t-protocol-inheritance-and-generics/76316 "关于协议继承和泛型的编译器错误？")
对于Swift中的泛型参数，协议存在自我遵守性问题。问题的核心是：协议类型（如Labeled）在作为泛型参数时，会被视为其存在性类型（any Labeled），而不是直接遵守协议。这种行为导致在某些情况下编译器报错。

当泛型参数有协议遵从性要求（如Storage<V: StorableObject>），传入协议类型会失败，因为any Labeled无法满足StorableObject的遵从性需求。而在没有遵从性约束（如AlternativeStorage<V>）时，协议类型作为泛型参数是可以接受的。

这种限制的原因与Swift的类型系统设计有关：
1.	存在性类型的语义要求：即使协议没有关联类型或静态方法，仍可能包含无法通过类型检查器验证的语义约束，例如“具有两个可能值”的协议（HasTwoValues）。
2.	类型逻辑不一致性：如果允许协议自我遵从，可能会在逻辑上引入不一致性。例如，any HasTwoValues将无法满足其语义要求。

尽管代码示例在理论上可能不会导致错误，Swift的设计选择是避免可能的语义或逻辑问题，因此协议默认不具有自我遵从性。这种行为也是SE-0335提案讨论的一部分。

## 推荐博文

[iOS 探索 RxSwift 之内存管理](https://juejin.cn/post/7159952712849702942/ "iOS 探索 RxSwift 之内存管理")

**摘要：** 这篇文章探讨了 RxSwift 的内存管理与循环引用问题，详细分析了 observe 与 observeWeakly 的区别，并通过源码揭示了 RxSwift 底层如何实现 KVO 属性监听。文章还重点讨论了循环引用的形成原因及解决方法，例如通过 [weak self] 或 unowned self 处理闭包捕获，以及正确使用 disposeBag 和 Rx 内置工具来管理对象生命周期，避免内存泄漏。

[深入理解 iOS 上的静态库、动态库、 framework 和 xcframework ](https://juejin.cn/post/7442893866724409355/ "深入理解 iOS 上的静态库、动态库、 framework 和 xcframework ")

**摘要：** 这篇文章系统地探讨了iOS开发中静态库、动态库、framework和xcframework的特性及使用场景。文章从Mach-O文件入手，详细讲解了静态库如何通过按需加载和符号优化提升性能，同时分析了符号冲突的解决办法；动态库则因其支持动态加载节省内存，但需面对启动性能和审核限制等问题。此外，framework作为标准化的二进制产物，不仅支持模块化，还能管理资源和版本；而xcframework进一步解决了跨平台和多架构支持的难题，为现代开发提供了便利。通过理解这些概念，开发者能够更好地选择三方库集成形式，优化工程结构，提升应用性能。

[Swift5.0 的 Runtime 机制浅析](https://juejin.cn/post/6844903889523884039/ "Swift5.0 的 Runtime 机制浅析")

**摘要：**  本文主要探讨了Swift 5.0中的运行时（Runtime）机制，重点分析了对象创建与销毁、方法调用机制、成员变量访问等。与Objective-C相比，Swift的运行时机制更为静态，方法调用在编译阶段就已确定，而不是在运行时动态分配，这使得Swift的执行效率更高。

在Swift中，类对象的内存布局类似于Objective-C，但方法调用和内存管理通过不同的机制实现。Swift的对象方法调用机制类似C++的虚函数调用，而Swift类的扩展方法无法在运行时进行动态替换。

此外，Swift对象的生命周期由引用计数管理，且编译时会自动插入内存分配、初始化、析构等函数，确保内存管理的高效性。对于方法调用，Swift通过虚表（vtable）实现多态，避免了运行时的动态查找方法。

## 话题讨论

**为什么现在年轻人都不爱换手机了？**

1. 经济下行，大家没钱了。
2. 手机性能过剩，用了几年都不卡。
3. 产品同质化严重，创新不足。

欢迎在文末留言参与讨论。



## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
