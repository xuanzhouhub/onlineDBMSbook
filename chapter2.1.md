# 数据模型

在概论中我们谈及了数据管理系统的目的、作用和历史，也列举了一些评判系统好坏的标准。本章进入正题。我们开始讨论数据管理系统的具体功能接口应该如何设计。

对应用程序而言，数据管理系统提供的最基本功能无非两个。第一，它能将数据保存到系统中。第二，在需要时，它能方便地从系统中取出数据。当然，如前文所述，系统还应该保证数据的持久性、安全性、真实性，并提供数据更新和数据处理的能力。但这些都是建立在数据存取功能之上的。我们首先需要确定的是数据的存取接口。

以如下数据为例：

> A man named Jason Chang, who was born on Jan 20, 2001, lives in Beijing, at 20 Yamaha Street.

> A woman named Jessie Li, who was born on Dec 4, 1992, lives in Shanghai, at 200 Sichuan Street.

系统应该提供什么样的接口，让我们可以方便的对以上数据进行存取？一种方式是将关于Jason Chang的数据打成一个包，一起存入系统。需要时，我们提供“Jason Chang”这个名字，系统即可将他的数据取出来。同理，我们也可以将关于Jessie Li的数据打包存入系统。需要时，通过“Jessie Li”这个名字将数据取出。计算机为了实现这样的存取功能，需要将数据组织在如下的映射结构中：

>"Jason Chang" &rarr; "A man named Jason Chang, who was born on Jan 20, 2001, lives in Beijing, at 20 Yamaha Street."

>"Jessie Li" &rarr; "A woman named Jessie Li, who was born on Dec 4, 1992, lives in Shanghai, at 200 Sichuan Street."

这里的人名可以视为**键**（key），关于人的数据可以视为**值**（value）。也就是说，我们是在用如下的**键值对**结构组织数据。

> *key* &rarr; *value* 

这个结构用“键”标识每一项数据，通过“键”对数据进行存取。

假设我们积累了很多人的数据，除了Jason Chang和Jessie Li，还有包括其他人。这个时候，我们想从系统中取出居住在地址20 Yamaha Street的人的信息，该如何做？我们发现，如果用“键值对”组织数据，系统是无法直接实现以上的数据抽取的。虽然“20 Yamaha Street”的字眼藏在键值对的值中，但对计算机而言，这些值只是一个个的它无法理解的字符串。我们只能将所有的键值对依次取出来，然后一个一个判断哪些人住在20 Yamaha Street。也就是说，“键值对”这种组织结构太简单，无法实现复杂的数据存取功能。

如果我们将数据组织在下面的结构中，情况就有所改变。

> name: Jason Chang \
> birthdate: Jan 20, 2001 \
> gender: male \
> address: 20 Yamaha Street\
> city: Beijing

> name: Jessie Li \
> birthdate: Dec 4, 1992 \
> gender: female \
> address: 200 Sichuan Street\
> city: Shanghai

这种结构将每个人视为一个**实体**（entity），每个实体被赋予了若干**属性**（attributes），比如姓名（name）、生日（birthdate）、住址（address）等。属性的**取值**（value）对实体进行了刻画。基于这样的结构，我们可以将实体整体存入系统，也可以将它们整体取出来。不仅如此，系统还可以对单个属性进行操作，比如改动某个人的住址。如果要查找居住在地址20 Yamaha Street的人，我们可以直接要求系统找到在address属性上的取值为“20 Yamaha Street”的实体。


