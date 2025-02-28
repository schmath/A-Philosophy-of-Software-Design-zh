# 第 1 章 介绍

> Chapter 1 Introduction(It’s All About Complexity)

Writing computer software is one of the purest creative activities in the history of the human race. Programmers aren’t bound by practical limitations such as the laws of physics; we can create exciting virtual worlds with behaviors that could never exist in the real world. Programming doesn’t require great physical skill or coordination, like ballet or basketball. All programming requires is a creative mind and the ability to organize your thoughts. If you can visualize a system, you can probably implement it in a computer program.

> 编写计算机软件是人类历史上最纯粹的创作活动之一。程序员不受诸如物理定律等实际限制的约束。我们可以用现实世界中永远不会存在的行为创建令人兴奋的虚拟世界。编程不需要很高的身体技能或协调能力，例如芭蕾或篮球。所有编程都需要具有创造力的头脑和组织思想的能力。如果您可以可视化系统，则可以在计算机程序中实现它。

This means that the greatest limitation in writing software is our ability to understand the systems we are creating. As a program evolves and acquires more features, it becomes complicated, with subtle dependencies between its components. Over time, complexity accumulates, and it becomes harder and harder for programmers to keep all of the relevant factors in their minds as they modify the system. This slows down development and leads to bugs, which slow development even more and add to its cost. Complexity increases inevitably over the life of any program. The larger the program, and the more people that work on it, the more difficult it is to manage complexity.

> 这意味着编写软件的最大限制是我们了解所创建系统的能力。随着程序的发展和获得更多功能，它变得复杂，其组件之间具有微妙的依赖性。随着时间的流逝，复杂性不断累积，程序员在修改系统时将所有相关因素牢记在心中变得越来越难。这会减慢开发速度并导致错误，从而进一步延缓开发速度并增加成本。在任何程序的生命周期中，复杂性都会不可避免地增加。程序越大，工作的人越多，管理复杂性就越困难。

Good development tools can help us deal with complexity, and many great tools have been created over the last several decades. But there is a limit to what we can do with tools alone. If we want to make it easier to write software, so that we can build more powerful systems more cheaply, we must find ways to make software simpler. Complexity will still increase over time, in spite of our best efforts, but simpler designs allow us to build larger and more powerful systems before complexity becomes overwhelming.

> 好的开发工具可以帮助我们应对复杂性，并且在过去的几十年中已经创建了许多出色的工具。但是，仅凭工具我们只能做些事情。如果我们想简化编写软件的过程，从而可以更便宜地构建功能更强大的系统，则必须找到简化软件的方法。尽管我们尽了最大努力，但复杂度仍会随着时间的推移而增加，但是更简单的设计使我们能够在复杂性压倒性优势之前构建更大，功能更强大的系统。

There are two general approaches to fighting complexity, both of which will be discussed in this book. The first approach is to eliminate complexity by making code simpler and more obvious. For example, complexity can be reduced by eliminating special cases or using identifiers in a consistent fashion.

> 有两种解决复杂性的通用方法，这两种方法都将在本书中进行讨论。第一种方法是通过**使代码更简单和更明显**来消除复杂性。例如，可以通过消除特殊情况或以一致的方式使用标识符来降低复杂性。

The second approach to complexity is to encapsulate it, so that programmers can work on a system without being exposed to all of its complexity at once. This approach is called modular design. In modular design, a software system is divided up into modules, such as classes in an object-oriented language. The modules are designed to be relatively independent of each other, so that a programmer can work on one module without having to understand the details of other modules.

> 解决复杂性的第二种方法是**封装它**，以便程序员可以在系统上工作而**不会立即暴露其所有复杂性**。这种方法称为模块化设计。在模块化设计中，软件系统分为模块，例如面向对象语言的类。这些模块被设计为彼此相对独立（低耦合），以便程序员可以**在一个模块上工作而不必了解其他模块的细节**。

Because software is so malleable, software design is a continuous process that spans the entire lifecycle of a software system; this makes software design different from the design of physical systems such as buildings, ships, or bridges. However, software design has not always been viewed this way. For much of the history of programming, design was concentrated at the beginning of a project, as it is in other engineering disciplines. The extreme of this approach is called the waterfall model, in which a project is divided into discrete phases such as requirements definition, design, coding, testing, and maintenance. In the waterfall model, each phase completes before the next phase starts; in many cases different people are responsible for each phase. The entire system is designed at once, during the design phase. The design is frozen at the end of this phase, and the role of the subsequent phases is to flesh out and implement that design.

> 由于软件具有很好的延展性，因此软件设计是一个贯穿软件系统整个生命周期的连续过程。这使得软件设计与诸如建筑物，船舶或桥梁的物理系统的设计不同。但是，并非总是以这种方式查看软件设计。在编程的大部分历史中，设计都集中在项目的开始，就像其他工程学科一样。这种方法的极端称为瀑布模型，该模型将项目划分为离散的阶段，例如需求定义，设计，编码，测试和维护。在瀑布模型中，每个阶段都在下一阶段开始之前完成；在许多情况下，每个阶段都由不同的人负责。在设计阶段，立即设计整个系统。

Unfortunately, the waterfall model rarely works well for software. Software systems are intrinsically more complex than physical systems; it isn’t possible to visualize the design for a large software system well enough to understand all of its implications before building anything. As a result, the initial design will have many problems. The problems do not become apparent until implementation is well underway. However, the waterfall model is not structured to accommodate major design changes at this point (for example, the designers may have moved on to other projects). Thus, developers try to patch around the problems without changing the overall design. This results in an explosion of complexity.

> 不幸的是，瀑布模型很少适用于软件。软件系统本质上比物理系统复杂。在构建任何东西之前，不可能充分可视化大型软件系统的设计，以了解其所有含义。结果，初始设计将有许多问题。在实施良好之前，问题不会变得明显。但是，瀑布模型的结构此时无法适应主要的设计更改（例如，设计师可能已转移到其他项目）。因此，开发人员尝试在不改变整体设计的情况下解决问题。这导致复杂性的爆炸式增长。

Because of these issues, most software development projects today use an incremental approach such as agile development, in which the initial design focuses on a small subset of the overall functionality. This subset is designed, implemented, and then evaluated. Problems with the original design are discovered and corrected, then a few more features are designed, implemented and evaluated. Each iteration exposes problems with the existing design, which are fixed before the next set of features is designed. By spreading out the design in this way, problems with the initial design can be fixed while the system is still small; later features benefit from experience gained during the implementation of earlier features, so they have fewer problems.

> 由于这些问题，当今大多数软件开发项目都使用诸如敏捷开发之类的增量方法，其中初始设计着重于整体功能的一小部分。设计，实施和评估此子集。发现和纠正原始设计的问题，然后设计，实施和评估更多功能。每次迭代都会暴露现有设计的问题，这些问题在设计下一组功能之前就已得到解决。通过以这种方式扩展设计，可以在系统仍然很小的情况下解决初始设计的问题。较新的功能受益于较早功能的实施过程中获得的经验，因此问题较少。

The incremental approach works for software because software is malleable enough to allow significant design changes partway through implementation. In contrast, major design changes are much more challenging for physical systems: for example, it would not be practical to change the number of towers supporting a bridge in the middle of construction.

> 增量方法适用于软件，因为软件具有足够的延展性，可以在实施过程中进行重大的设计更改。相比之下，对物理系统而言，主要的设计更改更具挑战性：例如，在建筑过程中更改支撑桥梁的塔架数量不切实际。

Incremental development means that software design is never done. Design happens continuously over the life of a system: developers should always be thinking about design issues. Incremental development also means continuous redesign. The initial design for a system or component is almost never the best one; experience inevitably shows better ways to do things. As a software developer, you should always be on the lookout for opportunities to improve the design of the system you are working on, and you should plan on spending some fraction of your time on design improvements.

> **增量开发意味着永远不会完成软件设计**。**设计在系统的整个生命周期中不断发生**：开发人员应始终在思考设计问题。增量开发还意味着不断的重新设计。系统或组件的初始设计几乎从来都不是最好的。经验不可避免地显示出更好的做事方式。作为软件开发人员，您应该始终在寻找机会来改进正在开发的系统的设计，并且应该计划将部分时间花费在设计改进上。

If software developers should always be thinking about design issues, and reducing complexity is the most important element of software design, then software developers should always be thinking about complexity. This book is about how to use complexity to guide the design of software throughout its lifetime.

> 如果软件开发人员应始终考虑设计问题，而降低复杂性是软件设计中最重要的要素，则软件开发人员应始终考虑复杂性。这本书是关于如何使用复杂性来指导软件设计的整个生命周期。

This book has two overall goals. The first is to describe the nature of software complexity: what does “complexity” mean, why does it matter, and how can you recognize when a program has unnecessary complexity? The book’s second, and more challenging, goal is to present techniques you can use during the software development process to minimize complexity. Unfortunately, there isn’t a simple recipe that will guarantee great software designs. Instead, I will present a collection of higher-level concepts that border on the philosophical, such as “classes should be deep” or “define errors out of existence.” These concepts may not immediately identify the best design, but you can use them to compare design alternatives and guide your exploration of the design space.

> 这本书有两个总体目标。首先是描述软件复杂性的性质：“复杂性”是什么意思，为什么重要，以及当程序具有不必要的复杂性时如何识别？本书的第二个也是更具挑战性的目标是介绍可在软件开发过程中使用的技术，以最大程度地减少复杂性。不幸的是，没有简单的方法可以保证出色的软件设计。取而代之的是，我将提出一些与哲学紧密相关的高级概念，例如“类应该很深”或“定义不存在的错误”。这些概念可能不会立即确定最佳设计，但您可以使用它们来比较设计备选方案并指导您探索设计空间。

## 1.1 How to use this book 如何使用这本书

Many of the design principles described here are somewhat abstract, so they may be hard to appreciate without looking at actual code. It has been a challenge to find examples that are small enough to include in the book, yet large enough to illustrate problems with real systems (if you encounter good examples, please send them to me). Thus, this book may not be sufficient by itself for you to learn how to apply the principles.

> 这里描述的许多设计原则有些抽象，因此如果不看实际的代码，可能很难理解它们。找到足够小的示例以包含在书中，但是又足够大以说明真实系统的问题是一个挑战（如果遇到好的示例，请发给我）。因此，这本书可能不足以让您学习如何应用这些原理。

The best way to use this book is in conjunction with code reviews. When you read other people’s code, think about whether it conforms to the concepts discussed here and how that relates to the complexity of the code. It’s easier to see design problems in someone else’s code than your own. You can use the red flags described here to identify problems and suggest improvements. Reviewing code will also expose you to new design approaches and programming techniques.

> 使用本书的最佳方法是与**代码审查**结合使用。阅读其他人的代码时，请考虑它是否符合此处讨论的概念，以及它与代码的复杂性之间的关系。**在别人的代码中比在您的代码中更容易看到设计问题**。您可以使用此处描述的红色标记来发现问题并提出改进建议。查看代码还将使您接触到新的设计方法和编程技术。

One of the best ways to improve your design skills is to learn to recognize red flags: signs that a piece of code is probably more complicated than it needs to be. Over the course of this book I will point out red flags that suggest problems related to each major design issue; the most important ones are summarized at the back of the book. You can then use these when you are coding: when you see a red flag, stop and look for an alternate design that eliminates the problem. When you first try this approach, you may have to try several design alternatives before you find one that eliminates the red flag. Don’t give up easily: the more alternatives you try before fixing the problem, the more you will learn. Over time, you will find that your code has fewer and fewer red flags, and your designs are cleaner and cleaner. Your experience will also show you other red flags that you can use to identify design problems (I’d be happy to hear about these).

> 改善设计技能的最好方法之一就是学会识别危险信号：信号表明一段代码可能比需要的复杂。在本书的过程中，我将指出一些危险信号，这些危险信号指示与每个主要设计问题有关的问题；最重要的内容总结在书的后面。然后，您可以在编码时使用它们：当看到红色标记时，停下来寻找可消除问题的替代设计。当您第一次尝试这种方法时，您可能必须尝试几种设计替代方案，然后才能找到消除危险信号的方案。不要轻易放弃：解决问题之前尝试的替代方法越多，您就会学到更多。随着时间的流逝，您会发现代码中的危险信号越来越少，并且您的设计越来越清晰。

When applying the ideas from this book, it’s important to use moderation and discretion. Every rule has its exceptions, and every principle has its limits. If you take any design idea to its extreme, you will probably end up in a bad place. Beautiful designs reflect a balance between competing ideas and approaches. Several chapters have sections titled “Taking it too far,” which describe how to recognize when you are overdoing a good thing.

> 在应用本书中的思想时，务必要节制和谨慎。每条规则都有例外，每条原则都有其局限性。如果您将任何设计创意都发挥到极致，那么您可能会陷入困境。精美的设计反映了相互竞争的思想和方法之间的平衡。有几章的标题为“太过分”，它们描述了如何在做得过大的事情上识别自己。

Almost all of the examples in this book are in Java or C++, and much of the discussion is in terms of designing classes in an object-oriented language. However, the ideas apply in other domains as well. Almost all of the ideas related to methods can also be applied to functions in a language without object-oriented features, such as C. The design ideas also apply to modules other than classes, such as subsystems or network services.

> 本书中几乎所有示例都是使用 Java 或 C ++编写的，并且大部分讨论都是针对以面向对象的语言设计类的。但是，这些想法也适用于其他领域。几乎所有与方法有关的思想也可以应用于没有面向对象功能的语言中的功能，例如 C。设计思想还适用于除类之外的模块，例如子系统或网络服务。

With this background, let’s discuss in more detail what causes complexity, and how to make software systems simpler.

> 在这种背景下，让我们详细讨论导致复杂性的原因以及如何简化软件系统。

> 
解决复杂性的方法
1.使代码更简单和更明显。
2.封装它，使用时不必了解细节。
