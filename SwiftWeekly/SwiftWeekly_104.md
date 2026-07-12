## 前言

嗨，Swift 社区的小伙伴们 👋

这是 **Swift 编辑组自主整理的第一百零四期周报**。经过一段时间的打磨，目前周报的各个模块已经逐步稳定下来，也越来越贴近大家的阅读习惯。

如果你对内容选题、结构安排或呈现方式有任何建议，**非常欢迎在文末留言**，你的反馈会直接影响后续周报的方向。

Swift 周报已在 GitHub 开源：
[https://github.com/SwiftCommunityRes/SwiftWeekly](https://github.com/SwiftCommunityRes/SwiftWeekly)

欢迎提交 issue、投稿或推荐内容。目前计划 **每两周发布**，也非常欢迎志同道合的朋友加入编辑组。

我们能算出星辰的轨道，却摸不透一阵台风的走向，渺小从来不是认输的理由，而强大便是在废墟上也能重新筑起万家灯火。👊👊👊

> **本期精选速览**
>
> * **新闻和社区**：苹果 300 亿美元芯片豪赌背后的 AI 硬件升级战略、iPhone 18 Pro 延续 LPDDR5X 架构、苹果测试长鑫存储 DRAM 能否入局
> * **提案**：SE-0513、SE-0531、SE-0532 正式通过；SE-0535 和 SE-0536 正在审查
> * **Swift 论坛**：`for await` 中 `weak self` 解包时机、Nanosaur 2 移植到 3DS、多语言 Swift Package 导入链接问题、SwiftRD 跨平台 IDE 集成
> * **推荐博文**：Swift 社区 2026 年 6 月版动态、SwiftUI Document 协议性能提升、跨平台 Swift 博客系列与 Android 应用

## 话题讨论

**OpenAI 突然宣布终止对中国 API 服务，国产大模型迎来「接棒」时刻——你更看好谁？**

6 月 25 日，OpenAI 向中国开发者发送邮件，宣布自 7 月 9 日起禁止来自中国（包括香港、澳门）的 API 调用。消息一出，百度、阿里、智谱等国内大模型厂商迅速推出「迁移扶持计划」，试图承接这波溢出需求。这场「断供」背后，是技术封锁升级还是市场策略调整？国产大模型能否真正填补空缺？

1. **百度文心一言**：全栈自研生态成熟，但「AI 味」质疑不断
2. **阿里通义千问**：开源路线坚定，生态建设速度较快
3. **智谱 GLM**：学术背景深厚，中英双语能力强
4. **字节豆包**：用户增长凶猛，但技术积累待验证
5. **DeepSeek**：性价比突出，但生态建设起步较晚

欢迎在留言区写下你的选择和理由，**下期周报将公布投票结果与读者观点摘要**。

## 新闻和社区

### 苹果承诺向博通投资超300亿美元用于美国芯片制造，消费电子AI化浪潮加速

*2026 年 7 月 9 日｜来源：新浪财经*

苹果（AAPL.US）宣布扩大与博通（AVGO.US）的合作，签署一项预计超过 300 亿美元的多年期协议，用于在美国生产超过 150 亿颗芯片。该协议包括对博通科罗拉多州工厂的 15 亿美元扩建投资，博通将为苹果制造用于蜂窝、Wi-Fi 和蓝牙连接的无线组件以及定制 ASIC 芯片。消息公布后博通股价上涨近 5%。这一合作是苹果迄今最大的美国制造投资，也是消费电子 AI 化浪潮下芯片需求持续扩张的最新注脚。

**一、苹果300亿美元芯片投资，消费电子AI化进入"硬件升级"阶段**

苹果与博通的 300 亿美元芯片协议，本质上是为 AI 时代的消费电子硬件升级提前锁定产能。苹果正在将 AI 能力深度嵌入 iPhone、iPad、Mac 等全系产品，AI 手机、AI PC、AI 可穿戴设备对芯片的算力、连接能力和功耗效率提出了更高要求。定制 ASIC 芯片成为苹果实现差异化竞争的核心手段。

从产业链角度看，苹果的巨额芯片投资将拉动整个消费电子供应链的订单增长。立讯精密（002475.SZ）作为苹果核心代工厂商，在 AI 手机和 AI 可穿戴设备的组装份额持续提升；工业富联受益于AI服务器和 AI 终端设备的制造需求；京东方在 AI 手机 OLED 屏幕领域市占率持续扩大；东山精密和华工科技在精密结构件和光通信模块等环节深度绑定苹果和 AI 硬件产业链。

**二、AI 手机和 AI PC 换机周期叠加，消费电子需求进入上行通道**

2026 年全球消费电子市场正在经历 AI 驱动的换机周期。AI 手机方面，苹果 iPhone 18 系列全面搭载 AI 功能，预计 2026 年下半年出货量将同比增长 15% 以上；AI PC 方面，联想、戴尔、惠普（HPQ.US）等厂商 AI PC 出货量快速增长，2026 年全球 AI PC 渗透率有望突破 40%。

换机周期对消费电子产业链的拉动是全方位的：芯片、屏幕、摄像头、结构件、电池等环节均将受益。立讯精密在 AI 手机组装和零部件领域的份额持续提升，京东方在 AI 手机 OLED 屏幕的出货量快速增长，工业富联在 AI 服务器和 AI PC 制造领域的订单饱满。消费电子行业正在从"存量竞争"走向"AI 驱动的增量增长"。

**三、苹果供应链本土化趋势强化，国内供应商份额有望提升**

苹果 300 亿美元美国芯片制造投资，反映的是全球科技巨头供应链多元化和本土化的趋势。但对中国消费电子供应链而言，这一趋势并非利空——苹果在中国的制造布局仍然庞大，且国内供应商在精密制造、成本控制和快速响应方面的优势难以替代。

从实际数据看，立讯精密 2026 年 Q1 来自苹果的营收同比增长超 20%，工业富联 AI 服务器业务营收同比增长超 50%，京东方在苹果供应链中的屏幕份额持续提升。国内消费电子供应商正在从"低端代工"向"精密制造+核心零部件"升级，在苹果和全球消费电子产业链中的地位不断强化。

### 消息称苹果 iPhone 18 Pro 的 A20 Pro 芯片沿用 LPDDR5X 架构

*2026 年 7 月 9 日｜来源：IT之家*

科技媒体 Wccftech 昨日（7 月 8 日）发布博文，报道称苹果 iPhone 18 Pro 和 iPhone 18 Pro Max 上装备的 A20 Pro 芯片不会升级至 LPDDR6，会继续采用 LPDDR5X 内存，但会升级内存性能。

IT之家查询公开资料，A19 Pro 芯片采用 4 通道 LPDDR5X 内存架构，每个通道的位宽为 16-bit，4 个通道组合形成 64-bit 的总内存位宽，并针对本地 AI 运行场景专门优化，配备 12GB 内存。

最新消息称 A20 Pro 芯片不会升级到 LPDDR6 内存架构，采用 6 通道 LPDDR5X 内存架构，每个通道的位宽依然为 16-bit，总内存位宽为 96-bit。

![](https://files.mdnice.com/user/17548/850ef92a-624f-4b74-a9a8-9025f49ba933.png)

![](https://files.mdnice.com/user/17548/6e7c7383-e815-48cc-836f-245318d89108.png)

针对本地 AI 处理场景而言，运算不仅依赖算力，也受内存带宽限制，更大的位宽可以减少等待数据处理时间。

**附：两种内存架构标准介绍**

**LPDDR5X**：一种面向移动设备的低功耗内存标准，重点在于兼顾带宽、功耗和封装空间，常用于智能手机和平板等终端。它是 LPDDR5 的增强版本，适合高性能移动 SoC 搭配使用，典型场景包括多任务处理、影像计算和本地 AI 推理。

**LPDDR6**：下一代低功耗移动内存标准，通常被视为 LPDDR5X 之后的演进方向。其目标是进一步提高数据传输效率与能效，适用于更高带宽需求的移动计算场景，例如更复杂的生成式 AI 模型、本地大模型推理与高规格图像处理。

### 消息称苹果启动长鑫存储DRAM芯片测试 拟用于中国市场销售设备

*2026 年 7 月 8 日｜来源：新浪财经*

7 月 8 日消息，据英国《金融时报》援引知情人士消息报道，苹果公司已开始测试中国存储芯片厂商长鑫存储技术（CXMT）生产的 DRAM 内存芯片，计划将其用于在中国市场销售的设备。报道称，苹果尚未承诺将这些芯片用于商业量产，目前仍处于评估阶段。

报道指出，苹果正在美国科技企业中牵头游说华盛顿，争取允许更广泛地使用长鑫存储的产品。据此前报道，苹果一直在向美国政府申请采购长鑫存储 DRAM 芯片的许可。苹果还同时有意采购长江存储的 NAND 闪存产品。这些举措旨在强化苹果供应链的韧性，提升对存储半导体市场进一步变化的抵御能力。

报道称，苹果此次游说的背景是存储芯片价格的失控式上涨。由于 AI 数据中心的爆炸性需求，三星、SK海力士和美光等主要存储厂商已将大量产能转向高利润的 HBM（高带宽内存），导致消费级 DRAM 和 NAND Flash 供应持续紧张、价格飙升。

据彭博社报道，严重的内存供应短缺已迫使苹果将 MacBook、iMac、iPad 等多款产品提价，部分 Mac 机型最高涨价 1000 美元。标准型 DRAM 合约价在 2026 年初飙升约 55% 至 60%，迫使苹果罕见上调 MacBook Air、iPad 等产品售价，为近十年来最大规模硬件涨价行动。

然而，美国银行在最新研报中对苹果大规模采用长鑫存储 DRAM 的可能性泼了冷水，并列出了三大限制因素：

**一是地缘政策约束**：长鑫存储被列入美国国防部 1260H 名单，虽非出口禁令，但触及敏感供应链审查，美国对华半导体管制政策形成实质性硬性门槛。

**二是技术指标差距**：苹果移动设备对 LPDDR5X 内存要求传输速率超过 10Gbps、工作电压 1.1V 并搭载 ECC 纠错功能。长鑫存储现有 LPDDR5X 最高速率虽可达 10.667Gbps，但受制于相对落后的制程工艺，芯片寄生电容与漏电流偏高，功耗与散热表现较难完全匹配旗舰 iPhone 的严苛规格。

**三是专利诉讼风险**：全球 DRAM 核心专利池由三星、SK 海力士与美光长期垄断，若苹果大举采用长鑫产品，极易遭第三方提告侵权，增加供应链法律成本与不确定性。

综合上述阻碍，美银研判指出，即便苹果采用长鑫存储 DRAM，初期也仅可能限于 iPhone 18e 等入门低端机型。鉴于低端 iPhone 在中国市场销量疲软，实际采购订单体量有限，难以形成具备产业意义的采购规模。

不过，美银与多数分析师均指出，苹果此举具有鲜明的商业战略意图。苹果可能会利用长鑫存储的 DRAM 作为筹码，在与三星、SK 海力士和美光三大 DRAM 制造商谈判 2026 年下半年或 2027 年的合约价格时，增加自身的议价能力。

报道指出，长鑫存储已跻身全球第四大 DRAM 内存芯片生产商，仅次于三星电子、SK 海力士和美光科技。据 Omdia 数据，按 2025 年第四季度 DRAM 销售额统计，长鑫存储全球市场份额已达 7.67%。长鑫存储去年约占全球 DRAM 晶圆产能的 11%，随着合肥、上海和北京新生产线陆续投产，这一比例预计将在 2028 年提升至 15%。

另外，报道还指出，长鑫存储目前处于满产状态，且难以满足中国本土企业的需求，这引发了其能否向苹果大规模供货的疑问。

## 提案

### 通过的提案

[SE-0513](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0513-commandline-executablepath.md "SE-0513")
**API 获取当前可执行文件的路径** 提案已通过审查。

该提案此前已在 **第一百零三期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0531](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0531-literal-expressions.md "SE-0531")
**字面表达（Literal Expressions）** 提案已通过审查。

该提案此前已在 **第一百零一期周报** 的「正在审查的提案」模块中做过详细介绍。

[SE-0532](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0532-optional-noncopyable-improvements.md "SE-0532")
**Optional 不可复制类型的改进与泛化** 提案已通过审查。

该提案此前已在 **第一百零一期周报** 的「正在审查的提案」模块中做过详细介绍。

### 正在审查的提案

[SE-0535](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0535-global-mirrors-configuration-cli.md "SE-0535")
**添加用于编辑全局镜像配置的CLI** 提案正在审查。

SPM 支持本地（每个项目）和共享（每个用户）镜像配置，尽管 CLI 只允许编辑本地配置文件。此提案在现有 CLI 中添加了可选的 `--global` 标志，用于编辑全局配置。

[SE-0536](https://github.com/swiftlang/swift-evolution/blob/main/proposals/0536-registry-search.md "SE-0536")
**软件包注册表搜索** 提案正在审查。

SE-0292 为 Swift 生态系统引入了软件包注册服务。其未来方向部分将软件包搜索确定为注册服务的自然扩展。本推销建议在软件包注册表规范中添加一个搜索端点，并在 Swift 软件包管理器中添加相应的 `swift package-registry search` 命令，使用户能够按名称、作者和其他标准在注册表中发现软件包。

## Swift论坛

### 1、`for await` 中的 `weak self` 应该在哪里解包

作者：kelin ｜ 发布日期：2026 年 7 月 10 日
[阅读原帖](https://forums.swift.org/t/for-await-and-weak-self/88192 "`for await` and `weak self`")

**核心内容：**
Vladimir Kelin 讨论在长期监听 **AsyncSequence** 时，`weak self` 是在 `for await` 循环前解包，还是在每次迭代中解包。两种写法都会编译，但生命周期语义明显不同。

**动机说明：**
如果观察任务可能持续很久，开发者通常希望对象释放后监听自动停止，而不是因为闭包提前强持有 `self` 导致实例被延长生命周期。

```swift
Task { @MainActor [weak self] in
    for await state in engine.stateUpdates {
        guard let self else { return }
        self.lastState = state
    }
}
```

**主要修改或代码示例：**
Itai Ferber 指出，如果在循环前 `guard let self`，`self` 会在整个循环期间被强持有；如果在循环内部解包，则每次收到新值都会重新读取弱引用，一旦对象释放就退出。对普通同步循环也类似，编译器通常不能把检查随意提升到循环外，因为这会改变可观察语义。

**讨论亮点：**
Slava Pestov 追问这里是否真的需要 `weak self`，提醒大家先确认是否存在引用循环。讨论最后聚焦到 **ARC**、弱引用读取和优化器不能改变对象生命周期语义。

**简要点评：**
长期观察类任务中，把 `guard let self` 放在循环内部通常更贴近"对象存在才继续处理"的意图；若希望任务本身持有对象到观察结束，则循环前解包更直接。

### 2、SE-0536：为 Swift Package Registry 增加搜索能力

作者：Mikaela Caron ｜ 发布日期：2026 年 7 月 10 日
[阅读原帖](https://forums.swift.org/t/se-0536-package-registry-search/88203 "SE-0536: Package Registry Search")

**核心内容：**
**SE-0536 Package Registry Search** 正式进入审查，审查期从 2026 年 7 月 10 日持续到 7 月 24 日。该提案希望为 **Swift Package Registry** 增加标准化搜索能力，让客户端能通过统一接口查找包。

**动机说明：**
Swift 包生态正在增长，但包发现能力仍依赖网站、第三方索引或人工检索。标准化搜索接口可以让 `swift package`、IDE 和私有 registry 以一致方式提供包发现体验。

**主要修改或代码示例：**
讨论重点集中在搜索结果结构、分页稳定性和查询语义上。Will Field-Thompson 质疑结果对象中的 `registry` 字段适用场景，并建议考虑基于游标的 `after` / `before` 分页，或让服务器通过 `Link` header 返回不透明分页信息。

**讨论亮点：**
Joseph Heck 建议区分模糊搜索和确定性过滤：例如 `scope`、`author`、`pkg`、`name` 这类限定条件最好保持精确匹配，避免过滤条件被模糊扩展后产生意外结果。也有人提醒 PyPI 的 `pip search` 已被关闭，说明服务端搜索接口需要谨慎设计。

**简要点评：**
这是 **SwiftPM** 生态基础设施层面的重要补齐。真正难点不只是"能搜"，而是如何在不同 registry 实现之间保持稳定、可分页、可预期的搜索语义。

### 3、Nanosaur 2 被移植到 Nintendo 3DS

作者：Alsey Coleman Miller ｜ 发布日期：2026 年 7 月 10 日
[阅读原帖](https://forums.swift.org/t/nanosaur-2-ported-to-nintendo-3ds/88193 "Nanosaur 2 ported to Nintendo 3DS")

**核心内容：**
Alsey Coleman Miller 分享了一个 **Nanosaur 2** 分支：将原本的 C 游戏引擎和渲染代码改写为 **Swift**，并加入 **Metal** 与 **Nintendo 3DS** 支持，同时让渲染层从 OpenGL 中解耦。

**动机说明：**
这个项目展示了 Swift 在复古游戏、掌机设备和跨平台渲染上的可行性。作者还为双屏设备加入支持，例如在下屏显示 HUD，适配 Anbernic DS 等设备形态。

**主要修改或代码示例：**
作者移除了原项目中对 Classic Mac Toolbox 的依赖，并向原始项目提交了 PR，内容包括 Swift 移植、Metal renderer 和 Nintendo 3DS port。项目重点不是单个 API，而是把旧游戏工程迁移成更现代、更可移植的架构。

**讨论亮点：**
社区成员对 Pangea Software 旧游戏开源表示惊喜，也有人补充 **Nanosaur** 在 Apple 游戏史中的定位并非"第一款 Mac 3D 游戏"，提醒相关历史表述需要更精确。

**简要点评：**
这类 showcase 很适合观察 Swift 的边界：它不只服务 Apple 平台应用，也能进入游戏移植、嵌入式设备和自定义渲染管线。

### 4、多语言 Swift Package 中的导入与链接问题

作者：eueu ｜ 发布日期：2026 年 7 月 10 日
[阅读原帖](https://forums.swift.org/t/multi-language-library/88196 "Multi-language library")

**核心内容：**
eueu 在 Linux 上使用 **Swift Package Manager 6.2** 构建同时包含 C、C++ 和 Swift 的库时遇到两个问题：应用侧需要额外 `import` C target 才能看到符号，以及 C++ 目标的对象文件存在但链接失败。

**动机说明：**
混合语言包是 Swift 跨平台和系统编程的重要场景。开发者希望对外暴露一个统一 Swift 模块，而不是要求使用方理解内部 C/C++/Swift target 拆分。

```swift
@_exported import TC
```

**主要修改或代码示例：**
Mahdi Bahrami 建议在 Swift 模块中使用 `@_exported import OtherLib` 转发依赖模块 API，这解决了"只想 import 一个库"的问题。Bassam Khouri 提到 Swift 6.4 起 **SwiftPM** 默认构建系统变为 **Swift Build**，未来对多语言 target 的支持可能更容易完善。

**讨论亮点：**
发帖者最终表示在 Swift 6.2.4 下也跑通了，不需要升级到 6.4 编译器；第一个问题由 `@_exported import` 解决，第二个链接问题则通过试错修复，仍在确认真正起作用的配置。

**简要点评：**
`@_exported import` 虽然是 underscored 属性，但在模块门面层很常见。多语言包的链接问题仍需要依赖 **SwiftPM** 和构建系统继续打磨，尤其是在 Linux 场景。

### 5、SwiftRD：面向 Visual Studio 与 IntelliJ 的 Swift IDE 集成

作者：Jascha ｜ 发布日期：2026 年 7 月 11 日
[阅读原帖](https://forums.swift.org/t/major-new-r-based-swift-ide-integration-in-progress-for-full-swift-support-in-visual-studio-and-intellij-with-bidirectional-c-interoperability-to-boot/88212 "Major new R# based Swift IDE-integration In Progress for full Swift support in Visual Studio and IntelliJ with bidirectional C++ interoperability to boot")

**核心内容：**
Jascha 介绍了 SoftOmni 正在开发的 **SwiftRD**：一个基于 **ReSharper** 的开源 Swift 实现，目标是在 Visual Studio、Rider 以及未来的 IntelliJ 系 IDE 中提供更完整的 Swift 支持，并支持与 JetBrains C++ 前端的双向互操作。

**动机说明：**
Swift 在 Windows 和 Linux 上的 IDE 体验仍明显弱于 macOS。SwiftRD 试图不依赖 **SourceKit**，而是用 C# 从零实现独立的 Swift 语言前端，为跨平台 IDE 提供语义分析、补全、重构和调试等能力。

**主要修改或代码示例：**
项目计划优先支持 **SPM** 工程，核心 Swift engine 预计 2026 年底基本完成，数据流分析计划在 2027 年第一季度推进；Early Access 预计在 2027 年第二季度，初始发布目标在 2027 年第三到第四季度。路线图包括语义高亮、格式化、补全、检查与 quick fix、调试、跳转定义、引用查找、DocC、Swiftly 版本管理以及测试运行集成。

**讨论亮点：**
Felix 表示期待跨平台 SPM 项目的支持；Jascha 补充说这正是项目推动的重要原因之一。Martin Lau 建议现代服务端 Swift 支持应考虑 **Hummingbird**，而不是维护状态较弱的 Kitura。

**简要点评：**
SwiftRD 仍是长期工程，但方向很值得关注：如果独立 Swift 前端和 IDE 插件生态成形，Swift 的非 Apple 平台开发体验可能会迎来重要补强。


## 推荐博文

以下三篇文章非常值得一读，适合本周「提升技能 + 开阔思路」：

[Swift 社区动态：2026年6月版](https://www.swift.org/blog/whats-new-in-swift-june-2026/ "Swift 社区动态：2026年6月版")

**摘要：** 这篇官方月度动态回顾了 WWDC 2026 期间 Swift 生态的多个重要进展。Apple在Platforms State of the Union 中宣布，核心操作系统内核的部分组件正在用Swift编写；QUIC传输层已被 Swift 重写并开源为 swift-nio-quic 包；Apple 还发布了Foundation Models框架的工具包，并承诺未来开源框架本身。全文展现了Swift正从应用层向操作系统底层稳步渗透的技术趋势。

[SwiftUI 新增文档协议，性能全面提升](https://www.infoq.com/news/2026/07/swiftui-wwdc26/ "SwiftUI 新增文档协议，性能全面提升")

**摘要：** 这篇报道系统梳理了 WWDC 2026上SwiftUI 的核心更新：新的 Document 协议通过快照差异比较和异步读写提升文档型应用的数据处理效率；工具栏API增强了按钮显示优先级的控制能力；滑动操作现已支持任意视图；AsyncImage 获得自动 HTTP 缓存支持，@State 实现惰性初始化，全新的ContentBuilder 则终结了困扰开发者多年的"编译器无法在合理时间内类型检查此表达式"的经典编译错误。

[跨平台Swift：博客系列与简易 Apple/Android 应用](https://forums.swift.org/t/cross-platform-swift-blog-series-and-simple-apple-android-app/87557/ "跨平台Swift：博客系列与简易Apple/Android应用")

**摘要：** 这篇社区分享介绍了一个名为 "Cross-platform Swift" 的博客系列及配套的可构建示例项目，使用 CMake 与官方 Swift Android SDK 构建了一个简易 Android 应用。随着 Swift 6.3 正式发布官方 Android SDK，该系列博客填补了从理论到实践的关键空白——涵盖环境配置、Swift与Java/Kotlin 互操作，以及双端共享业务逻辑的具体模式。


## 关于我们

**Swift 社区** 是由 Swift 爱好者共同维护的技术组织，主要通过微信公众号运营。

我们专注于 **Swift 实战、SwiftUI、Swift 基础** 三大方向，每周为你带来精选内容与最新生态资讯。

**关注公众号：「Swift社区」**
后台回复 "进群" 即可加入开发者交流圈。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
