## 前言

前几期周报内容是同步翻译的英文版周报，目前英文版停更，周报停滞半年多。经过多次讨论，我们决定**重启周报**，分模块整理内容同步给大家。

周报内容模块分为：**新闻**、**提案**、**Swift论坛**、**推荐博文**。初期计划每两周发布一期，欢迎志同道合的朋友一起加入周报整理。

昨日的生活与工作是否也曾迷茫？对新技术渴望突破的心是否依旧执着？**Swift社区**，为你的技术栈添砖加瓦，你，准备好了吗？

## 新闻和社区


## 提案

### 通过的提案


### 正在审查的提案


## Swift论坛
1) 讨论[是否应该用Codable还是用NSCoding](https://forums.swift.org/t/should-i-stick-with-codable-or-switch-back-to-nscoding/61604 "是否应该用Codable还是用NSCoding")

2) 讨论[NSKeyedArchiver, CoreData和其他的存储方案](https://forums.swift.org/t/nskeyedarchiver-coredata-and-other-storage-solutions/61603 "NSKeyedArchiver, CoreData和其他的存储方案")

3) 讨论[数组的悬空指针](https://forums.swift.org/t/dangling-pointer-from-array/61609 "数组的悬空指针")
```Swift
do {
    var array = [0, 1, 2, 3, 4]
    let ptrToArray = UnsafeBufferPointer<Int>(start: &array, count: array.count)
    
    for number in ptrToArray {
        print(number)
    }
}
```
解决
```Swift
let array = [0, 1, 2, 3, 4]
array.withUnsafeBufferPointer { ptrToArray in
    for number in ptrToArray {
        print(number)
    }
}
```

4) 讨论[如何从 ReducerProtocol 中创建的alert回调中触发操作](https://forums.swift.org/t/how-to-trigger-action-from-alert-callback-created-in-reducerprotocol/61598 "如何从 ReducerProtocol 中创建的alert回调中触发操作")

5) 讨论[键路径与闭包的代码大小差异](https://forums.swift.org/t/code-size-difference-with-keypath-vs-closure/61599 "键路径与闭包的代码大小差异")

6) 讨论[将 Objective-C 代码库迁移到 Swift](https://forums.swift.org/t/migrating-an-objective-c-codebase-to-swift/61592 "将 Objective-C 代码库迁移到 Swift")
Steve Barnegren 撰写的从 Objective-C 迁移到 Swift 30 的博客文章是一本不错的读物。
文章链接: https://www.steveonstuff.com/2022/01/13/migrating-from-objc-to-swift.html

7) 讨论[RawRepresentable<String> 和 LosslessStringConvertible的区别](https://forums.swift.org/t/difference-between-rawrepresentable-string-and-losslessstringconvertible/61600 "RawRepresentable<String>和LosslessStringConvertible的区别")
LosslessStringConvertible 改进了 CustomStringConvertible，这会影响其他事情，例如对 String(describing:) 的调用。 
从语义上讲，LosslessStringConvertible 意味着它可以表示为字符串（例如整数），而 RawRepresentable<String> 意味着它在底层是一个字符串（例如原始类型为 String 的枚举）。

8) 讨论[无法使用protocol重新创建的类 - 扩展存储属性](https://forums.swift.org/t/i-cant-recreate-my-class-using-protocols-extension-stored-properties/61589 "无法使用protocol重新创建的类 - 扩展存储属性")
简短的回答是“protocol不能定义存储的属性”。 协议一致性可以在定义类型的模块之外定义，这很自然地得出结论：这样的协议如何添加存储？
您能做的最好的事情就是让协议要求您的类型具有存储空间。 您的类型定义仍然必须实际定义该存储。

9) 讨论[状态初始化器中的 UUID](https://forums.swift.org/t/uuid-in-state-initializer/61593 "状态初始化器中的 UUID")

10) 讨论[对于金融计算用Decimal还是Double](https://forums.swift.org/t/decimal-or-double-for-financial-calculations/61585 "对于金融计算用Decimal还是Double")

## 推荐博文

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
