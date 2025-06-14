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
1) 讨论[Swift SDKs for WebAssembly 现已在 swift.org 上提供](https://forums.swift.org/t/swift-sdks-for-webassembly-now-available-on-swift-org/80405 "Swift SDKs for WebAssembly 现已在 swift.org 上提供")

Swift 官方宣布现已在 swift.org 上发布适用于 WebAssembly 的 SDK，支持 Swift 6.2 及其开发版本。

•	发布了两个 SDK：一个是完整标准库版本，支持 Swift Testing；另一个是 Embedded Swift 版本，生成的 WebAssembly 二进制体积更小（如 “Hello, World!” 仅约 9.7KB）。
•	Toolchain 集成了 WasmKit 工具，可使用 swift run 运行支持 WASI 的 WebAssembly 程序。未来还将支持 swift test。
•	完整 SDK 包含 Swift Testing，但 Embedded Swift 尚不支持测试框架。官方计划未来增加对 Foundation 和 XCTest 的支持。
•	帖子感谢了众多社区成员的贡献，推动了 Swift 在 WebAssembly 平台的兼容性发展。

2) 讨论[SE‑0483：InlineArray 类型糖 二轮评审](https://forums.swift.org/t/second-review-se-0483-inlinearray-type-sugar/80337 "SE‑0483：InlineArray 类型糖 二轮评审")

Swift 社区于 2025 年 6 月 6 日启动了对 SE‑0483（InlineArray 类型糖）的第二轮评审，评审期将持续至 2025 年6 月 20 日。

•	针对前一轮反馈，提案做出如下调整：将语法分隔符 x 改为 of；扩展动机部分以引用其他语言对固定长度 inline 存储数组语法的支持；在“备选方案”中加入了是否应显示“inline”本质的讨论。
•	感兴趣的开发者可下载 Swift 官方最新主分支快照的 toolchain，在 Linux/macOS/Windows 上启用 InlineArrayTypeSugar 实验功能进行试用。
•	帖子中列出了开发者在评审时应考虑的问题，如：该特性是否必要、是否契合 Swift 语言风格、是否优于现有类型定义方式等。
•	社区成员反馈主要集中在这些方面：
•	许多人支持将 x 改为 of，认为更清晰且易用。
•	有人质疑是否真的需要类型糖，认为 InlineArray<5, Int> 已足够表达，且担心语法扩展未来会影响可扩展性（如适用于其他固定容器类型）。
•	还有人建议应进一步扩展语法支持重复字面量、元组及其他固定大小类型，讨论其一致性与易用性。
•	一些用户提出若能使用 [5 of 1] 表达重复项，将使代码更加简洁，与现有数组字面量语法更一致。

总结来说，此轮评审聚焦于：选择 of 作为类型糖分隔词，增强提案的动机及可选方案讨论，引发社区对是否应引入这种语法、如何确保其扩展性及与现有语法一致性的深入讨论。

3) 讨论[Swift 对 WebAssembly 支持的愿景已获接受](https://forums.swift.org/t/accepted-vision-a-vision-for-webassembly-support-in-swift/80332 "Swift 对 WebAssembly 支持的愿景已获接受")

Swift 平台指导组于 2025年6月6日 正式接受了由 Max Desiatov 提交的“WebAssembly 支持愿景”文档，标志着对未来发展路线的认同 ￼。

•	愿景提出了 Swift 在 WebAssembly 上的中长期目标，包括加强核心库的 Wasm API 覆盖、改进 Swift/SwiftPM 的交叉编译能力、推进 Component Model 支持，以及确保 WASI 未来版本可用。
•	措施还包括提升 Swift 与 WebAssembly 组件互操作性的无缝性，拟比肩对 C/C++ 的互操作支持。
•	文档强调改进 Swift 编译到 Wasm 后的调试体验，使其在调试工具上能与其他平台保持一致。
•	虽为“强烈认可”整体方向，实际细节仍需通过标准 Swift 变更提案流程进一步审查，可能经历修改或驳回。

综上，“愿景”文档被采纳代表社区与指导组对 Swift 全面支持 WebAssembly 的信心，后续将围绕 API 丰富、跨编译、组件互操作、调试改进等关键方面进行具体演进。

4) 提议[结构化任务取消令牌](https://forums.swift.org/t/pitch-structured-task-cancellation-tokens/80355 "结构化任务取消令牌")

Swift 社区在 2025 年 6 月 8 日 发起了有关“结构化任务取消令牌”（CancellationToken）的提案初轮讨论，旨在改善当前 Swift 并发模型中任务取消的局限性，特别是在取消原因与作用域表达方面。

•	当前 Swift 的 Task.isCancelled 机制仅提供布尔状态，缺乏取消的上下文信息，不利于错误处理和资源清理。
•	此提案引入新的 CancellationToken 类型，它：
•	携带结构化取消原因；
•	可通过 @TaskLocal 在任务树中自动传递；
•	与现有取消机制兼容，不破坏旧代码。

示例代码：

定义任务取消时的原因：
```Swift
enum MyCancellationReason: CancellationTokenReason {
    case userCancelled
    case networkTimeout
    case systemPressure
}
```
创建带取消令牌的任务：
```Swift
let token = CancellationToken(reason: .userCancelled)

let task = Task(token: token) {
    try CancellationToken.checkCancellation() // 检查是否已被取消
    // 执行工作...
}
```
从任意位置触发取消：
```Swift
token.cancel() // 自动传播给该 token 创建的所有子任务
```
检查取消原因：
```Swift
do {
    try CancellationToken.checkCancellation()
} catch is CancellationError {
    if let reason = CancellationToken.current?.reason as? MyCancellationReason {
        print("任务因 \(reason) 被取消")
    }
}
```
社区讨论了：
•	是否采用 protocol 让用户自定义原因类型 vs 直接使用 enum/string；
•	是否应将取消信息视为 Error（大多反馈认为不是）；
•	Task(token:) 构造函数设计是否足够简洁；
•	是否引入“取消范围”（如带超时的作用域）来扩展取消能力。

总结：该提案为 Swift 并发引入更强大且结构清晰的任务取消控制，支持更好的调试、资源清理与代码组织。当前仍在 pitch 阶段，尚未进入正式评审流程。是否采纳将取决于进一步的社区反馈与设计细化。

5) 讨论[新的 containerization 框架](https://forums.swift.org/t/new-containerization-framework/80374 "新的 containerization 框架")

Swift 社区在 2025 年 6 月 9 日发布了一个开源的 Swift 编写的容器化框架，该框架专为 macOS 上运行 Linux 容器设计，并利用 Apple Silicon 的硬件优势 ￼。

包含两个独立项目：
•	container：命令行工具，用于创建和启动 Linux 容器，实质上是基于 Linux 内核和轻量虚拟机运行。
•	containerization：Swift 包，可供集成到应用中，用于以容器作为 sidecar 方式嵌入容器功能 ￼ ￼。
•	每个容器运行在自己的优化 VM 中，启动时间为子秒级，且为每个容器分配独立 IP，提升隔离性与安全性。
•	所构建的容器镜像遵循 OCI 标准，适用于 Kubernetes 等生态，具有轻量核心系统、加速启动性能、较低内存占用，降低攻击面 ￼。
社区提问关注：
•	是否支持 BSD 或非 Linux 操作系统；
•	每个容器一 VM 模式带来的资源开销；
•	与现有 Docker Desktop 等工具的差异与性能对比 ￼。

总结：Apple 开源了一个全新的、用 Swift 实现的容器化框架，核心在于每个 Linux 容器都在独立轻量级 VM 上运行，具备高隔离性、启动迅捷与低资源占用优势。该项目适用于开发者在 macOS 上进行 Linux 容器开发、集成 sidecar 容器功能，以及未来在生产或 CI/CD 场景的潜力。社区正在评估其对多平台支持、资源优化及与现有方案的兼容性。


## 推荐博文


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
