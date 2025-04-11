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
1) 提议[Swift对WebAssembly支持的愿景](https://forums.swift.org/t/pitch-a-vision-for-webassembly-support-in-swift/79060 "Swift对WebAssembly支持的愿景")
该提案由 Swift 团队成员提出，旨在描绘 Swift 支持 WebAssembly（Wasm）的一种长远蓝图，并鼓励社区就 Swift 在这一新兴生态系统中的角色展开讨论。

背景与动机：
WebAssembly 是一种为可移植性、高性能和安全性而设计的中间语言，已经从仅限于浏览器的运行环境扩展到服务器端、边缘计算、插件系统等领域。Swift 作为一种强大、安全的编程语言，其扩展到 WebAssembly 平台将带来以下优势：
- 实现真正的跨平台支持（包括网页、嵌入式、服务器）
- 拓展 Swift 在插件和工具链开发中的适用性
- 为 Swift 提供在现代模块化系统（如组件模型）中的定位

愿景目标概述：
- 支持WASI（WebAssembly System Interface）：这是一个标准化的系统接口，使 Wasm 模块可以安全地访问文件系统、环境变量等资源。Swift 需要在编译器、标准库等层面支持 WASI ABI。
- 优化Swift编译器以生成高效的Wasm代码：例如处理内存布局、优化函数调用、错误处理等。
- 实现“组件模型”支持：组件模型是 Wasm 的新兴标准，它支持模块组合、语言间互操作、强类型接口等。Swift 若能导出/导入组件，将极大提高其在多语言系统中的整合能力。
- 支持Swift包管理器（SwiftPM）构建Wasm目标：使开发者可以像为其他平台构建 Swift 包一样，为 Wasm 构建目标，简化开发流程。
- 开发者体验的提升：例如提供更好的错误信息、调试支持、工具链集成（如Xcode、LLDB调试器）等。

潜在应用场景：
- 将 Swift 代码编译为 Web 应用中的 WebAssembly 模块
- 使用 Swift 编写插件，在宿主应用（如使用 Wasm 的文本编辑器、IDE 等）中加载执行
- 在构建工具或 DevOps 工具中使用 Swift 写任务脚本，并部署在 Wasm 虚拟环境中执行（确保隔离性与安全性）

现有工作基础：
- Swift 已能通过 SwiftWasm 项目编译为 Wasm，并有早期 WASI 支持；
- SwiftPM 和标准库的模块化为组件模型的未来集成奠定了基础；
- Swift 编译器的多目标架构已为添加 Wasm 后端提供技术可能。

呼吁与未来方向：
作者呼吁社区参与进来，共同推动 Swift 对 Wasm 的支持，例如贡献提案、工具、反馈使用场景。官方团队计划逐步完善底层支持，并探索 Swift 在 Wasm 组件生态中的角色。

2) 提议[简化 Swift 中抛出和异步函数的影响](https://forums.swift.org/t/pitch-simplifying-effects-of-throwing-and-asynchronous-functions/78996 "简化 Swift 中抛出和异步函数的影响")
提出了在 Swift 中引入新的关键字，以简化同时具有抛出（throws）和异步（async）效果的函数的声明和调用。具体而言，建议引入以下关键字：

- trawait：作为 try await 的简写，用于调用可能抛出错误的异步函数。
- thrasync：作为 async throws 的简写，用于声明既异步又可能抛出错误的函数。
- rethrasync：作为 async rethrows 的简写，用于声明异步函数，其错误由调用者处理。

这些新关键字旨在提高代码的可读性和一致性，减少开发者在编写和阅读代码时的认知负担。此外，提案还建议在未来的语言模式中，通过启用 SimplifiedFunctionEffects 特性标志，逐步弃用现有的 try await 和 async throws 语法，以推动社区采用更简洁的表达方式。

3) 提议[Swift 中的多生产者单消费者异步通道提案](https://forums.swift.org/t/pitch-multiproducersingleconsumerasyncchannel/78932 "Swift 中的多生产者单消费者异步通道提案")
提出了一个新类型 MultiProducerSingleConsumerAsyncChannel<Element>（简称 MPSC 通道），旨在提供一种强大、灵活且类型安全的异步通信机制，用于多个生产者发送数据到单个消费者，支持背压控制、资源管理以及高并发。

提案背景

目前 Swift 的 AsyncStream 和 AsyncChannel 等类型虽然支持异步流处理，但：
- AsyncStream 的生产者接口 (AsyncStream.Continuation) 通常只允许一个生产者；
- 缺乏清晰的“所有权”语义（谁负责关闭流、处理终止等）；
- 不支持精细控制的缓冲机制或背压策略；
- 不利于构建多个生产者协同向同一消费者发送数据的场景。

因此，提出一种 支持多个生产者、单个消费者、具备完整生命周期管理和缓冲控制的异步通道 类型，类似于 Rust 中的 mpsc、Kotlin 的 Channel 或 Swift Concurrency 未来规划的 AsyncChannel。

核心结构与功能

声明方式：

```Swift
let (consumer, producer) = MultiProducerSingleConsumerAsyncChannel.makeChannel(
    Element.self,
    buffering: .bounded(max: 10)
)
```
支持三种缓冲方式：

- `.bounded(max: N)`：固定大小缓冲；
- `.unbounded(initial: N)`：初始容量后自动增长；
- `.byEstimatedBytes(max: N)`：根据估算内存字节数控制背压。

Producer 接口

```swift
await producer.send("value") // 异步发送一个值
await producer.finish()      // 终止发送
```

支持并发使用、取消时抛出错误。

Consumer 接口

```swift
for await value in consumer {
  print("received:", value)
}
```

支持迭代、手动消费、提前终止。

示例代码

多个生产者：

```swift
let (consumer, producer) = MultiProducerSingleConsumerAsyncChannel.makeChannel(Int.self)

Task {
  for i in 0..<10 {
    await producer.send(i)
  }
}

Task {
  for i in 100..<110 {
    await producer.send(i)
  }
}

Task {
  for await val in consumer {
    print("Got value:", val)
  }
}
```

带缓冲控制：

```swift
let (consumer, producer) = MultiProducerSingleConsumerAsyncChannel.makeChannel(
    Int.self,
    buffering: .byEstimatedBytes(max: 1024 * 1024)
)
```

---
生命周期管理

- 消费者取消时生产者会收到 `CancellationError`；
- 所有生产者关闭后消费者自动完成；
- 支持作用域自动清理。

---

应用场景

- UI 多源事件整合；
- 网络数据流合并；
- 多任务数据采集系统；
- Actor 模型消息管道。

---

总结

这个提案为 Swift 并发系统引入了关键的通信构建块，能够以类型安全、可控的方式连接多个生产者与一个消费者，具备丰富的缓冲策略与生命周期管理能力。

4) 讨论[Xcode 16.3 中无法在异步函数中使用 FileManager 的 enumerator(at:) 的 makeIterator 方法](https://forums.swift.org/t/xcode-16-3-cant-use-makeiterator-via-filemanagers-enumerator-at-in-async-function/78976 "Xcode 16.3 中无法在异步函数中使用 FileManager 的 enumerator(at:) 的 makeIterator 方法")
在 Xcode 16.3 中，开发者发现无法在异步函数中使用 FileManager 的 enumerator(at:) 方法返回的 DirectoryEnumerator 的 makeIterator 方法。这是由于 NSEnumerator 的 Sequence 遵循在 Swift Concurrency 中被标记为不兼容，导致在异步上下文中使用时编译器报错。

问题背景

开发者在使用自定义执行器的 Actor 中调用 FileManager 的 enumerator(at:) 方法，并在异步函数中使用其返回的 DirectoryEnumerator 进行目录遍历。然而，升级到 Xcode 16.3 后，编译器报错，提示无法在异步上下文中使用 makeIterator 方法。

技术分析

在 Swift 5.10 中，NSEnumerator 的 Sequence 遵循被标记为 @available(*, noasync)，意味着其 makeIterator 方法在异步上下文中不可用。此外，NSEnumerator 也被标记为 @unchecked Sendable，进一步限制了其在并发环境中的使用。这导致在异步函数中直接使用 DirectoryEnumerator 的 makeIterator 方法会导致编译错误。

解决方案

为了绕过这一限制，开发者可以创建一个自定义的 Sequence 类型，手动包装 DirectoryEnumerator，并实现自己的迭代器，从而避免直接调用被标记为 noasync 的 makeIterator 方法。

示例代码：自定义迭代器
```Swift
struct DirectoryIterator: Sequence {
    let enumerator: FileManager.DirectoryEnumerator

    func makeIterator() -> AnyIterator<Any> {
        AnyIterator {
            enumerator.nextObject()
        }
    }
}

await Task {
    guard let enumerator = FileManager.default
        .enumerator(at: .applicationDirectory,
                    includingPropertiesForKeys: [.pathKey],
                    options: .skipsSubdirectoryDescendants) else { return }

    for case let path as URL in DirectoryIterator(enumerator: enumerator) {
        print(path)
    }
}.value
```
通过这种方式，编译器不再将 makeIterator 识别为异步上下文中的调用，从而避免了编译错误。

简化方法：使用类型擦除

另一种更简洁的方法是利用类型擦除，将 enumerator 包装为 AnySequence，从而避免直接调用 makeIterator：
```Swift
for case let path as URL in AnySequence(enumerator) {
    print(path)
}
```
这种方法同样可以绕过编译器的限制，且代码更为简洁。

⸻

注意事项

虽然上述方法可以绕过编译器的限制，但需要注意的是，这些方法并未解决 NSEnumerator 在并发环境中的潜在线程安全问题。因此，在使用这些方法时，仍需确保在适当的线程或队列中执行，以避免潜在的并发问题。 ￼

⸻

总结

在 Xcode 16.3 中，NSEnumerator 的 Sequence 遵循被标记为不兼容 Swift Concurrency，导致在异步函数中使用 FileManager 的 enumerator(at:) 方法时出现编译错误。通过自定义迭代器或使用类型擦除的方式，可以绕过这一限制，实现目录的异步遍历。然而，开发者仍需注意潜在的线程安全问题，确保在适当的上下文中使用这些方法

5) 讨论[泛型函数中的 Typed throws 不推断错误类型](https://forums.swift.org/t/typed-throws-do-not-infer-type-in-generic-type-throwing-functions/79036 "泛型函数中的 Typed throws 不推断错误类型")

在 Swift 中，开发者发现当使用泛型函数并指定 throws 的错误类型时，编译器并不会自动推断闭包中抛出的错误类型，导致类型不匹配的编译错误。

问题背景

开发者尝试定义一个泛型函数 withSingleTaskInThrowingTaskGroup，该函数接受一个抛出特定错误类型的异步闭包，并期望整个函数只抛出该特定错误类型。然而，在使用该函数时，编译器报错，提示抛出的表达式类型为 any Error，无法转换为指定的错误类型。 ￼

⸻

技术分析

在 Swift 6 模式下，编译器不会自动推断闭包中抛出的错误类型，除非在闭包签名中显式指定 throws(特定错误类型)。这意味着，如果在闭包中使用 throw 抛出错误，但未在闭包签名中指定错误类型，编译器会将其视为抛出 any Error，从而导致类型不匹配的编译错误。 ￼

⸻

解决方案

为了避免编译错误，开发者需要在闭包签名中显式指定抛出的错误类型。例如：
```Swift
struct E: Error {}

func f() async throws(E) {
    try await withSingleTaskInThrowingTaskGroup(cancellationError: E()) {
        () throws(E) in
        throw E()
    }
}
```
在上述代码中，通过在闭包签名中指定 throws(E)，编译器能够正确推断闭包中抛出的错误类型，从而避免类型不匹配的编译错误。 ￼

⸻

注意事项

需要注意的是，即使在函数签名中指定了抛出的错误类型，如果在闭包中未显式指定错误类型，编译器仍然无法推断出正确的错误类型。因此，建议在使用泛型函数并指定 throws 的错误类型时，始终在闭包签名中显式指定错误类型，以确保类型一致性。

⸻

总结

在 Swift 中，使用泛型函数并指定 throws 的错误类型时，编译器不会自动推断闭包中抛出的错误类型。为了避免类型不匹配的编译错误，开发者应在闭包签名中显式指定抛出的错误类型。

## 推荐博文


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
