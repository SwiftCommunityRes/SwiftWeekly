## 前言

**本期是 Swift 编辑组自主整理周报的第十一期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。


> **周报精选**
>
> 新闻和社区：部分 iPhone 14 Pro / Max 被爆开机闪现水平线
> 
> 提案：`DiscardingTaskGroups` 提案正在审查
> 
> Swift 论坛：讨论修改 SE-0368 以删除前缀 `+` 运算符
>
> 推荐博文：SwiftUI 的优势、劣势和缺陷
> 
> **话题讨论：** 
> 
> 疫情放开，你处于什么阶段

## 新闻和社区

### 部分 iPhone 14 Pro / Max 被爆开机闪现水平线

一些 iPhone 14 Pro 和 iPhone 14 Pro Max 用户报告说，当设备被打开时，iPhone 显示屏上闪烁着水平线，但没有明确的原因或如何修复它。

在 Reddit 的主题帖子中，数十名 iPhone 14 Pro 用户报告说，当设备被打开时，一条或多条绿色和黄色的线条可能会在屏幕上闪烁，几秒钟后消失。根据这些用户的说法，苹果支持部门已经通知他们，该问题不是硬件缺陷造成的，而是 iOS 16 的错误 Bug。

![](https://files.mdnice.com/user/17787/ce2b2a90-fc9c-4b44-8a32-13231e4e9198.png)

### iOS 16.2 不能升级 Home 应用架构

苹果已取消 iOS 16.2 升级到新 Home 家庭架构的选项，iOS 16.2 和 macOS Ventura 13.1 的主要新功能之一是能够升级到新的 Home 家庭应用架构。虽然苹果没有分享具体的变化细节，但表示，该升级为 HomeKit 配件提供了“更好的性能和可靠性”。

![](https://files.mdnice.com/user/17787/b9c275dc-da92-405e-b108-cdd13178785e.png)

### AppleWatch 或可无创测血压

Apple Watch 无创测血压功能即将到来，苹果正积极积累相关技术。IT 之家 12 月 23 日消息，知情人士在今年 4 月透露，苹果计划在 Apple Watch 中添加血压监测功能，但由于遇到障碍，该项技术预计最早要到 2024 年才能推出。苹果目前也在积极地积累技术支持，美国商标和专利局（USPTO）公示了一项新的苹果专利（专利号 US 20220400959），涉及获取和分析无创血压测量数据的系统和方法。

![](https://files.mdnice.com/user/17787/3edae191-378a-48a6-9031-ff6b8ad169d7.png)

### iPhone15 系列将继续采用高通5G基带芯片
苹果 iPhone 15 系列将采用高通骁龙 X70 5G 基带芯，根据 DigiTimes 报道，苹果 iPhone 15 系列将继续采用高通 5G 调制解调器（基带芯片），因为苹果公司仍在继续开发自有的 5G 定制芯片。

## 提案

### 正在审查的提案

[SE-0381](https://github.com/apple/swift-evolution/blob/main/proposals/0381-task-group-discard-results.md "SE-0381") **DiscardingTaskGroups** 提案正在审查。

该提案建议为 `TaskGroup` 和 `ThrowingTaskGroup` 引入一个新的布尔参数 `discardResults`。此参数将控制 `TaskGroup` 是保留其已完成子任务的结果，然后确定是传递给 `next()`，还是立即丢弃。

[SE-0382](https://github.com/apple/swift-evolution/blob/main/proposals/0382-expression-macros.md "SE-0382") **Expression Macros** 提案正在审查。

`Expression Macros` 提供了一种用新型表达式扩展 Swift 的方法，这些表达式可以对其参数执行任意语法转换以生成新代码。 `Expression Macros` 使得用以前只有引入新的语言特性才能实现的方式扩展 Swift 成为可能，帮助开发人员构建更具表现力的库并消除无关的样板。

## Swift论坛

1) Swift to C++ [将 Swift 参数标签合并到生成的 C++ 函数名中](https://forums.swift.org/t/swift-to-c-incorporating-swift-argument-labels-into-generated-c-function-name/62195 "将 Swift 参数标签合并到生成的 C++ 函数名中")

2) 讨论[如何测试发送动作的长时间运行效果？](https://forums.swift.org/t/how-to-test-long-running-effect-that-sends-actions/62201 "如何测试发送动作的长时间运行效果？")

3) 议案 [[Pitch] 结果构建器范围内的不合格查找](https://forums.swift.org/t/pitch-result-builder-scoped-unqualified-lookup/62190 "[Pitch] 结果构建器范围内的不合格查找")

**介绍:**

结果构建器为定义声明式 DSL 提供了基础——特定领域的语言提供了在特定领域工作的定制语法，例如生成图表或文本处理。 利用结果构建器的复杂 DSL API 遇到了设计可扩展性和类型检查性能方面的问题，引入了需要解决的关键挑战。 

扩展结果构建器以支持在其主体内进行范围内的非限定名称查找，即特定于构建器类型的范围内名称间距，将启用新的 API 模式，显着降低类型检查的复杂性，同时改善调用站点的美感。

4) 议案[修改 SE-0368 以删除前缀 + 运算符](https://forums.swift.org/t/pitch-amend-se-0368-to-remove-prefix-operator/62173 "修改 SE-0368 以删除前缀 + 运算符")

内容:[SE-0368](https://forums.swift.org/t/se-0368-staticbigint/59421 "SE-0368")包括对 `StaticBigInt` 的以下操作：

```Swift
/// Returns the given value unchanged.
public static prefix func + (_ rhs: Self) -> Self
```

这被包括在内，以便前缀 + 可以作为文字前缀包含在上下文中，在这些上下文中，值需要是 `StaticBigInt` 类型，而不是另一种类型的文字，以便与 - 对称：

```Swift
let signs: [StaticBigInt] = [-1, 0, +1]
```

事实证明，这是一个源代码的突破性变化，因为有如下示例：

```Swift
let a: Int = 7
let b = +1     // Inferred as `StaticBigInt` because concrete `+` beats
               // the generic one on `AdditiveArithmetic`
let c = a + b  // Error: Cannot convert `b` from `StaticBigInt` to `Int`
```

之前，`b` 被赋予了 `Int` 类型，这个例子编译正确。建议修改 `SE-0368` 以删除此运算符。 这对于想要使用 `StaticBigInt` 值的代码来说是一个小小的不便，但是不存在这样的代码，因为 5.7 中不存在该类型。

这样的代码可以省略前导 + 作为解决方法。

一旦解决了源中断问题，我们就可以调查其他选项以在空闲时恢复所需的语法。

5) 讨论 [ArgumentParser 包出现 no such file 错误](https://forums.swift.org/t/no-such-file-errors-with-argumentparser-package/62183 "ArgumentParser 包出现 no such file 错误")

6) 讨论[如何打印 HTTPS URL 参数和正文](https://forums.swift.org/t/how-can-i-print-https-url-params-and-body/62153 "如何打印 HTTPS URL 参数和正文")

7) 提议 [<Success, Failure> Guard Evaluation 会更好](https://forums.swift.org/t/pitch-better-result-success-failure-guard-evaluation/62158 "<Success, Failure> Guard Evaluation 会更好")

内容:

在 `SE-0235` 中将结果类型引入标准语言是我在构建库时最喜欢的功能之一。 当返回的 Result 用户想要评估时，通常看起来有点像这样：

```Swift
let result:  Result<Data, MyCustomError> = getResult()

switch result {
case .success(let data):
  // Do something with the data here
case .failure(let error):
  // Handle error
}
```

这对大多数情况都很好。 然而，如果我们需要级联多个结果，它会变得有点难看。

**例如：**

```Swift
let firstResult:  Result<Data, MyCustomError> = getFirstResult()

switch firstResult {
case .success(let data):
  let secondResult: Result<Data, MyCustomError> = getSecondResult(using: data)
  switch secondResult {
  case .success(let secondData):
    // Do something with secondData
  case .failure(let secondError):
    // Handle secondError
  } 
case .failure(let firstError):
  // Handle firstError
}
```

如上所述，嵌套切换变得有点沉重。 这常常让我想起嵌套的 if 语句，作为一个“从不嵌套”的人，我通常会在这里求助于 `guard ` 关键字。 我认为 guard 关键字对于评估 Result 类型也非常有用，但是因为它现在有效，但 gaurd 关键字对于 Result type 用起来有问题。

```Swift
let firstResult:  Result<Data, MyCustomError> = getFirstResult()
guard case .success(let data) = firstResult else {
  // Handle first error - But no reference to firstError! 
  return
}
 
let secondResult: Result<Data, MyCustomError> = getSecondResult(using: data)
guard case .success(let secondData) = secondResult else {
  // Handle second error - But no reference to secondError! 
  return
} 
```

正如评论所暗示的那样，我没有引用 `guard` 语句的 `else` 部分中的错误类型。 据我所知，没有办法使用这种语法并访问返回的错误类型。

也许有一些方法可以通过扩展 `guard` 语句或更新 `Result` 类型来实现此功能？

所以这就是为什么我要提出这个建议。我不是确定能百分百修复。甚至不确定这是对语言的有用更改还是其他 Swift 用户想要的东西。让我们在这里讨论一下！

8) 讨论 [Swift 是否允许重载属性](https://forums.swift.org/t/are-we-allowed-to-overload-a-property-or-not/62167 "Swift 是否允许重载属性")

## 推荐博文

[2021 年的 SwiftUI: 优势、劣势和缺陷](https://juejin.cn/post/7140825514108780580 "2021 年的 SwiftUI: 优势、劣势和缺陷")

**摘要：** 这篇文章主要目的是帮助你理解 SwiftUI 的利弊，这样你可以就 SwiftUI 是否适合下一个项目做出更明智的决定。
  
[用 SwiftUI 实现 AI 聊天对话 app - iChatGPT](https://juejin.cn/post/7175051294808211512 "用 SwiftUI 实现 AI 聊天对话 app - iChatGPT")

**摘要：** 关于 ChatGPT 的话题，大家都不陌生，我们直入话题，因为 ChatGPT 目前限制中国访问服务，所以如果直接使用 ChatGPT 网页进行对话，还是不太方便。通过 ChatGPT SessionToken 就可以不限制网络访问，所以大家发挥想象力实现各种的聊天机器人、小程序，而原生 app 可能体验更好

[SwiftUI 布局协议 - Part 2](https://mp.weixin.qq.com/s/fgHkd_EFPkNwG3G3KPq92w)

**摘要：** 在 Part 1 我们探索了布局协议的基础知识，为理解布局是如何工作的打下了坚实的基础。现在，是时候深入研究那些更少提及的功能了，以及如何使用它们来为我们带来便利。

## 话题讨论

**疫情放开，你处于什么阶段**

123

欢迎在文末留言参与讨论。

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的各种交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。

周报仓库：https://github.com/SwiftCommunityRes 文章中外引链接较多，可以点击 **阅读原文** 更加方便阅读。


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
