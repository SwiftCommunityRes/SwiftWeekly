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
1. 讨论[宣布 Android 工作组](https://forums.swift.org/t/announcing-the-android-workgroup/80666 "宣布 Android 工作组")
Swift 社区于 2025 年 6 月 25 日 正式成立 Android Workgroup，目标是将 Android 作为 Swift 的正式支持平台，并持续维护其生态。

* 工作组制定了章程，可在 swift.org/android-workgroup 查看。
* 正在开发包含 AArch64、x86_64 和 armv7 架构的 Swift Android SDK，并在 CI 中运行完整编译器验证套件，计划发布适用于 Swift 6.2 和 6.3 的 SDK snapshot。
* 社区成员可通过 GitHub roadmap 跟踪任务进展并参与，还可暂用第三方基于 Skip、Readdle 等工具链的 SDK 进行试用。
* 工作组作用包括：推动 Swift 与 Kotlin/Java 的无缝互操作、探索在 VS Code、Windows 等平台的 IDE 支持，并考虑未来实现 SwiftUI 或 Jetpack Compose 的跨平台 UI 支持。

总结：该公告标志着 Swift 正式迈向 Android 平台，Android Workgroup 将协调 SDK 开发、CI 测试、跨平台集成与社区参与。下一步将聚焦发布首批官方 Android SDK snapshot，并强化与 Java/Kotlin 互操作及 IDE 支持。


2. 讨论[为 Swift.org 的全新愿景](https://forums.swift.org/t/a-different-vision-for-swift-org/80570 "为 Swift.org 的全新愿景")
Daniel Steinberg 于 2025年6月20日 在 Swift 论坛上提出对 swift.org 当前首页及网站内容布局的新构想，目标是让网站成为“每日启动页”而非单纯文档中心 ￼。

* 构想的内容包括：
	* 首页顶部保留“Getting Started”“Install”等核心链接，下方则动态更新多类内容，例如：
        1.	从活跃的论坛讨论中精选摘要，帮助访问者快速掌握重要讨论；
        2.	每周推荐一个 Swift 包，搭桥推广 Swift Package Index；
        3.	展示 Swift Evolution 提案、pre‑proposal 和 vision 文档的最新动态；
        4.	聚合来自社区的相关新闻、书籍、会议与视频；
        5.	Swift.org 博客最新文章推送；
        6.	编辑每日快笔、精华摘要或主题推荐；
        7.	定期发布授权技术文章；
        8.	支持查看过往首页档案；
        9.	可能推出 Swift · Podcast 版块；
        10.	“新手专栏”与“前沿专题”，包括启用 feature-flag 或实验版本的指南；
        11.	简短 Swift 代码演示视频，展示新特性；
        12.	小型代码挑战（例如类似 Wordle 的 Swift Playground）。
	* 借此让使用者不用跳转就能看出 Swift 多平台、多生态、多领域的活跃状态。
	* 社区反馈亮点：
	* Joannis_Orlandos 强烈支持，特别赞同提案中对 Swift Evolution 推案作 TL;DR 的建议 ￼；
	* James_Dempsey 表示这与正在进行的信息架构项目高度一致，鼓励社区参与该项目 ￼；
	* Lafeuille 则偏好现有简洁风格，担忧过多模块可能导致用户感到不知所措()；
	* Jonathan Grynspan 比较了 Rust、Go、Kotlin 网站，建议 Swift 可以借鉴他们在主页展示赞助商与生态案例的方法 ￼。

总结：Daniel 提出的“每日启动页”目标是让 swift.org 更具活力、多元化，对论坛讨论、提案、工具、生态项目做动态展示。支持者认为可增强社区感与可见性，但也有人担心首页信息会过于繁杂。与此构想同步进行的信息架构项目也在评估相关调整。

3. 提议[禁用 SwiftPM 中 unsafe flags 的校验](https://forums.swift.org/t/pitch-disable-checks-for-unsafe-flags-in-swiftpm/80698 "禁用 SwiftPM 中 unsafe flags 的校验")
Swift 社区于 2025年6月26日 提出此 pitch，建议在 Swift 6.2 中移除 Swift Package Manager（SwiftPM）对依赖包中 unsafeFlags 的限制，以解决很多构建问题。

* 当前 SwiftPM 仅允许部分“安全”编译选项传递给依赖。若某个依赖使用了 unsafeFlags（如 -I 添加头文件路径），SwiftPM 会阻止构建，即使调用者信任该依赖。
* 这在如 JNI（Java Native Interface）、Foundation for Android 等跨平台工程中成为障碍。
* 本提案建议在 Swift 6.2 中临时取消对 unsafeFlags 的拦截检查，未来通过 Evolution 正式设计更安全的机制（例如 allowlist 或 manifest 声明）。

示例代码:

📦 Package.swift 中的 unsafeFlags 使用：
```Swift
.target(
  name: "MyCLibraryWrapper",
  dependencies: [],
  cSettings: [
    .unsafeFlags(["-I/usr/include/jni"])  // JNI 头文件路径
  ]
)
```
在当前 SwiftPM 中，如果这是某个依赖包的内容，将导致主包构建失败。

📦 主项目中的依赖声明：
```Swift
.package(url: "https://github.com/example/MyCLibraryWrapper.git", from: "1.0.0")
```

当 MyCLibraryWrapper 使用 unsafeFlags 时，即使开发者信任它，SwiftPM 也会抛出如下错误：
```Swift
error: the package 'MyCLibraryWrapper' uses unsafe flags, which are not allowed in dependencies
```
此提案提出在 Swift 6.2 中临时移除此限制，允许开发者顺利构建依赖。

社区反馈要点：
* ✅ 支持者认为这将极大改善真实开发工作流程，尤其是在 Swift for Android、Swift‑Java 融合项目中；
* ⚠️ 担忧者提醒：解除限制可能导致依赖包设置危险参数（如启用恶意宏或路径注入），应搭配安全机制，如 allowlist 或首次信任（TOFU）策略；
* 💡 建议扩展功能：
* 引入 safeFlags, declaredFlags 等 API；
* 明确 unsafeFlags 对构建结果的影响（增量构建、安全审计）；
* 允许用户在 Package.swift 声明信任或进行沙盒隔离。

总结：
该提案旨在解决 SwiftPM 在跨平台项目中因 unsafeFlags 而导致构建失败的痛点。通过在 Swift 6.2 中临时取消校验，使依赖能够顺利构建，并为将来设计更安全的 flag 管理系统提供缓冲期。社区普遍支持，强调需关注安全性与可维护性。

4. 讨论[MainActor.assumeIsolated 在主线程崩溃](https://forums.swift.org/t/mainactor-assumeisolated-crashes-on-main-thread/80624 "MainActor.assumeIsolated 在主线程崩溃")
Florian Pircher 于 2025 年 6 月 23 日 报告在使用 MainActor.assumeIsolated { … } 时即便在主线程中执行，也会触发断言失败（EXC_BREAKPOINT / SIGTRAP）。他在 macOS App 的 awakeFromNib() 中使用示例代码遇到了此问题，并测试过 Swift 6.2 + Xcode 26 beta 与 Swift 6.1 + Xcode 16.4，均复现 ￼。

💻 示例代码
```Swift
class CommitDetailsTextView: NSTextView { // 隐式 @MainActor
    override func awakeFromNib() { // 隐式非 @MainActor
        super.awakeFromNib()
        MainActor.assumeIsolated {
            self._awakeFromNib()
        }
    }

    private func _awakeFromNib() {
        self.font = Self.displayFont
        // ...
    }
}
```
崩溃栈：

Thread 0 Crashed:: … libswiftCore.dylib … MainActor.assumeIsolated <…>

表明即使当前运行在线程 main-thread，assumeIsolated 也触发了 runtime 检查。

尝试的替代方案也会崩溃：
```Swift
func awakeFromNibOnMainThread(_ body: @escaping @MainActor () -> ()) {
    if Thread.isMainThread {
        MainActor.assumeIsolated { body() }
    } else {
        Task { @MainActor in body() }
    }
}
```
但仍会因 assumeIsolated 而崩溃()。

💬 社区反馈亮点
* 初步判断为 bug：帖子首条回复表示“Looks like a bug.”()。
* 建议临时用纯 Task { @MainActor in … } 替代，但这会产生异步调度，难以保证同步行为 ￼。
* Rick van Voorden 和其他用户也在讨论是否应允许 legacy AppKit/Objective-C 调度的代码在 assumeIsolated 生效 ￼。

✅ 总结

问题: 即使在主线程，MainActor.assumeIsolated 也会在 AppKit 初始化时崩溃。

原因: 可能因运行时检测当前执行环境与 MainActor 不一致而触发断言。

目前状态: 已确定为 bug，目前最佳 workaround 是改用 Task { @MainActor … }，虽然会异步。

后续建议: 建议等待 Swift 团队修复，或寻求更低级的同步执行解决方案，但目前没有稳定替代。

5. 讨论[成功在“生产”环境使用 swift‑java](https://forums.swift.org/t/successful-use-of-swift-java-in-production/80664 "成功在“生产”环境使用 swift‑java")
Sergio Campama 于 2025年6月25日 分享了在生产环境中使用 swift‑java 的经验：他部署了一个基于 Hummingbird 的网站，用于处理硬件设备生成的 XLS 文件。由于暂找不到纯 Swift 的 XLS 库，他使用 swift‑java 调用 Java 的 Apache POI 实现 XLS 解析与生成，最终实现了跨 macOS 和 Linux 的成功运行，并感谢了 swift‑java 社区的努力。

* 初期，他先用 Python 实现 XLS 功能；然后观摩 WWDC 的 Java 互操作演示，决定用 swift‑java 构建 Swift 包，并集成 Apache POI 库。
* 经过一段时间理解 swift‑java 的架构后，他成功在 macOS（包括 CLI 与 Xcode 调试）以及 Linux（运行于 GCP 上的 Docker 容器）上运行该包。
* 他还指出文档目前偏少，希望增加官方教程；swift‑java 核心贡献者 ktoso 表示项目正趋于稳定，将在适当时间补齐文档。

总结:
Sergio 成功将 Apache POI 集成到 Swift 中，用于处理 Excel（XLS）文件，以替代 Python，实现了跨平台 CLI、调试、CI/CD 部署能力。项目运行在 macOS 与 Linux（Docker+GCP）环境，并正式投入“生产”使用。他也呼吁增强 swift‑java 文档，而核心开发者已在规划中。

## 推荐博文


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
