# 数据模型

在概论中我们谈及了数据管理系统的目的、作用和历史，也列举了一些评判系统好坏的标准。本章进入正题。我们开始讨论数据管理系统的具体功能接口应该如何设计。

对应用程序而言，数据管理系统提供的最基本功能无非两个。第一，它能将数据保存到系统中。第二，在需要时，它能方便地从系统中取出数据。当然，如前文所述，系统还应该保证数据的持久性、安全性、真实性，并提供数据更新和数据处理的能力。但这些都是建立在数据存取功能之上的。我们首先需要确定的是数据的存取接口。

以如下数据为例：

> A man named Jason Chang, who was born on Jan 20, 2001, lives in Beijing, at 20 Yamaha Street.

> A woman named Jessie Li, who was born on Dec 4, 1992, lives in Shanghai, at 200 Sichuan Street.

系统应该提供什么样的接口，让我们可以方便的对以上数据进行存取？一种方式是将关于Jason Chang的数据打成一个包，一起存入系统。需要时，我们提供“Jason Chang”这个名字，系统即可将他的数据取出来。同理，我们也可以将关于Jessie Li的数据打包存入系统。需要时，通过“Jessie Li”这个名字将数据取出。对于计算机而言，相当于数据被组织在如下的映射结构中：

>"Jason Chang" --> "A man named Jason Chang, who was born on Jan 20, 2001, lives in Beijing, at 20 Yamaha Street."

>"Jessie Li" --> "A woman named Jessie Li, who was born on Dec 4, 1992, lives in Shanghai, at 200 Sichuan Street."


> name: Jason Chang \
> birthdate: Jan 20, 2001 \
> gender: male \
> address: 20 Yamaha Street, Beijing
