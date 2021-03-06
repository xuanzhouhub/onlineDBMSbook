# 本书的内容安排

本书会谈及广泛的数据管理系统。但由于市面上的系统种类繁多，无法做到一一列举，本书会着重阐述和对比两类系统。一类是传统的关系数据库，它仍然是目前应用最广泛的数据管理系统。另一类是NoSQL数据库的典型代表 - 文档数据库。本书希望，读者通过掌握这两类系统的使用方法，能够理解数据管理系统背后的设计思想，从而可以举一反三，以便未来能够迅速掌握其他系统。除了这两类系统，本书也会见缝插针地介绍其他常用的数据管理系统，目的也是为了阐述系统背后的设计思想，让读者能够站得更高，看得更远。

对于关系数据库和文档数据库，本书将分别介绍它们的基本功能、内部实现原理、以及用它们进行数据库设计的方法。随后，我们将在两种应用场景中讨论数据管理系统的使用方法，一种是事务处理场景，另一种是数据分析场景。前者更多将数据当作事实的凭据，后者更多将数据当作历史记载。如前文所述，数据的两种功用对数据管理功能提出了不一样的要求。我们将讨论数据管理系统和应用程序是如何配合起来满足这些要求的。此外，我们将单独开辟一章，讨论数据管理系统如何扩展，以应对应用规模扩张带来的挑战。

第二、三章将首先介绍文档数据库。虽然文档数据库远比关系数据库年轻，但它的功能更简单，更易掌握，更适合初学者。

第四、五章介绍关系数据库。这两章的大部分内容都可以在其他教材中找到，但我们会增加并强调现代互联网应用对关系数据库的使用方法。

第六章讲解事务处理技术。除了介绍数据管理系统本身提供的事务处理功能，我们还会讲解应用程序是如何利用数据管理系统确保数据一致性的。

第七章介绍数据管理系统的运维知识，主要聚焦如何进行性能调优。

第八章介绍数据分析系统。数据分析除了会用到关系型和文档型数据库，还会用到其他的数据存储平台和数据处理引擎。这一章都会一一介绍。

第九章介绍如何实现数据管理的能力扩展。这一章也会涉及除数据库以外的其他的数据管理工具，比如缓存和消息队列。

第十章总结本书涉及的所有数据管理系统，并阐述衡量和选择系统的基本原则。

[**上一页<<**](chapter1.3.md) | [**>>下一页**](chapter2.1.md)
