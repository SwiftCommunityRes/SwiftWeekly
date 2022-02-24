# 高级 SwiftUI 动画 —— Part4：TimelineView
## 前言
笔者从发布高级 SwiftUI 动画系列的[Part3](https://swiftui-lab.com/swiftui-animations-part3/ 高级 SwiftUI 动画 —— AnimatableModifier) 至今已经两年了，对 2021 年 WWDC 介绍的 `TimelineView` 和 `Canvas` 感到激动。这开启了一个全新的可能性，笔者将试图在这一部分和下一部分的系列中阐释这些可能性。

![](https://swiftui-lab.com/wp-content/uploads/2021/06/hello-there-25.gif "Hello There")

在这篇文章中，我们将详细地探索 `TimelineView` 。我们将从最常见的用途缓慢开始。然而笔者认为，最大的可能性来自于 `TimelineView` 和我们已知现有的动画相结合。在其他事物中，通过一点创意，这样的组合将让我们最终实现“关键帧类似”的动画。

在第 5 部分，我们将探索 `Canvas` 视图，以及它和我们的新朋友 `TimelineView` 相结合是如此的优秀。

上文中展示的动画，是使用本文中介绍的技术创建的。该动画的完整代码可在此 [gist](https://gist.github.com/swiftui-lab/c1d089207d6f7b365729b1af2e695cc4) 中找到。

## TimelineView 的组件

`TimelineView` 是一个容器视图，它以相关调度程序确定的频率重新评估其内容：

```swift
TimelineView(.periodic(from: .now, by: 0.5)) { timeline in

    ViewToEvaluatePeriodically()

}
```

`TimelineView` 接收调度程序作为参数。 稍后我们将详细认识它们，现在，上述示例使用每半秒触发一次的调度程序。

另一个参数是一个内容闭包，它接收一个看起来像这样的 `TimelineView.Context` 参数：

```swift
struct Context {
    let cadence: Cadence
    let date: Date

    enum Cadence: Comparable {
        case live
        case seconds
        case minutes
    }
}
```

`Cadence` 是一个枚举类型，我们可以使用它来决定在我们的视图中显示什么。 可能的值是：live、seconds 和 minutes。 以此为提示，避免显示与 `Cadence` 无关的信息。 典型的例子，是避免在具有秒或分钟节奏的调度程序的时钟上显示毫秒。

请注意，`Cadence` 不是你可以更改的东西，而是反映设备状态的东西。文档仅提供了一个例子。 在 watchOS 上，降低手腕时 `Cadence` 会减慢。 如果你发现了 `Cadence` 发生变化的其他情况，笔者非常想知道。 请在下方发表评论。

好吧，这一切看起来都很棒，但是我们应该注意许多微妙之处。 让我们开始构建我们的第一个 `TimelineView` 动画，看看它们是什么。

## 理解 TimelineView 如何工作

观察下面的代码。 我们有两个随机变化的表情符号。 两者之间的唯一区别是，一个写在内容闭包中，而另一个被放在单独的视图中以提高可读性。

```swift
struct ManyFaces: View {
    static let emoji = ["😀", "😬", "😄", "🙂", "😗", "🤓", "😏", "😕", "😟", "😎", "😜", "😍", "🤪"]
    
    var body: some View {
        TimelineView(.periodic(from: .now, by: 0.2)) { timeline in

            HStack(spacing: 120) {

                let randomEmoji = ManyFaces.emoji.randomElement() ?? ""
            
                Text(randomEmoji)
                    .font(.largeTitle)
                    .scaleEffect(4.0)
                
                SubView()
                
            }
        }
    }
    
    struct SubView: View {
        var body: some View {
            let randomEmoji = ManyFaces.emoji.randomElement() ?? ""

            Text(randomEmoji)
                .font(.largeTitle)
                .scaleEffect(4.0)
        }
    }
}
```

现在，让我们看下运行代码会发生什么：

![](https://swiftui-lab.com/wp-content/uploads/2021/06/emojis-changing-one.gif "Emoji")

惊了？ 为什么左边的 emoji 会变，而另一个总是悲伤？ 事实证明， `SubView` 没有接收到任何变化的参数，这意味着它没有依赖关系。 `SwiftUI` 没有理由重新计算视图的主体。 2021 年 WWDC 的一个精彩演讲是 `Demystify SwiftUI`。 它解释了视图标识、生命周期和依赖关系。 所有这些主题对于理解时间线为何如此运行都非常重要。

为了解决这个问题，我们更改了 `SubView` 视图以添加一个参数，该参数将随着时间轴的每次更新而改变。 请注意，我们不需要使用参数，它只需要在那里。 尽管如此，我们将看到这个未使用的值稍后会非常有用。

```swift
struct SubView: View {
    let date: Date // just by declaring it, the view will now be recomputed apropriately.
    
    var body: some View {

        let randomEmoji = ManyFaces.emoji.randomElement() ?? ""

        Text(randomEmoji)
            .font(.largeTitle)
            .scaleEffect(4.0)
    }
}
```

现在 `SubView` 是这样创建的：

```swift
SubView(date: timeline.date)
```

最后，我们的两个表情都可以体验到情绪的狂飙：

![](https://swiftui-lab.com/wp-content/uploads/2021/06/emojis-changing-two.gif "Emoji")

## 按照时间线执行

大多数关于 `TimelineView` 的示例（截至编写本文）通常是关于绘制时钟的。 这就说得通了。 时间线提供的数据毕竟是一个日期类型实例。

有史以来最简单的 `TimelineView` 时钟：

```swift
TimelineView(.periodic(from: .now, by: 1.0)) { timeline in
            
    Text("\(timeline.date)")

}
```

时钟可能会变得更加精致。 例如，使用带有形状的模拟时钟，或使用新的 `Canvas` 视图绘制时钟。

但是，`TimelineView` 不仅仅用于时钟。 在许多情况下，我们希望每次时间线更新我们的视图时，视图处理一些事情。 放置此代码的最佳位置是 ` onChange(of:perform) ` 闭包。

在以下示例中，我们使用此技术每 3 秒更新一次模型。

![](https://swiftui-lab.com/wp-content/uploads/2021/06/anim-part4-example-3.gif "Animation")

```swift
struct ExampleView: View {
    var body: some View {
        TimelineView(.periodic(from: .now, by: 3.0)) { timeline in
            QuipView(date: timeline.date)
        }
    }

    struct QuipView: View {
        @StateObject var quips = QuipDatabase()
        let date: Date
        
        var body: some View {
            Text("_\(quips.sentence)_")
                .onChange(of: date) { _ in
                    quips.advance()
                }
        }
    }
}

class QuipDatabase: ObservableObject {
    static var sentences = [
        "There are two types of people, those who can extrapolate from incomplete data",
        "After all is said and done, more is said than done.",
        "Haikus are easy. But sometimes they don't make sense. Refrigerator.",
        "Confidence is the feeling you have before you really understand the problem."
    ]
    
    @Published var sentence: String = QuipDatabase.sentences[0]
    
    var idx = 0
    
    func advance() {
        idx = (idx + 1) % QuipDatabase.sentences.count
        
        sentence = QuipDatabase.sentences[idx]
    }
}
```

需要注意的是，每次时间线更新，我们的 `QuipView` 都会刷新两次。 也就是说，在时间线更新时一次，然后在之后立即再次，因为通过调用 `quips.advance()` 导致 `quips.sentence` 的 `@Published` 值发生变化并触发视图更新。 这很好，但需要注意，因为稍后它会变得更加重要。

> 我们从中得出的一个重要概念是，尽管时间线可能会产生一定数量的更新，但视图的内容很可能会更新更多次。

## TimelineView 与传统动画相结合

新的 `TimelineView` 带来了很多新的机会。 正如我们将在以后的文章中看到的那样，将它与 `Canvas` 结合起来是一个很好的补充。 但为动画的每一帧编写所有代码给了我们带来了很多负担。 笔者将在本节中介绍的技术，使用我们已熟知的动画并且热衷于视图动画从一个时间线更新到下一个时间线。 这最终将让我们在纯 `SwiftUI` 中创建我们自己的类似关键帧的动画。

但是让我们慢慢开始，从我们的小项目开始：如下所示的节拍器。 调高音量播放视频，欣赏节拍声如何与钟摆同步。 此外，就像节拍器一样，每隔几拍就会响起一次铃声：

https://swiftui-lab.com/wp-content/uploads/2021/06/metronome.mp4

首先，让我们看看我们的时间线是什么样的：

```swift
struct Metronome: View {
    let bpm: Double = 60 // beats per minute
    
    var body: some View {
        TimelineView(.periodic(from: .now, by: 60 / bpm)) { timeline in
            MetronomeBack()
                .overlay(MetronomePendulum(bpm: bpm, date: timeline.date))
                .overlay(MetronomeFront(), alignment: .bottom)
        }
    }
}
```

节拍器速度通常以 bpm（每分钟节拍数）指定。 该示例使用周期性调度程序，每 60/bpm 秒重复一次。 对于我们的例子，`bpm = 60`，所以调度程序每 1 秒触发一次。 即每分钟 60 次。

`Metronome` 视图由三层组成：`MetronomeBack`、`MetronomePendulum` 和 `MetronomeFront`。 它们按此顺序叠加。 每次时间线更新都必须刷新的唯一视图是 `MetronomePendulum`，它可以左右摆动。 其他视图不会刷新，因为它们没有依赖关系。

MetronomeBack 和 Metronome Front 的代码非常简单，它们使用了一种称为圆形梯形的自定义形状。 为避免使此页面过长，自定义形状的代码在此 [gist](https://gist.github.com/swiftui-lab/62c3a7512644271e7881985f0b4f7357) 。

```swift
struct MetronomeBack: View {
    let c1 = Color(red: 0, green: 0.3, blue: 0.5, opacity: 1)
    let c2 = Color(red: 0, green: 0.46, blue: 0.73, opacity: 1)
    
    var body: some View {
        let gradient = LinearGradient(colors: [c1, c2],
                                      startPoint: .topLeading,
                                      endPoint: .bottomTrailing)
        
        RoundedTrapezoid(pct: 0.5, cornerSizes: [CGSize(width: 15, height: 15)])
            .foregroundStyle(gradient)
            .frame(width: 200, height: 350)
    }
}

struct MetronomeFront: View {
    var body: some View {
        RoundedTrapezoid(pct: 0.85, cornerSizes: [.zero, CGSize(width: 10, height: 10)])
            .foregroundStyle(Color(red: 0, green: 0.46, blue: 0.73, opacity: 1))
            .frame(width: 180, height: 100).padding(10)
    }
}
```
然而，`MetronomePendulum` 视图是事情开始变得有趣的地方：

```swift
struct MetronomePendulum: View {
    @State var pendulumOnLeft: Bool = false
    @State var bellCounter = 0 // sound bell every 4 beats

    let bpm: Double
    let date: Date
    
    var body: some View {
        Pendulum(angle: pendulumOnLeft ? -30 : 30)
            .animation(.easeInOut(duration: 60 / bpm), value: pendulumOnLeft)
            .onChange(of: date) { _ in beat() }
            .onAppear { beat() }
    }
    
    func beat() {
        pendulumOnLeft.toggle() // triggers the animation
        bellCounter = (bellCounter + 1) % 4 // keeps count of beats, to sound bell every 4th
        
        // sound bell or beat?
        if bellCounter == 0 {
            bellSound?.play()
        } else {
            beatSound?.play()
        }
    }
        
    struct Pendulum: View {
        let angle: Double
        
        var body: some View {
            return Capsule()
                .fill(.red)
                .frame(width: 10, height: 320)
                .overlay(weight)
                .rotationEffect(Angle.degrees(angle), anchor: .bottom)
        }
        
        var weight: some View {
            RoundedRectangle(cornerRadius: 10)
                .fill(.orange)
                .frame(width: 35, height: 35)
                .padding(.bottom, 200)
        }
    }
}
```

我们的视图需要跟踪我们在动画中的位置。 我称之为动画阶段。 由于我们需要跟踪这些阶段，我们将使用 `@State` 变量：

1. `pendulumOnLeft`: 跟踪钟摆 `Pendulum` 摆动的方向。
2. `bellCounter`: 记录节拍的数量，以确定是否应该听到节拍或铃声。

该示例使用 `.animation(_:value:)` 修饰语。 此版本的修改器，在指定值更改时应用动画。 请注意，也可以使用显式动画。 无需调用 `.animation()`，只需在 `withAnimation` 闭包内切换 `pendulumOnLeft` 变量。

为了使我们的视图在动画阶段前进，我们使用 `onChange(of:perform)` 修饰符监视日期的变化，就像我们在前面的 quip 示例中所做的那样。

除了在每次日期值更改时推进动画阶段，我们还在 `onAppear` 闭包中执行此操作。 否则，一开始就会有停顿。

最后一段与 `SwiftUI` 无关的代码是创建 `NSSound` 实例。 为了避免使示例过于复杂，笔者创建了几个全局变量：

```swift
let bellSound: NSSound? = {
    guard let url = Bundle.main.url(forResource: "bell", withExtension: "mp3") else { return nil }
    return NSSound(contentsOf: url, byReference: true)
}()

let beatSound: NSSound? = {
    guard let url = Bundle.main.url(forResource: "beat", withExtension: "mp3") else { return nil }
    return NSSound(contentsOf: url, byReference: true)
}()
```
如果你需要声音文件，可以到 freesound 下载：https://freesound.org/

示例代码中的声音为：

- 钟声: [metronome_pling](https://freesound.org/people/m1rk0/sounds/50071/) 根据许可证 CC BY 3.0 (m1rk0)

- 节拍声: [metronome.wav](https://freesound.org/people/Druminfected/sounds/250552/) 根据 CC0 1.0 

## TimelineScheduler

正如我们已经看到的，`TimelineView` 需要一个 `TimelineScheduler` 来确定何时更新其内容。 `SwiftUI` 提供了一些预定义的调度器，比如我们使用的那些。 但是，我们也可以创建自己的自定义调度程序。 笔者将在下一节中详细说明。 但让我们从已有的调度器开始。

时间线调度器基本上是一个采用 `TimelineScheduler` 协议的结构。 现有的类型有：

- `AnimationTimelineSchedule`： 尽可能快地更新，给你绘制动画每一帧的机会。 它具有让你限制更新频率和暂停更新的参数。 在 `TimelineView` 与新的 `Canvas` 视图结合使用时，这将非常有用。
- `EveryMinuteTimelineSchedule`： 顾名思义，它每分钟更新一次，在每分钟开始时更新。
- `ExplicitTimelineSchedule`： 可以提供一个数组，其中包含你希望时间线更新的所有时间。
- `PeriodicTimelineSchedule`： 可以提供开始时间和发生更新的频率。

尽管你可以以这种方式创建 `Timeline`：

```swift
Timeline(EveryMinuteTimelineSchedule()) { timeline in
    ...
}
```

自 Swift 5.5 和 [SE-0299](https://github.com/apple/swift-evolution/blob/main/proposals/0299-extend-generic-static-member-lookup.md) 的引入以来，我们现在已经支持类枚举语法。 这使代码更具可读性并改进了自动完成功能。 建议我们改用这种语法：

```swift
TimelineView(.everyMinute) { timeline in
    ...
}
```
*注意：你可能听说过，但今年也引入了样式。 更好的是，对于样式，只要你使用的是 Swift 5.5，你就可以使用以前的版本进行反向部署。*

对于每个现有的调度程序，可能有多个类似枚举的选项。 例如，这两行代码创建了 `AnimationTimelineSchedule` 类型的调度程序：

```swift
TimelineView(.animation) { ... }

TimelineView(.animation(minimumInterval: 0.3, paused: false)) { ... }
```

你甚至可以创建属于自己的调度程序（不要忘记 `static` 关键字）：

```swift
extension TimelineSchedule where Self == PeriodicTimelineSchedule {
    static var everyFiveSeconds: PeriodicTimelineSchedule {
        get { .init(from: .now, by: 5.0) }
    }
}

struct ContentView: View {
    var body: some View {
        TimelineView(.everyFiveSeconds) { timeline in
            ...
        }
    }
}
```

## 自定义 TimelineScheduler

如果现有调度程序都不符合你的需求，可以创建自己的调度程序。 思考以下动画： 

![](https://swiftui-lab.com/wp-content/uploads/2021/06/beating-heart.gif)

在这个动画中，我们有一个心形表情符号，它会以不规则的间隔和不规则的幅度改变其比例。
它以 1.0 的比例开始，0.2 秒后增长到 1.6，0.2 秒后增长到 2.0，然后缩小到 1.0 并保持 0.4 秒，然后重新开始。 换一种说法：

尺度变化：1.0 → 1.6 → 2.0 → 重新开始

变化之间的时间：0.2 → 0.2 → 0.4 → 重新开始

我们可以创建一个 `HeartTimelineSchedule`，它完全按照心脏的需要进行更新。 但是以可重用性的名义，让我们做一些更通用的东西，将来可以重用。

我们新调度程序将被称为：`CyclicTimelineSchedule`，并将接收一组时间偏移量。 每个偏移值都将相对于数组中的前一个值。 当调度程序用尽偏移量时，它将循环回到数组的开头并重新开始。

```swift
struct CyclicTimelineSchedule: TimelineSchedule {
    let timeOffsets: [TimeInterval]
    
    func entries(from startDate: Date, mode: TimelineScheduleMode) -> Entries {
        Entries(last: startDate, offsets: timeOffsets)
    }
    
    struct Entries: Sequence, IteratorProtocol {
        var last: Date
        let offsets: [TimeInterval]
        
        var idx: Int = -1
        
        mutating func next() -> Date? {
            idx = (idx + 1) % offsets.count
            
            last = last.addingTimeInterval(offsets[idx])
            
            return last
        }
    }
}
```

实现 `TimelineSchedule` 有几个要求：

- 提供 `entry(from:mode:)` 函数。
- 我们 `Entries` 的类型必须符合 `Sequence where Entries.Element == Date`

有几种方法可以符合 `Sequence`。 此示例实现 `IteratorProtocol` 并声明符合 `Sequence` 和 `IteratorProtocol`。 你可以在[此处](https://developer.apple.com/documentation/swift/sequence)阅读有关序列一致性的更多信息。

对于实现 `IteratorProtocol` 的 `Entries`，我们必须编写 `next()` 函数，该函数在时间线中生成日期。 我们的调度程序会记住最后日期并添加适当的偏移量。 当没有更多的偏移量时，它会循环回到数组中的第一个。

最后，锦上添花的是，为我们的调度器创建一个类似枚举的初始化器：

```swift
extension TimelineSchedule where Self == CyclicTimelineSchedule {
    static func cyclic(timeOffsets: [TimeInterval]) -> CyclicTimelineSchedule {
            .init(timeOffsets: timeOffsets)
    }
}
```

现在我们已经准备好 `TimelineSchedue` 类型了，让我们为我们的心脏注入一些活力：

```swift
struct BeatingHeart: View {
    var body: some View {
        TimelineView(.cyclic(timeOffsets: [0.2, 0.2, 0.4])) { timeline in
            Heart(date: timeline.date)
        }
    }
}

struct Heart: View {
    @State private var phase = 0
    let scales: [CGFloat] = [1.0, 1.6, 2.0]
    
    let date: Date
    
    var body: some View {
        HStack {
            Text("❤️")
                .font(.largeTitle)
                .scaleEffect(scales[phase])
                .animation(.spring(response: 0.10,
                                   dampingFraction: 0.24,
                                   blendDuration: 0.2),
                           value: phase)
                .onChange(of: date) { _ in
                    advanceAnimationPhase()
                }
                .onAppear {
                    advanceAnimationPhase()
                }

        }
    }
    
    func advanceAnimationPhase() {
        phase = (phase + 1) % scales.count
    }
}
```

你现在应该熟悉这种模式，它与我们使用节拍器的模式相同。 使用 `onChange` 和 `onAppear` 推进动画，使用 `@State` 变量来跟踪动画，并设置一个动画，将我们的视图从一个时间线更新过渡到下一个。 在这种情况下，我们使用 `.spring` 动画，给它一个很好的摇晃效果。

## 关键帧动画

心脏和节拍器示例在某种程度上是关键帧动画。 我们在整个动画中定义了几个关键点，在这里我们改变了我们视图的参数，并让 `SwiftUI` 动画这些点之间的过渡。 以下示例将尝试概括该想法，并使其更加明显。 认识我们的新项目朋友，跳跃的家伙：

![](https://swiftui-lab.com/wp-content/uploads/2021/06/jumping-emoji-1.gif)

如果你仔细观察动画，你会注意到这个表情符号角色的许多参数在不同的时间点发生了变化。 这些参数是：`y-offset`、`rotation` 和 `y-scale`。 同样重要的是，动画的不同片段有不同的动画类型（线性、缓入和缓出）。 由于这些是我们更改的参数，因此最好将它们放在一个数组中。 让我们开始： 

```swift
struct KeyFrame {
    let offset: TimeInterval    
    let rotation: Double
    let yScale: Double
    let y: CGFloat
    let animation: Animation?
}

let keyframes = [
    // Initial state, will be used once. Its offset is useless and will be ignored
    KeyFrame(offset: 0.0, rotation: 0, yScale: 1.0, y: 0, animation: nil),

    // Animation keyframes
    KeyFrame(offset: 0.2, rotation:   0, yScale: 0.5, y:  20, animation: .linear(duration: 0.2)),
    KeyFrame(offset: 0.4, rotation:   0, yScale: 1.0, y: -20, animation: .linear(duration: 0.4)),
    KeyFrame(offset: 0.5, rotation: 360, yScale: 1.0, y: -80, animation: .easeOut(duration: 0.5)),
    KeyFrame(offset: 0.4, rotation: 360, yScale: 1.0, y: -20, animation: .easeIn(duration: 0.4)),
    KeyFrame(offset: 0.2, rotation: 360, yScale: 0.5, y:  20, animation: .easeOut(duration: 0.2)),
    KeyFrame(offset: 0.4, rotation: 360, yScale: 1.0, y: -20, animation: .linear(duration: 0.4)),
    KeyFrame(offset: 0.5, rotation:   0, yScale: 1.0, y: -80, animation: .easeOut(duration: 0.5)),
    KeyFrame(offset: 0.4, rotation:   0, yScale: 1.0, y: -20, animation: .easeIn(duration: 0.4)),
]
```

重要的是要知道，当 `TimelineView` 出现时，它会绘制我们的视图，即使没有计划的更新，或者它们是否在将来。 当 `TimelineView` 出现时，它需要显示一些东西，以便绘制我们的视图。 我们将使用第一个关键帧作为我们的视图状态，但是当我们循环时，该帧将被忽略。 这是一个实施决策，你可能需要或想要以不同的方式进行。

现在，让我们看看我们的时间线：

```swift
struct JumpingEmoji: View {
    // Use all offset, minus the first
    let offsets = Array(keyframes.map { $0.offset }.dropFirst())
    
    var body: some View {
        TimelineView(.cyclic(timeOffsets: offsets)) { timeline in
            HappyEmoji(date: timeline.date)
        }
    }
}
```

我们已经从我们在前一个示例中所做的工作中受益，并重用了 `CyclicTimelineScheduler`。 如前所述，我们不需要第一个关键帧的偏移量，因此我们将其丢弃。

现在，有趣的部分：

```swift
struct HappyEmoji: View {
    // current keyframe number
    @State var idx: Int = 0

    // timeline update
    let date: Date
    
    var body: some View {
        Text("😃")
            .font(.largeTitle)
            .scaleEffect(4.0)
            .modifier(Effects(keyframe: keyframes[idx]))
            .animation(keyframes[idx].animation, value: idx)
            .onChange(of: date) { _ in advanceKeyFrame() }
            .onAppear { advanceKeyFrame()}
    }
    
    func advanceKeyFrame() {
        // advance to next keyframe
        idx = (idx + 1) % keyframes.count
        
        // skip first frame for animation, which we
        // only used as the initial state.
        if idx == 0 { idx = 1 }
    }
    
    struct Effects: ViewModifier {
        let keyframe: KeyFrame
        
        func body(content: Content) -> some View {
            content
                .scaleEffect(CGSize(width: 1.0, height: keyframe.yScale))
                .rotationEffect(Angle(degrees: keyframe.rotation))
                .offset(y: keyframe.y)
        }
    }
}
```

为了更好的可读性，我将所有变化的参数放在一个名为 `Effects` 的修改器中。 如你所见，它还是相同的模式：使用 `onChange` 和 `onAppear` 来推进我们的动画，并为每个关键帧片段添加一个动画。 那里没有什么新鲜事。

## 不要！ 这是一个陷阱！
在你的 `TimelineView` 发现路径中，你可能会遇到此错误：

> Action Tried to Update Multiple Times Per Frame

让我们看一个生成此消息的示例： 

```swift
struct ExampleView: View {
    @State private var flag = false
    
    var body: some View {

        TimelineView(.periodic(from: .now, by: 2.0)) { timeline in

            Text("Hello")
                .foregroundStyle(flag ? .red : .blue)
                .onChange(of: timeline.date) { (date: Date) in
                    flag.toggle()
                }

        }
    }
}
```

代码看起来没有问题，它应该每两秒改变一次文本颜色，在红色和蓝色之间交替。那么可能会发生什么？稍等片刻，看看你是否能找出背后的原因。

我们不是在处理一个 bug。事实上，这个问题是可以预见的。
`
重要的是要记住，时间线的第一次更新是在它第一次出现时，然后它遵循调度程序规则来触发以下更新。因此，即使我们的调度程序没有产生更新， `TimelineView` 内容也至少会生成一次。

在这个具体的例子中，我们监控 `timeline.date` 值的变化，当它发生变化时，我们切换 `flag` 变量，它会产生颜色变化。

`TimelineView` 将首先出现。两秒后，时间线将更新（例如，由于第一次调度程序更新），触发 `onChange` 关闭。这将反过来改变标志变量。现在，由于我们的 `TimelineView` 依赖于它，它需要立即刷新，触发标志变量的另一个切换，强制另一个 `TimelineView` 刷新，依此类推……你明白了：每帧多次更新。

那么我们该如何解决呢？解决方案可能会有所不同。在这种情况下，我们只需封装内容并将标志变量移动到封装的视图内。现在 `TimelineView` 不再依赖它：

```swift
struct ExampleView: View {
    var body: some View {

        TimelineView(.periodic(from: .now, by: 1.0)) { timeline in
            SubView(date: timeline.date)
        }

    }
}

struct SubView: View {
    @State private var flag = false
    let date: Date

    var body: some View {
        Text("Hello")
            .foregroundStyle(flag ? .red : .blue)
            .onChange(of: date) { (date: Date) in
                flag.toggle()
            }
    }
}
```

## 探索新点子
**每次时间线更新刷新一次**：如前所述，这种模式使我们的视图每次更新计算它们的主体两次：第一次是在时间线更新时，然后在我们推进动画状态值时再次计算。在这种类型的动画中，我们在时间上间隔了关键点，这非常好。

在这些时间点太靠近的动画中，你可能需要/想要避免这种情况。如果你需要更改存储的值，但要避免视图刷新……你可以使用一个技巧。使用 `@StateObject` 代替`@State`。确保你不要在 `@Published` 中设置这样的值。如果在某个时候，你想要/需要告诉你的视图刷新，你可以随时调用` objectWillChange.send()`

**匹配动画持续时间和偏移量**：在关键帧示例中，我们为每个动画片段使用不同的动画。为此，我们将动画值存储在数组中。如果你仔细观察，你会发现在我们的具体示例中，偏移量和动画持续时间匹配！这是合理的，对吧？因此，你可以定义一个具有动画类型的枚举，而不是在数组中包含 `Animation` 值。稍后在你的视图中，你将根据动画类型创建动画值，但使用偏移值的持续时间对其进行实例化。类似这样：

```swift
enum KeyFrameAnimation {
    case none
    case linear
    case easeOut
    case easeIn
}

struct KeyFrame {
    let offset: TimeInterval    
    let rotation: Double
    let yScale: Double
    let y: CGFloat
    let animationKind: KeyFrameAnimation
    
    var animation: Animation? {
        switch animationKind {
        case .none: return nil
        case .linear: return .linear(duration: offset)
        case .easeIn: return .easeIn(duration: offset)
        case .easeOut: return .easeOut(duration: offset)
        }
    }
}

let keyframes = [
    // Initial state, will be used once. Its offset is useless and will be ignored
    KeyFrame(offset: 0.0, rotation: 0, yScale: 1.0, y: 0, animationKind: .none),

    // Animation keyframes
    KeyFrame(offset: 0.2, rotation:   0, yScale: 0.5, y:  20, animationKind: .linear),
    KeyFrame(offset: 0.4, rotation:   0, yScale: 1.0, y: -20, animationKind: .linear),
    KeyFrame(offset: 0.5, rotation: 360, yScale: 1.0, y: -80, animationKind: .easeOut),
    KeyFrame(offset: 0.4, rotation: 360, yScale: 1.0, y: -20, animationKind: .easeIn),
    KeyFrame(offset: 0.2, rotation: 360, yScale: 0.5, y:  20, animationKind: .easeOut),
    KeyFrame(offset: 0.4, rotation: 360, yScale: 1.0, y: -20, animationKind: .linear),
    KeyFrame(offset: 0.5, rotation:   0, yScale: 1.0, y: -80, animationKind: .easeOut),
    KeyFrame(offset: 0.4, rotation:   0, yScale: 1.0, y: -20, animationKind: .easeIn),
]
```

如果你想知道为什么我一开始不这样做，我只是想向你展示两种方式都是可能的。 第一种情况更灵活，但更冗长。 也就是说，我们被迫为每个动画指定持续时间，但是，它更灵活，因为我们可以自由使用与偏移量不匹配的持续时间。

然而，当使用这种新方法时，你可以轻松地添加一个可自定义的因素，这可以让你减慢或加快动画速度，而无需触摸关键帧。

**嵌套 TimelineViews**：没有什么能阻止你将一个 `TimelineView` 嵌套在另一个 `TimelineView` 中。 现在我们有了 `JumpingEmoji`，我们可以在 `TimelineView` 中放置三个 `JumpingEmoji` 视图，使它们一次出现一个，并有延迟：

![](https://swiftui-lab.com/wp-content/uploads/2021/06/wave-emoji-1.gif)

对于 Emoji 波浪的全部源码，检出这个 [gits](https://gist.github.com/swiftui-lab/f4e77af35ba15853cc1426c735cc6cdc)。

## GifImage 示例
笔者原本还有一个示例，但是它在笔者发布文章的时候废弃了。 它没有入选的原因是并发 API 还不稳定。 幸运的是，现在可以安全地发布它。 该代码使用 `TimelineView` 来实现动画 gif 的视图。 视图从 URL（可以是本地的或远程的）异步加载 gif。 此 [gist](https://gist.github.com/swiftui-lab/aa5d73b81c8696dee4a5996954b22e5c) 中提供了所有代码。

## 小结
恭喜阅读到这么长的一篇文章的结尾。这是一次骑行！我们从最简单的 `TimelineView` 示例转到视图的一些创造性使用。 在第 5 部分中，笔者将探索新的 `Canvas` 视图，以及它与 `TimelineView` 的结合程度。 通过将它们放在一起，我们将扩展 `SwiftUI` 动画世界中的更多可能性。
