**01  Create a Database called movies?**
  ``` use movies```

**02  Create a collection called moviedetails ?**
    ```  db.createCollection("moviedetails")
        { ok: 1 }```

 **03 Create above 5 movie documents into a moviedetails collection.**

``` movies> db.moviedetails.insertMany([{title:"jurassic park",type:"Adventure",Director:"steven spielberg",year:1993},{title:"forrest gump",type:"drama",Director:"Robert zemeckies",year:1994},{title:"Titanic",type:"romance",Director:"james cameron",year:1997},{title:"The Dark Knight",type:"Action",Director:"chirstopher nolan",year:2008},{title:"Avatar",type:"science fiction",Director:"james cameron",year:2009}])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("654c817e493d256bb41167de"),
    '1': ObjectId("654c817e493d256bb41167df"),
    '2': ObjectId("654c817e493d256bb41167e0"),
    '3': ObjectId("654c817e493d256bb41167e1"),
    '4': ObjectId("654c817e493d256bb41167e2")
  }
}
```


 **04.List all documents created ?**



``` movies> db.moviedetails.find()
[
  {
    _id: ObjectId("654c817e493d256bb41167de"),
    title: 'jurassic park',
    type: 'Adventure',
    Director: 'steven spielberg',
    year: 1993
  },
  {
    _id: ObjectId("654c817e493d256bb41167df"),
    title: 'forrest gump',
    type: 'drama',
    Director: 'Robert zemeckies',
    year: 1994
  },
  {
    _id: ObjectId("654c817e493d256bb41167e0"),
    title: 'Titanic',
    type: 'romance',
    Director: 'james cameron',
    year: 1997
  },
  {
    _id: ObjectId("654c817e493d256bb41167e1"),
    title: 'The Dark Knight',
    type: 'Action',
    Director: 'chirstopher nolan',
    year: 2008
  },
  {
    _id: ObjectId("654c817e493d256bb41167e2"),
    title: 'Avatar',
    type: 'science fiction',
    Director: 'james cameron',
    year: 2009
  }
]
```

**05. List James Cameron’s movies ?**

```movies> db.moviedetails.find({Director:"james cameron"})
[
  {
    _id: ObjectId("654c817e493d256bb41167e0"),
    title: 'Titanic',
    type: 'romance',
    Director: 'james cameron',
    year: 1997
  },
  {
    _id: ObjectId("654c817e493d256bb41167e2"),
    title: 'Avatar',
    type: 'science fiction',
    Director: 'james cameron',
    year: 2009
  }
]
```




**06.List  James Cameron’s movies released in 2009 ?**


```movies> db.moviedetails.find({year:2009})
[
  {
    _id: ObjectId("654c817e493d256bb41167e2"),
    title: 'Avatar',
    type: 'science fiction',
    Director: 'james cameron',
    year: 2009
  }
]
```
**07.Delete the movie which you don’t like ?**
```movies> db.moviedetails.remove({title:"Titanic",type:"romance",Director:"james cameron",year:1997})
DeprecationWarning: Collection.remove() is deprecated. Use deleteOne, deleteMany, findOneAndDelete, or bulkWrite.
{ acknowledged: true, deletedCount: 1 }
```


**08.Add the movie which is your favourite ?**
```movies> db.moviedetails.insertOne({title:"LEO",type:"Action",Director:"vithushan",year:2023})
{
  acknowledged: true,
  insertedId: ObjectId("654c8dca493d256bb41167e3")
}
```


**09.List movie Directed  by Christopher Nolan in 1994 ?**

```
db.moviedetails.find({Director:"Christopher Nolan"},{year:1994})

```



**10.  List out the Director’s Name in your document. ?**
 ```   movies> db.moviedetails.distinct("Director")
[
  'Robert zemeckies',
  'chirstopher nolan',
  'james cameron',
  'steven spielberg',
  'vithushan'
]
```



