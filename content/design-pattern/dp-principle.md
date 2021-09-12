+++
title = "设计模式6大原则"
description = ""
date = 2021-08-30
draft = false
toc = true
categories = [
  "设计模式"
]
tags = [
  ""
]
images = []
+++

#### 1.单一职责原则（Single Responsibility Principle，简称SRP ）
>There should never be more than one reason for a class to change.

理解：不同的类具备不同的职责，各司其职。做系统设计是，如果发现有一个类拥有了两种职责，那么就要问一个问题：可以将这个类分成两个类吗？如果真的有必要，那就分开，千万不要让一个类干的事情太多。

总结：一个类只承担一个职责

#### 2.里氏替换原则（Liskov Substitution Principle,简称LSP）
>Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it.

理解：父类可被子类替换，但反之不一定成立。也就是说，代码中可以将父类全部替换为子类，程序不会出现异常，但反过来就不一定了。

总结：在继承类是，务必重写（override）父类中所有的方法，尤其需要注意父类的protected方法（它们往往是让你重写的），子类尽量不要暴露自己的public方法供外界调用。

#### 3.依赖倒置原则（Dependence Inversion Principle,简称DIP）
>High level modules should not depends upon low level modules.Both should depend upon abstractions.Abstractions should not depend upon details.Details should depend upon abstractions.

理解：高层模块不应该依赖于底层模块，而应该依赖于抽象。抽象不应依赖于细节，细节应依赖于抽象。应该面向接口编程，不该面向实现类编程。面向实现类编程相当于就事论事，那是正向依赖；面向接口编程，相当于透过现象看本质，抓住事务的共性，那就是反向依赖，即依赖倒置。

#### 4.接口隔离原则（Interface Segregation Principle,简称ISP）
>The dependency of one class to another one should depend on the smallest possible interface.

理解：不要对外暴露没有实际意义的接口。也就是说，尽量保证接口的实用性。当需要对外暴露接口时，需要再三斟酌，若没必要对外提供就删了吧，因为一旦提供了就意味着，将来要多做一件事情，何苦给自己找事做呢。

总结：不要对外暴露没有实际意义的接口。
#### 5.迪米特法则（Law of Demeter,简称LoD）
>Only talk to you immediate friends.

理解：尽量减少对象之间的交互，从而减小类之间的耦合。在做系统设计时，不要让一个类依赖于太多其他的类，需尽量减小依赖关系，否则死都不知道怎么死的。

总结：一定要做到：低耦合、高内聚。


#### 6.开放封闭原则（Open Close Principle,简称OCP）
> Software entities like classes,modules and functions should be open for extension but closed for modifications.

对扩展开放，对修改关闭。

在程序需要进行拓展的时候，不能去修改原有的代码，实现一个热插拔的效果。简言之，是为了使程序的扩展性好，易于维护和升级。想要达到这样的效果，我们需要使用接口和抽象类，后面的具体设计中我们会提到这点。

