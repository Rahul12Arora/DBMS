# DBMS
Essential theory concepts of DBMS

<h2>Indexes</h2>


<ul>
  <li>Indexes is a collection of keys from a field in Mongo document that points to the actual document</li>
  <li>We create indexes so that we can easily locate & search documents we need based on the value of that key</li>
  <li>Since we have a separate collection of keys as indexes, we can perform operations like binary search after sorting the index collection</li>
  <li>that gives us the advantage of not going through the whole collection in order to find the documents that we need based of that key</li>
  <li>Disadvantage of keys is that it creates overhead & when a new document is added the index collection also needs to be updated</li>
</ul>

<h3>Create Index</h3>

```
db.getCollection("materialmasters").createIndex({isActive:1})
```

<h3>View Index</h3>

```
db.getCollection("leads").getIndexes()
```

<h3>Unique Index</h3>

```
db.books.createIndex({ isActive: 1 }, { unique: true })
```

**If you attempt to create a unique index on the "isActive" field with db.books.createIndex({ isActive: 1 }, { unique: true }), MongoDB will reject this index creation because there are two documents with the same "isActive" value ("true"). Unique indexes require that the indexed field's values be unique across the entire collection.**
