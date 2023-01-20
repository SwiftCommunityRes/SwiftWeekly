## 前言

前几期周报内容是同步翻译的英文版周报，目前英文版停更，周报停滞半年多。经过多次讨论，我们决定**重启周报**，分模块整理内容同步给大家。

周报内容模块分为：**新闻**、**提案**、**Swift论坛**、**推荐博文**。初期计划每两周发布一期，欢迎志同道合的朋友一起加入周报整理。

昨日的生活与工作是否也曾迷茫？对新技术渴望突破的心是否依旧执着？**Swift社区**，为你的技术栈添砖加瓦，你，准备好了吗？

## 新闻和社区


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
