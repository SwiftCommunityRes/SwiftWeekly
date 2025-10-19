## 前言

**本期是 Swift 编辑组自主整理周报的第八十七期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

成功就是多一点的坚持，这一分钟不放弃，下一分钟就会有希望。生活的温柔，就藏在每一个日出日落里，藏在每一步的挣扎努力中！👊👊👊

> **周报精选**
>
> 新闻和社区：李乐成会见美国苹果公司首席执行官蒂姆·库克
> 
> 提案：
> 
> Swift 论坛：
>
> 推荐博文：
>

## 话题讨论

**公司推行‘企业文化’，究竟是凝聚团队的精神内核，还是控制员工的思想枷锁？**

1. 精神内核——认同感与归属感： 优秀的文化能让员工拥有共同的愿景和价值观，提升团队凝聚力和幸福感。
2. 思想枷锁——抹杀个性与创造力： 强调“统一思想”和“绝对服从”，会压抑员工的个性与批判性思维，阻碍创新。


## 新闻和社区  

### 动摇索尼独供地位，消息称三星为苹果 iPhone 18 系列在美建新厂

2025 年 10 月 16 日

报道称苹果已开始为 iPhone 18 系列相机深度布局供应链，三星电子时隔近十年将重返苹果相机图像传感器供应链，并在美国德州新建产线，预计 2027 年为苹果 iPhone 18 系列供应传感器。

该媒体指出，为配合三星的产能扩张，韩国测试合作伙伴 Doosan Tesna 本周宣布，将在 2026 年至 2027 年 3 月期间，投资 1713.83 亿韩元（现汇率约合 8.58 亿元人民币）用于采购新的测试系统，此项投资金额相当于该公司总资产的 21.77%，是一笔重大的财务承诺。

该媒体认为 Doosan Tesna 本次扩展，直接关联三星电子在得克萨斯州奥斯汀新建的图像传感器生产线，而该产线预计将于 2027 年为 iPhone 18 系列（IT之家注：苹果 2027 年应发布 iPhone 19 系列，这里尚不清楚是否为笔误）供应关键相机组件。

![](https://pics1.baidu.com/feed/c2cec3fdfc0392456ca9d272e91c3bd27c1e25c3.jpeg@f_auto?token=9e1267eb8fe923a338999991b99ee3a7)

苹果公司的供应链策略调整是促成这一变化的关键。过去，苹果 iPhone 的图像传感器一直由日本索尼独家供应。然而，据报道，由于 2023 至 2024 年间可能出现的供应延迟问题，苹果决定将三星电子纳为新的供应商，以分散风险并确保供应链稳定。对于三星而言，这是一次重大的回归，因此确保产品的高完成度至关重要，这也对下游的测试环节提出了更高的要求。

Doosan Tesna 是斗山集团旗下的半导体测试企业，它在 2022 年由斗山集团收购了韩国半导体测试公司 Tesna 后成立。该公司专门负责半导体制造后段工艺中的测试环节，主要测试产品包括相机图像传感器（CIS）、应用处理器（AP）和无线通信芯片（RF）等。

Doosan Tesna 超过 90% 的收入来自三星的晶圆代工和系统大规模集成电路（System LSI）部门，其业务与三星紧密绑定。值得注意的是，该公司此次采购的设备来自日本的 Advantest 等公司，而不再是其以往主要使用的 Teradyne 设备。

Advantest 的测试系统广泛用于 GPU、内存和 AI 处理器等高性能芯片的验证，这一转变暗示三星为苹果生产的新型图像传感器可能技术更复杂、性能更强大，需要更先进的验证流程来确保良率与品质。(来源：IT之家)

### 苹果公司正式推出M5芯片 首发3款新品

2025 年 10 月 16 日

北京时间周三晚间，苹果公司如期发布自研 M 系芯片的第五代新品，并在三台设备上首发。

![](https://pics7.baidu.com/feed/95eef01f3a292df5c928c37dc922c37035a87396.jpeg@f_auto?token=7b789b18dfab5b5f275a9e7ba99f439c)

与 9 月发布的 A19 Pro 芯片一样，M5 同样采用台积电第三代 3nm 工艺，即 N3P。

据苹果介绍，M5 芯片的 10 核 GPU，每个核心均配备神经引擎加速器，使得基于 GPU 的人工智能工作负载运行速度大幅提升——其 GPU 峰值计算性能较 M4 翻了 4 倍有余，总体图形性能相比 M4 芯片提升最多 45%。

M5 芯片的统一内存带宽也提升近 30%，从 M4 的 120GB/s 跃升至 153GB/s。

首发搭载 M5 芯片的 3 台设备，分别是 14 英寸 MacBook Pro、iPad Pro，以及 Vision Pro。芯片似乎也是这些产品最大的升级点。三款产品都是 10 月 17 日开始接受预购，10 月 22 日正式发售。

苹果介绍称，随着处理器升级，新版 MacBook Pro 在 AI 任务处理上比 M4 版本快 3.5 倍，图形性能和游戏帧率提高最高提升 1.6 倍，多线程能力也提高了 20%。存储方面，现在入门版本的用户也能选择 4TB 的 SSD。

除了芯片外，新款 14 英寸 MacBook Pro 几乎在所有其他方面都与上一代机型保持一致，包括接口、屏幕、电池等。

苹果中国商店显示，M5 版 14 英寸 MacBook Pro 售价 12,999 元起。

新款 iPad Pro 的提升点明显要更多一些。除了芯片本身的参数提升外，款 iPad Pro 的存储读写速度提升最高达 2 倍，而 256GB 和 512GB 机型起始配备 12GB 统一内存——较上一代增加 50%。iPad Pro 也支持快充功能，约 30 分钟可充 50% 的电量。

![](https://pics0.baidu.com/feed/ac4bd11373f082025d5a70883ee864fdaa641b64.jpeg@f_auto?token=fcf9e758b28f757e308f17cb763a953b)

苹果旗舰平板也搭载了自研 N1 无线网络芯片，支持 Wi-Fi 7、蓝牙 6 和 Thread 协议。蜂窝网络机型搭载苹果自研的 C1X 蜂窝调制解调器。

新款 iPad Pro 的国行起售价依然是 8999 元，256GB 和 512GB 版本为“残血版” M5 芯片（砍掉一个性能核心）。

从老款 M2 芯片升级至 M5 芯片后，Vision Pro 能够渲染的像素数量提高了 10%，同时能将刷新率提升至最高 120Hz 以减少动态模糊。电池续航也提升了 30 分钟，现支持单次充电最长 2.5 小时常规使用或 3 小时视频播放。

![](https://pics3.baidu.com/feed/38dbb6fd5266d016ca90ad73e2384b1734fa3587.jpeg@f_auto?token=777e3b2d42666d131722eb648ba8bedc)

本月初，苹果宣布将在该设备上推出实时沉浸式体育赛事。随着功能不断拓展，升级芯片也合乎逻辑。考虑到三星将在下周发布安卓 XR 竞品，这次的更新节点相当及时。

如预期那样，新 Vision Pro 也通过推出新编织头带改善用户的佩戴体验。国行商店的起售价依然是 29,999元。

![](https://pics1.baidu.com/feed/d000baa1cd11728b0359db0149ef5cdec3fd2c44.jpeg@f_auto?token=2efb4132046852d13c77fc24545087cc)

引发全球网友强烈关注的是，配备新头带的 Vision Pro 重量飙升至 750 至 800 克，而原始版本的重量为 600-650 克。知名苹果爆料人马克·古尔曼在社交媒体上表示，新 Vision Pro 明显更重但“解决了舒适性问题”。感到不可思议的网友在评论区里反驳称，设备变得更重本身就是舒适性问题。（来源：财联社）

### 李乐成会见美国苹果公司首席执行官蒂姆·库克

2025 年 10 月 15 日

10 月 15 日，工业和信息化部部长李乐成在北京会见美国苹果公司首席执行官蒂姆・库克，双方就苹果公司在华业务发展、加强电子信息领域合作等议题进行交流。部总工程师钟志红参加会见。

![](https://pics3.baidu.com/feed/f3d3572c11dfa9ecae19e10e87306913908fc1e1.jpeg@f_auto?token=dd0e953a4e3b4305d8df1b4679db0f82)

李乐成表示，中国超大规模市场和完备的产业体系，蕴含着巨大投资和消费潜力。中国将坚定不移推进高水平对外开放，大力推进“智能产业化”和“产业智能化”，为包括苹果公司在内的外资企业进一步营造良好营商环境。希望苹果公司继续深耕中国市场，积极参与中国新型工业化进程，与中国产业链上下游企业协同创新发展。

库克感谢工业和信息化部对苹果公司在华发展的支持，表示将继续加大在华投资，进一步提高对华合作层次和水平，实现互利共赢发展。工业和信息化部有关司局负责人参加会见。(来源：IT之家)

## 提案


## Swift论坛

1、讨论[未赋值变量出现神秘默认值](https://forums.swift.org/t/mysterious-default-value-for-un-assigned-variable/82670 "未赋值变量出现神秘默认值")

在这个帖子里，用户 MojtabaHs 抛出了一个令人费解的 Swift 行为：即便变量未被初始化，就能在闭包捕获后似乎“自动”拥有了一个看似默认但却不合理的值。帖子提供了一个最小重现例子：
```Swift
func foo(date: Date, action: () -> Void) -> Date {
    action()
    return date
}

var actionDate: Date!

let resultDate = foo(date: Date.now) {
    actionDate = resultDate
    print("Assigned")
}

print(actionDate == resultDate)  // false
print(actionDate)                // Optional(2001-01-01 00:00:00 +0000)  —— 一个奇怪的日期常量
```
类似现象也出现在 Int, Bool, Double 等类型上（例如打印出 0、false、0.0），而对于 String 类型则可能打印 nil。帖子作者指出，他并不认为这是设计行为，更倾向于它是一个编译器或优化层的 bug。

社区反馈与调试线索
* bbrk24 提出这可能是出于 “zero-initialization” 的行为：即未初始化的内存被视作全部 0 的比特位，而类型如 Date 内部若以 double 存储秒数，从 0 开始可能就映射为某个基准时间。对于 String 而言，全部 0 的内存在内存布局上可能正好与 nil 相符。 ￼
* jamieQ 认为问题可能与“闭包捕获在变量声明之前”有关。他在帖子里用一个 do { … } 包装示例演示：在非顶层代码里，这段异常行为被编译器捕捉为错误 —— “closure captures ‘resultBar’ before it is declared” 的错误。 ￼
* xwu (Xiaodi Wu) 指出这种未初始化访问此前在 Swift 的 “脚本模式 / 顶层代码”里就存在 bug。他表示：虽然这个行为应该被修复，但你不会在库级变量、局部变量或存储属性中看到同样问题。 ￼
* Slava Pestov 在后续回应中指出，这可能是编译器在查询“resilient struct 的存储属性”时的一处系统性问题：在某些优化 / 接口抽象场景下，编译器或 SIL 分析可能错误地认为结构体无存储属性，从而在代码生成里引入不合理假设。 ￼
* jamieQ 还提到一个更底层的问题：当值为 address-only 的 let 绑定在闭包初始化中被捕获，编译器的 DI（definite-initialization）检查可能尚不识别这种情形，从而允许未初始化使用。 ￼


总结与建议

这起现象目前被多数社区成员视为 一个 bug / 未定义行为，而非语言设计特性。其核心原因可能是编译器在优化、闭包捕获和未初始化访问分析之间的错判，尤其在处理 resilient（可演化）类型或模块接口抽象时。

关键提醒与实践建议包括：
* 避免在闭包中捕获尚未初始化的变量，尤其在顶层或脚本环境代码中更容易触发此类问题。
* 如果你在代码中遇到类似行为，应当向 Swift 项目提交 bug 报告，提供最小重现样例。
* 在安全关键代码中，尽量使用明确初始化的可选型或非可选型变量，避免依赖隐式行为。
* 在未来版本的 Swift / 编译器优化中，应关注这个问题是否被修复，尤其与 resilient 结构体 / 存储属性查询相关的补丁。

2、讨论[帮助理解 Approachable Concurrency 示例代码编译失败](https://forums.swift.org/t/help-with-approachable-concurrency-sample-code/82634 "帮助理解 Approachable Concurrency 示例代码编译失败")

这篇帖子的作者 ibex10 引用了 Apple 在“Swift 6.2 发布 — Approachable Concurrency”文章中的示例代码，希望理解为什么在自己的环境里编译会失败。原始示例如下：

// 在 '-default-isolation MainActor' 模式下
```Swift
struct Image {
  // 该缓存由主 actor 保护，因此认为是安全的
  static var cachedImage: [URL: Image] = [:]

  static func create(from url: URL) async throws -> Image {
    if let image = cachedImage[url] {
      return image
    }
    let image = try await fetchImage(at: url)
    cachedImage[url] = image
    return image
  }

  @concurrent
  static func fetchImage(at url: URL) async throws -> Image {
    let (data, _) = try await URLSession.shared.data(from: url)
    return await decode(data: data)
  }
}
```
ibex10 在 Xcode 中得到错误：
```Swift
Static property 'cachedImage' is not concurrency-safe because it is nonisolated global shared mutable state
```
即使自己设置了 Approachable Concurrency 为 Yes，并且启用了 Default Actor Isolation: MainActor，仍然被编译器认为 cachedImage 是非隔离（nonisolated）的共享可变全局状态，不是并发安全的。

社区反馈与排查路径
* 检查编译器 / 设置版本
EngOmarElsayed 建议检查 Swift 语言版本是否正确。后来 ibex10 发现：在命令行用 swiftc 构建时错误消失，说明 Xcode 的构建设置可能有问题。  ￼
* Strict Concurrency Checking 的作用
Dmitry Kozhinov 指出：在 Swift 6 语言模式下，SWIFT_STRICT_CONCURRENCY（严格并发检查）应始终处于 “Complete” 模式，否则编译器可能忽略相关检查。  ￼
* Xcode 与目标架构影响
Robert Ryan 提出：可能是 Xcode 针对不同目标（project / target / build setting）中 Default Actor Isolation 的设置不一致引起的问题。也有人观察到，在 Intel 机器上编译会报错，而在 Apple Silicon 机器上同样代码能编译通过。  ￼

3、提议[可等待赋值(Awaitable Assignment)](https://forums.swift.org/t/pitch-awaitable-assignment/82627 "可等待赋值(Awaitable Assignment)")

这个提议提出了一个对 Swift 并发模型中 跨隔离域赋值语句 的语法改进建议，目的是让 await 在赋值操作中的使用更一致、更直观。

核心内容

目前在 Swift 中，对于跨隔离域（例如从非隔离上下文对 actor 隔离属性赋值）时，不能直接写：

await self.storage = produceValue()

即使语义上是异步获取右侧值并赋给左侧属性，在非隔离上下文中访问隔离属性（包括 setter）受到限制。论坛中举例：
```Swift
@concurrent
func produceValue() async -> Int {
  0
}

class AsyncTest {
  var storage: Int = 5

  subscript(index: Int) -> Int {
    get { 0 }
    set(newValue) { }
  }

  func performAssignment() async {
    await self.storage = produceValue()
    await self[0] = produceValue()
  }
}
```
上面这段在当前模型下是允许的（因为 self.storage = produceValue() 会被视为先 await 再赋值）。但在 @MainActor 隔离的类中，从非隔离 nonisolated 方法中尝试同样写法就会报错：
```Swift
@MainActor
class IsolatedTest {
  var storage: Int = 5

  subscript(index: Int) -> Int {
    get { 0 }
    set(newValue) { }
  }

  nonisolated func performAssignment() async {
    // ERROR: Main actor-isolated property 'storage' cannot be mutated from a nonisolated context
    await self.storage = produceValue()
    await self[0] = produceValue()
  }
}
```
这个语法限制被视为一种可用性负担 —— 使用者不得不绕开、写成显式的 setter 方法或使用 MainActor.run 来包装赋值。

因此，提案建议移除这一限制 — 允许在这种情形下写 await prop = expr 或 await obj[key] = expr，使语法更一致，不需要手动拆成多个步骤。这个特性草案已在 GitHub 上初始化为 SE-0NNN awaitable-assignment。 ￼

优点与担忧

支持者观点：
* 这将极大提升并发代码的可读性、简洁性与 ergonomics，特别是在常见的异步赋值场景中减少样板。
* 它能消除开发者因语法限制而不得不引入额外封装（setter 方法或跳进 actor 执行上下文）的负担。tkrajacic 在帖中评论“这将是一个巨大的可用性改进”。 ￼

反对 / 保守观点：
* 核心开发者 John McCall 提出了风险担忧：允许这种语法可能鼓励开发者写 “跳岛式的修改” —— 即在不同 actor 之间零散地跨越多个赋值操作，而非将一组修改合并为原子事务（transactional changes）。他认为这种零散修改可能增加高层数据竞争的可能性。 ￼
* 此外，这并非真正改变属性或 setter 的语义，而是语法层面的糖。提案作者强调它不涉及引入异步 setter。 ￼

总结与展望

这个 pitch 是对 Swift 并发语法一致性和可用性的探索 — 在赋值语句中也能自然使用 await，减少额外语法结构，让代码更直观。

4、提议[已接受（含修改）SE-0494：为快速比较具体类型添加 `isTriviallyIdentical(to:)` 方法](https://forums.swift.org/t/accepted-with-modifications-se-0494-add-isidentical-to-methods-for-quick-comparison-to-concrete-types/82695 "已接受（含修改）SE-0494：为快速比较具体类型添加 `isTriviallyIdentical(to:)` 方法")

这个提议为 Swift 添加了一个新的实例方法，用于在常量时间内快速判断两个对象是否"显而易见地相同"，并最终以**修改后的名称**通过审核。

核心内容

该提议最初建议添加名为 `isIdentical(to:)` 的方法，但语言指导小组（LSG）在审核反馈后要求将其重命名为 `isTriviallyIdentical(to:)`。

方法功能：
- 如果两个对象可以在**常量时间**内确定为相等，则返回 `true`；否则返回 `false`
- 这是一种**性能优化检查**，用于快速识别显而易见的相同情况，而不是深度或语义比较
- 适用于需要频繁比较对象的场景，如缓存优化、记忆化（memoization）等

命名争议与最终决定

社区反馈普遍支持添加该 API，但对命名表达了担忧。LSG 最初建议重命名为 `isTriviallyIdentical(to:)`，后续社区反馈大致支持这一改动。

为什么选择 "Trivially"：
LSG 承认 "triviality"（平凡性）是一个技术性且有些模糊的概念——数学、C++ 等语言以及日常英语对它的理解各不相同，Swift 过去也特意避免使用这个术语（如 `BitwiseCopyable`）。但由于找不到更好的替代方案，`isTriviallyIdentical(to:)` 确实能传达正确的含义：既廉价又与相等性不同。

根据讨论中的解释：
- **"Trivially"** 强调这是一个**极快的、底层的、常量时间的检查**
- 它源自数学和逻辑学，指"简单且显而易见"的情况
- 相比 `isKnownIdentical(to:)`，`isTriviallyIdentical(to:)` 更能准确传达这是性能优化而非深度比较

其他决定

LSG 还决定为 `Span` 类型添加同名方法，并仍在考虑是否正式废弃现有方法，但认为这不需要进一步的演进审核。

总结

SE-0494 最终**接受并修改通过**：
- 方法重命名为 `isTriviallyIdentical(to:)`
- 也将添加到 `Span` 类型中
- 目标：为常见的对象比较场景提供常量时间的快速检查，作为性能优化手段
- 适用场景：缓存、记忆化、频繁比较等需要快速识别"显然相同"对象的情况

这是一个聚焦于**性能优化**的实用改进，通过添加底层快速检查方法来提升特定场景下的代码效率。

5、讨论[TaylorTorch：现代 Swift 封装 LibTorch](https://forums.swift.org/t/taylortorch-a-modern-swift-wrapper-for-libtorch/82630 "TaylorTorch：现代 Swift 封装 LibTorch")

TaylorTorch 是一个现代化的 Swift 封装库，旨在将 PyTorch 的 C++ 引擎（LibTorch）与 Swift 的自动微分系统相结合，提供一个纯 Swift 的深度学习框架。

项目背景与目标

该项目由 Pedro N. Rodriguez H（GitHub 用户 pedronahum）发起，灵感来源于对《Differentiable Programming》一书的深入研究。他希望复兴 Swift for TensorFlow 的愿景，但这次以 PyTorch 的成熟后端为基础。

核心特性
* Swift 风格的 API：采用协议导向设计和 Sequential 构建器，使模型构建更加符合 Swift 的编程习惯。
* 丰富的层支持：包括 Linear、Conv2D/3D、Multi-Head Attention、BatchNorm、GNN 等层。
* 图神经网络（GNN）支持：内置图神经网络组件，灵感来自 DeepMind 的 Graph Nets。
* 示例项目：提供 MNIST（图像分类）、序列到序列翻译和 Karate Club 问题（图神经网络）等示例，帮助用户快速上手。

相关资源
* GitHub 仓库：https://github.com/pedronahum/TaylorTorch
* Swift Package Index 页面：https://swiftpackageindex.com/pedronahum/TaylorTorch
* Swift 论坛讨论帖：https://forums.swift.org/t/taylortorch-a-modern-swift-wrapper-for-libtorch/82630

未来计划

目前，该项目处于实验性阶段，但未来计划包括：
* 扩展操作符支持：增加对更多操作符的支持。
* GPU/Metal 支持：实现对 GPU 和 Metal 的支持，提升性能。
* 丰富的模型库：构建更丰富的模型库，满足不同的应用需求。

## 推荐博文

[ Swift并发编程中的全局执行器详解](https://juejin.cn/post/7562024713381855242/ " Swift并发编程中的全局执行器详解")

**摘要：**  Swift全局执行器是现代并发编程的架构基石，它通过声明式语法将复杂的线程安全管理转化为清晰的领域边界定义。无论是系统提供的@MainActor还是自定义全局执行器，其核心价值在于为特定功能域建立独立的并发环境，让开发者能够用业务语言表达并发意图，而非陷入琐碎的锁管理。

这种范式转变使得UI更新、网络请求、数据存储等不同性质的操作能够自然地运行在合适的执行上下文中，既保证了线程安全，又维持了代码的可读性与可维护性。全局执行器不仅仅是技术工具，更是构建可靠并发应用的架构思维，它让开发者能够站在更高抽象层次上思考如何组织异步代码。

[SwiftUI 为什么弃用MVVM？拥抱声明式UI的新范式](https://juejin.cn/post/7560558010063618086/ "SwiftUI 为什么弃用MVVM？拥抱声明式UI的新范式")

**摘要：**  SwiftUI的声明式特性正在改变iOS开发的架构思路。随着SwiftUI日益成熟，传统的MVVM模式显得越来越冗余。声明式UI的核心是直接描述界面状态，而MVVM通过ViewModel中介管理状态的方式反而增加了复杂度。

现代SwiftUI开发更推荐简洁的架构方式——视图直接响应状态变化，业务逻辑封装在模型层。SwiftData、编程式导航等新特性都减少了对中间层的需求。实际性能测试也表明，简约架构在启动速度和运行效率上更具优势。

这不仅是技术方案的更新，更是开发思维的转变。开发者需要从“如何控制UI”转向“如何描述UI”，充分利用SwiftUI原生的状态管理机制，在保持代码简洁的同时获得更好的性能表现。

[Swift Approachable Concurrency (易用并发)](https://juejin.cn/post/7551726019867607079/ "Swift Approachable Concurrency (易用并发)")

**摘要：**  Swift 6.2引入的"易用并发"通过简化并发编程的复杂度，让开发者能更轻松地编写正确的多线程代码。其核心设计理念是默认在主线程执行代码，仅在必要时才将任务移至后台，这特别适合以UI为中心的移动应用开发。

这一特性通过三个关键机制实现：默认主线程隔离确保代码天然线程安全；nonisolated方法继承调用者线程上下文；推断隔离遵从性自动保持协议实现与类型隔离域一致。开发者可通过配置编译器标志在项目或Swift Package中启用这些功能。

在实际编码中，只需使用@concurrent标记耗时任务即可将其移至后台，其余代码默认在主线程安全执行。这种设计大幅减少了传统并发编程中的常见错误，同时保持了性能与灵活性，为从Swift 5向Swift 6过渡提供了平滑的迁移路径。

## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
