## 前言

前几期周报内容是同步翻译的英文版周报，目前英文版停更，周报停滞半年多。经过多次讨论，我们决定**重启周报**，分模块整理内容同步给大家。

周报内容模块分为：**新闻**、**提案**、**Swift论坛**、**推荐博文**。初期计划每两周发布一期，欢迎志同道合的朋友一起加入周报整理。

昨日的生活与工作是否也曾迷茫？对新技术渴望突破的心是否依旧执着？**Swift社区**，为你的技术栈添砖加瓦，你，准备好了吗？

## 新闻和社区


## 提案

### 通过的提案


### 正在审查的提案


## Swift论坛
1) Swift to C++[将 Swift 参数标签合并到生成的 C++ 函数名中](https://forums.swift.org/t/swift-to-c-incorporating-swift-argument-labels-into-generated-c-function-name/62195 "将 Swift 参数标签合并到生成的 C++ 函数名中")

2) 讨论[如何测试发送动作的长时间运行效果？](https://forums.swift.org/t/how-to-test-long-running-effect-that-sends-actions/62201 "如何测试发送动作的长时间运行效果？")

3) 议案[[Pitch] 结果构建器范围内的不合格查找](https://forums.swift.org/t/pitch-result-builder-scoped-unqualified-lookup/62190 "[Pitch] 结果构建器范围内的不合格查找")
介绍:
结果构建器为定义声明式 DSL 提供了基础——特定领域的语言提供了在特定领域工作的定制语法，例如生成图表或文本处理。 利用结果构建器的复杂 DSL API 遇到了设计可扩展性和类型检查性能方面的问题，引入了需要解决的关键挑战。 扩展结果构建器以支持在其主体内进行范围内的非限定名称查找，即特定于构建器类型的范围内名称间距，将启用新的 API 模式，显着降低类型检查的复杂性，同时改善调用站点的美感。

4) 议案[修改 SE-0368 以删除前缀 `+` 运算符](https://forums.swift.org/t/pitch-amend-se-0368-to-remove-prefix-operator/62173 "修改 SE-0368 以删除前缀 `+` 运算符")
内容:
[SE-0368](https://forums.swift.org/t/se-0368-staticbigint/59421)包括对 StaticBigInt 的以下操作：
```Swift
/// Returns the given value unchanged.
public static prefix func + (_ rhs: Self) -> Self
```
这被包括在内，以便前缀 + 可以作为文字前缀包含在上下文中，在这些上下文中，值需要是 StaticBigInt 类型，而不是另一种类型的文字，以便与 - 对称：
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
（之前，b 被赋予了 Int 类型，这个例子编译正确。）
建议修改 SE-0368 以删除此运算符。 这对于想要使用 StaticBigInt 值的代码来说是一个小小的不便，但是，
今天不存在这样的代码，因为 5.7 中不存在该类型。
这样的代码可以省略前导 + 作为解决方法。
一旦解决了源中断问题，我们就可以调查其他选项以在空闲时恢复所需的语法。

5) 讨论[ArgumentParser 包出现“no such file”错误](https://forums.swift.org/t/no-such-file-errors-with-argumentparser-package/62183 "ArgumentParser 包出现“no such file”错误")

6) 讨论[如何打印 HTTPS URL 参数和正文](https://forums.swift.org/t/how-can-i-print-https-url-params-and-body/62153 "如何打印 HTTPS URL 参数和正文")

7) 提议[<Success, Failure> Guard Evaluation会更好](https://forums.swift.org/t/pitch-better-result-success-failure-guard-evaluation/62158 "<Success, Failure> Guard Evaluation会更好")
内容:
在 SE-0235 中将结果类型引入标准语言是我在构建库时最喜欢的功能之一。 当返回的 Result 的用户想要评估它时......它通常看起来有点像这样：
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
例如：
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
如上所述，嵌套切换变得有点沉重。 这常常让我想起嵌套的 if 语句，作为一个“从不嵌套”的人，我通常会在这里求助于 guard 关键字。 我认为 guard 关键字对于评估 Result 类型也非常有用——但是因为它现在有效，但gaurd关键字对于Result type用起来有问题
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
正如评论所暗示的那样，我没有引用 guard 语句的 else 部分中的错误类型。 据我所知，没有办法使用这种语法并访问返回的错误类型。
也许有一些方法可以通过扩展 guard 语句或更新 Result 类型来实现此功能？
所以这就是为什么我要提出这个建议。 我不是 100% 确定修复是什么或应该是什么。 我什至不确定这是对语言的有用更改还是其他 Swift 用户想要的东西 - 但让我们在这里讨论一下！

8) 讨论[Swift 是否允许重载属性？](https://forums.swift.org/t/are-we-allowed-to-overload-a-property-or-not/62167 "Swift 是否允许重载属性？")
## 推荐博文

## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
