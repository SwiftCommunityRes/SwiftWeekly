## 前言

**本期是 Swift 编辑组自主整理周报的第二十期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

最无情的永远不是环境，而是缺乏勇气的内心。**Swift社区**与你一起，赤胆平乱世，长枪定江山！👊👊👊

> **周报精选**
>
> 新闻和社区：担心泄密！外媒：苹果公司限制员工使用ChatGPT
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

### 担心泄密！外媒：苹果公司限制员工使用ChatGPT

中新经纬 5 月 19 日电 据华尔街日报中文网 19 日报道，其获悉的一份文件以及知情人士的消息显示，苹果公司已经限制使用 ChatGPT 和其他外部 AI 工具。

根据这份文件，苹果公司担心员工使用这类程序可能会泄露机密数据。该文件还称，苹果公司还告诉员工，不要使用微软所有的 GitHub 的产品 Copilot。Copilot 可以自动编写软件代码。

ChatGPT 是 AI 研究公司 OpenAI 开发的一款人工智能聊天机器人。该产品于 2022 年 11 月发布，可以进行从历史到哲学等话题的对话，并对计算机程序代码提供修改建议。

值得注意的是，在 ChatGPT 爆火的背后，也出现过商业泄密的重大事故。

今年 4 月，据多家媒体报道，三星电子引入聊天机器人 ChatGPT 不到 20 天，便曝出机密资料外泄，如半导体设备测量数据、产品良率等内容。为杜绝类似事故再发生，三星制定相关保护措施，该公司向员工表示，“若采取信息保护紧急措施后仍发生类似事故，公司内部网络可能会切断 ChatGPT 连接”。

此外，已经有国家监管机构注意到了数据安全风险。

当地时间 3 月 31 日，意大利个人数据保护局宣布，即日起禁止使用聊天机器人 ChatGPT ，限制其开发公司 OpenAI 处理意大利用户信息，并开始立案调查。意大利个人数据保护局认为，3 月 20 日 ChatGPT 平台出现了用户对话数据和付款服务支付信息丢失情况，而该平台没有就收集处理用户信息进行告知，且缺乏大量收集和存储个人信息的法律依据。(中新经纬APP)

### 苹果公司大幅削减其MR头显销售预期，不足百万台

品玩 5 月 19 日讯，据界面新闻消息，苹果公司已将其期待已久的混合现实（MR）头显的销售预期下调约三分之二。报道指出，苹果最初希望每年销售约 300 万台，但现在已将销售预期削减至约 100 万台，随后又下调至 90 万台。该公司将于 6 月 5 日举行全球开发者大会，预计将在会上展示该产品。该设备的售价预计会高达 3000 美元左右，是 Meta Platforms 最昂贵的 Quest Pro 头显售价的三倍。

## 提案


## Swift论坛
1) 讨论[SwiftUI 图表、超大数据集和图表叠加](https://forums.swift.org/t/swiftui-charts-very-large-data-sets-and-chart-overlay/65054 "SwiftUI 图表、超大数据集和图表叠加")

2) 讨论[带有线程安全属性包装器的可发送警告](https://forums.swift.org/t/sendable-warning-with-thread-safe-property-wrapper/65053 "带有线程安全属性包装器的可发送警告")
当使用有针对性的严格并发进行构建时，我收到一条警告，我想知道除了使我的类型“未经检查的可发送”之外，我是否可以做任何事情。

考虑一些线程安全的属性包装器：
```Swift
@propertyWrapper struct ThreadSafe<Value: Sendable>: Sendable {
    private let lock: Lock<Value>

    var wrappedValue: Value {
        get { lock.withLock { $0 } }
        set { lock.withLock { $0 = newValue } }
    }
    
    init(wrappedValue: Value) {
        self.init(lock: .init(initialState: wrappedValue))
    }
    
    private init(lock: Lock<Value>) {
        self.lock = lock
    }
}
```
并考虑使用它来强制执行线程安全和可发送性的类：
```Swift
final class SomeSendable: Sendable {
    @ThreadSafe
    var someBool: Bool = false
}
```
即使我的课程是线程安全的，我仍然收到此警告：
```Swift
Stored property '_someBool' of 'Sendable'-conforming class 'SomeSendable' is mutable

```
编译器诊断似乎没有检查属性包装器的可发送性。

有没有办法在不使我的类型“未选中”的情况下平息此警告？
**回答**
问题是任何带有 var 的类总是不可发送的，并且属性包装器不允许 let。

但对我来说，真正的问题是 SomeSendable 使用起来真的不是那么安全，特别是 @ThreadSafe 是不安全的。 它使得以易受竞争影响的方式使用可变状态变得太容易了。 由于数据被锁定，您肯定不会遇到运行时崩溃，但您很容易得到不正确的结果。

例如，像旋转 1,000 个任务来切换布尔值这样简单的事情在最后总是会产生一个真值，但有时你会得到假，有时你会得到真：
```Swift
let object = SomeSendable()
for _ in 1...1000 {
  Task { object.toggle() }
}
try await Task.sleep(for: .seconds(1))
print(object.someBool)
```
这是一个相当大的问题，它正在发生，因为@ThreadSafe 允许直接写入底层值。 所以像：
```Swift
object.someBool = !object.someBool
```
…隐藏竞争条件。

实际上，您可能应该直接在类中保留 Lock 值，而不是使用 @ThreadSafe 属性包装器，然后仅通过它的 withValue 进行变异。 当然，如果可变数据的安全是最重要的问题，那么您真的应该使用 actor。

3) 讨论[无法在文档注释中使用片段？](https://forums.swift.org/t/using-snippets-in-documentation-comments-not-possible/65046 "无法在文档注释中使用片段？")
我阅读 SE-0356 的方式应该可以在 Swift 包的 Snippets 文件夹中创建一个片段文件，然后通过@Snippet 在我的文档评论中引用它。

但这似乎并不像我预期的那样工作（使用 Xcode 14.3 / Swift 5.8）：

@Snippet 给我警告：“符号源文档不支持指令”
显示我记录的类型的快速帮助不包括片段。
使用菜单“产品”>“构建文档”生成没有代码片段的文档。

**回答**
片段在 Swift 5.7 中实现，并可通过 swift-docc-plugin 与 SwiftPM 一起使用，但正如其他人指出的那样，没有与基于 Xcode 的文档工作流集成，因为它使用不同的构建系统。 我会更新提案。

4) 讨论[Xcode 忽略 Package.resolved 文件](https://forums.swift.org/t/xcode-ignoring-package-resolved-file/65031 "Xcode 忽略 Package.resolved 文件")
我不确定这是 SPM 问题还是 Xcode 问题，但将 SPM 与 Xcode 一起使用时最令人沮丧的经历之一是它经常忽略我的 repo 中的 Package.resolved 文件，通常是在切换分支或不同机器之间时。

Package.resolved 文件应该是我的依赖项的真实来源，它永远不应该被忽略——如果有问题，包解析失败，但永远不要改变我的依赖项。

似乎发生的情况是，Xcode 更愿意使用其源缓存中恰好满足包版本要求的库版本，而不是解析文件中的库版本。 例如，我有一个版本要求为“2.2.0 up to next minor”的库。 Package.resolved 文件中有 2.2.3，所以这是我希望始终使用的版本，除非我进行一些会引入冲突的更改。 当我在另一台机器上打开同一个项目时，出于某种原因它坚持要更改为 2.2.2，大概这是它缓存中的版本。 为什么？ 如果可以忽略已解析文件的意义何在？

**回答**
我可能遗漏了一些细节，但在更新到 Xcode 14.3 并在我们的 CI 中面对这个问题时，我们意识到我们从未使用 -onlyUsePackageVersionsFromResolvedFile 标志调用 xcodebuild。 现在我们这样做了，而且 CI 似乎尊重我们的 Package.resolved 文件。

对于我们来说，这个问题只存在于 Xcode 的 GUI 中。 （与此同时，我同样感到困惑，为什么需要 -onlyUsePackageVersionsFromResolvedFile 而不是 CLI 和 GUI 的默认模式！）

5) 讨论[如果没有 Objective-C 或 Swift，如何在 C 或 C++ 中从 CGDirectDisplayID 检索显示名称？](https://forums.swift.org/t/without-objective-c-or-swift-how-can-a-display-name-be-retrieved-from-cgdirectdisplayid-in-c-or-c/65034 "如果没有 Objective-C 或 Swift，如何在 C 或 C++ 中从 CGDirectDisplayID 检索显示名称？")
我试图在纯 C++（或 C）中从 CGDirectDisplayID 获取显示名称

我可以在 Objective-C++ 中做到这一点，类似于：
```ObjectiveC
#import <Foundation/Foundation.h>
#import <CoreGraphics/CoreGraphics.h>
#import <IOKit/graphics/IOGraphicsLib.h>
#import <Cocoa/Cocoa.h>

#include <string>


bool getDisplayNameForDispID(CGDirectDisplayID dispID,
                             std::string& strOutName)
{
    bool bRes = false;
    
    strOutName.clear();
    
    NSArray *screens = [NSScreen screens];

    for (NSScreen *screen in screens)
    {
        NSDictionary* screenDictionary = [screen deviceDescription];
        if(screenDictionary)
        {
            NSNumber* screenID = [screenDictionary objectForKey:@"NSScreenNumber"];
            if(screenID)
            {
                CGDirectDisplayID aID = [screenID unsignedIntValue];
                
                if(aID == dispID)
                {
                    //Got it
                    NSString* pName = [screen localizedName];
                    
                    strOutName.assign([pName UTF8String], [pName lengthOfBytesUsingEncoding:NSUTF8StringEncoding]);

                    bRes = true;
                    
                    break;
                }
            }
        }
    }    

    return bRes;
}
```
但是，我不想仅仅为了完成这一项任务而将这个缓慢的 Objective-C 代码添加到我的项目中。 在低级 C 中，必须有一种方法可以做到这一点。

我知道有一个完整的主题专门讨论它。 由于 CGDisplayIOServicePort 已弃用并且仅返回 0 并且任何后续调用都会执行操作，因此请注意，没有任何解决方法为 macOS Ventura 提供工作。

**回答**
如果您坚持不直接使用任何 Objective C 代码，您仍然可以使用 Objective C 运行时 API 从 C 调用 Objective C API，例如：
```ObjectiveC
Class nsScreen = objc_lookUpClass("NSScreen");
objc_object *screens = objc_msgSend(nsScreen, sel_getUid("screens"));

// Desugaring "fast enumeration" is particularly knarly.
// for (NSScreen *screen in screens)
objc_object *enumerator = objc_msgSend(screens, sel_getUid("objectEnumerator"));
objc_object *screen;
while ((screen = objc_msgSend(enumerator, sel_getUid("nextObject")) != nil) {
    // ...
}
// ...
```
你会发现它比 Objective C 代码（实际上只是这类函数调用的语法糖）要“迟钝”得多，因为你需要一直转换所有内容。

我也完全忘记了手动添加内存管理。 你需要保留/释放一大堆东西。 真是一团糟。 如果你可以管理它，我强烈建议将其编译为 Objective C。

6) 讨论[任务取消是否传播到 URLSession 任务？](https://forums.swift.org/t/does-task-cancellation-propagate-to-urlsessiontasks/65041 "任务取消是否传播到 URLSession 任务？")
```Swift
let task = Task {
  let (data, response) = try await URLSession.shared.data(from: URL(string: "https://some-image-url.com")!)
  // ...
}
```
然后我执行 task.cancel()，URLSession 是否也会自动取消 URLSessionTask？ 假设 URLSessionTask 也被取消似乎很粗心，但我找不到关于此事的任何文档。 但是，如果 URLSessionTask 没有自动取消，那么我不得不使用基于闭包的 URLSession.dataTask(with:,completionHandler:) 来获取对 URLSessionTask 的引用，然后还调用 dataTask.cancel( ) 在 task.cancel() 之上，这有点奇怪。
**回答**
```Swift
import Foundation

func main() async {
    let t = Task {
        do {
            print("\(Date.now): task will start")
            let url = URL(string: "https://postman-echo.com/delay/10")!
            let request = URLRequest(url: url, cachePolicy: .reloadIgnoringLocalCacheData, timeoutInterval: 60.0)
            let (data, response) = try await URLSession.shared.data(for: request)
            print("\(Date.now): task did complete, response: \(response), data: \(data)")
        } catch {
            print("\(Date.now): task did error")
        }
    }
    if true {
        try? await Task.sleep(for: .seconds(1))
        print("\(Date.now): will cancel task")
        t.cancel()
        print("\(Date.now): did cancel task")
    }
    print("\(Date.now): waiting")
    try? await Task.sleep(for: .seconds(60))
}

await main()
```
打印结果：
```Swift
2023-05-18 08:18:52 +0000: task will start
2023-05-18 08:18:53 +0000: will cancel task
2023-05-18 08:18:53 +0000: did cancel task
2023-05-18 08:18:53 +0000: waiting
2023-05-18 08:18:53 +0000: task did error
```

7) 讨论[发展 Swift 工作组](https://forums.swift.org/t/evolving-the-swift-workgroups/65052 "发展 Swift 工作组")
今天，Swift 核心团队宣布对 Swift 的结构、工作和周围的人进行前瞻性的改变。 这些更改包括新的组、名称、组织以及作为每个组的一流概念的包含。
链接：https://www.swift.org/blog/evolving-swift-project-workgroups/

##  推荐博文
[万字长文详解如何使用 Swift 提高代码质量 | 京东云技术团队](https://juejin.cn/post/7231359714055077946/ "万字长文详解如何使用 Swift 提高代码质量 | 京东云技术团队")

**摘要：** 文章介绍了如何使用 Swift 提高代码质量。 Swift 的三个重要特性：富有表现力、安全性和快速。通过使用这些特性，可以提高代码质量并减少 Crash 的发生率。同时，本文还分享了一些实践技巧来提高使用 Swift 编写代码的效率和可读性，如利用编译检查、减少使用 Any/AnyObject 、不推荐大量使用 Dictionary 数据结构等。最后，从性能优化的角度，谈到了使用源代码打包，减少方法动态派发，使用 Slice 共享内存优化性能等来提高代码质量。

[swiftUI 中视图叠加的强大能力](https://swiftwithmajid.com/2023/05/03/the-power-of-overlays-in-swiftui/ "swiftUI 中视图叠加的强大能力")

**摘要：** 本博客文章讨论了 SwiftUI 中两个有趣的叠加使用案例。第一个案例涉及使用叠加来保持视图的结构标识，这对于防止性能问题和状态丢失至关重要。第二个用例是通过叠加视图修饰符构建自定义导航转换，使开发人员能够创建流畅的动画而不依赖 NavigationView 或 NavigationStack。提供示例以说明这些概念，并提供其他资源供进一步学习。总体而言，本文展示了 SwiftUI 中叠加功能的强大之处以及它们如何增强应用程序开发中用户体验。

[SwiftUI 中的文件导入和导出](https://swiftwithmajid.com/2023/05/10/file-importing-and-exporting-in-swiftui/ "SwiftUI 中的文件导入和导出")

**摘要：** 本篇博客讨论了如何使用 fileImporter 和 fileExporter 视图修饰符在 SwiftU I视图中导入和导出文件。文章包括两种操作的代码示例，以及一个额外部分介绍如何使用 fileMover 视图修改器进行文件移动。此外，还介绍了 TextDocument 类型，它符合 FileDocument 协议并允许从文件读取纯文本字符串，并将字符串数据导出到文件。总体而言，这篇文章强调了使用这些简单的视图修饰符可以轻松实现 SwiftUI 应用程序中的文件管理体验。



## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
