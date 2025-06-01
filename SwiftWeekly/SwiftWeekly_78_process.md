## 前言

**本期是 Swift 编辑组自主整理周报的第五十期**，每个模块已初步成型。各位读者如果有好的提议，欢迎在文末留言。

Swift 周报在 [GitHub 开源](https://github.com/SwiftCommunityRes/SwiftWeekly "SwiftWeekly")，欢迎提交 issue，投稿或推荐内容。目前计划每两周周一发布，欢迎志同道合的朋友一起加入周报整理。

间歇性的努力和蒙混过日子，都是对之前努力的清零。时间永不停歇，社会时刻发展，**Swift社区**也在华丽蜕变！👊👊👊

> **周报精选**
>
> 新闻和社区：
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
>
>**上期话题结果**


## 新闻和社区  


## 提案


## Swift论坛
1) 提议[可扩展枚举](https://forums.swift.org/t/se-0487-extensible-enums/80114 "可扩展枚举")

该提议旨在引入“可扩展枚举（extensible enums）”这一新特性，使枚举能够在定义后通过扩展添加新的 case。当前 Swift 中的枚举是封闭的，所有 case 必须在原始定义中列出，这限制了某些 API 的灵活性，尤其是在跨模块或插件架构中。SE-0487 提出，通过标记为 @extensible 的枚举可以允许在其他模块中添加新的 case，从而提升库的可扩展性和未来兼容性。为了支持这一能力，提议还引入了新语法和运行时行为的变化，例如新的 switch 匹配策略。讨论中关注的点包括语义清晰性、编译器处理、ABI 影响以及如何保证已编写代码的兼容性。该提议目前正处于积极讨论阶段，社区对其潜力表现出浓厚兴趣。

2) 提议[让 UUID 遵循 LosslessStringConvertible 协议](https://forums.swift.org/t/pitch-conform-uuid-to-losslessstringconvertible/80084 "让 UUID 遵循 LosslessStringConvertible 协议")

该提议建议将标准库中的 UUID 类型添加对 LosslessStringConvertible 协议的遵循。该协议的要求是类型能够从其 description 文本精确还原自身实例。由于 UUID 本身已经具有 uuidString 属性来表示其标准化字符串形式，并且可以通过该字符串重新初始化，因此完全符合该协议的语义。
```Swift
extension UUID: LosslessStringConvertible {
  public init?(_ description: String) {
    self.init(uuidString: description)
  }

  public var description: String {
    uuidString
  }
}
```
这项更改将带来更好的泛型兼容性，例如可用于基于 LosslessStringConvertible 构建的 API（如 String.init<T: LosslessStringConvertible>(_ description: String)）。该提议受到社区普遍支持，被认为是一个小而有益的改进，且没有 ABI 或源兼容性问题。

3) 讨论[提升对“追溯一致性”支持的易用性](https://forums.swift.org/t/basic-quality-of-life-improvements-for-retroactive/80180 "提升对“追溯一致性”支持的易用性")

该提议讨论了 Swift 中“追溯一致性（retroactive conformance）”的使用体验问题，并提出了几项基础但实用的改进措施。当前，当一个类型在扩展中添加协议一致性后，往往需要显式声明相关成员函数，这在已满足协议要求的情况下会显得冗余。

提议的主要目标是：
	•	允许使用现有成员自动满足协议一致性，而无需重复声明。
	•	提升错误信息的清晰度，帮助开发者识别为什么协议一致性失败。
	•	改善与泛型约束交互的体验，避免开发者在追溯一致性中遇到不必要的限制。

例如，目前开发者可能需要重复声明成员以使扩展符合协议：
```Swift
extension MyType: Equatable {
  static func == (lhs: MyType, rhs: MyType) -> Bool {
    lhs.id == rhs.id
  }
}
```
若 == 已定义，未来希望可简化为：
```Swift
extension MyType: Equatable {}
```
该 pitch 尚未包含完整的语法提案或实现细节，当前处于早期讨论阶段。社区反馈强调其方向合理，尤其适合提升大型项目和多模块代码的可维护性。开发者普遍支持改善追溯一致性的可用性，并建议优先关注诊断质量和语义推导能力的提升。

4) 讨论[预览 Swift 宏开发用 SwiftSyntax 预构建包](https://forums.swift.org/t/preview-swift-syntax-prebuilts-for-macros/80202 "预览 Swift 宏开发用 SwiftSyntax 预构建包")

该帖宣布了一个供宏开发者使用的新预览功能：SwiftSyntax 的预构建二进制包。Swift 宏的实现依赖 SwiftSyntax 和相关组件，这些库频繁变动，版本匹配问题常给开发者带来困扰。为简化体验，Swift 项目团队推出了官方构建的 SwiftSyntax 预编译版本，并托管在 swift-macro-prebuilts GitHub 仓库。

开发者现在可以在 Swift 宏项目中通过添加如下依赖，快速集成正确版本的 SwiftSyntax：
```Swift
.package(url: "https://github.com/apple/swift-macro-prebuilts", from: "0.50900.1")
```
优点包括：
	•	省去手动同步 SwiftSyntax 与 Swift 工具链版本的工作量
	•	加快构建速度
	•	避免源码依赖的编译开销

预构建包以与特定 Swift 工具链兼容为目标，版本号与 Swift 版本一致（例如 0.50900.1 对应 Swift 5.9）。未来计划是让该机制成为宏开发的推荐方式，简化整个宏生态工具链。社区反馈积极，许多宏作者表示这将极大提升开发体验和版本稳定性。

5) 讨论[关于 type(of: s.foo) 的陷阱](https://forums.swift.org/t/type-of-s-foo-gotcha/80156 "关于 type(of: s.foo) 的陷阱")

该帖子指出一个关于 type(of:) 函数在访问实例属性时可能引发误解的语义陷阱。开发者可能直觉地认为 type(of: s.foo) 会返回属性 foo 的运行时类型，尤其当 foo 是协议类型或有类型擦除时。但实际上，它返回的是编译时静态类型，这可能导致结果与预期不符。

示例代码：
```Swift
protocol P {}
struct S: P {}

struct Wrapper {
  var value: P
}

let s = Wrapper(value: S())
print(type(of: s.value))  // 输出 P，而不是 S
```
虽然 s.value 在运行时中实际保存的是 S 类型的实例，但 type(of:) 返回的是 P，即属性声明时的静态类型。这是因为 Swift 中 type(of:) 是泛型函数，它的类型参数是在编译时推导的。

讨论指出该行为虽符合语言设计，但易误导开发者。若想获取实际底层类型，应显式使用 Swift.type(of:) 和 any 关键字或结合类型转换，例如：
```Swift
print(type(of: s.value as Any))  // 输出 S
```
社区讨论建议可能通过改进文档或静态警告提升此类易错用法的可发现性，避免初学者或跨语言用户踩坑。

## 推荐博文


## 话题讨论


## 关于我们

**Swift社区**是由 Swift 爱好者共同维护的公益组织，我们在国内以微信公众号的运营为主，我们会分享以 **Swift实战**、**SwiftUl**、**Swift基础**为核心的技术内容，也整理收集优秀的学习资料。

欢迎关注公众号:Swift社区，后台点击进群，可以进入我们社区的交流讨论群。希望我们Swift社区是大家在网络空间中的另一份共同的归属。

<img width="500" alt="Swift社区" src="https://user-images.githubusercontent.com/24238160/132703149-34121c6c-fd18-491c-a697-58a0fabf3060.png">

特别感谢 Swift社区 编辑部的每一位编辑，感谢大家的辛苦付出，为 Swift社区 提供优质内容，为 Swift 语言的发展贡献自己的力量。
