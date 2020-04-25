# 文档数据库的基本功能

本节介绍文档数据库的功能和使用方法。市面上有不少文档数据库系统，如MongoDB、微软的CosmosDB、亚马逊的DocumentDB等。这些系统的基本功能大同小异，但具体的使用接口有时候会很不一样。由于MongoDB是目前使用得最为广泛的文档数据库系统，本节将它作为范例讲解文档数据库的功能。读者在使用其他文档数据库的时候需查阅相应文档。

数据管理系统最基本的功能是存取数据。文档数据库将数据存取的功能抽象为了创建文档（Create）、读取文档（Read）、更新文档（Update）和删除文档（Delete）四种类型的操作，简称为CRUD操作。在介绍这四种操作之前，我们先了解文档数据库的数据组织体系。

## 文档的组织体系

从上一节的介绍可知，文档数据库将数据组织在一个个的文档中。每个文档通常描述现实世界中的一个实体或对象。为了方便文档的管理，文档数据库还会将相同类型的文档归为一类，放置在同一个**文档集**（Collection）中。然后，属于同一个应用的文档集们又会被放置在同一个**数据库**（Database）中。

换言之，一个文档数据库系统通常会维护多个数据库，每个数据库对应一个应用，为这个应用提供数据管理功能。一个数据库包含了若干文档集，每个文档集用于存放某一类对象的数据；比如，关于人的数据存放在一个文档集中，关于书的数据存放在另一个文档基中。一个文档集又包含了若干文档，每个文档描述了一个对象，比如一个人或一本书。

在使用文档数据库系统时，我们首先需要指定一个数据库作为我们的访问对象。在MongoDB中，我们可以使用下面的指令：

```bson
use myDB
```

这里，我们指定了myDB这个数据库作为访问对象。指定完成后，接下来的指令都会被实施在myDB上。对MongoDB而言，如果myDB这个数据库并不存在，那么这个指令会促使系统创建一个称为myDB的数据库。

当一个数据库刚被创建的时候，它里面没有任何文档集。因此，我们需要创建一些文档集，用于存放文档。人们在使用MongoDB时，一般不会显式地创建文档集，而通常会使用创建文档的指令顺带创建文档集，如下：

```bson
db.myNewCollection.insertOne( { x: 1 } )
```

这个指令实际上是想在文档集myNewCollection中插入一个文档 {x:1}。如果这个myNewCollection文档集并不存在，它将被系统自动创建。这里的db指代我们当前正在使用的数据库，即我们刚才指定的myDB。也就是说，新的文档集myNewCollection将被放置在myDB中。当然，我们也可以使用createCollection指令显示地创建文档集，如下:

```bson
db.createCollection("myBook", {max : 5000} )
```

这个指令要求系统创建一个称为myBook的文档集，并且指定这个文档集最多只能容纳5000个文档。

## 文档的创建

文档数据库系统允许用户创建任意形式的文档，并将它放置在任意一个文档集中。在MongoDB中，我们可以使用insertOne指令将一个新的文档插入到某个文档集中，比如：

```bson
db.person.insertOne( {
  "name": "Jason Chang",
  "birthdate": "Jan 20, 2001",
  "gender": "male",
  "address": "20 Yamaha Street",
  "city": "Beijing"
} )
```

上面这个指令将创建一个关于Jason Chang的文档，并将它插入到称为person的文档集中。前文提到，每一个文档通常有一个ID属性，作为文档的标识。如果在插入文档时用户没有设置这个ID属性，MongoDB将会自动为ID属性赋一个唯一值。

我们还可以使用insertMany指令向一个文档集中一次性插入多个文档，比如：

```bson
db.book.insertMany( [
  {"title":"An Apple Tree", "author":"Steven Tang"},
  {"title":"Home", "author":"Jing Ba"},
  {"title":"Step by Step", "author":"Newton Wei"}
] )
```

这里，我们向文档集book中插入了三个关于书的文档。

## 文档的查询（读取）

假设我们使用下面的命令创建了文档集person，并且往里面插入了两个文档：

```bson
db.person.insertMany([
  {
    "name": "Jason Chang",
    "birthdate": {
      "day":20,
      "month":"Jan",
      "year":2001
    },
    "gender": "male",
    "address": "20 Yamaha Street",
    "city": "Beijing"
  },
  {
    "name": "Jessie Li",
    "birthdate": {
      "day":4,
      "month":"Dec",
      "year":1992
    },
    "gender": "female",
    "address": "200 Sichuan Street",
    "city": "Shanghai"
  }
])
```

MongDB提供find指令，让我们在一个文档集中找到想要的文档，比如：

```bson
db.person.find( {
  "gender": "female",
  "city": "Shanghai"
} )
```

这个指令想要在文档集person中查找gender属性为“female”并且city属性为“Shanghai”的文档，实质上就是和{"gender":"female", "city": "Shanghai"}相匹配的文档。基于文档匹配这种运算方式，我们通常可以这样理解：指令x.find(y)的目的是在x中找到所有的y的匹配。

文档匹配只是一种基本运算。MongoDB在其上增加了很多灵活性，便于用户表达更广泛的需求。以下指令是想找到city属性为“Shanghai”或“Beijing”的文档：

```bson
db.person.find( { "city": { $in: [ "Shanghai", "Beijing" ] } } )
```

同样的目的也可以使用逻辑符号$or来实现：

```bson
db.person.find( { $or: [ { "city": "Shanghai" }, { "city": "Beijing" } ] } )
```

以下指令是要找到在属性birthdate的子属性year上取值大于2000的文档：

```bson
db.person.find( { "birthdate.year": { $gt: 2000 } } )
```

这里的$gt表示“大于”（greater than）。

在不做特殊要求的前提下，find指令将找到所有满足条件的文档，并返回这些文档的所有属性，比如：

```bson
db.person.find( { "gender": "female", "city": "Shanghai" } )
结果为：
{
  "_id": ObjectId("4b2b9f67a1f631733d917a7a"),
  "name": "Jessie Li",
  "birthdate": {
    "day":4,
    "month":"Dec",
    "year":1992
  },
  "gender": "female",
  "address": "200 Sichuan Street",
  "city": "Shanghai"
}
```

很多时候，我们并不需要一个文档的所有属性。find指令可以让我们指定哪些属性是需要被返回的，例如：

```bson
db.person.find( { "gender": "female", "city": "Shanghai" }, { "name": 1, "city": 1 } )
结果为：
{
  "_id": ObjectId("4b2b9f67a1f631733d917a7a"),
  "name": "Jessie Li",
  "city": "Shanghai"
}
```

这里，我们只要求系统返回name和city两个属性。所得到的查询结果就被大大简化了。（ID属性是文档的标识属性。因此，即使不指定，它也会被返回。）

MongoDB的查询指令还有很多功能细节。这里不再赘述。在实际使用时，读者可以查阅MongoDB的[使用手册](https://docs.mongodb.com/manual/)。

## 文档的更新

在MongoDB中，我们使用update指令实现对文档的更新。其中，updateOne用于更新单个文档，updateMany用于更新多个文档。

update指令的参数分为两部分，前一个参数用于指定对什么文档做更新，后一个参数指定更新文档的哪些属性。

```bson
db.person.updateOne(
   { "name": "Jason Chang" },
   {  $set: { "address": "889 Alibaba Street", "city": "Hangzhou" } }
)
```

以上指令首先找到在属性name上取值为“Jason Chang”，然后将这个文档的city属性改为了“Hangzhou”，address属性改为了“889 Alibaba Street”。这里用的具体指令为updateOne，也就是说，如果文档集person中存在两个名叫Jason Chang的人，那么只有其中一个人的文档会被修改。

```bson
db.person.updateMany(
   { "birthdate.year": {$lt: 2000} },
   {  $set: { "group": "adult" } }
)
```

以上指令首先找到在属性birthdate的子属性year上取值小于2000的文档（$lt代表“小于”（less than）），即在2000年之前出生的人，然后将这些人的group属性改为“adult”。这里使用的具体指令为updateMany。因此凡是在2000年之前出生的人，无论多少，都会被更新。有一些被选中的文档可能并没有这个group属性。遇到这种情况，Mongo会自动为这些文档添加group属性，然后再更新它的取值。

## 文档的删除

从一个文档集中删除文档通常使用delete指令。具体指令也分为deleteOne和deleteMany。

```bson
db.person.deleteMany({})
```

以上指令没有指定删除对象的条件，它将把文档集person中的所有文档全部删除。

```bson
db.person.deleteMany( { "name": "Jason Chang" } )
```

以上指令则是将名叫Jason Chang的人从文档集person中删除。由于使用的具体指令为deleteMany，如果有person中包含两个名叫Jason Chang的人，他们都将被删除。

```bson
db.person.deleteOne( { "_id": ObjectId("4b2b9f67a1f631733d917a7a") } )
```

以上指令的目的是将特定ID的文档删除。


以上是对文档数据库CRUD操作的简单介绍。在使用具体系统时，比如MongoDB，读者需要查阅相关文档，从而才能准确掌握CRUD指令的具体使用方法。



[**上一页<<**](chapter2.2.md) | [**>>下一页**](chapter2.4.md)


