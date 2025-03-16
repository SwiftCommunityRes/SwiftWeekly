## 前言

**本期是 Swift 编辑组自主整理周报的第七十三期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

半山腰总是挤的，你得去山顶看看。像**Swift社区**一样，向前看，轻舟已过万重山！👊👊👊

> **周报精选**
>
> 新闻和社区：iOS 19 的设计大更新，是苹果对 AI OS 的押注
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

### iOS 19 的设计大更新，是苹果对 AI OS 的押注

2025 年 3 月 12 日

![](https://img.36krcdn.com/hsossms/20250312/v2_df1334f4048a4f778e2055b02e00bdc0@000000_oswg295602oswg696oswg800_img_000?x-oss-process=image/format,jpg/interlace,1)

去年的 WWDC 上，苹果为所有屏幕前的观众带来了久违的 One more thing——Apple Intelligence。 

不过一年的沸沸扬扬以后，大家都难免有些疲惫，苹果似乎也是如此，在继续推进 Apple Intelligence 的同时，苹果终于将目光转回了设计上。 

据彭博社报道，苹果公司计划于今年晚些时候对 iOS、iPadOS 和 macOS 进行重大界面设计更新。

![](https://img.36krcdn.com/hsossms/20250312/v2_766df03a28c040fdb8020883b060283b@000000_oswg51161oswg1080oswg721_img_000?x-oss-process=image/format,jpg/interlace,1)

设计的最终目的，是交互 

上一次，苹果如此对设计动大刀，是 2013 年的 WWDC。 

2013 年 6 月 10 日，苹果首席执行官 Tim Cook 站在台上宣布 iOS 7 的发布，然后聚光灯转移到刚从 Scott Forstall 手中接手软件设计的 Jony Ive 身上。 

他没有急于介绍 iOS 7，而是先谈起了自己对设计的理解： 

我认为简约、清晰与高效中蕴含着深刻而持久的美。真正的简约远非仅仅摒弃杂乱与装饰，而是要在复杂中建立秩序。

短短的一句话，几乎成为 UI 设计的金科玉律，也道出了为什么拟物化被淘汰的原因——在小尺寸的屏幕上使用拟物化设计，需要在图标中填充大量的信息，这些信息会浪费人的注意力，同时也增加了不少的辨识成本，从而导致交互的迟钝。 

而扁平化干净的线条与配色，让使用者可以迅速分辨出该图标的含义，通过简化视觉元素，让功能本身成为设计的焦点，同时，也无比契合苹果一贯「少即是多」的设计语言。

![](https://img.36krcdn.com/hsossms/20250312/v2_d0e191fd2f8f4fa6a513ce658b687fc3@000000_oswg51555oswg800oswg500_img_000?x-oss-process=image/format,jpg/interlace,1)

所以，哪怕拟物化曾是美学标杆，无论人们如何评价 iOS 7 的扁平化变革，苹果依然果断将其推入历史。 

很明显，从 iPhone 在国内兴起到 iOS 7 短短几年时间，彼时的用户对拟物化 UI 仍意犹未尽，以至于多年后，SmartisanOS 那套迟到的拟物 UI 依然被人津津乐道。 

遗憾的是，锤子也和拟物化一起，成为了时代的眼泪。

![](https://img.36krcdn.com/hsossms/20250312/v2_935c9b8212d34269a2a8662dfa5182a0@000000_oswg48463oswg752oswg564_img_000?x-oss-process=image/format,jpg/interlace,1)

时间来到现在，iPhone、iPad 与 Mac 的功能愈发复杂，功能的入口也随之变得越来越繁杂。 

举个最直观的例子，相机 App 的界面如今已近乎「窒息」。 

如果你打开照片格式或照片风格选项，取景框之外的每一寸空间几乎都被二级菜单入口占据，甚至顶部菜单还与功能选项发生了明显的重叠，让整个界面显得局促不堪。

![](https://img.36krcdn.com/hsossms/20250312/v2_b55d480b2747424899cb3bb493c5d8d6@000000_oswg79040oswg1080oswg607_img_000?x-oss-process=image/format,jpg/interlace,1)

还有一个或许更直观的例子：iPhone、iPad 与 Mac 之间的操作逻辑已逐渐分化，曾经那种无缝上手的体验，如今已不再是理所当然的事情，切换设备时的适应成本正变得越来越高。 

设计影响交互，交互决定体验，iOS 7 以来构建的 UI 体系，已经无法满足当前多设备协同的需求，而这，正是苹果无法容忍的。

![](https://img.36krcdn.com/hsossms/20250312/v2_4010a4aac1d346ea9de9322643209ca7@000000_oswg55617oswg980oswg551_img_000?x-oss-process=image/format,jpg/interlace,1)

因此，苹果决定重塑设计语言，通过更统一的视觉与交互逻辑，让不同设备之间的操作体验更加一致。 

为了达成这个目的，苹果选择 Vision Pro 作为锚点，让整体视觉风格向 visionOS 靠拢。显然，苹果仍然视 Vision Pro 为「明日产品」，并希望以其设计理念作为未来 UI 体系的基石。

![](https://img.36krcdn.com/hsossms/20250312/v2_10b549c57080419988fdef6b00609479@000000_oswg536351oswg1080oswg590_img_000?x-oss-process=image/format,jpg/interlace,1)

本次更新内容将涵盖操作系统的核心视觉元素，包括图标、菜单、应用程序、窗口样式以及系统按钮，目的是通过简化交互逻辑，让用户更便捷地使用设备。

![](https://img.36krcdn.com/hsossms/20250312/v2_a9f6f0641d854c088ae551a836dd74a8@000000_img_000?x-oss-process=image/format,jpg/interlace,1)

visionOS 随着 Vision Pro 一起问世，以空间计算为核心，强调数字内容与物理空间的有机融合，其设计原则包含三个层级： 

1. 层级感知：通过动态景深与虚实叠加，构建类似现实世界的光影层次感（如窗口悬浮高度暗示操作优先级） 

2. 物理隐喻：沿用触控直觉（如滑动、拖拽），但引入三维空间操作（物体旋转、空间缩放），降低学习成本 

3. 情境响应：界面元素会根据环境光线变化自动调整透明度和色调，确保视觉舒适度 

这套设计语言本质是将 iPhone 的平面交互升维至空间，同时保留苹果标志性的设计美学。 

很显然，目前的主流移动终端依旧是以屏幕为内容承载物，所以这套语言的大多数层级都不能照搬到 iPhone、iPad 或 MacBook 上，但其中的材质语言，是完全可以统一的地方。 

visionOS 为了与现实世界有机结合，精心挑选了一个在现实世界中存在，又可以成为虚拟世界桥梁的材质——毛玻璃。

![](https://img.36krcdn.com/hsossms/20250312/v2_e5356ab8bdda44b7877ade1d8273d2e6@000000_oswg92706oswg1080oswg791_img_000?x-oss-process=image/format,jpg/interlace,1)

毛玻璃这种材质首次出现在 iOS 7 上，系统大量使用了毛玻璃材质，将其作为扁平化设计的补充策略。 

通过高斯模糊叠加半透明层，系统界面（如控制中心、通知栏和多任务切换窗口）在保持极简视觉的同时，构建了立体层级感。 

这一设计巧妙平衡了扁平化浪潮下的信息密度问题，不仅区分信息层级，更通过虚实叠加引导用户注意力，用模糊的底层内容暗示非当前操作焦点，毛玻璃成为核心交互元素，正式成为「交互状态的可视化载体」。

![](https://img.36krcdn.com/hsossms/20250312/v2_dae13df0cdb14cc1aaab7ed8612e69ae@000000_oswg37557oswg1080oswg608_img_000?x-oss-process=image/format,jpg/interlace,1)

2014 年，随着 UIVisualEffectView 和 UIBlurEffect 等原生 API 的开放，开发者可在应用内自由实现动态模糊效果，键盘弹出时的背景虚化、文件夹展开时的层级过渡，都可以设计毛玻璃效果。 

毛玻璃逐渐从系统级控件扩展至第三方应用，成为 iOS 生态的标志性设计语言。 

而如今，在 iOS 19，毛玻璃将迎来新一轮的重塑与强化，最终可能成为三个终端设备的共同交互认知——在 iPhone、iPad 与 Mac 等基于屏幕显示的移动终端上，毛玻璃材质用于平面层级的轻量化交互； 

而在 Vision Pro 上，毛玻璃用于承载三维空间中的多窗口叠加与深度交互，本质是通过光学隐喻构建数字世界的认知框架。

![](https://img.36krcdn.com/hsossms/20250312/v2_775a8aee5b9a4cc89337687f2177717f@000000_oswg95882oswg1080oswg608_img_000?x-oss-process=image/format,jpg/interlace,1)

从现在第三方给出的概念图来看，iOS 19 甚至有将图标改为圆形的尝试，不过这种形态的可能性并不算大，因为使用完整的圆形并不符合苹果目前的主流终端设备——它们的显示屏都以矩形为主。

![](https://img.36krcdn.com/hsossms/20250312/v2_d2f9be4469504b969b9078bb88b19961@000000_oswg63865oswg1080oswg609_img_000?x-oss-process=image/format,jpg/interlace,1)

如果一切顺利的话，这套全新的系统体系将在今年 6 月的 WWDC 上与我们见面，并更新在 iOS 19、iPadOS 19、macOS 16、visionOS 3 等系统中。 

与爆料一同而来的，还有一个坏消息：此次更新仅限于交互设计方面，苹果无意合并其不同操作系统的底层架构，仍将保持 iOS、iPadOS 和 macOS 的独立性。 

一直以来呼声较高的 iPadOS 与 macOS，将继续保持独立。

苹果之所以突然对设计动刀，除了交互上的麻烦已经积重难返以外，还有另外一个因素。 

苹果一向是一家偏向保守的科技公司。相比追逐潮流，它更倾向于整合已有技术，经过精细打磨后再推出，以确保最佳的用户体验。 

但这种保守在已经形成燎原之势的 AI 时代，已经相当严重地拖了苹果的后腿。 

不仅是在国内迟迟无法落地，导致 iPhone 16 系列的 AI 体验形同鸡肋，甚至被戏称 Apple Intelligence 最直观的变化是让 iPhone 全系升级到 8GB RAM。 

即便是在已落地的海外市场，Apple Intelligence 的表现也远未达到人们的期待。

![](https://img.36krcdn.com/hsossms/20250312/v2_aed2fd7dee104873851f64f13d234c44@000000_oswg67725oswg980oswg551_img_000?x-oss-process=image/format,jpg/interlace,1)

这一切都是因为苹果将自己圈在一个自己画下的禁咒里。 

当其他厂商争相接入各种 AI API，推动智能化生态时，苹果却始终对「将用户数据交给外部服务商」持谨慎态度。 

而按照苹果一贯的传统，第三方应用在 iOS 上几乎无法获得跨应用操作的权限。这意味着，如果苹果想要构建真正系统级的 AI 生态链，唯一的选择，就是完全依赖自己的 AI。

![](https://img.36krcdn.com/hsossms/20250312/v2_6976f21e14d34dae8381d983444aea1a@000000_oswg36721oswg1080oswg579_img_000?x-oss-process=image/format,jpg/interlace,1)

但奈何，自家的 Siri 也不争气。 

Siri 本应是苹果 AI 战略的核心入口，但多年来，它的功能局限、交互僵化，逐渐沦为智能助手领域的「边缘角色」。如今，苹果想要在 AI 时代重回主导地位，必须解决一个关键问题：如何让 Siri 从「语音助手」升级为 AI 生态的核心枢纽。 

为了让 Siri 变得更聪明，苹果不得不破例引入 ChatGPT，借助第三方 AI 提供支持，同时还宣布开发一个更个性化的 Siri，这个 Siri 能深入理解用户的个人背景，并具备跨应用执行任务的能力，成为真正的 AI 助手。 

![](https://img.36krcdn.com/hsossms/20250312/v2_da8889b5e4824113be311d2719dd4109@000000_oswg67186oswg1080oswg540_img_000?x-oss-process=image/format,jpg/interlace,1)

但现实却并不乐观。 

前不久，知名爆料人 Mark Gurman 也表示，苹果自研的大语言模型进展受阻，最初打算将 LLM Siri 与 iOS 18.4 一起推出，但进展并不乐观，于是苹果推迟到了 5 月份的 iOS 18.5，而现在看来，可能 要在 2025 年 9 月推出的 iOS 19 至 2026 年 3 月的 iOS 19.4 上才能看到全新的 LLM Siri，而路透社等媒体也跟进了这条新闻。 

至于跨应用 AI 的能力，恐怕也得一并延期。 

既不愿意彻底开放生态，也无法迅速造出自己的 AI，左脚绊右脚，苹果就这么在 AI 移动端落地的路上磕磕绊绊，不知道什么时候才能跑起来。 

随着 Apple Intelligence 的推迟，消费者与投资人的信心也在悄然动摇。 

2024 年 9 月，由于 AI 相关功能延期，iPhone 销售预期下调，苹果股价单日暴跌 4.85%，创下两年半来的最大跌幅。

![](https://img.36krcdn.com/hsossms/20250312/v2_542d291d5b7d428dbec44bbaeae78658@000000_oswg185827oswg1080oswg607_img_000?x-oss-process=image/format,jpg/interlace,1)

而在竞争更加激烈的中国市场，情况更是不容乐观。 

2024 年第四季度，苹果的市场份额跌至 16.7%，排名第三，落后于华为和小米，销售额同比大跌 18%，中国市场份额的大幅丢失，导致 iPhone 在全球销量同比下滑了 5%，在全球市场的市场份额下跌 1 个百分点至 19%。 

此时，iOS 19 的更新毫无疑问是围魏救赵，能吸引很大一部分注意力，争取一些时间。

![](https://img.36krcdn.com/hsossms/20250312/v2_dcb1286afc634d03b3b37309aec8fc67@000000_img_000?x-oss-process=image/format,jpg/interlace,1)

也说得过去——毕竟，如果 AI 是改变移动终端的最终答案，Apple Intelligence 就是第一步，而操作系统，则是这一切的基石。 

既然 Apple Intelligence 还需要时间，那就在等待的时间里，做点值得期待的事。 

![](https://img.36krcdn.com/hsossms/20250312/v2_4d8e25c89c3449d19bba3658f77a2d56@000000_oswg61496oswg1080oswg608_img_000?x-oss-process=image/format,jpg/interlace,1)

不过，这个转移目光的方式，可不一定管用，短短一年时间， 苹果已经从万众期待，变成「狼来了」——用网友的话来说，之前承诺的 Apple Intelligence 还没来，又要端新的大饼上桌。

这大饼到底是真好吃，还是画饼充饥，就不好说了。

### Siri新功能“拖后腿” 苹果公司智能家居中枢被推迟

2025 年 3 月 12 日

![](https://pics4.baidu.com/feed/d62a6059252dd42a62dad44fa245dcbacbeab895.jpeg@f_auto?token=0aaf660e86b4e77ef12b6b8dc5e67967)

3 月 10 日消息，苹果公司近日宣布，2024 年承诺推出的“更具个性化”版本的 Siri 将推迟推出。知名科技记者马克·古尔曼称，这一延迟也导致苹果公司计划推出的智能家居中枢发布时间延后。

苹果公司在声明中表示，升级版 Siri 功能是其更广泛的苹果智能（Apple Intelligence）套件的一部分，“实现这些功能所需的时间比我们预想的要长”，预计将在“未来一年”内推出。

由于苹果智能家居中枢依赖于 Siri 的新功能，所以其推出也被推迟。

马克·古尔曼此前曾报道，苹果智能家居中枢设备最早可能在 2025 年 3 月发布。据悉，该设备将配备一块6英寸的触摸屏，可安装在墙上，用于视频通话和管理智能家居设备，主要通过语音控制。

苹果公司在智能家居领域早有布局，2014年就发布了智能家居平台 HomeKit，支持该协议的智能家居产品可通过 iPhone、iPad、Apple TV、HomePod 控制，也能使用 Siri 语音助手控制。

然而，在日益激烈的智能家居市场竞争中，面对一众竞争对手，苹果公司试图通过升级 Siri，为用户带来更先进的语音交互体验，进而提升其智能家居产品的竞争力。此次 Siri 升级延迟，或许是苹果公司在追求更高级别的对话能力、重新定义人机交互模式过程中，遇到了技术挑战。

截至发稿，苹果公司尚未对智能家居中枢的具体细节及后续计划作出进一步说明。（来源：GPLP犀牛财经）

## 提案


## Swift论坛
1) 提议[values的交换性观察](https://forums.swift.org/t/pitch-transactional-observation-of-values/78315 "values的交换性观察")

在 Swift 论坛的提案“values的交换性观察”中，提出了一个新的机制，旨在通过可组合的 @Observable 数据源，提供一个 AsyncSequence，以便安全、简洁地观察模型的变化。该机制在第一个 willSet 时启动事务，并在事务结束时于第一个一致性点发出值，与 Swift 并发性进行交互。

此提案的动机在于，虽然最初的观察工具与 SwiftUI 无缝集成，但其目标更为广泛。通过引入一个闭包初始化的 Observed 类型，作为一个序列来跟踪闭包返回的值，当闭包中的某些内容发生变化时，该序列会发出新值。这使得编写异步序列来跟踪变化变得简单，同时确保访问在并发性方面的安全性。

例如，考虑一个使用 @Observable 标记的简单 Person 类型，其中包含 firstName 和 lastName 属性，以及一个组合属性 name。通过创建一个 Observed 异步序列，可以在每次更新 name 属性时获取新值。此外，如果 Person 类型包含一个可选的 Pet 属性（同样使用 @Observable 标记），则可以创建一个更复杂的表达式，在 person 或其 pet 发生变化时，异步序列会发出相应的问候语。

这一提案为非 SwiftUI 系统提供了与 SwiftUI 相同级别的“恰到好处的魔法”，使开发者能够避免在确保 UI 随值变化而更新时所固有的复杂性。

2) 提议[解除函数调用中显式专门化的限制](https://forums.swift.org/t/pitch-lifting-restriction-on-explicit-specialization-in-function-calls/78231 "解除函数调用中显式专门化的限制")

在提案中，建议解除当前对函数调用中显式类型专门化的语法限制。目前，Swift 不允许在调用泛型函数时显式指定类型参数，开发者需要通过传递元类型参数或依赖类型推断来实现。例如，对于一个解码函数，通常需要传递类型的元类型参数：
```Swift
func decode<T>(_ type: T.Type, from data: Data) throws -> T
```
调用时需要提供 MyType.self，这对于新手来说可能并不直观。提议允许在函数调用中直接指定类型参数，如：
```Swift
let value = decoder.decode<MyType>(from: data)
```
这种语法在其他编程语言（如 C++、Java、Rust、C#）中已被广泛采用。Haskins 还提交了一个实验性的拉取请求，展示了解除此限制的可行性。

总而言之，这一提案旨在使 Swift 的泛型函数调用更加直观，减少对类型推断的依赖，提高代码的可读性和可维护性。

3) 提议[宣布成立测试工作组](https://forums.swift.org/t/announcing-the-testing-workgroup/78336 "宣布成立测试工作组")

在 Swift 论坛的公告“宣布成立测试工作组”中，Stuart Montgomery 宣布成立一个新的 Swift 测试工作组，旨在指导 Swift 代码的测试体验、库和工具的发展。该工作组由 Swift 测试的核心贡献者和社区中倡导质量与测试工具的成员组成。有关该工作组的章程、成员以及参与方式的详细信息，请参阅 Swift.org 上的测试工作组页面。  ￼

创建测试工作组的想法最初出现在语言指导小组去年夏天审查测试愿景文档期间，并在其批准公告中提到：

	将创建一个新的 Swift 测试工作组，负责监督 Swift 项目内的测试工作，最终归属于生态系统指导小组。

总而言之，Swift 测试工作组的成立标志着 Swift 社区在提升代码质量和测试工具方面迈出了重要一步，期待更多开发者的参与和贡献。

4) 提议[在 Linux 上的 Swift System 中支持 io_uring](https://forums.swift.org/t/pitch-io-uring-support-in-swift-system-on-linux/78340 "在 Linux 上的 Swift System 中支持 io_uring")

“在 Linux 上的 Swift System 中支持 io_uring”中，提议为 Linux 的 io_uring 提供一个低级 Swift API，以解决可伸缩性和线程池枯竭问题。  ￼

io_uring 是 Linux 于 2019 年引入的异步和批量系统调用解决方案，特别关注 IO 操作。传统的 Unix 平台主要使用同步文件 IO 系统调用，例如 read(2)，这在高并发场景下可能导致内存和 CPU 开销增加。io_uring 通过允许批量提交和完成 IO 操作，减少了系统调用的开销，提高了性能。

提案中介绍的 IORing 结构体提供了以下功能：
* 注册和注销资源（文件和缓冲区），这是一种 io_uring 特有的高效处理文件描述符的方式。
* 注册和注销事件文件描述符（eventfd），允许异步等待完成事件。
* 将 IO 请求加入队列。
* 从队列中取出已完成的 IO 操作。

此外，IOResource<T> 类表示注册的文件描述符和缓冲区，IORequest 结构体表示可以加入内核执行的 IO 操作。这些设计旨在使 Swift 开发者能够直接或通过中间层（如 Swift NIO）利用 io_uring 的优势，从而提升在 Linux 服务器上的可伸缩性和效率。

该提案旨在通过在 Swift System 中引入对 io_uring 的支持，提升 Swift 在 Linux 平台上的异步 IO 能力，满足高性能和高并发应用的需求。

5) 提议[UTF8Span——对连续字节的安全 UTF-8 处理](https://forums.swift.org/t/se-0464-utf8span-safe-utf-8-processing-over-contiguous-bytes/78307 "UTF8Span——对连续字节的安全 UTF-8 处理")

在 Swift 论坛的提案“SE-0464: UTF8Span: Safe UTF-8 Processing Over Contiguous Bytes”中，提出了引入 UTF8Span 类型，以便在连续内存中高效且安全地处理 UTF-8 编码的数据。  ￼

UTF8Span 旨在提供一种轻量级的视图，使开发者能够直接在连续的 UTF-8 编码字节上进行操作，而无需将其转换为 String 类型。这对于需要处理大量文本数据且关注性能的应用程序尤为重要。

该提案目前正处于审查阶段，审查期从 2025 年 3 月 5 日开始，至 2025 年 3 月 19 日结束。社区成员被鼓励在此期间提供反馈，以改进该提案并决定其在 Swift 中的未来方向。

总而言之，UTF8Span 的引入将为 Swift 开发者提供一种高效且安全的方式来处理连续内存中的 UTF-8 数据，提升文本处理的性能和灵活性。

## 推荐博文

[Swift 编译器入门](https://theswiftdev.com/the-swift-compiler-for-beginners/ "Swift 编译器入门")

**摘要：** 这篇文章介绍了如何使用Swift编译器（swiftc命令）构建可执行文件，并深入探讨了编译和链接的过程。文章首先展示了如何编译一个简单的Swift源文件，并生成可执行文件。接着，讲解了如何使用Swift编译器的各种参数（如-D DEBUG）来控制编译过程，添加自定义编译标志。对于多个Swift源文件，文章说明了如何将它们一起编译成单个二进制文件。

在编译过程中，swiftc命令将源文件转换为中间的目标文件（.o文件），然后使用链接器（ld命令）将这些目标文件和库文件链接成最终的可执行文件。文章还解释了静态链接和动态链接的概念，静态链接会将代码直接复制到最终的二进制文件中，而动态链接则在运行时解析库。

文章最后介绍了编译过程中的低级命令和步骤，帮助读者理解编译器和链接器如何协同工作，以生成最终的可执行文件。通过了解这些基础，开发者可以更好地理解程序构建的背后工作原理。

[Swift 编程模式](https://juejin.cn/post/7481580233645572122/ "Swift 编程模式")

**摘要：** 这篇文章探讨了Swift编程语言中的面向对象编程（OOP）和函数式编程（FP）两种范式，并通过具体示例展示了它们的应用和差异。函数式编程通过高阶函数如map()和filter()，提供了更高的抽象层次，避免了命令式编程中的状态管理问题，代码更简洁。面向对象编程则通过封装、继承和多态等特性，将代码组织为对象和类的层次结构，但可能存在过度依赖继承和类层次复杂的问题。

Swift支持多种编程范式，枚举、结构体和类都可以定义属性、方法和初始化器，且枚举和结构体是值类型，类是引用类型。协议和扩展为面向协议编程（POP）提供了强大支持，允许开发者定义行为规范而不依赖具体的类层次结构。文章还提到Swift在并发编程方面的劣势，并尝试通过改进parallelMap等函数来实现线程安全。

文章通过编程练习帮助读者巩固对Swift中OOP和FP的理解，展示了如何在实际开发中选择合适的编程范式。Swift的灵活性和对多种编程范式的支持使其成为现代iOS开发的强大工具。

[Swift 编译器优化技术：WMO](https://zhuanlan.zhihu.com/p/500171634/ "Swift 编译器优化技术：WMO")

**摘要：** 这这篇文章详细介绍了Swift编译器中的**全模块优化（Whole-Module Optimization, WMO）**技术，并探讨了其对程序性能的提升作用。WMO通过将整个模块作为一个编译单元进行优化，能够显著提高程序的运行效率，通常可以带来2到5倍的性能提升。文章首先解释了相关的术语，如翻译单元、模块、类型检查等，接着深入探讨了WMO的工作原理和实现方式。

WMO与传统的单文件编译模式不同，它允许编译器在整个模块范围内进行优化，如函数内联、类型推断、无用代码去除等。文章还比较了WMO与**链接时优化（LTO）**的区别，指出WMO是在模块级别进行优化，而LTO则是在整个程序范围内进行跨模块优化。

最后，文章通过Xcode的编译流程和Swift驱动器的实现细节，展示了WMO如何在实际编译过程中发挥作用，并解释了其与增量编译、多线程编译等技术的结合方式。WMO的引入使得Swift编译器能够在保持高效编译的同时，提供更强大的优化能力，从而提升应用程序的性能。


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
