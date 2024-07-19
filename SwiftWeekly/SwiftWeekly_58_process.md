## 前言

**本期是 Swift 编辑组自主整理周报的第五十八期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

所谓自由，并不是随心所欲，而是自我主宰。**Swift社区**心中有光，不惧路长，铅华尽洗，静待花开！👊👊👊

> **周报精选**
>
> 新闻和社区：iPhone 17 设计新动向：苹果放弃 RCC 材料
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

## 新闻和社区  

### iPhone 17 设计新动向：苹果放弃 RCC 材料

2024 年 7 月 19 日

关于 " 郭明錤称 iPhone 17 不使用节省空间的主板材料 " 这一话题，近日引发了广泛关注。根据苹果分析师郭明錤的最新消息，苹果公司已经决定在 iPhone 17 中不采用原计划的新型树脂涂覆铜箔（RCC）组件。

RCC 原本被寄予厚望，因为它能够显著减薄主板厚度，节省内部空间，使手机有机会打造更薄的机身或探索其他利用新增空间的方法。然而，苹果及其供应商在使用 RCC 方面一直面临挑战，主要是因为 RCC 在耐久性和脆弱性方面存在问题，并且无法通过苹果的严格跌落测试。

![](https://pics7.baidu.com/feed/aa18972bd40735fa9c42585f6e795abd0e240858.jpeg@f_auto?token=557d79b3ba69500ddd7251497b9f390c)

郭明錤在报告中指出，由于 RCC 无法满足苹果对品质的高标准要求，因此 iPhone 17 将不会采用 RCC 作为 PCB 主板材料。这一决策对苹果公司的产品设计和市场策略都可能产生一定影响，同时也可能为竞争对手提供市场机会。(来源：中关村在线)

### 郭明錤：苹果未追加 iPhone 16 系列订单，备货量预估 8700 万部

2024 年 7 月 19 日

7 月 19 日消息，天风证券（601162）分析师郭明錤今天发布投资简报，表示在 WWDC 2024 全球开发者之后，不时有消息称苹果公司追加 iPhone 16 系列订单，不过鉴于台积电和大立光的供应链消息，都暗示苹果并没有追加订单。

![](https://e.thsi.cn/img/846384a704a4487a)

郭明錤在投资简报中，简要附上了台积电、大立光两家苹果关键供应商的回应信息：

　　台积电：我们没有看到出货成长突然增加 (We did not see kind of unit growth suddenly increased)。

　　大立光：今年高端机型订单跟去年差不多。

　　部分供应链厂商订单追加原因分析

　　郭明錤对此认为，针对苹果下半年 iPhone 16 系列机型，部分供应商的确遇到了追加订单的情况，但从 EMS / 组装的角度看，2H24 iPhone 16 订单并没有太大变化（约 8700 万部），依旧略低于 2H23 iPhone 15 的订单量（约 9100 万部）。

　　援引郭明錤观点，台积电、大立光跟组装厂商的订单趋势若一致，则该趋势应相当具有参考性；至于某些厂商的 iPhone 16 订单增加，可能跟个别产业或零组件的特定原因有关。

　　“Apple Intelligence 推动 iPhone 16 销量”仍有待观察

　　Apple Intelligence 的推出是普遍被认为 iPhone 16 订单增加的原因。但目前 Apple Intelligence 在下半年仅提供给美国用户测试的 Beta 版，且 Apple Intelligence Siri 仅支持英语。

　　先不论是否仅凭 Apple Intelligence 就能推动换机需求 (这是另外一个很大的议题)，要消费者在 2H24 为测试版本的 Apple Intelligence 购买新款 iPhone 16 的预期或许过于乐观。(来源：IT之家)

### 消息称苹果正洽谈购买更多电影版权，以壮大 Apple TV + 片库

2024 年 7 月 18 日

![](https://pics1.baidu.com/feed/7af40ad162d9f2d35f085f87d390dc1d6227ccc3.jpeg@f_auto?token=60ae0c460a14d51820f6dd563cd777e1)

据彭博社报道，苹果公司正在积极洽谈从各大好莱坞电影公司购买更多电影版权，以扩充其流媒体平台 Apple TV + 的内容库。

知情人士称，苹果一直以来专注于为其流媒体平台制作原创内容，但现在越来越希望通过购买传统电影公司的庞大片库来扩充其服务内容。虽然《Ted Lasso》和《The Morning Show》等原创剧集取得了一定成功，但 Apple TV + 的爆款作品相对较少，Apple TV + 的片库规模与竞争对手 Netflix 和迪士尼 + 相比仍有差距。

据IT之家了解，自 2019 年 11 月上线以来，Apple TV + 一直定位为提供高质量原创内容的高端流媒体服务。尽管收获了众多奖项和好评，包括今年的 72 项艾美奖提名，但订阅用户数量仍不及竞争对手。研究机构 MoffettNathanson 的数据显示，仅有 11% 的美国家庭使用 Apple TV+，而 Netflix 的这一比例为 55%。内容库规模有限被认为是制约 Apple TV + 增长的重要因素，数据显示，拥有庞大片库的流媒体平台，如 Netflix，用户流失率更低。

为了应对这一挑战，苹果已经开始尝试购买版权。今年早些时候，苹果从好莱坞电影公司购买了约 50 部电影的版权，在美国市场上线，其中包括《贱女孩》和《泰坦尼克号》等热门影片。这些引进电影的积极反响鼓励苹果继续寻求更多合作，苹果的目标是购买更多电影版权。与此同时，华纳兄弟、探索频道和迪士尼等大型电影公司也愈发愿意出售内容给竞争对手以增加收入。(来源：IT之家)

### 苹果公司推出住房基金，支持湾区经济适用房建设

2024 年 7 月 17 日

苹果公司 7 月 17 日宣布正与旧金山住房加速器基金、Sobrato 慈善基金会和 Destination：Home 等经济适用房开发领域的专家联手推出新的湾区住房创新基金。该基金将提供有针对性的优惠贷款，推动经济适用房的开发，是苹果公司 25 亿美元大额承诺的一部分，旨在解决加州各社区的住房可负担性问题。湾区住房创新基金首期投资 5000 万美元，将支持旧金山湾区的四个项目，在未来两年内建造 400 多套住房。

苹果公司 2019 年曾表示，将提供 25 亿美元来应对加利福尼亚州的住房危机。苹果对加州的承诺包括：10 亿美元的经济适用房投资基金以及 10 亿美元的首次购房者抵押贷款援助基金，苹果拥有的 3 亿美元土地也将用于经济适用房建设。(来源：界面新闻)

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
