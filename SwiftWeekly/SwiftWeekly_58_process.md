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

1) 提议[Unicode 规范化](https://forums.swift.org/t/pitch-unicode-normalization/73240 "Unicode 规范化")
**内容大概**
这是一个关于在Swift标准库中引入Unicode标准化功能的提案。主要内容包括：

1. 介绍了Unicode标准化的概念，包括规范等价性和兼容等价性，以及四种标准化形式（NFD、NFC、NFKD、NFKC）。

2. 解释了标准化在文本处理中的重要性，特别是在字符串比较和数据结构中的应用。

3. 指出了当前Foundation库中标准化API的局限性。

4. 提出了三个层次的新API：
   - 针对String和Character的标准化方法
   - 用于自定义存储和增量标准化的API
   - 有状态的标准化器

5. 提议添加一些辅助功能，如检查字符串是否已标准化、Unicode标量的新属性等。

6. 讨论了标准化在不同Unicode版本间的稳定性问题。

这个提案旨在改进Swift的文本处理能力，使开发者能更方便、高效地处理Unicode文本。它强调了标准化在确保字符串等价性和提高性能方面的重要作用。

2) 讨论[Quatable 实现需要很长时间进行类型检查](https://forums.swift.org/t/equatable-implementation-takes-a-long-time-to-type-check/73241 "Quatable 实现需要很长时间进行类型检查")
**内容大概**
这个讨论主要涉及Swift中Equatable协议实现的性能问题。

1. 讨论者假设底层模型是一个class，或者有其他原因无法使用自动合成的Equatable实现。

2. 有人建议将相关的状态提取到一个单独的struct中，然后依赖自动合成的Equatable实现。

3. 讨论者尝试isolate了缓慢的`func ==`实现，并对结果感到困惑：
   - 在完整项目中，Xcode报告`func ==`大约需要240-250毫秒。
   - 在干净的新项目中，同样的函数只需要120-130毫秒。
   - 将SwiftUI的Color属性改为String类型后，时间进一步减少到约60毫秒。

4. 移除属性会逐渐减少类型检查时间，但没有发现单个属性造成显著差异。

5. 这些结果在Xcode 15.4和16.0 beta 3 (16A5202i)中都相同。

6. 讨论者询问是否应该提交这个问题供进一步调查。

这个讨论突显了Swift编译器在处理复杂的Equatable实现时可能存在的性能问题，特别是在涉及SwiftUI组件时。它也反映了开发者在优化代码性能时可能遇到的困惑。

3) 讨论[从 Range 和 ClosedRange 创建 Vector 结构](https://forums.swift.org/t/create-a-vector-structure-from-range-and-closedrange/73232 "从 Range 和 ClosedRange 创建 Vector 结构")
**内容大概**
这段讨论主要涉及在Swift中创建一个通用的Vector结构，支持从不同类型的范围（Range和ClosedRange）创建向量

1. 有人建议使用UnsafeMutableBufferPointer的`allocate(capacity:)`方法来简化代码并避免使用未绑定的指针。

2. 讨论了使用自定义类型而非Array的原因，可能是为了在语句之间保持稳定的缓冲区地址。

3. 提出了一个基于协议的实现方案，定义了VectorType协议，并对Float、Double和Int类型进行了扩展。

4. 实现了一个泛型Vector结构，包含了从Range和ClosedRange创建向量的静态方法。

5. 使用了Accelerate框架中的vDSP函数来高效地生成Float和Double类型的范围。

6. 创建了一个DataBuffer类来管理底层的内存分配和释放。

7. 代码示例展示了如何创建和使用不同类型的Vector。

8. 讨论者提到代码可以进一步优化和简化，但他倾向于在代码中明确表示所有可能性。

这个实现提供了一种灵活的方式来创建不同数值类型的向量，并展示了如何利用Swift的泛型和协议来创建可重用的数学工具。

4) 提议[使用保留字符的部分应用](https://forums.swift.org/t/partial-application-using-a-reserved-character/73225 "使用保留字符的部分应用")
**内容大概**
这个讨论主要涉及向Swift语言添加部分应用（partial application）功能的提议。

1. 提议者建议引入部分应用功能，允许开发者通过预填充现有函数的部分参数来创建新函数。

2. 提出的语法使用保留字符 `$` 或 `&`，例如：
   ```swift
   let partialFoo = foo$(foo2: 5)
   ```

3. 对于没有参数名的函数，可以使用位置占位符：
   ```swift
   let partialFoo = foo$($1: 5)
   ```

4. 如果提供所有参数，将返回一个 `() -> T` 类型的函数：
   ```swift
   let partialFoo = foo$("foo", 5)
   ```

5. 这种语法在SwiftUI中可能很有用，例如：
   ```swift
   Button("Some Text", action: foo$("foo", 5))
   ```

6. 另一种建议是使用保留词，如 `partial`：
   ```swift
   let partialFoo = partial foo("foo", 5)
   ```

7. 讨论者认为这种方法可以在不改变函数调用方式的情况下实现部分应用。

8. 提到Swift 3中移除了柯里化（currying），但认为现在可以探索将某些函数式编程特性引入语言的替代方法。

9. 讨论者认为重新审视这些话题可能会产生更符合Swift当前哲学的新想法。

10. 有人提出关于weak self如何影响这种函数调用的疑问。

这个提议旨在为Swift增加更多函数式编程的特性，提高代码的可重用性和灵活性，同时保持语言的简洁性和明确性。

5) 讨论[在 Swift 协议中，您是否可以拥有一个 func 参数，它是一个协议，如果它也符合它，您可以用不同的协议定义进行交换？](https://forums.swift.org/t/in-a-swift-protocol-can-you-have-a-func-parameter-that-is-a-protocol-where-you-can-swap-out-with-a-different-protocol-definition-if-it-also-conforms-to-it/73222 "在 Swift 协议中，您是否可以拥有一个 func 参数，它是一个协议，如果它也符合它，您可以用不同的协议定义进行交换？")
**内容大概**
这个讨论主要涉及Swift协议的灵活性和类型系统。

1. 提问者想要创建一个协议，其中包含一个函数，该函数接受一个协议类型的参数，但希望能够用符合该协议的其他协议来替换这个参数类型。

2. 提供了一个示例代码结构：
   - 定义了一个顶层协议 `ApplicationState`
   - 定义了两个特定功能的协议 `UserState` 和 `FreezeState`，它们都符合 `ApplicationState`
   - 定义了一个 `Foo` 协议，其中包含一个接受 `ApplicationState` 类型参数的 `update` 函数

3. 在实现中，提问者希望能够用更具体的 `UserState` 类型替换 `ApplicationState`：

   ```swift
   struct Bar: Foo { 
     func update(_ value: any ApplicationState) { } // 符合协议定义
     func update(_ value: any UserState) { } // 理想中想要的实现
   }
   ```

4. 提问者表示可以通过类型转换 `any ApplicationState as? any UserState` 来实现目的，但希望避免在所有使用 `Foo` 协议的地方都进行类型转换。

5. 询问是否有可能直接在协议定义中实现这种灵活性。

这个问题涉及Swift的类型系统和协议的设计，反映了开发者在处理复杂类型关系时遇到的挑战，以及对更灵活的协议系统的需求。

## 推荐博文


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
