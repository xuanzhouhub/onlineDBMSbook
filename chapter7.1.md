# 查询处理概述

前几个小节


## 关系数据库的基本框架

SQL语言用CREATE VIEW命令来创建视图，其基本格式如下：

```bson
CREATE VIEW <视图名> [（<列名1> [, <列名2>] ...）] 
AS <子查询>
[WITH CHECK OPTION];
```

其中子

> [例5.31] 创建男生信息的视图。<br>
> &nbsp;&nbsp;&nbsp;&nbsp;CREATE VIEW M\_Student <br>
> &nbsp;&nbsp;&nbsp;&nbsp;AS<br>
> &nbsp;&nbsp;&nbsp;&nbsp;SELECT Sno, Sname, Age <br>
> &nbsp;&nbsp;&nbsp;&nbsp;FROM Student <br>
> &nbsp;&nbsp;&nbsp;&nbsp;WHERE Gender = '男'; <br>


## 查询处理步骤


## 示例

























