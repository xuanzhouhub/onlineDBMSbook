# 查询处理的性能问题

前几个


## 视图的创建

SQL语

```bson
CREATE VIEW <视图名> [（<列名1> [, <列名2>] ...）] 
AS <子查询>
[WITH CHECK OPTION];
```

其中

> [例5.31] 创建男生信息的视图。<br>
> &nbsp;&nbsp;&nbsp;&nbsp;CREATE VIEW M\_Student <br>
> &nbsp;&nbsp;&nbsp;&nbsp;AS<br>
> &nbsp;&nbsp;&nbsp;&nbsp;SELECT Sno, Sname, Age <br>
> &nbsp;&nbsp;&nbsp;&nbsp;FROM Student <br>
> &nbsp;&nbsp;&nbsp;&nbsp;WHERE Gender = '男'; <br>





## 衡量算法性能的通用标准

SQL语言用DROP VIEW命令来删除视图，其基本格式为：



## 查询处理算法的衡量标准





















