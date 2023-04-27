## 前言

**本期是 Swift 编辑组自主整理周报的第十三期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

渺小不可怕，可怕的是比你优秀的强者还比你更加努力。**Swift社区**不会辜负每一位努力的勇士，优秀终将与你不期而遇！👊👊👊

> **周报精选**
>
> 新闻和社区：
> 
> 提案：
> 
> Swift 论坛：
>

## 新闻和社区


## 提案


## Swift论坛
1) 讨论[避免未使用的异步结果的可发送警告](https://forums.swift.org/t/avoiding-sendable-warning-for-unused-async-result/64633 "避免未使用的异步结果的可发送警告")
*** 内容大概 ***
有一个独立于专用actor的功能：
```Swift
@globalActor
final class SomeDedicatedActor {
    actor Actor {}
    static let shared = Actor()
}

@SomeDedicatedActor
func f() async -> [Any] {
    // ...
}
```
我们通常从与@SomeDedicatedActor 隔离的其他函数调用 f()，但我们有一个调用是我们想从不同的 actor 进行的。 我们做这个调用纯粹是为了 f 的副作用，根本不关心返回结果。 我希望以下构造是有效的，但是通过 Targeted/Complete Sendable 检查，我们会收到警告：
```Swift
@MainActor
func g() async {
    // ⚠️ Non-sendable type '[Any]' returned by implicitly asynchronous call
    // to global actor 'SomeDedicatedActor'-isolated function cannot cross
    // actor boundary
    _ = await f()
}
```
如果不使用 Swift 会忽略跨角色边界传输结果是否合理？

* 如果是这样，那么这只是一个虚假的警告，还是这个构造现在实际上是不安全的（因为该值确实强行跨越参与者边界）？
* 如果不是，是否有理由必须跨界传输结果？

*** 回答 ***
如果该值是不可发送的，它可能具有只允许在其原始 actor 中发生的 deinit 效果。 因此，忽略结果实际上必须“避免返回”actor 的结果，因为它必须在离开 actor 的隔离上下文之前销毁该值。 这对我来说似乎相当微妙，但也许它与编写一个返回非 Sendable 类型的隔离方法是一致的，因为您永远无法使用隔离之外的结果。

2) 讨论[在函数参数列表中使用 $ 进行绑定](https://forums.swift.org/t/using-for-binding-in-function-parameter-list/64645 "在函数参数列表中使用 $ 进行绑定")
*** 内容大概 ***
最近发现可以像这样在闭包参数中使用 $ 变量名：
```Swift
Bind("Title") { $title in
      TextField(title, text: $title)
}
```
然而，对于像这样的函数参数来说，同样的事情似乎是不可能的：
```Swift
func foo(title $title: Binding<String>) {
      TextField(title, text: $title)
}
```
但是编译器在函数声明处给出了一个错误：
```Swift
Cannot declare entity named '$title'; the '$' prefix is reserved for implicitly-synthesized declarations
```
*** 回答 ***
您需要在参数上使用属性包装器。
```Swift
func foo(@Binding title: String) {
  TextField(title, text: $title)
}

foo($title: .constant("R.I.P. Taylor Hawkins 🥁"))
```

3) 讨论[Task - 等待变量更改](https://forums.swift.org/t/task-awaiting-for-variable-change/64626 "Task - 等待变量更改")
*** 内容大概 ***
在使用 Task 时有一个如何解决问题的建议。
在等待 Task 内部的一些变量更改以进一步移动。
意思是说：
```Swift
Task {
  ... for example here comes some complex code that is sending requests 
   through web socket to outer world, 
   response from websocket will change the variable result on this clas 
   but out of this scope

   // with this line we are waiting for variable change with reasonable timeout
   do {
      try await @change(variable: self.result, timeout:10 sec)
   } catch {
      ... timeout
      print("we are waiting too long for server response")
   }
}
```
*** 回答 ***
您目前可以使用异步序列解决此问题。 现在的一个常见模式是执行以下操作：
```Swift
static func main() async {
  var cont = AsyncStream<Int>.Continuation!  
  let stream = AsyncStream<Int> { cont = $0 }
  let continuation = cont
  
  setupWebsocket(continuation)

  for await element in stream {
    // process the result
  }
}

func setupWebsocket(continuation: AsyncStream<Int>.Continuation) {
  // Setup the web socket and at some point call the following code
  continuation.yield(2) // Yield your result
}
```
另一件可能对这里有帮助的事情是当前正在发生的 Observation pitch，这将允许你观察类并让 Task 改变它； 然而，重要的是你需要确保一切都是线程安全的。

4) 更新[Foundation 的下一步计划 - 2023 年 4 月更新](https://forums.swift.org/t/whats-next-for-foundation-april-2023-update/64637 "Foundation 的下一步计划 - 2023 年 4 月更新")
链接：https://www.swift.org/blog/future-of-foundation/
更多相关的详细信息链接：https://www.swift.org/blog/foundation-preview-now-available/

5) 更新[Swift Evolution Dashboard支持即将推出的Feature Flags](https://forums.swift.org/t/swift-evolution-dashboard-support-for-upcoming-feature-flags/64617 "Swift Evolution Dashboard支持即将推出的Feature Flags")
Swift Evolution Dashboard 现在包括对即将推出Feature Flags的支持。

Swift 5.8 引入了使用新编译器选项启用即将推出的功能的能力：-enable-upcoming-feature 后跟即将推出的功能的名称。

这些即将到来的特征标识符被称为即将到来的特征标志或简称 UFF。
（详见 SE-0362 1）

随着Dashboard的更新，您现在可以轻松找到所有带有即将推出的功能标志的提案以及用于每个功能的标志名称。

您可以使用 Swift Evolution 仪表板来：

* 查看提案的 UFF（如果有的话）
* 按名称搜索 UFF
* 过滤以查看所有带有 UFF 的提案
* 新的 UFF 过滤器按钮与现有的搜索字段和状态过滤器结合使用。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
