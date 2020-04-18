# 文档模型

本书首先进入文档数据库的世界。凡是将文档模型作为数据模型的数据管理系统，我们统称为文档数据库系统。顾名思义，文档模型就是将数据组织成一个个的文档。文档是一个很模糊的概念。文档模型中的“文档”并不是指我们通常看到的文本或文章，而是像下面这样的数据组织方式：

```json
{
  "name": "Jason Chang",
  "birthdate": "Jan 20, 2001",
  "gender": "male",
  "address": "20 Yamaha Street",
  "city": "Beijing"
}
```
```json
{
  "name": "Jessie Li",
  "birthdate": "Dec 4, 1992",
  "gender": "female",
  "address": "200 Sichuan Street",
  "city": "Shanghai"
}
```

熟悉Javascript或者Web编程的朋友很快能反应过来：这不就是JSON（JavaScript Object Notation）描述对象的方式吗？没错。JSON使用的数据模型就是文档模型。我们通常使用一个文档去描述一个实体或对象。在上面的例子中，我们使用了两个文档分别描述Jason Chang和Jessie Li这两个人。每一个文档的内容放在一对花括号“{”、“}”之中。其内容为多个属性的集合。比如，Jason Chang的文档包括了姓名（name）、生日（birthdate）、性别（gender）、住址（address）、城市（city）五个属性。其中，name属性上的取值为“Jason Chang”，birthdate属性上的取值为“Jan 20, 2001”，如此类推。
