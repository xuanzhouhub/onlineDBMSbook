# 前言

我们为什么还需要一本《数据管理系统》教材？

斗转星移。数据管理系统的种类、形态和使用方法实际上一直在变化。上世纪70年代建立起的关系数据库理论看上去依然美妙。基于它的SQL数据库系统依然是软件开发者的首选。然而，竞争者在不断涌现。NoSQL数据库在十年前掀起了一股潮流。以谷歌和亚马逊为首的互联网公司率先向关系数据库发难。它们针对各自的业务场景构建了更易于使用、并且扩展能力更强的非关系型数据管理系统。这些系统被公布后，被开源社区吸收、再创造，进化成了各式各样的NoSQL数据库。如今，像MongoDB和Cassandra这样的通用NoSQL数据库已经在互联网行业中被广泛使用。像“时序数据库”和“图数据库”这样为特殊领域定制的数据管理系统也在不少应用中站稳了脚跟。面对众多可选的数据管理系统，软件开发者应该何去何从？选择合适的系统工具对软件开发而言至关重要。而传统数据管理教材不曾教导我们如何选择。

近年来，我们也看到：软件的开发方式在改变，从而引发了数据管理系统使用方式的改变。从前，我们习惯于将数据库和应用逻辑分开设计。如果你熟悉关于关系数据库的早年文献，你会认同这种分离原则 - 数据最好只有一套，用于反应现实世界的状态，例如某银行的用户存款记录；而应用软件可以有多套（比如理财产品服务软件和定额存款服务软件），他们共享同一个数据库，从而可以看到一个一致的现实世界（a single source of truth）。在这一理念下，数据库理应成为独立的个体，它的设计应由DBA独立完成，而不应依赖于上层软件的设计。然而，这样的软件设计理念如今似乎不再流行了。在互联网应用的开发实践中，敏捷开发模式成为了主流。它倡导软件设计以用户为中心，倡导快速迭代。这意味着从功能到数据的开发次序，即数据库的设计依赖于上层软件的设计。在当前流行的“微服务”软件架构中，应用逻辑和数据库之间的分离不再被重视，而“服务”之间的分离显得更加重要。以上面的银行应用为例：在“微服务”架构下，“理财产品服务”和“定额存款服务”通常不会直接构建在共享数据库之上，它们会跟“账户管理服务”打交道，而由“账户管理服务”单独管理用户存款数据。我们无法断言新的开发模式一定比传统开发模式更先进。但显然我们不能再单纯地认为数据库设计是一个独立的过程。这与传统数据管理教材的观点产生了分歧。

互联网对数据管理系统的扩展能力也提出了更高的要求。不少互联网应用都经历过快速的业务增长。如果系统的数据处理能力无法扩展，或者跟不上业务的增长，应用就会濒临崩溃。学界对分布式数据管理系统的研究已经有多年历史，成果虽然丰富，但能付诸实践的很少。人们在实践中发现，传统SQL数据库很难独立扩展。而要真正做到业务处理能力的扩展，需要协同应用层和数据层的设计。此外，不同的数据管理系统（包括SQL和NoSQL系统）有不同的扩展方式，对上层应用的构建也有不同的要求。当代的开发人员已经在应用扩展的实践中积累了不少经验，但这些经验尚未得到很好的凝练。传统的数据管理教材部分谈及了数据库自身的扩展理论，却没有吸收互联网时代的实践经验，没有考虑应用层和数据层的协同扩展，因而缺乏指导意义。

本书将从更宏观的层次，即系统设计的层次，来讲解数据管理系统。作者不崇拜任何一类系统或软件开发方式。相反，本书将阐述不同数据管理系统的设计初衷，并对它们进行横向比较，从而帮助开发者在软件设计过程中做出更合理的选择。SQL数据库是本书的阐述对象之一。由于现有的经典教材已经对SQL数据库进行了全面介绍，本书更多会引述现有教材的内容。对于NoSQL数据库，本书将选择其中的文档数据库进行深入讲解。对其他种类的数据管理系统，本书也会有所涉及。

本书将讲解不同的数据库设计方式，并分析它们的适用场景，从而帮助开发者去因时制宜地使用数据管理系统。传统的独立于上层应用的数据库设计方式只是内容之一。本书还会阐述从应用逻辑出发的数据库设计方式，讨论如何协同设计应用逻辑和数据库模式。SQL数据库和NoSQL数据库的设计方法本书都会涉及。

本书还将介绍数据管理系统乃至整个应用软件的扩展方法，从而帮助应用开发者应对业务增长问题。这包括传统SQL数据库的并行化方法与工具，也包括使用NoSQL数据库对应用进行扩展的方案。本书会着重讨论如何调整应用层的业务逻辑，以配合数据库的扩展。

对于传统的SQL数据库，我们已经拥有若干经典教材，比如由Abraham Silberschatz，Henry F. Korth和S. Sudarshan合著的《Database System Concepts》，由Héctor García-Molina，Jeffrey Ullman和Jennifer Widom合著的《Database System: The Complete Book》，在国内有王珊教授和沙师煊教授合著的《数据库系统概论》。作者认为没有必要重复这些教材的内容。因此，本书对SQL数据库的介绍将相对简略，很多地方只会给出一些索引，引导读者在以上的经典教材中查阅相关内容。

本书的对象是需要使用数据管理系统的使用者。这包括在校的相关专业学生和密切接触数据管理技术的软件从业者。对于只想了解数据管理系统而并不急于去使用它的读者，本书可能难度过高。对于参与数据管理系统开发的技术人员，本书则缺少对系统实现细节的描述。本书聚焦在如何合理使用数据管理系统去构建应用软件。

作者希望本书成为一本开放式的教材，能够随时被修改和补充，并且能随时接受读者的批评。作者作为科研工作者，对应用开发实践的了解不可能全面，因此不可避免会产生偏见和错误。希望通过开放评论，及时发现这些偏见和错误，并及时完善。作者特别欢迎富有软件开发经验的人士对本书提出建设性意见。对于有帮助的建议，作者会在书中点名致谢。互联网应用带给我们的启示是大部分开创性工作都不可能一触而就，而需要反复迭代。因此，作者决定将书稿公布在网上，通过读者反馈进行快速迭代。

[本书目录](contents.md)
