## 前言

前几期周报内容是同步翻译的英文版周报，目前英文版停更，周报停滞半年多。经过多次讨论，我们决定**重启周报**，分模块整理内容同步给大家。

周报内容模块分为：**新闻**、**提案**、**Swift论坛**、**推荐博文**。初期计划每两周发布一期，欢迎志同道合的朋友一起加入周报整理。

昨日的生活与工作是否也曾迷茫？对新技术渴望突破的心是否依旧执着？**Swift社区**，为你的技术栈添砖加瓦，你，准备好了吗？

## 新闻和社区


## 提案

### 通过的提案


### 正在审查的提案


## Swift论坛
1) [Move-Only类型的非正式介绍](https://forums.swift.org/t/an-informal-introduction-to-move-only-types/61358 "Move-Only类型的非正式介绍")

2) [相同的值相等的复杂性保证](https://forums.swift.org/t/same-values-equality-complexity-guarantees/61334 "相同的值相等的复杂性保证") 
```Swift
let foo: String = ....
let bar = foo
foo == bar // is this O(1) ?
```

3) 资料分享[swift package SignalHandler](https://forums.swift.org/t/signal-handling-in-swift/61351 "swift package SignalHandler")

4) 讨论[在 Linux 上使用 5.7 `Regex` 的问题](https://forums.swift.org/t/issues-with-using-5-7-regex-on-linux/61344 "在 Linux 上使用 5.7 `Regex` 的问题")

5) 讨论[Swift 论坛的 iOS 应用](https://forums.swift.org/t/an-ios-app-for-the-swift-forum/61335/1 "Swift 论坛的 iOS 应用")
Discourse Hub App可以用来浏览Swift论坛内容，App基于WebView，本质与用浏览器没有区别😂

6) 讨论[检测 Mac 设备上可用的 USB 端口数量](https://forums.swift.org/t/detect-the-number-of-usb-ports-available-on-the-mac-device/61321 "检测 Mac 设备上可用的 USB 端口数量")

7) 讨论[比较两个“any Error”的相等性](https://forums.swift.org/t/comparing-two-any-error-s-for-equality/61338 "比较两个“any Error”的相等性")
问题描述：有一个错误类型，它包含另一个存在的any Error：
```Swift
@frozen public
struct RecursiveError<Location>:Error
{
    /// The location (key or index) where the error occurred.
    public
    let location:Location
    /// The underlying error that occurred.
    public
    let error:any Error

    @inlinable public
    init(_ error:any Error, in location:Location)
    {
        self.location = location
        self.error = error
    }
}
```
Unit Test:
```Swift
$0.test(name: "int32-to-uint8", decoding: bson,
    failure: RecursiveError<String>.init(
        IntegerOverflowError<UInt8>.int32(.max),
        in: "int32"))
{
    try $0["int32"].decode(to: UInt8.self)
}
```
解决方法：
```Swift
extension Error where Self:Equatable
{
    fileprivate
    func equals(_ other:any Error) -> Bool
    {
        (other as? Self).map { $0 == self } ?? false
    }
}
```

8) 讨论[Boolean运算和`async let`](https://forums.swift.org/t/boolean-operators-and-async-let/61354 "Boolean运算和`async let`")
执行：
```Swift
async let first: Int[] = someAsyncCall()
async let second: Int[] = anotherAsyncCall()

let bothEmpty = (await first).isEmpty && (await second).isEmpty
// or
let bothEmpty = await (first.isEmpty && second.isEmpty)
// or any other variation I can think of
```
会有以下Error：
```
'async let' in an autoclosure that does not support concurrency
Capturing 'async let' variables is not supported
```
Boolean运算是使用标记为自动闭包的 rhs 参数定义的，这意味着右侧的表达式会自动捆绑到闭包中，从而延迟其执行直到需要。 值得注意的是，这个 rhs 闭包属性没有被标记为 async ，所以没有 await 语句可以出现在它的“内部”。
解决：
```Swift
let bothEmpty = await [first, second].allSatisfy(\.isEmpty)
```

## 推荐博文

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
