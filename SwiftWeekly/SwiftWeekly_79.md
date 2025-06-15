## 前言

**本期是 Swift 编辑组自主整理周报的第七十九期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

何为进步？何为强大？超越少年的你，超越去年的你。亦或者像 **Swift社区**一样，超越上周，超越昨天的自己。👊👊👊

> **周报精选**
>
> 新闻和社区：Apple 强力扩充面向开发者的工具，旨在促进创意、创新与设计的发展
> 
> 提案：SwiftPM 的警告控制设置提案已通过
> 
> Swift 论坛：讨论新的 containerization 框架
>
> 推荐博文：Apple 将密码监控服务从 Java 迁移到 Swift
>
> **话题讨论：** 
> 
> 人工智能是否应全面进入中小学课堂？
>
>**上期话题结果**

![](https://files.mdnice.com/user/47553/a22524b7-99fd-4eb2-96e4-e3647ad3c019.jpg)

高考是人生中最公平的一次机会，且是唯一一次仅用分数就能改变命运的机会。

## 话题讨论

教育部宣布将发布《人工智能教育白皮书》，推动AI 技术深度融入基础教育。与此同时，DeepSeek 等国产大模型引发教育变革讨论：**有人认为 AI 是未来竞争力核心，也有人担忧技术依赖侵蚀思维能力和教育公平，人工智能是否应全面进入中小学课堂？**

1. 赞同：AI素养是未来公民必备技能，应从中小学普及
2. 反对：基础教育应聚焦思维与人格培养，而非工具依赖
3. 中立：分层审慎推进，按学段、区域特点差异化实施

## 新闻和社区  

### 消息称苹果 Apple 智能加持新版 Siri 将跳票至 iOS 26.4 上线

2025 年 6 月 13 日

6 月 13 日消息，据彭博社报道，苹果公司旗下搭载 Apple 智能的新版 Siri 项目再次延期，预计相应功能将被延期到明年 3 月的 iOS 26.4 版本。

苹果公司最初计划在 2024 年（去年）秋季上线新版 Siri，之后相应功能跳票至 2025 年（今年）初，再延至今年 5 月（上月），而如今跳票至“明年春季”，延期了一年以上。

彭博社透露，新版 Siri 延迟的原因“主要是技术问题”，当前 Siri 采用的“混合架构”存在严重问题，该架构试图将原版 Siri 回应内容与新版 Siri 的 AI 回复内容相结合，但在测试中有三分之一的几率失败。

Swift社区注意到，相应项目进展缓慢也导致了苹果高层出现变动，苹果人工智能主管 John Giannandrea 如今被边缘化，逐渐退出 Siri 和其他面向消费者的项目。当前，新版 Siri 项目由 Craig Federighi 和 Vision Pro 项目负责人 Mike Rockwell 接手，核心技术“Siri LLM”也正在进行彻底重构。

展望未来，彭博社表示苹果的长期目标是将 Siri 打造成一个具有持续在线、对话式、主动协助能力的“数字助理”，当前苹果还在开发类似 ChatGPT 的 AI 聊天工具“Knowledge”，支持进行调用互联网信息资源。（来源：IT之家）

### iPhone 全新惊艳设计曝光 苹果前辈旗舰闻声价崩沦为百元机！

2025 年 6 月 12 日

据知名科技记者马克·古尔曼最新披露，苹果公司正秘密研发两款 20 周年纪念版 iPhone，计划于 2027 年 9 月正式发布。这两款机型分别聚焦形态创新与材质突破，旨在以渐进式革新替代 iPhone X 时代的颠覆性变革，延续苹果对工业设计的极致追求。

值得一提的是，由于 iPhone16 新机的上市，导致 iPhone15 价格持续走低。据权威科技媒体报道，iPhone15 在拍易得【www.paiyide.net】最新一期的活动中成交价仅 239 元，创下了该机上市以来的价格新低，浏览器访问拍易得官网 www.paiyide.net可获得最新详情！

![](https://doc-fd.zol-img.com.cn/t_s2000x2000/g7/M00/0B/08/ChMkK2hKl7uIFHZMAAAtHrwBscgAAtinwOzwJwAAC02742.jpg)

消息称，苹果首款折叠屏 iPhone 已进入试产阶段，预计 2026 年下半年量产，并可能随 iPhone 18 系列同步亮相。而 20 周年纪念版将搭载 7.76 英寸内屏，分辨率达 2713×1920，首次应用屏下摄像头技术，实现“无开孔”真全面屏效果。外屏则采用 5.49 英寸挖孔屏设计，兼顾便携性与多任务处理需求。技术层面，该机型通过超薄玻璃（UTG）与柔性 OLED 面板的组合，着力解决折叠屏常见的折痕与耐用性难题。（来源：中关村在线）

### 被苹果公司要求转移在华生产？消息人士：富士康将在印度投资10亿美元扩建工厂组装iPhone

2025 年 6 月 11 日

英国路透社 11 日发布一则独家消息称，中国台湾代工制造商富士康计划投资 10 亿美元，扩建其在印度南部的一家工厂，并在那里组装苹果手机。

![](https://img.huanqiucdn.cn/dp/api/files/imageDir/ebb7ce28035ddde6522f26fa06938afdu5.jpg?imageView2/2/w/1260)

报道称，这是苹果公司受困于中美贸易摩擦和疫情危机之际，悄悄渐进地将生产重心从中国转移的一部分。而此前，尚无媒体报道过这此举的规模。

两位消息人士透露，富士康在中国制造的一些苹果手机机型将转移到印度这家工厂生产。不过由于谈判是私下进行的，细节尚未敲定，这两位消息人士拒绝透露姓名。

其中一位消息人士称，根据该计划，富士康将在泰米尔纳德邦的工厂增加约 6000 个工作岗位。此外，富士康还在印度南部的安得拉邦经营着一家独立工厂，在那里为中国小米公司等生产智能手机。上月，富士康高管曾透露加大在印度的投资，但没有给出具体细节。

“苹果公司强烈要求其客户将部分手机生产搬出中国，”另一位消息人士说。

对此，富士康表示，不会对与客户相关的问题发表评论，而苹果没有回复置评请求。

据报道介绍，印度是全球第二大智能手机市场，苹果在印度智能手机销量中约占 1%。在印度，价格昂贵的苹果手机常常被视为地位的象征。

报道还援引香港“对比法”技术市场研究公司的尼尔·沙阿(Neil Shah)的分析称，由于印度的劳动力成本比中国更低，再加上在印度供应商基地的逐步扩大，苹果公司将能够把印度作为一个出口中心。

而与此同时，印度也在努力推动富士康等公司在该国进行生产制造，并于上个月启动了一项 66.5 亿美元的计划，旨在激励五家全球智能手机制造商建立或扩大在印度的生产。

企业撤离中国内地的问题，其实在疫情期间乃至更早前就有讨论。今年 2 月 10 日，商务部新闻发言人高峰在新闻发布会上表示，下一步将继续加大对外资企业的服务力度，协助外资企业积极应对疫情，有针对性地协调解决外资企业在投资、生产、经营过程中的实际问题。当月 19 日，时任外交部发言人耿爽在网上记者会上回答涉及在华外资企业情况的提问时表示，中方有关部门正在有针对性地协调解决外资企业在投资、生产、经营中遇到的实际问题，最大程度减少疫情影响，一些具备条件的在华外资企业已开始陆续复工复产。

更早前的 2019 年，国家发改委还专门发文表示，“对外国企业撤离的判断还是要基于数据和事实。”文章引用数据称，美中贸易全国委员会涵盖超过 200 家在华经营的美国企业，据其调查显示，2018 年组织内超过 90% 的美国公司在华实现盈利，87% 的美国企业 2019 年没有搬迁或者将其任何业务迁出中国的计划，83% 的美国企业过去一年没有削减或停止对华投资。(来源： 环球网)

### Apple 强力扩充面向开发者的工具，旨在促进创意、创新与设计的发展

2025 年 6 月 9 日

设备端 Apple 智能模型调用、大语言模型与 Xcode 的集成，以及贯穿 Apple 旗下各平台的优雅新设计，为开发者提供一切所需，助力其快速自如地打造出兼具美感与现代功能的 app。

![](https://www.apple.com.cn/newsroom/images/2025/06/apple-supercharges-its-tools-and-technologies-for-developers/article/Apple-WWDC25-Liquid-Glass-Icon-Composer-250609_big.jpg.large_2x.jpg)

加利福尼亚州，库比提诺 Apple 今日发布适用于开发者工具的新技术与改进，助力开发者为 Apple 旗下各个平台打造更美观、更智能、更具吸引力的 app 体验。赏心悦目的全新软件设计能够进一步凸显内容，为 iOS 26、iPadOS 26、macOS Tahoe 26、watchOS 26 以及 tvOS 261 带来更生动愉悦的体验，同时保留原有的熟悉感。基础模型框架与一整套可供开发者运用设备端智能的工具齐亮相，而 Xcode 26 现可调用大语言模型，供开发者访问 Xcode 的 Coding Tools 以及其他智能功能。

上述新资源壮大了 Apple 面向开发者提供的丰富且不断扩充的技术组合，包括超过 25 万个助力开发者将其 app 与 Apple 软硬件功能相集成的 API。这些 API 涵盖一系列广泛功能，如机器学习、增强现实、健康与健身、空间计算以及高性能图形处理。随着每一次平台发布，Apple 都会对其技术和工具进行扩充和调整，致力于协助开发者将构想转化为现实，为 Apple 旗下各个平台带来细腻丰富、响应灵敏、不断优化的体验。

“对于贯穿 Apple 旗下各平台、广受用户欢迎的体验，开发者起到了至关重要的作用。”Apple 全球开发者关系副总裁 Susan Prescott 表示，“通过提供对设备端 Apple 智能基础模型以及全新 Xcode 26 智能功能的访问，我们为开发者赋能，助力他们为全球用户打造更丰富且直观易用的 app。”

## 提案

### 通过的提案

[SE-0475](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0475-observed.md "SE-0475") **值的事务观察** 提案通过审查。该提案已在 **第七十五期周报** 正在审查的提案模块做了详细介绍。

[SE-0480](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0480-swiftpm-warning-control.md "SE-0480") **SwiftPM 的警告控制设置** 提案通过审查。该提案已在 **第七十六期周报** 正在审查的提案模块做了详细介绍。

[SE-0485](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0485-outputspan.md "SE-0485") **OutputSpan：委托连续内存的初始化** 提案通过审查。该提案已在 **第七十八期周报** 正在审查的提案模块做了详细介绍。

## Swift论坛

1、讨论[Swift SDKs for WebAssembly 现已在 swift.org 上提供](https://forums.swift.org/t/swift-sdks-for-webassembly-now-available-on-swift-org/80405 "Swift SDKs for WebAssembly 现已在 swift.org 上提供")

Swift 官方宣布现已在 swift.org 上发布适用于 WebAssembly 的 SDK，支持 Swift 6.2 及其开发版本。

* 发布了两个 SDK：一个是完整标准库版本，支持 Swift Testing；另一个是 Embedded Swift 版本，生成的 WebAssembly 二进制体积更小（如 “Hello, World!” 仅约 9.7KB）。
* Toolchain 集成了 WasmKit 工具，可使用 swift run 运行支持 WASI 的 WebAssembly 程序。未来还将支持 swift test。
* 完整 SDK 包含 Swift Testing，但 Embedded Swift 尚不支持测试框架。官方计划未来增加对 Foundation 和 XCTest 的支持。
* 帖子感谢了众多社区成员的贡献，推动了 Swift 在 WebAssembly 平台的兼容性发展。

2、讨论[SE‑0483：InlineArray 类型糖 二轮评审](https://forums.swift.org/t/second-review-se-0483-inlinearray-type-sugar/80337 "SE‑0483：InlineArray 类型糖 二轮评审")

Swift 社区于 2025 年 6 月 6 日启动了对 SE‑0483（InlineArray 类型糖）的第二轮评审，评审期将持续至 2025 年6 月 20 日。

* 针对前一轮反馈，提案做出如下调整：将语法分隔符 x 改为 of；扩展动机部分以引用其他语言对固定长度 inline 存储数组语法的支持；在“备选方案”中加入了是否应显示“inline”本质的讨论。
* 感兴趣的开发者可下载 Swift 官方最新主分支快照的 toolchain，在 Linux/macOS/Windows 上启用 InlineArrayTypeSugar 实验功能进行试用。
* 帖子中列出了开发者在评审时应考虑的问题，如：该特性是否必要、是否契合 Swift 语言风格、是否优于现有类型定义方式等。
* 社区成员反馈主要集中在这些方面：
* 许多人支持将 x 改为 of，认为更清晰且易用。
* 有人质疑是否真的需要类型糖，认为 `InlineArray<5, Int>` 已足够表达，且担心语法扩展未来会影响可扩展性（如适用于其他固定容器类型）。
* 还有人建议应进一步扩展语法支持重复字面量、元组及其他固定大小类型，讨论其一致性与易用性。
* 一些用户提出若能使用 `[5 of 1]` 表达重复项，将使代码更加简洁，与现有数组字面量语法更一致。

总结来说，此轮评审聚焦于：选择 of 作为类型糖分隔词，增强提案的动机及可选方案讨论，引发社区对是否应引入这种语法、如何确保其扩展性及与现有语法一致性的深入讨论。

3、讨论[Swift 对 WebAssembly 支持的愿景已获接受](https://forums.swift.org/t/accepted-vision-a-vision-for-webassembly-support-in-swift/80332 "Swift 对 WebAssembly 支持的愿景已获接受")

Swift 平台指导组于 2025年6月6日 正式接受了由 Max Desiatov 提交的“WebAssembly 支持愿景”文档，标志着对未来发展路线的认同。

* 愿景提出了 Swift 在 WebAssembly 上的中长期目标，包括加强核心库的 Wasm API 覆盖、改进 Swift/SwiftPM 的交叉编译能力、推进 Component Model 支持，以及确保 WASI 未来版本可用。
* 措施还包括提升 Swift 与 WebAssembly 组件互操作性的无缝性，拟比肩对 C/C++ 的互操作支持。
* 文档强调改进 Swift 编译到 Wasm 后的调试体验，使其在调试工具上能与其他平台保持一致。
* 虽为“强烈认可”整体方向，实际细节仍需通过标准 Swift 变更提案流程进一步审查，可能经历修改或驳回。

综上，“愿景”文档被采纳代表社区与指导组对 Swift 全面支持 WebAssembly 的信心，后续将围绕 API 丰富、跨编译、组件互操作、调试改进等关键方面进行具体演进。

4、提议[结构化任务取消令牌](https://forums.swift.org/t/pitch-structured-task-cancellation-tokens/80355 "结构化任务取消令牌")

Swift 社区在 2025 年 6 月 8 日 发起了有关“结构化任务取消令牌”（CancellationToken）的提案初轮讨论，旨在改善当前 Swift 并发模型中任务取消的局限性，特别是在取消原因与作用域表达方面。

* 当前 Swift 的 `Task.isCancelled` 机制仅提供布尔状态，缺乏取消的上下文信息，不利于错误处理和资源清理。
* 此提案引入新的 `CancellationToken` 类型，它：
* 携带结构化取消原因；
* 可通过 `@TaskLocal` 在任务树中自动传递；
* 与现有取消机制兼容，不破坏旧代码。

示例代码：

定义任务取消时的原因：

```swift
enum MyCancellationReason: CancellationTokenReason {
    case userCancelled
    case networkTimeout
    case systemPressure
}
```

创建带取消令牌的任务：

```swift
let token = CancellationToken(reason: .userCancelled)

let task = Task(token: token) {
    try CancellationToken.checkCancellation() // 检查是否已被取消
    // 执行工作...
}
```

从任意位置触发取消：

```swift
token.cancel() // 自动传播给该 token 创建的所有子任务
```

检查取消原因：

```swift
do {
    try CancellationToken.checkCancellation()
} catch is CancellationError {
    if let reason = CancellationToken.current?.reason as? MyCancellationReason {
        print("任务因 \(reason) 被取消")
    }
}
```

社区讨论了：

* 是否采用 protocol 让用户自定义原因类型 vs 直接使用 enum/string；
* 是否应将取消信息视为 Error（大多反馈认为不是）；
* `Task(token:)` 构造函数设计是否足够简洁；
* 是否引入“取消范围”（如带超时的作用域）来扩展取消能力。

总结：该提案为 Swift 并发引入更强大且结构清晰的任务取消控制，支持更好的调试、资源清理与代码组织。当前仍在 pitch 阶段，尚未进入正式评审流程。是否采纳将取决于进一步的社区反馈与设计细化。

5、讨论[新的 containerization 框架](https://forums.swift.org/t/new-containerization-framework/80374 "新的 containerization 框架")

Swift 社区在 2025 年 6 月 9 日发布了一个开源的 Swift 编写的容器化框架，该框架专为 macOS 上运行 Linux 容器设计，并利用 Apple Silicon 的硬件优势。

包含两个独立项目：

* container：命令行工具，用于创建和启动 Linux 容器，实质上是基于 Linux 内核和轻量虚拟机运行。
* containerization：Swift 包，可供集成到应用中，用于以容器作为 sidecar 方式嵌入容器功能。
* 每个容器运行在自己的优化 VM 中，启动时间为子秒级，且为每个容器分配独立 IP，提升隔离性与安全性。
* 所构建的容器镜像遵循 OCI 标准，适用于 Kubernetes 等生态，具有轻量核心系统、加速启动性能、较低内存占用，降低攻击面。

社区提问关注：

* 是否支持 BSD 或非 Linux 操作系统；
* 每个容器一 VM 模式带来的资源开销；
* 与现有 Docker Desktop 等工具的差异与性能对比。

总结：Apple 开源了一个全新的、用 Swift 实现的容器化框架，核心在于每个 Linux 容器都在独立轻量级 VM 上运行，具备高隔离性、启动迅捷与低资源占用优势。该项目适用于开发者在 macOS 上进行 Linux 容器开发、集成 sidecar 容器功能，以及未来在生产或 CI/CD 场景的潜力。社区正在评估其对多平台支持、资源优化及与现有方案的兼容性。

## 推荐博文

[Apple 将密码监控服务从 Java 迁移到 Swift](https://www.swift.org/blog/swift-at-apple-migrating-the-password-monitoring-service-from-java/ "Apple 将密码监控服务从 Java 迁移到 Swift")

**摘要：** Apple 的密码监控服务原本是用 Java 写的，每天要处理全球几十亿次请求，检查用户的密码是否泄露。但随着用户量增长，Java 版本的性能开始不够用了——启动慢、内存占用高，而且在高负载时容易卡顿。于是，团队决定用 Swift 重写整个服务。

Swift 的代码比 Java 更简洁，同样的功能代码量减少了 85%，而且运行效率更高。由于 Swift 没有 Java 那样的垃圾回收机制，内存管理更高效，单个服务实例的内存占用从原来的几十 GB 降到了几百 MB。最终，新版本的性能提升了 40%，几乎所有的请求都能在 1 毫秒内完成，同时节省了一半的服务器资源。

这次迁移不仅让服务跑得更快，还让开发和维护变得更简单。Swift 的语法清晰，内置的异步编程支持也让代码更易读。对于 Apple 来说，这次成功尝试证明 Swift 不仅能开发手机和电脑应用，还能高效运行在服务器上，处理海量数据请求。未来，他们可能会在更多后端服务中使用 Swift。

[基于 Swfit 实现人脸变老](https://blog.csdn.net/s1t16/article/details/145320327/ "基于 Swfit 实现人脸变老")

**摘要：** 这是一个使用Swift实现的创意人脸老化效果项目，其核心思路是将预制皱纹自然地融合到照片中的人脸上。整个处理流程从人脸特征识别开始，通过Face++的API精准定位面部关键点，为后续处理奠定基础。

在技术实现上，项目采用了创新的图像变形算法。通过Moving Least Squares方法，使预制皱纹能够智能地跟随面部特征点进行形变，确保皱纹与五官完美贴合。这一过程借助OpenGL进行高效渲染，保证了处理速度。最终的图像融合环节特别选择了柔光混合模式，这种处理方式既保留了原始肤色，又能让皱纹看起来自然不突兀。

这个方案的一个巧妙之处在于其通用性，仅需一张皱纹贴图就能适配各种肤色的人脸照片。虽然目前主要以添加皱纹来模拟老化效果，与真实衰老过程相比还有提升空间，但整个技术框架具有很强的扩展性。实际上，这套基于特征点变形的算法同样适用于美颜、虚拟化妆等其他图像处理场景，展现了不错的技术复用价值。从实现角度来看，Swift与OpenGL的结合既保证了性能，又保持了代码的简洁性，为类似功能的开发提供了有益参考。

[WWDC25 后 SwiftUI 的新变化](https://swiftwithmajid.com/2025/06/10/what-is-new-in-swiftui-after-wwdc25/ "WWDC25 后 SwiftUI 的新变化")

**摘要：** Apple 在 WWDC25 为 SwiftUI 带来了重磅更新，全新"液态玻璃"设计语言让界面更加通透立体，开发者只需使用Xcode26重新编译即可自动获得新视觉效果。导航栏和标签页系统全面升级，新增的Tab API让布局更灵活，工具栏也支持玻璃质感设计。

功能方面终于加入了TextEditor富文本支持和原生WebView组件，大幅提升了开发效率。macOS版本获得显著性能优化，列表滚动更加流畅，并新增了专门的性能分析工具。这些改进使SwiftUI在跨平台开发中变得更加强大易用。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
