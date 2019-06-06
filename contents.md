# 目录

## 第一章 概述
__1.1.__ 什么是系统  
&nbsp;&nbsp;&nbsp;&nbsp; __1.1.1.__ 软件设计的模块化  
&nbsp;&nbsp;&nbsp;&nbsp; __1.1.2.__ 系统的目的  
&nbsp;&nbsp;&nbsp;&nbsp; __1.1.3.__ 系统的设计考虑  
__1.2.__ 什么是数据库管理系统  
&nbsp;&nbsp;&nbsp;&nbsp; __1.2.1.__ 数据库管理系统的功能  
&nbsp;&nbsp;&nbsp;&nbsp; __1.2.2.__ 数据库管理系统的设计考虑  
__1.3.__ 数据库系统简史  
&nbsp;&nbsp;&nbsp;&nbsp; __1.3.1.__ 70年代以前：数据库系统早期形态  
&nbsp;&nbsp;&nbsp;&nbsp; __1.3.2.__ 70-80年代：关系数据库的崛起  
&nbsp;&nbsp;&nbsp;&nbsp; __1.3.3.__ 90年代：开源与新型数据库的萌芽  
&nbsp;&nbsp;&nbsp;&nbsp; __1.3.4.__ 2000年以后：数据库的多样化  
__1.4.__ 本书的内容安排
	
## 第二章 文档数据库
2.1. 文档数据库的基本功能  
&nbsp;&nbsp;&nbsp;&nbsp; 2.1.1. 文档数据模型  
&nbsp;&nbsp;&nbsp;&nbsp; 2.1.2. 文档CRUD操作  
&nbsp;&nbsp;&nbsp;&nbsp; 2.1.3. 接口与程序调用方式  
	2.2. 文档数据库的存储结构  
&nbsp;&nbsp;&nbsp;&nbsp; 2.2.1. 存储体系结构概览  
&nbsp;&nbsp;&nbsp;&nbsp; 2.2.2. 文档数据库的存储管理  
&nbsp;&nbsp;&nbsp;&nbsp; 2.2.3. B树索引  
	2.3. 文档数据库的数据一致性  
&nbsp;&nbsp;&nbsp;&nbsp; 2.3.1. 什么是数据一致性（linearizability）  
&nbsp;&nbsp;&nbsp;&nbsp; 2.3.2. 如何保证数据一致性（日志和并发控制）  
	2.4. 文档数据库的可用性保障  
&nbsp;&nbsp;&nbsp;&nbsp; 2.4.1. 什么是系统的可用性  
&nbsp;&nbsp;&nbsp;&nbsp; 2.4.2. 如何获得可用性（共识协议Raft）  
	2.5. 一致性和性能的折中选择  
&nbsp;&nbsp;&nbsp;&nbsp; 2.5.1. MongoDB的系统参数设置  
&nbsp;&nbsp;&nbsp;&nbsp; 2.5.2. MongoDB 的Read / Write Concerns  
		
## 第三章 文档数据库设计
3.1. 软件开发的OO建模  
&nbsp;&nbsp;&nbsp;&nbsp; 3.1.1. 概念设计  
&nbsp;&nbsp;&nbsp;&nbsp; 3.1.2. 详细设计  
&nbsp;&nbsp;&nbsp;&nbsp; 3.1.3. 对象的持久化  
	3.2. 数据模型与模式  
&nbsp;&nbsp;&nbsp;&nbsp; 3.2.1. 数据模型  
&nbsp;&nbsp;&nbsp;&nbsp; 3.2.2. 数据库模式  
	3.3. 文档数据库逻辑设计  
&nbsp;&nbsp;&nbsp;&nbsp; 3.3.1. 从对象到文档  
&nbsp;&nbsp;&nbsp;&nbsp; 3.3.2. 嵌套还是引用  
&nbsp;&nbsp;&nbsp;&nbsp; 3.3.2. 范式化与逆范式化  
	3.4. 文档数据模式物理设计  
&nbsp;&nbsp;&nbsp;&nbsp; 3.4.1. 辅助索引的创建与使用  
&nbsp;&nbsp;&nbsp;&nbsp; 3.4.2. Read / Write Concerns的选择  
		
## 第四章 关系数据库
4.1. 关系数据库的设计理念  
&nbsp;&nbsp;&nbsp;&nbsp; 4.1.1. 应用逻辑与数据库的分离原则  
&nbsp;&nbsp;&nbsp;&nbsp; 4.1.2. 申明式程序设计语言  
	4.2. 关系模型（指向现有教材）  
	4.3. 关系数据库的存储结构（指向现有教材）  
	4.4. SQL语言（指向现有教材）  
	4.5. 查询处理与查询优化（指向现有教材）  
	4.6. SQL的接口与程序调用方式（指向现有教材）  
	
## 第五章 关系数据库设计
5.1 应用出发的数据库设计方式  
&nbsp;&nbsp;&nbsp;&nbsp; 5.1.1 对象的持久化需求  
&nbsp;&nbsp;&nbsp;&nbsp; 5.1.2 从对象到关系  
&nbsp;&nbsp;&nbsp;&nbsp; 5.1.3 ORM工具  
&nbsp;&nbsp;&nbsp;&nbsp; 5.1.4 对象与关系的不匹配问题  
	5.2 独立的数据库设计方式  
&nbsp;&nbsp;&nbsp;&nbsp; 5.2.1 ER模型（指向现有教材）  
&nbsp;&nbsp;&nbsp;&nbsp; 5.2.2 关系范式（指向现有教材）  
&nbsp;&nbsp;&nbsp;&nbsp; 5.2.3 关系模型概念设计（指向现有教材）  
	5.3 关系数据库物理设计  
&nbsp;&nbsp;&nbsp;&nbsp; 5.3.1 物理模式设计  
&nbsp;&nbsp;&nbsp;&nbsp; 5.3.2 索引的创建与使用（指向现有教材）  
&nbsp;&nbsp;&nbsp;&nbsp; 5.3.3 约束的使用（指向现有教材）  

## 第六章 事务处理
6.1 事务的概念  
&nbsp;&nbsp;&nbsp;&nbsp; 6.1.1 并发与程序正确性要求  
&nbsp;&nbsp;&nbsp;&nbsp; 6.1.2 事务的ACID性质（指向现有教材）  
&nbsp;&nbsp;&nbsp;&nbsp; 6.1.3 隔离级别（指向现有教材）  
	6.2 事务的实现方案  
&nbsp;&nbsp;&nbsp;&nbsp; 6.2.1 持久化机制（指向现有教材）  
&nbsp;&nbsp;&nbsp;&nbsp; 6.2.2 隔离机制（指向现有教材）  
	6.3 事务的使用方法  
&nbsp;&nbsp;&nbsp;&nbsp; 6.3.1 隔离级别的选择  
&nbsp;&nbsp;&nbsp;&nbsp; 6.3.2 低效的事务设计  
&nbsp;&nbsp;&nbsp;&nbsp; 6.3.3 事务的拆分与补偿  
	6.4 文档数据库的事务处理  
&nbsp;&nbsp;&nbsp;&nbsp; 6.4.1 标志位的使用  
&nbsp;&nbsp;&nbsp;&nbsp; 6.4.2 队列的使用  
&nbsp;&nbsp;&nbsp;&nbsp; 6.4.3 案例  

## 第七章 数据库的维护与调优
7.1 数据的备份与归档（指向现有教材）  
	7.2 系统性能瓶颈诊断（指向现有教材）  
	7.3 系统性能调优（指向现有教材）  

## 第八章 数据管理能力的扩展
8.1 缓存机制  
	8.2 消息队列  
	8.3 关系数据库的扩展  
&nbsp;&nbsp;&nbsp;&nbsp; 8.3.1 数据复制  
&nbsp;&nbsp;&nbsp;&nbsp; 8.3.2 分库分表  
&nbsp;&nbsp;&nbsp;&nbsp; 8.3.3 分库分表中间件  
	8.4 分布式数据库  
&nbsp;&nbsp;&nbsp;&nbsp; 8.4.1 分布式数据库的架构  
&nbsp;&nbsp;&nbsp;&nbsp; 8.4.2 数据的分片  
&nbsp;&nbsp;&nbsp;&nbsp; 8.4.3 查询并行化及其代价  
&nbsp;&nbsp;&nbsp;&nbsp; 8.4.4 分布式事务及其代价  
&nbsp;&nbsp;&nbsp;&nbsp; 8.4.5 典型分布式数据库系统  
	8.5 NoSQL数据库的扩展  
&nbsp;&nbsp;&nbsp;&nbsp; 8.5.1 NoSQL数据库的设计理念  
&nbsp;&nbsp;&nbsp;&nbsp; 8.5.2 NoSQL扩展的机制  
&nbsp;&nbsp;&nbsp;&nbsp; 8.5.3 文档数据库的扩展  
&nbsp;&nbsp;&nbsp;&nbsp; 8.5.4 典型NoSQL数据库系统  
	8.5 应用的协同扩展  
&nbsp;&nbsp;&nbsp;&nbsp; 8.5.1 弱一致性的容忍  
&nbsp;&nbsp;&nbsp;&nbsp; 8.5.2 分布式连接的规避  
&nbsp;&nbsp;&nbsp;&nbsp; 8.5.3 分布式事务的规避  
&nbsp;&nbsp;&nbsp;&nbsp; 8.5.4 业务逻辑的扩展  
		
## 第九章 数据分析系统
9.1 BI与OLAP  
&nbsp;&nbsp;&nbsp;&nbsp; 9.1.1 数据仓库  
&nbsp;&nbsp;&nbsp;&nbsp; 9.1.2 多维数据分析  
&nbsp;&nbsp;&nbsp;&nbsp; 9.1.3 BI工具  
	9.2 大数据分析工具链  
&nbsp;&nbsp;&nbsp;&nbsp; 9.2.1 HDFS  
&nbsp;&nbsp;&nbsp;&nbsp; 9.2.2 Hadoop  
&nbsp;&nbsp;&nbsp;&nbsp; 9.2.3 Spark和Flink  
&nbsp;&nbsp;&nbsp;&nbsp; 9.2.4 大数据生态与常见工具  
	9.3 数据分析过程  
&nbsp;&nbsp;&nbsp;&nbsp; 9.3.1 数据的收集与清洗  
&nbsp;&nbsp;&nbsp;&nbsp; 9.3.2 数据探索  
&nbsp;&nbsp;&nbsp;&nbsp; 9.3.3 数据分析系统的构建  
&nbsp;&nbsp;&nbsp;&nbsp; 9.3.4 数据可视化  

## 第十章 权衡
10.1 数据库系统的设计考量  
	10.2 各类系统的对比  
	10.3 更换系统的代价  
	10.4 做出合理的选择  
	10.5 未来的数据管理系统  
 
