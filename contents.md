# 目录

## 第一章 概述（作者：周烜）
__[1.1. 什么是系统](chapter1.1.md)__  
&nbsp;&nbsp;&nbsp;&nbsp; 1.1.1. 系统的定义  
&nbsp;&nbsp;&nbsp;&nbsp; 1.1.2. 一个好系统一定是一个好的模块  
&nbsp;&nbsp;&nbsp;&nbsp; 1.1.3. 折衷  

__[1.2. 什么是数据管理系统](chapter1.2.md)__   
&nbsp;&nbsp;&nbsp;&nbsp; 1.2.1. 关于数据  
&nbsp;&nbsp;&nbsp;&nbsp; 1.2.2. 数据管理功能  
&nbsp;&nbsp;&nbsp;&nbsp; 1.2.3. 数据管理系统的目的  

__[1.3. 数据管理系统的历史](chapter1.3.md)__  
&nbsp;&nbsp;&nbsp;&nbsp; 1.3.1. 从文件系统到关系数据库  
&nbsp;&nbsp;&nbsp;&nbsp; 1.3.2. 数据管理系统的多样化   

__[1.4. 本书的内容安排](chapter1.4.md)__
	
## 第二章 文档数据库（作者：周烜，周欢）
__[2.1. 数据模型] (chapter2.1.md)__  
&nbsp;&nbsp;&nbsp;&nbsp; 2.1.1. 数据的组织方式  
&nbsp;&nbsp;&nbsp;&nbsp; 2.1.2. 数据模型选择

__[2.2. 文档模型] (chapter2.2.md)__  
&nbsp;&nbsp;&nbsp;&nbsp; 2.2.1. 模型的表示  
&nbsp;&nbsp;&nbsp;&nbsp; 2.2.2. 文档的匹配 

__[2.3. 文档数据库的基本功能] (chapter2.3.md)__  
&nbsp;&nbsp;&nbsp;&nbsp; 2.3.1. 文档的组织体系  
&nbsp;&nbsp;&nbsp;&nbsp; 2.3.2. 文档的创建  
&nbsp;&nbsp;&nbsp;&nbsp; 2.3.3. 文档的查询  
&nbsp;&nbsp;&nbsp;&nbsp; 2.3.4. 文档的更新  
&nbsp;&nbsp;&nbsp;&nbsp; 2.3.5. 文档的删除  


__[2.4. 文档数据库的存储结构] (chapter2.4.md)__  
&nbsp;&nbsp;&nbsp;&nbsp; 2.4.1. 存储体系结构  
&nbsp;&nbsp;&nbsp;&nbsp; 2.4.2. 文档的物理组织  
&nbsp;&nbsp;&nbsp;&nbsp; 2.4.3. 文档集的物理组织

__[2.4. 文档数据库的索引] (chapter2.5.md)__  
&nbsp;&nbsp;&nbsp;&nbsp; 2.5.1. B+树结构   
&nbsp;&nbsp;&nbsp;&nbsp; 2.2.2. B+树的插入与删除  
&nbsp;&nbsp;&nbsp;&nbsp; 2.2.3. 索引创建与使用

		
## 第三章 文档数据库设计（作者：周烜，周欢）
__3.1. 软件开发的OO建模__  
&nbsp;&nbsp;&nbsp;&nbsp; 3.1.1. 概念设计  
&nbsp;&nbsp;&nbsp;&nbsp; 3.1.2. 详细设计  
&nbsp;&nbsp;&nbsp;&nbsp; 3.1.3. 对象的持久化  

__3.2. 数据模型与模式__  
&nbsp;&nbsp;&nbsp;&nbsp; 3.2.1. 数据模型  
&nbsp;&nbsp;&nbsp;&nbsp; 3.2.2. 数据库模式  

__3.3. 文档数据库逻辑设计__  
&nbsp;&nbsp;&nbsp;&nbsp; 3.3.1. 从对象到文档  
&nbsp;&nbsp;&nbsp;&nbsp; 3.3.2. 嵌套还是引用  
&nbsp;&nbsp;&nbsp;&nbsp; 3.3.2. 范式化与逆范式化  

__3.4. 文档数据模式物理设计__  
&nbsp;&nbsp;&nbsp;&nbsp; 3.4.1. 辅助索引的创建与使用  
&nbsp;&nbsp;&nbsp;&nbsp; 3.4.2. Read / Write Concerns的选择  
		
## 第四章 关系数据库 （作者：周烜，周欢）
__4.1. 关系数据库的设计理念__  
&nbsp;&nbsp;&nbsp;&nbsp; 4.1.1. 应用逻辑与数据库的分离原则  
&nbsp;&nbsp;&nbsp;&nbsp; 4.1.2. 申明式程序设计语言  

__4.2. 关系模型（指向现有教材）__

__4.3. 关系数据库的存储结构（指向现有教材）__  

__4.4. SQL语言（指向现有教材）__  

__4.5. 查询处理与查询优化（指向现有教材）__  

__4.6. SQL的接口与程序调用方式（指向现有教材）__  
	
## 第五章 关系数据库设计 （作者：周烜，周欢）
__5.1 应用出发的数据库设计方式__  
&nbsp;&nbsp;&nbsp;&nbsp; 5.1.1 对象的持久化需求  
&nbsp;&nbsp;&nbsp;&nbsp; 5.1.2 从对象到关系  
&nbsp;&nbsp;&nbsp;&nbsp; 5.1.3 ORM工具  
&nbsp;&nbsp;&nbsp;&nbsp; 5.1.4 对象与关系的不匹配问题  

__5.2 独立的数据库设计方式__  
&nbsp;&nbsp;&nbsp;&nbsp; 5.2.1 ER模型（指向现有教材）  
&nbsp;&nbsp;&nbsp;&nbsp; 5.2.2 关系范式（指向现有教材）  
&nbsp;&nbsp;&nbsp;&nbsp; 5.2.3 关系模型概念设计（指向现有教材）  

__5.3 关系数据库物理设计__  
&nbsp;&nbsp;&nbsp;&nbsp; 5.3.1 物理模式设计  
&nbsp;&nbsp;&nbsp;&nbsp; 5.3.2 索引的创建与使用（指向现有教材）  
&nbsp;&nbsp;&nbsp;&nbsp; 5.3.3 约束的使用（指向现有教材）  

## 第六章 事务处理 （作者：周烜，周欢）
__6.1 事务的概念__  
&nbsp;&nbsp;&nbsp;&nbsp; 6.1.1 并发与程序正确性要求  
&nbsp;&nbsp;&nbsp;&nbsp; 6.1.2 事务的ACID性质（指向现有教材）  
&nbsp;&nbsp;&nbsp;&nbsp; 6.1.3 隔离级别（指向现有教材）  

__6.2 事务的实现方案__  
&nbsp;&nbsp;&nbsp;&nbsp; 6.2.1 持久化机制（指向现有教材）  
&nbsp;&nbsp;&nbsp;&nbsp; 6.2.2 隔离机制（指向现有教材）  

__6.3 事务的使用方法__  
&nbsp;&nbsp;&nbsp;&nbsp; 6.3.1 隔离级别的选择  
&nbsp;&nbsp;&nbsp;&nbsp; 6.3.2 低效的事务设计  
&nbsp;&nbsp;&nbsp;&nbsp; 6.3.3 事务的拆分与补偿  

__6.4 文档数据库的事务处理__  
&nbsp;&nbsp;&nbsp;&nbsp; 6.4.1 标志位的使用  
&nbsp;&nbsp;&nbsp;&nbsp; 6.4.2 队列的使用  
&nbsp;&nbsp;&nbsp;&nbsp; 6.4.3 案例  

 
## 第七章 权衡 （作者：周烜，周欢）
__10.1 数据库系统的设计考量__  

__10.2 各类系统的对比__  

__10.3 更换系统的代价__  

__10.4 做出合理的选择__  

__10.5 未来的数据管理系统__  
 
