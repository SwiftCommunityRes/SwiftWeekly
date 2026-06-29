## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百零三期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

风会吹暖每一寸土壤，那些默默努力的时光，终将在春日里绽放成芬芳。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：苹果宣布涨价后股价大跌 6%，AI 时代的成本压力终于浮出水面；AI Siri 嵌入、iPhone 18 定价韧性与折叠屏周期共振
> * **提案**：SE-0513（executablePath）重新进入审查；SE-0534 选择与构建元数据完全匹配版本标识符正在审查
> * **Swift 论坛**：`some` 与 `any` 边界取舍、宏展开中字符串插值识别、Xcode 切换分支丢失 Swift Package 产品、`Embedded Swift` 跑通 SwiftOS 内核与用户态
> * **推荐博文**：Swift 6.4 带来新语言特性与 Swift Testing/XCTest 互操作、Swift 6.4 `async defer` 终结「伪并发」陷阱、DoorDash 利用 Copilot 将 XCTest 迁移到 Swift Testing

## 话题讨论
**“恋爱难还是结婚难？”——当代年轻人为什么对亲密关系“提不起劲”？
如果你也觉得脱单比升职还难，来选选你的“心动理由”吧！**

1. 经济压力太大：房、车、彩礼，还没开始就被劝退？
2. 工作已经够累了：下班只想躺平，没精力经营感情？
3. 社交圈子太小：公司家里两点一线，连新朋友都认识不了？
4. 观念变了：觉得一个人更自由，不想为别人改变自己？

欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### 苹果宣布涨价后股价大跌 6%，AI 时代的成本压力终于浮出水面

*2026 年 6 月 26 日｜来源：金十数据*

苹果正式上调多款 MacBook 与 iPad 售价，国行同步调价，iPhone、Apple Watch 与 AirPods 暂未涉及；消息公布后股价单日收跌逾 6%，创 2025 年 4 月以来最大跌幅。

![](https://files.mdnice.com/user/38782/92e6284d-0ce6-4e61-8b52-83201486887b.png)

本轮涨价的根因是「AI 抢内存、存储」：Counterpoint Research 数据显示，过去三个季度内存和存储价格已上涨至原四倍，源自供应商把更多产能切给 HBM。为支持今年秋季推出的新版 AI Siri，IDC 预测所有新款 iPhone 都将配备 12GB 内存，约 54% 的存量 iPhone 也将无法完整支持新版 Siri。

![](https://files.mdnice.com/user/38782/a4ae49f8-c74b-4856-95c8-3d1e98626136.png)

涨价潮最大受益者是存储厂商：美光最新财季毛利率从一年前 39% 跃升至 84.9%，反超英伟达和 Meta；DRAM 单季涨 60%、NAND 涨约 80%，并已锁下 220 亿美元长期协议。库克直言这是其 40 多年职业生涯中从未见过的成本压力，且未来仍可能继续调整售价。

### AI Siri 嵌入、iPhone 18 定价韧性与折叠屏周期共振

*2026 年 6 月 25 日｜来源：新浪财经*

摩根大通 Chatterjee 团队预计 iPhone 18 系列涨幅约 50 美元（即中个位数百分点区间），低于市场对「全系普涨 200 美元」的悲观预期，并维持「增持」评级；存储成本通胀对 iPhone 的同比冲击约 100 美元，可由 40 美元供应链议价、15 美元自研调制解调器等垂直整合抵消，毛利影响控制在约 30 个基点。

AI 端，新版 Siri 由 Apple Intelligence 驱动，在 iOS 27 / iPadOS 27 / macOS 27 / visionOS 27 上以开发者测试版推出，因依赖服务器模型的部分能力日用量受限，更多访问权限预计将随 iCloud+ 订阅分级，意味着 AI 也是服务订阅 ARPU 上移的新抓手。

硬件端，折叠 iPhone 将于 7 月底正式量产、9 月发布，搭载三星显示越南厂供应的折叠 OLED，富士康负责首批组装，铰链供应链已做好 1000–2000 万部准备；Counterpoint 预测 2026 年全球折叠屏出货量同比增长 20%，全球约 27% 的 iPhone 用户对折叠形态「极感兴趣」（中国近 40%），给 ASP 注入新一轮向上弹性。

## 提案

### 正在审查的提案

[SE-0513](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0513-commandline-executablepath.md "SE-0513")
**API 获取当前可执行文件的路径** 提案正在审查。

该提案此前曾在 **第九十六期周报** 中介绍过，后被拒绝，本期重新进入审查。

[SE-0534](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0534-swiftpm-exact-literal-version-matching.md "SE-0534")
**选择与构建元数据完全匹配版本标识符** 提案正在审查。

此提案添加了一个选择式清单 API，`.exactLiteral(...)`，该 API 从字面上匹配版本标识符，包括构建元数据，同时保持现有的 `.exact(...)` 和范围行为不变。

## Swift 论坛

### 1、赋值到 existential 时应使用 `any` 还是 `some`

作者：atifdev10 ｜ 发布日期：2026 年 6 月 27 日
[阅读原帖](https://forums.swift.org/t/is-there-a-difference-between-using-any-and-some-if-im-assigning-the-value-to-an-existential-type-in-the-end-anyway/87768 "Is there a difference between using `any` and `some` if I'm assigning the value to an existential type in the end anyway?")

**动机：**
如果初始化器最终只是把值存入 `any Hashable`，参数写成 `some Hashable` 和 `any Hashable` 是否等价？

```swift
struct Foo {
  var anyHashable: any Hashable

  init(_ value: some Hashable) {
    anyHashable = value
  }

  init(_ value: any Hashable) {
    anyHashable = value
  }
}
```

**核心设计：**
Ben Levine 和 Slava Pestov 都指出，两种写法在源码层面相近，但 ABI 和运行时成本不同。如果调用方已经持有一个 **existential box**，`some Hashable` 版本可能需要先打开 existential、复制载荷，再在初始化器内部重新装箱；而 `any Hashable` 可以直接接收最终要存储的形式。Jamie 还从 SIL 角度指出泛型版本会出现额外的 `init_existential_addr`。

**讨论亮点：**
API 演进取舍：如果未来可能不再存储 type-erased 值，`some` 会保留转向泛型实现的空间；但若设计目标就是立刻存入 existential，`any` 更直接。

**简要点评：**
这是一处少见的「优先 existential 参数」的场景，性能敏感代码尤其值得注意。

### 2、宏展开中如何判断字符串插值

作者：Daryle Walker ｜ 发布日期：2026 年 6 月 28 日
[阅读原帖](https://forums.swift.org/t/are-string-interpolations-accepted-during-a-macro/87776 "Are string interpolations accepted during a macro?")

**动机：**
Daryle Walker 在实现表达式 **macro** 时遇到诊断不符合预期的问题：代码先尝试把第一个参数识别为 `StringLiteralExprSyntax`，再通过 `representedLiteralValue` 判断是否包含字符串插值；但测试 `#myMacro(\("Helo"))` 时，触发的是「不是字符串字面量」，而不是「包含字符串插值」。

```swift
guard let literal = node.arguments.first?.expression(StringLiteralExprSyntax.self)
else {
  throw .notStringLiteral
}

guard let string = literal.representedLiteralValue else {
  throw .interpolationTermsPresent
}
```

**核心设计：**
关键点是 **SwiftSyntax** 宏拿到的是已经解析后的语法树。字符串插值只有在字符串字面量内部才有意义，例如 `"\(value)"`；而 `\("Helo")` 本身不是一个字符串字面量表达式，因此第一层 `StringLiteralExprSyntax` 匹配就会失败。若要测试插值分支，应传入真正的字符串字面量，并让 `representedLiteralValue` 因包含插值而返回 `nil`。

**讨论亮点：**
宏测试中 raw string 的写法容易让人误以为外层测试字符串里的 `\(...)` 会变成被测代码里的字符串插值。

**简要点评：**
诊断分层要先确认语法节点类型，再检查字面量内容；测试用例最好覆盖「非字符串表达式」和「含插值的字符串字面量」两个独立路径。

### 3、切换 Git 分支后 Xcode 仍可能丢失 Swift Package 产品

作者：Jesse Squires ｜ 发布日期：2024 年 5 月 16 日
[阅读原帖](https://forums.swift.org/t/missing-package-product-error-for-all-local-swift-packages-when-switching-git-branches/38041/48 "\"Missing package product\" error for all local Swift Packages when switching git branches")

**动机：**
这个老帖在 2024 年再次被顶起：Jesse Squires 表示，`Missing package product` 问题在 **Xcode 15.4** 中仍会发生，而且不只影响本地包，也会影响远程 **Swift Package**。原始问题来自 2020 年，表现为切换 Git 分支或在 Xcode 打开时执行 `git pull` 后，项目突然无法识别包产品。

典型错误日志类似：

```text
error: Missing package product '<package name>'
```

**核心设计：**
复杂项目通常依赖多个 **SPM** 包，分支切换会改变 `Package.resolved`、包版本或本地包布局；如果 Xcode 没有及时刷新依赖图，构建就会被阻断。后续回复中，Kai Engelhardt 和 Alexei 也确认这是团队日常开发中的长期痛点，并希望 Xcode 与 SPM 集成能被提升优先级。

**讨论亮点：**
讨论中常见临时处理包括重启 Xcode、清理 DerivedData、重置包缓存、重新解析包，严重时甚至需要重新 clone。

**简要点评：**
这不是语言层面的 Swift 问题，却会直接影响 Swift 开发效率；在大型工程中，包解析缓存和 IDE 状态一致性仍是需要重点打磨的基础体验。

### 4、SwiftOS：用 Embedded Swift 从零构建内核和用户态

作者：Andrey ｜ 发布日期：2026 年 6 月 16 日
[阅读原帖](https://forums.swift.org/t/swiftos-a-from-scratch-kernel-and-userland-in-embedded-swift/87440 "SwiftOS — a from-scratch kernel and userland in Embedded Swift")

**动机：**
Andrey 分享了 **SwiftOS**：一个几乎完全用 **Embedded Swift** 编写的 64 位 ARM 小型操作系统。它可以在 QEMU `virt` 上启动，也能运行在 Hetzner Cloud ARM VM 上，并由系统自身提供网站服务。项目使用 Swift 6.3.2 toolchain，面向 `aarch64-none-none-elf`，没有 Foundation，也没有完整标准库。

**核心设计：**
大致构建参数如下：

```text
-target aarch64-none-none-elf
-enable-experimental-feature Embedded
-wmo
-parse-as-library
-Osize
```

系统能力包括真实的 **MMU** 地址空间隔离、基于 capability 的句柄、Swift 编写的用户态 coreutils、`console-login`、`sshd`、自研 syscall ABI、内核 TCP/IP 栈、三层文件系统、SMP 调度，以及静态链接的 nginx 和 Node.js。底层仍需要少量 C/汇编处理 MMIO、启动、异常向量和上下文切换；作者也记录了 `ld.lld`、Unicode 数据表、`putchar` shim、16 字节堆对齐等 Embedded Swift 实践细节。

**讨论亮点：**
讨论亮点包括是否能移植到 Raspberry Pi、Swift 是否需要内联汇编、以及真实云主机带来的 ACPI、GICv3、PCIe、virtio-net 等差异。后续作者还补充 OpenSSL 在 Hetzner VM 上缺少熵源的问题，并用内核 jitter entropy 通过 `SYS_RANDOM` 解决。

**简要点评：**
SwiftOS 展示了 **Embedded Swift** 已经能触达非常底层的系统编程场景，也暴露出 freestanding 工具链、链接器和硬件抽象仍需要继续完善。

## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[Swift 6.4 带来新语言特性与 Swift Testing/XCTest 互操作](https://www.infoq.com/news/2026/06/swift-6-4-beta-features/ "Swift 6.4 带来新语言特性与 Swift Testing/XCTest 互操作")

**摘要：** InfoQ 对 Swift 6.4（Xcode 27 beta）做了全景梳理：去掉冗余括号、新增并发任务警告、引入 `weak let` 与 `~Sendable`、支持隐式成员初始化器；`defer` 也首次能 `await`，补齐 Swift 5.5 以来的并发空白。测试侧，Swift Testing 与 XCTest 实现双向互操作，`#expect` 提供更可读的失败信息；Swift Foundation 同步推进 Data、NSData 桥接以及 URL 的纯 Swift 重写。

[WWDC26 最被忽视的王炸：告别“伪并发”陷阱，Swift 6.4 的 async defer](https://kinds.blog.csdn.net/article/details/161947066/ "WWDC26 最被忽视的王炸：告别“伪并发”陷阱，Swift 6.4 的 async defer")

**摘要：** 文章追溯了 `defer` 在 `async/await` 时代被「包一层 `Task`」绕过的尴尬——清理任务与函数生命周期脱钩，会带来资源泄漏和竞态风险。Swift 6.4 的 `async defer` 让异步清理回到「与函数同生死」的可靠语义，是一次表面小、影响深的修正。

[DoorDash 利用 Copilot 将基于 XCTest 的 iOS 测试套件转换为 Swift Testing](https://www.infoq.cn/article/dWBoVzphLY2HgoB0TwsU/ "DoorDash 利用 Copilot 将基于 XCTest 的 iOS 测试套件转换为 Swift Testing")

**摘要：** DoorDash 借助 Cursor 与自动化工具，把 CI 中两位数分钟、串行化的 XCTest 迁移到 Swift Testing：测试运行快 4–7 倍，`#expect` 提供更可读的失败信息；并以「每个迁移测试必须连续 10 次通过」为可靠性门槛。最终 CI 测试执行提速约 60%，整体构建提速约 40%，同时暴露出 XCTest 顺序执行所掩盖的共享状态、时间假设等隐藏问题。


## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 “进群” 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
