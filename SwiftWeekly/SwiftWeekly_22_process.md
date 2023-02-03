## 前言

**本期是 Swift 编辑组自主整理周报的第十三期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

渺小不可怕，可怕的是比你优秀的强者还比你更加努力。**Swift社区**不会辜负每一位努力的勇士，优秀终将与你不期而遇！👊👊👊

> **周报精选**
>
> 新闻和社区：因iPhone销量下降 苹果利润2016年以来首次低于预期
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

### 因iPhone销量下降 苹果利润2016年以来首次低于预期

2 月 3 日凌晨，多家美股科技巨头公布财报。苹果 2023 财年 Q1 净利润录得 299 亿美元，低于市场预期，原因是 iPhone 的供应出现问题，导致销售疲软。苹果当季销售额下降 5% ，至 1172 亿美元，全球各地的销售额均出现下滑。除服务和 ipad 以外，所有产品类别的销售额都有所下降。这是自 2016 年以来苹果首次未能达到华尔街的利润预期。不过，苹果CEO库克在最新业绩会上表示，中国市场的需求已经有非常好的复苏，去年 12月 和 11 月相比市场确实发生了很大变化。库克还表示，苹果将很快在印度开设第一批零售店。

### App 和 App 内购买项目即将实行税率和价格调整

App Store 的交易和支付机制旨在帮助您在覆盖全球的 175 个国家和地区的商店中，以 45 种货币为您的产品和服务便捷地进行定价与销售。我们会根据税款和外币汇率变化，定期在相关地区的 App Store 更新定价。相关调整将根据金融数据机构提供的公开汇率信息进行，以此确保 App 和 App 内购买内容的定价在所有商店中保持平衡。

2023 年 2 月 13 日起，哥伦比亚、埃及、匈牙利、尼日利亚、挪威、南非和英国 App Store 的 App 及 App 内购买项目 (自动续期订阅除外) 的价格将上调。由于乌兹别克斯坦的增值税率从 15% 下调至 12%，该地区的价格亦将相应下调。您的收益将随之进行调整，并会根据不含税的价格来进行计算。

虽然爱尔兰、卢森堡、新加坡和津巴布韦 App Store 的价格不会改变，但您的收益将进行调整以反映以下税率调整：

爱尔兰：电子报纸和期刊的增值税率从 9% 下调至 0%
卢森堡：增值税率从 17% 下调至 16%
新加坡：商品和服务税率从 7% 上调至 8%
津巴布韦：增值税率从 14.5% 上调至 15%
此外，在柬埔寨、吉尔吉斯斯坦、印度尼西亚、新加坡、韩国、塔吉克斯坦、泰国和乌兹别克斯坦销售产品和服务的当地开发者的收益将在一月底前相应增加。

Apple 在计算抽成之前会根据您提供的税务类别信息估算并移除相关税费。《付费 App 协议》的附录 B 亦将更新以反映此调整。

以上调整生效后，在“我的 App”中“价格与销售范围”部分会随即更新。一如既往，您可以随时在 App Store Connect 中更改您的 App 和 App 内购买项目的价格 (包括自动续期订阅)。如果您有提供订阅项目，您可以选择为现有订阅者保留当前价格。

正如我们此前所宣布，从 2023 年春季起，App 和 App 内购买项目的定价功能升级将带来 700 个新增的价格点；我们还将提供针对全球不同地区更加灵活的价格设定，您将能够不受全球均衡价格的影响，自由管理外币汇率变化。

### Ask Apple Q&A 和调查表

![](https://devimages-cdn.apple.com/wwdc-services/articles/images/5A13BEF0-31D6-466B-B88B-8484635BEA2A/2048.jpeg)

感谢大家参与 10 月、11 月和 12 月举办的三场精彩的 Ask Apple 活动周。Ask Apple 参与者仍可以根据需要访问并查阅 Slack 中的 Q&A。

我们非常希望获得您的反馈，如果您尚未与我们分享您的 Q&A 体验，恳请完成我们的简短调查表。只需几分钟时间即可完成，并且您的回答将被匿名处理。

我们期待不久之后能再次与您沟通交流。

## 提案

### 通过的提案


### 正在审查的提案


## Swift论坛
1) 讨论[如何设置需要异步初始化的静态变量](https://forums.swift.org/t/how-to-set-static-variable-that-requires-async-initialization/62661 "如何设置需要异步初始化的静态变量")
```Swift
@globalActor public actor ImageDatabase{
    
    public static var shared: ImageDatabase = ImageDatabase() 
    // 'async' call cannot occur in a global variable initializer
    
    private var transport : ImageTransportLayer
    
    private init() async {
           self.transport = await ImageTransportLayer()
    }    
}

@ImageDatabase class ImageTransportLayer { } // CRUD
```
解决方法：可以稍后在应用程序启动序列中手动初始化 ImageTransportLayer
```Swift
@globalActor public actor ImageDatabase {
    private init() {}
    public static var shared: ImageDatabase = ImageDatabase()

    private var transport: ImageTransportLayer?
    public func initTransport() async {
        transport = await ImageTransportLayer()
    }
}

@ImageDatabase class ImageTransportLayer {} // CRUD

Task {
    await ImageDatabase.shared.initTransport()

    // Continue using ImageDatabase.shared
}
```

2) 讨论[macOS Catalina 上的 Swift 5.7 和适用于 macOS 的工具链](https://forums.swift.org/t/swift-5-7-on-macos-catalina-and-a-toolchain-for-macos/62656 "macOS Catalina 上的 Swift 5.7 和适用于 macOS 的工具链")

3) 发布[VSCode Swift v1.0.0](https://forums.swift.org/t/vscode-swift-v1-0-0/62668 "VSCode Swift v1.0.0")
Swift Visual Studio Code 扩展的 1.0 版已经发布。 它不再处于预览状态。
此版本对 v0.10.0 进行了一些小的添加，并修复了一些错误。 更新日志链接：https://marketplace.visualstudio.com/items/sswg.swift-lang/changelog

4) 讨论[AsyncSequences 和cooperative任务取消](https://forums.swift.org/t/asyncsequences-and-cooperative-task-cancellation/62657 "AsyncSequences 和cooperative任务取消")

5) 讨论[函数签名的属性包装器](https://forums.swift.org/t/property-wrapper-on-a-functions-signature/62660 "函数签名的属性包装器")

6) 提问[将函数集成到结构中](https://forums.swift.org/t/integrating-a-function-into-a-struct/62634 "将函数集成到结构中")
目标是有一个接受字符串的字段，它下面的文本将打印一条消息，其中包含输入的单词和它包含的字母数。
 ```Swift
 import SwiftUI

struct Test1: View {
    
    @State private var newWord = ""
    
    var body: some View {
        VStack {
            TextField("Enter a word", text: $newWord)
                .frame(height: 50)
                .cornerRadius(10)
                .background(.gray.opacity(0.1))
                .padding(.horizontal, 20)
            
            //Text(countLetters(myWord: newWord))
            Text(myMessage)
        }
    }
}

func countLetters(myWord: String) -> (String, Int) {
    var myCounter = 0
    var characters = ""
    for letter in myWord {
        characters += "\(letter)"
        myCounter += 1
    }
    return (characters, myCounter)
}
var myWordCount = countLetters(myWord: "Gregory")
var myMessage = "There are \(myWordCount) letters in the"
 ```
 解决：字符串有一个 .count 属性，可以直接使用：
 ```Swift
 struct ContentView: View {
    
    @State var text = ""
    
    var body: some View {
        VStack {
            TextField("Enter a word", text: $text)
            Text("There are \(text.count) letters in your word")
        }
    }
}
 ```

7) 发布[AsyncObjects 2.0](https://forums.swift.org/t/released-asyncobjects-2-0/62664 "AsyncObjects 2.0")

8) 提议[添加 KeyPaths Boolean 自定义运算符](https://forums.swift.org/t/pitch-add-keypaths-boolean-custom-operators/62626 "添加 KeyPaths Boolean自定义运算符")
内容大概：
在[SE-0249](https://github.com/apple/swift-evolution/blob/main/proposals/0249-key-path-literal-function-expressions.md) 引入了在允许 (Root) -> Value 函数的任何地方使用关键路径表达式 \Root.value 的能力。

现在在各个项目中得到了广泛的使用。
在这里试图提议的是为关键路径添加一些新的运算符，以便在尝试对其应用任何逻辑时更容易使用它。

这里有几个例子：

假设我们想过滤字典并获取所有为真的值。
我们现在可以通过以下方式使用关键路径轻松完成此操作：
 ```Swift
let dict = ["a": true, "b": true, "c": false]
let filtered = dict.filter(\.value) // returns ["a": true, "b": true]
```
但是如果我们想过滤字典中的错误值怎么办？那么现在我们不能使用关键路径，我们需要依赖闭包：
```Swift
let filtered = dict.filter { !$0.value } // returns ["c": false]
```
这里的建议是添加以下运算符：
```Swift
prefix func !<V>(keyPath: KeyPath<V, Bool>) -> (V) -> Bool {
    { !$0[keyPath: keyPath]}
}

func ==<T, V: Equatable>(lhs: KeyPath<T, V>, rhs: V) -> (T) -> Bool {
    return { $0[keyPath: lhs] == rhs }
}

func !=<T, V: Equatable>(lhs: KeyPath<T, V>, rhs: V) -> (T) -> Bool {
    return { $0[keyPath: lhs] != rhs }
}
```
这将使我们能够按如下方式使用关键路径：
```Swift
let dict = ["a": true, "b": true, "c": false]

let filtered = dict.filter(!\.value)

let filtered2 = dict.filter(\.value == false)
```

## 推荐博文

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
