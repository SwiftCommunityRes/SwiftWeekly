## 前言

**本期是 Swift 编辑组自主整理周报的第五十一期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

也许未来无法预知，纵然梦想遥不可及。**Swift社区**会告诉你，未来可以自己创造，梦想始终青睐勇者！👊👊👊

> **周报精选**
>
> 新闻和社区：苹果突然宣布：裁员超600人！库克减持苹果，套现2.4亿元
> 
> 提案：同步互斥锁提案正在审查
> 
> Swift 论坛：讨论检查漏洞：关于 rethrows 的类型检查
>
> 推荐博文：在 ARM 和 RISC-V 微控制器上开始使用嵌入式 Swift
>
> **话题讨论：** 
> 
> 你看好 Al 电脑这一概念吗？
>
>**上期话题结果**

![](https://files.mdnice.com/user/17787/983f059b-1662-4e92-b221-0ca9a0cb518b.jpg)

根据投票结果可以出，程序开发的终极结果可能是在更加简单、快捷、兼容和统一的方向上不断前进，但具体会出现哪种形式的统一，还需要根据未来的技术发展和市场需求来进一步观察和探讨。

## 新闻和社区  

### 消息称苹果最快年底推出 M4 系列芯片：更擅长处理 AI 任务，支持最高 512GB 统一内存

2024 年 4 月 12 日

4 月 12 日消息，彭博社的马克 古尔曼在最新一期 Power On 时事通讯中，认为苹果正加速研发 M4 系列 Apple Silicon 芯片，有望提前到 2024 年年底装备在新款 Mac 设备中，且重点提高处理 AI 任务的性能。

苹果公司于去年 10 月发布了 M3、M3 Pro 和 M3 Max 芯片，古尔曼认为苹果同样会在今年 10 月前后推出 M4 系列芯片。

古尔曼认为苹果会率先升级 iMac 、低端 14 英寸 MacBook Pro 、高端 14 英寸 MacBook Pro 、16 英寸 MacBook Pro 和 Mac mini 机型；然后在 2025 年春季更新 13 英寸和 15 英寸 MacBook Air 机型；在 2025 年中期更新 Mac Studio；在 2025 年晚些时候更新 Mac Pro。

援引古尔曼报道，苹果公司即将生产 M4 处理器，预计至少有三个主要型号。低端芯片代号为 Donan，中端芯片代号为 Brava，高端芯片代号为 Hidra。

Donan 芯片将用于入门级 MacBook Pro、MacBook Air 机型和低端 Mac mini，Brava 芯片将用于高端 MacBook Pro 和高端 Mac mini。

Hidra 芯片是为 Mac Pro 设计的，这表明该芯片上市后会叫“Ultra”或“Extreme”级芯片。

M4 版本的 Mac 台式机可支持最高 512GB 的统一内存，比目前的 192GB 限制有了明显的提升。

M4 芯片将采用与 M3 芯片相同的 3 纳米工艺制造，但苹果供应商台积电可能会使用改进版的 3 纳米工艺，以提高性能和能效。苹果还计划增加一个经过大幅改进的神经引擎，增加用于人工智能任务的内核数量。（来源：IT之家）

### 消息称苹果加速推进折叠屏技术研发，首款产品有望明年登场

2024 年 4 月 9 日

 4 月 9 日消息，根据经济日报报道，苹果公司正在加速推进折叠屏产品，并认为会在 2025 年推向市场，但目前尚不确认产品形态。

![](https://files.mdnice.com/user/17787/ea0a8d24-b7cb-49ab-9656-7557e8050986.png)

该报道称苹果公司可能会在 2025 年推出首款折叠产品，并认为苹果的入局会改变现有折叠屏手机市场，当前三星和华为占据了全球折叠屏 80% 以上的市场份额，而苹果加入之后可能会出现“三足鼎立”的情况。

该报道称苹果公司的 iPhone 业务已出现疲态，在高端市场日益受到三星和华为的折叠屏冲击，因此正加速研发折叠产品以巩固其地位。

但报道认为苹果公司所面临的挑战在于，对用户体验的执着追求反而成为了“偶像包袱”，这固然能为用户带来极致体验，但现有的供应链可能无法达到其要求，一直阻碍苹果进军折叠屏市场。

IT之家此前报道苹果公司已经在研发折叠屏产品，只是现有的铰链供应很难达到其要求，因此项目一直没有太大的进展。（来源：IT之家）

### 苹果突然宣布：裁员超600人！库克减持苹果，套现2.4亿元

2024 年 4 月 6 日

综合央视财经、界面新闻 4 月 6 日报道，英国广播公司 4 月 5 日报道，因叫停自动驾驶电动汽车项目，美国苹果公司裁员 600 多人。苹果公司的公告显示，这批员工于 3 月 28 日接到裁员通知，裁员决定将于 5 月 27 日起生效。这是疫情以来该公司首次大规模裁员。

据了解，苹果公司曾投资数十亿美元研发一款没有方向盘和踏板的全自动驾驶汽车。不过，该公司从未公开承认该项目的存在。今年 2 月，苹果在内部宣布取消长达数年的自动驾驶电动汽车研发计划。当时有媒体报道称，该项目的部分员工将被调往其他部门，其他员工则可能被解雇。上述公告未明确提及苹果造车项目。裁员将影响到加州圣克拉拉八个办事处的员工，苹果公司总部则未受影响。

![](https://files.mdnice.com/user/17787/81b816d6-dcf7-4e99-8721-e19522d725d8.png)

截至当地时间 4 月 5 日，苹果报 169.58 美元，涨幅 0.45% ，市值 2.61 万亿美元。

美东时间 4 月 3 日，知名苹果爆料人马克·古尔曼( Mark Gurman )撰文表示，苹果公司的多个团队正在研究推进个人机器人技术，该领域有潜力成为苹果公司不断变化的“下一大事件”之一。

据悉，苹果的工程师在开发一种可以跟随用户在家中走动的移动机器人。苹果还开发了一种先进的桌面家用设备，利用机器人来将显示屏四处移动。尽管研发仍处于起步阶段，而且尚不清楚这些产品最终会发布，但苹果寻找新收入来源的压力越来越大。

据财联社，有行业分析表示，随着人工智能的迅猛发展，机器人成为一个可落地的AI应用，不少需求已被验证，这也是科技公司关注机器人研发的一个重要动因。人形机器人可能就是 AI 的终极形态。

中国电子学会发布的《中国机器人产业发展报告》显示，家庭服务机器人已占据我国服务机器人市场超过六成的份额，预计到 2024 年，中国服务机器人市场规模有望突破 100 亿美元。根据公开资料，国内扫地机器人头部企业科沃斯和石头科技 2022 年销额、销量合计市占率分别为 60.5% 和 50%。科沃斯此前亦与 iRobot 签署合作协议，有望最终达到将扫地机器人市场规模共同做大的目的。

值得一提的是，据媒体报道，在今年 CES 2024 上，科沃斯、石头科技等发布的新品售价都在 1000 美元以上。这些产品瞄准中高端市场，而且纷纷接入 Matter 智能家居协议，与苹果智慧家庭的生态打通，欲在 iRobot 抢食。

另财联社据 Choice 数据统计，A股苹果概念板块中，同时还叠加机器人概念的上市公司包括英洛华、蓝思科技、奥拓电子、畅联股份、博杰股份、天准科技、大族激光、领益智造、卓兆点胶、精研科技、凌云光、智立方、佳禾智能、科森科技、工业富联、宇环数控、智信精密、博众精工以及佰奥智能。

据多家媒体 4 月 5 日报道，SEC 监管文件显示，苹果 CEO 蒂姆・库克在 4 月 1 日和 2 日两天之内出售了 19.64 万股股票，套现超 3300 万美元（约合人民币 2.4 亿元）。

出售完这些股票之后，库克目前直接持有的苹果股票已减至 328.02 万股。以 4 月 4 日苹果公司收盘价算，库克持有苹果公司股票的市值约为 5.5 亿美元（约合 39.8 亿元人民币）。

## 提案

### 通过的提案

[SE-0425](https://github.com/apple/swift-evolution/blob/main/proposals/0425-int128.md "SE-0425") **128 位整数类型** 提案通过审查。该提案已在 **四十九期周报** 正在审查的提案模块做了详细介绍。

### 正在审查的提案

[SE-0432](https://github.com/apple/swift-evolution/blob/main/proposals/0432-noncopyable-switch.md "SE-0432") **不可复制类型的借阅和消费模式匹配** 提案正在审查。

不可复制类型（特别是不可复制枚举）上的模式匹配，除了对消耗模式匹配的现有支持外，还可以推广允许借用其主题的模式匹配。

[SE-0433](https://github.com/apple/swift-evolution/blob/main/proposals/0433-mutex.md "SE-0433") **同步互斥锁** 提案正在审查。

本提案向标准库引入了互斥锁（mutex）。`Mutex` 将成为同步模块中的一种新的同步原语。

[SE-0434](https://github.com/apple/swift-evolution/blob/main/proposals/0434-global-actor-isolated-types-usability.md "SE-0434") **global-actor-isolated 类型的可用性** 提案正在审查。

该提案涵盖了一系列关于 `global-actor-isolated` 类型的可用性类型的并发规则的变更，旨在提高其可用性。

## Swift论坛

1) 提议[SE-0433: 同步互斥锁](https://forums.swift.org/t/se-0433-synchronous-mutual-exclusion-lock/71174 "SE-0433: 同步互斥锁")

**内容概括**

SE-0433: 同步互斥锁

SE-0433 是一项提案，旨在引入 Swift 编程语言的同步互斥锁(SMEL)。SMEL 是一种同步原理，只允许一个线程在一次之内访问共享资源。该提案旨在提供更一致和可预测的锁定行为，使 Swift 编码变得更容易并安全。

**演变**

Swift 演变过程是指改变 Swift 编程语言的过程。提案被提交给 Swift 演变邮件列表，社区讨论并给予反馈。提案根据反馈进行修改后，由 Swift 核心团队做出最终决定。

**提案审查**

提案审查是演变过程中非常重要的一部分。审查负责人负责监督审查过程，审查可以在本论坛帖子上发布或者直接发送给审查负责人。撰写审查时，应该提供有用的反馈，评估与 Swift 相匹配的提案，并与其他语言相似功能进行比较。

审查过程是一个机会，让 Swift 社区改进提案并决定 Swift 语言的方向。审查过程是演变过程中非常重要的一部分，并且鼓励参与。

该提案在社区中获得积极反馈，许多人认为这是 Swift 语言急需的补充。一些审查人士表示，提议的 SMEL 并不完全取代专门锁定解决方案，但是它补充了 Swift 标准库的空白。另一些人表示，提议的 SMEL 易于移植，并且应该很容易将其融入现有的 Swift 代码中。

整体而言，审查 SE-0433 的反馈都很积极，并且该提案很可能在 Swift 演变过程中继续前进。

2) 讨论[检查漏洞:关于 rethrows 的类型检查](https://forums.swift.org/t/type-checking-hole-regarding-rethrows/71162 "检查漏洞:关于 rethrows 的类型检查")

**内容概括**

讨论在 Swift 论坛上发生了，涉及到了 `rethrows` 的类型检查漏洞。该代码编译通过，但在运行时使用时会产生一条崩溃。编译器抱怨称没有什么东西可以"尝试"，但是局部函数在考虑 rethrows 传播时并没有正确地进行类型检查。

参与讨论的 Lincoln Wu (CrystDragon) 表示已知有关 rethrows 检查的问题，但由于标准函数，比如 `DispatchQueue.sync`，遵循 rethrows 精神，以及一个更安全的实现不允许的方式使用它们，因此无法修复。然而，斯拉瓦·佩斯特夫(Slava_Pestov)希望这些模式足够奇怪而罕见，以便在所有新代码中完全可以使用类型的抛出来代替 rethrows，并且有一天可以逐步弃用 rethrows。

蒂诺(Tino)建议一种简单的修复方法，但斯拉瓦_Pestov 解释说，这样做需要引入一个 rethrows(不安全)逃逸口，或者需要迁移现有的使用方式到类型的抛出来，而且在那个阶段并不值得麻烦。斯拉瓦_Pestov 还表示，Swift 已经达到了兼容性问题导致修复错误的状态，而且关注的是成本和受益比。

3) 讨论[使用 NSLock 时，读取值时是否需要调用 lock()?](https://forums.swift.org/t/while-using-nslock-do-i-need-to-call-lock-when-reading-a-value/71170 "使用 NSLock 时，读取值时是否需要调用 lock()?")

**内容概括**

在使用 NSLock 时，读取值时是否需要调用 lock() 方法?

在 Swift 语言中，NSLock 类提供了一种方法来同步共享资源的访问。lock() 方法用于锁定资源，而 unlock() 方法用于释放锁定。

当使用 NSLock 时，需要记住锁定应该持续仅需要必要的时间，并尽快释放它以允许其他线程访问资源。

在某些情况下，可能需要在读取资源值之前调用 lock() 方法，以防止其他线程同时修改值。然而，在其他情况下，读取值时可能无需调用 lock()，只要当前没有其他线程正在修改值即可。

譬如，如果在多线程环境下更新计数器，则可能无需调用 lock() 方法读取计数器值。然而，如果计数器被非多线程安全方式修改，则可能需要调用 lock() 方法以防止其他线程同时修改值。

一般而言，使用 NSLock 时，需要仔细考虑资源的使用情况以及其行为，并采取适当的锁定策略以确保资源以多线程安全方式访问。

4) 讨论[寻找 AttributeSyntax 装饰的类型](https://forums.swift.org/t/finding-type-decorated-by-attributesyntax/71206 "寻找 AttributeSyntax 装饰的类型")

**内容概括**

讨论集中讨论了找到一个对象装饰了 `AttributeSyntax` 协议的类型。讨论涉及使用 Swift 语言以及一个名为 `swift-syntax` 的工具。

用户 Matt Cox 正在使用一个名为 `SyntaxVisitor` 的工具，以搜寻具有 `name` 属性设置为"Foo"的 `AttributeSyntax` 节点。这种做法很好，但是下一步就是要收集具有"Foo"属性的对象了。在这种情况下，用户想要获得一个具有"Bar"属性的 `StructDeclSyntax` 节点，以便能够检查其子节点。

用户正在苦苦思考如何获得这个对象。他问道，如果能够得到一个 `AttributeSyntax` 节点，那么该节点所附着的对象(类、枚举、结构体等)是如何获得的呢?

约翰.麦考回复了这个问题，表示如果阅读树形结构正确，那么 `AttributeSyntax` 节点的父节点应该是一个名为 `AttributeListSyntax` 的节点，而父节点应该是属性列表所在节点。

Matt Cox 感谢约翰.麦考的帮助，而 Wes 建议使用 https://swift-ast-explorer.com 这个工具来帮助回答相关问题。Matt Cox 认为该工具很有帮助，并感谢 Wes 提供这个工具。

5) 讨论[可否丢弃 Unmanaged.retain() 返回值?](https://forums.swift.org/t/is-it-safe-to-discard-returned-value-of-unmanaged-retain/71176 "可否丢弃 Unmanaged.retain() 返回值?")

**内容概括**

在《Is it safe to discard the returned value of Unmanaged.retain()?》中讨论了 Unmanaged 结构中的 retain 函数的行为。retain 函数返回一个新的 Unmanaged 实例，但是该实例并没有被标记为 `@discardableResult` 属性，且文档没有解释为什么这样做。实现并不会修改该结构，它只是返回了一个与原来的 Unmanaged 引用相同的"指针"。

帖子的作者 Nathan S. 问是否可以将返回的 Unmanaged 直接丢弃或者必须对其做某些事情，而不是直接丢弃。

Kyle Sluder 回应说可能是因为 retain 函数模仿了 Obj-C 的 retain 函数，而且在 Swift 中 retain 函数没有被标记为 `@discardableResult` 属性，所以它可以在未来被标记为这个属性并且不会破坏旧代码。

Nathan S. 回应说他会使用返回的 Unmanaged 来关闭警告直到 `@discardableResult` 被添加。

Kyle Sluder 回应说可以覆盖-retain 函数以便它返回与自身不同的东西，但是必须确保 Swift 能将返回值传递给兼容性问题的库。

综上所述，讨论还指出了 `Unmanaged.retain()` 函数的行为，并且讨论了将其标记为 `@discardableResult` 的优缺点。

6) 讨论[没有 MainActor 警告的扩展](https://forums.swift.org/t/no-mainactor-warning-in-extension/71180 "没有MainActor警告的扩展")

**内容概括**

约西普·卡瓦尔(Josip Cavar)注意到，当一个扩展调用并发函数时，并没有出现“MainActor 警告”，与预期相反。

卡瓦尔提供了一个示例，在 Swift 5.10 中展示了这种行为。该示例演示了当移除 “start” 函数从扩展中并调用它从主线程时，就会出现 “MainActor警告”，与预期相符。然而，当把 “start” 函数留在扩展中时，没有警告被产生。

```Swift
@MainActor
public final class Test {
    func process() {
    }
}

public extension Test {
    func start() {
        let browser = NWBrowser(
            for: .bonjour(type: MIDINetworkBonjourServiceType， domain: nil)，
            using: NWParameters()
        )
        browser.browseResultsChangedHandler = { [weak self] newResult， changes in
            Task { [weak self] in
                self?.process() // no warning， compiles ok
            }
        }
    }
}
```

Quinn “The Eskimo!”(埃斯库莫)对卡瓦尔的帖子发表了回应，表示这种行为是预期的，并且将“严格并发检查”设置为“完成”将在扩展中生成“MainActor警告”。埃斯库莫还提供了一个示例演示了这一点。

卡瓦尔承认埃斯库莫的解释并感谢他的回应。

总之， 讨论揭示了 Swift 并发系统中扩展调用并发函数而不会默认生成 “MainActor警告” 的小特性。但是，将 “严格并发检查” 设置为 “完成” 将正确生成警告。

7) 讨论[Swift String 对字符的理解是否稳定?](https://forums.swift.org/t/will-swift-strings-understanding-of-characters-remain-stable/71164 "Swift String 对字符的理解是否稳定?")

**内容概括**

**论文摘要**: 论文标题为 “Swift String 对于字符的理解是否稳定?”的 Swift 论坛帖子讨论了 Swift String 对于字符的理解是否会随着时间的推移而变化。该帖子考虑了由于演变的 Unicode 规则和标准库中的修复而可能发生的变化对 Swift String 的行为的影响。

讨论围绕着一个字符串中包含的字符的稳定性和解释，尤其是当字符串包含 unicode 字符时。如果 Swift String 只包含标准库版本的 Unicode 中定义的字符，则其对字符的理解是稳定的。然而，如果字符串包含未被定义的字符，则在处理该字符串时，由于更新版本的 Unicode 规则，其解释可能会发生变化。

帖子还指出，苹果平台上的 Swift 标准库是系统库，因此可以跨设备支持不同版本的 Unicode。通过使用 `.age` 属性，可以强制设置最大版本，从而排除不能被可靠地解释的字符。

帖子承认标准库代码中可能会出现错误并被修复，标准库维护人员将决定是否修复错误，这可能会改变现有字符串的行为。另一种选择是继续使用错误的实现以保持稳定性，但这种做法被反对。

帖子还讨论了发现错误后的潜在解决方案，并讨论了如何改变字符串的行为。结论是，即使有些属性行为发生变化，仍然推荐采取改变字符串行为的解决方案。

讨论强调了维持稳定的 Swift String 实现，同时应对潜在的 Unicode 规则变化和标准库错误修复。

## 推荐博文

[在 ARM 和 RISC-V 微控制器上开始使用嵌入式 Swift](https://www.swift.org/blog/embedded-swift-examples/ "在 ARM 和 RISC-V 微控制器上开始使用嵌入式 Swift")

**摘要：**  这篇 Swift 官方博客介绍了嵌入式 Swift 在 ARM 和 RISC-V 微控制器上的应用。文章首先介绍了 Swift 作为一种可扩展的编程语言，在桌面应用、移动应用、服务器后端和系统软件等领域的广泛应用。随后，作者介绍了一种新的实验性编译模式，使得 Swift 可以针对 ARM 和 RISC-V 微控制器等嵌入式环境进行开发，这对于构建 IoT 设备等专业和业余电子项目非常有用。虽然在嵌入式环境中，并非所有 Swift 的特性都适用，但新的 Embedded Swift 编译模式关闭了某些语言特性，以产生适用于固件的独立二进制文件。

尽管关闭了一些语言特性，但 Embedded Swift 子集仍然与开发人员喜爱的“完整” Swift 非常接近，并且易于编写符合惯例、易于阅读的 Swift 代码。

[讲讲 swift 中 defer 的实现原理和使用场景](https://juejin.cn/post/7350860141582385188/ "讲讲 swift 中 defer 的实现原理和使用场景")

**摘要：**  这篇文章详细介绍了 Swift 中的 defer 语句，探讨了其用法和实现原理，并提供了多个具体的使用场景。通过分析 Swift 官方源码，解释了 defer 的底层实现机制，以及在特殊场景下的行为。文章强调了 defer 在资源管理和清理工作中的重要性，并指出了一些常见的误用情况，例如在 defer 中使用 return 语句。总的来说，defer 是 Swift 中一个非常有用的特性，它简化了资源管理和清理工作的代码编写。

[详细讲讲 swift 5.9 出的新语法：参数包](https://juejin.cn/post/7337225888264519734/ "详细讲讲 swift 5.9 出的新语法：参数包")

**摘要：**  这篇文章详细介绍了 Swift 5.9 中引入的新功能：参数包（Parameter Packs），并探讨了在日常开发中的应用场景。文章解释了参数包的概念，指出在之前的代码中，随着泛型数量增加，函数声明变得越来越冗长且难以维护，而参数包能够通过简化函数声明的方式提高代码的可读性和可维护性。文章提供了几个实用的例子，包括利用参数包简化 KeyPath 取值、优化缓存性能开销大的函数以及封装高阶函数等。

## 话题讨论

苹果宣布为提升电脑销售，计划使用专注于人工智能的 M4 芯片彻底改造整个 Mac 系列，公司将致力于快速过渡到新处理器，此次改造将带来人工智能功能和内存改进。消息一出，苹果股价当日拉升。**你看好 Al 电脑这一概念吗？**

1. 看好，不是概念有实际提升。
2. 不看好，真正提升有限。
3. 不好说，先看产品。

欢迎在文末留言参与讨论。


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
