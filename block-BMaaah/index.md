writeCode

Write code to execute below expressions.

1. Create a database named `blog`.
   > use blog
2. Create a collection called 'articles'.
   > blog> db.createCollection('articles')
3. Insert multiple documents(at least 3) into articles. It should have fields
   >

- title as string
- createdAt as date
- details as String
- author as nested object
  - author should have
    - name
    - email
    - age
    - example author: {name: 'abc', email: 'abc@gmail', age: 25}
- tags : Array of strings like ['html', 'css']

```js
// An article should look like in the database
{
  _id: 'some_random_id',
  title: '',
  details: '',
  author: {
    name: '',
    email: '',
    age: ''
  },
  tags: ['js', 'mongo']
}
```

```js
>
db.articles.insertMany(documents);
  var documents = [
  {
    _id: 'abc',
    title: 'abc1',
    createdAt: "27 May 2022",
    details: 'sdfjlj',
    author: {
      name:'abc',
      email: 'abc@gmail.com',
      age: 22
    },
    tags: ['cricket', 'football']
  },
  {
    _id: 'xyz',
    title: 'xyz1',
    createdAt: "26 May 2022",
    details: 'sdfjlkjlkf',
    author: {
      name:'xyz',
      email: 'xyz@gmail.com',
      age: 21
    },
    tags: ['html', 'css']
  },
  {
    _id: 'lmn',
    title: 'lmn1',
    createdAt: "25 May 2022",
    details: 'sdjfklnlksnfl',
    author: {
      name:'lmn',
      email: 'lmn@gmail.com',
      age: 20
    },
    tags: ['java', 'php']
  },

]


```

4. Find all the articles using `db.COLLECTION_NAME.find()`
   > db.articles.find()
5. Find a document using \_id field.
   > test> db.articles.find({\_id:'lmn'})
6. 1. Find documents using title
      > db.articles.find({title:'lmn1'})
7. 2. Find documents using author's name field.
      db.articles.find({name:'lmn'})
8. Find document using a specific tag.
   db.articles.find({details:{exists:false}})
9. Update title of a document using its \_id field.
   > db.articles.update({\_id:'lmn'},{$set:{title:'lmn2'}})
10. Update a author's name using article's title.

    > db.articles.update({title:'lmn2'},{$set:{name:'lmnop'}})

11. rename details field to description from all articles in articles collection.
    > db.details.renameCollection("description");
12. Add additional tag in a specific document.
    > db.articles.update({title:'lmn2'},{$push:{weight:50}})
13. Update an article's title using $set and without $set.
    > db.articles.update({age:21},{$set:{title:'xyz2'}})
    > db.articles.update({age:21},{title:'xyz2'})

- Write the differences here ?
  in the $set example we update field title.but in 2nd example we don't use $set then title is added in documents and all other fields is deleted.

13. find an article using title and increment it's auhtor's age by 5.
    > db.articles.update({title:'xyz2'},{$set:{age:26}})
14. Delete a document using \_id field with `db.COLLECTION_NAME.remove()`.
    > db.articles.remove({\_id:'lmnop})
    > // Sample data

```js
db.users.insertMany([
  {
    age: 49,
    name: 'Maurice Brock',
    email: 'wuk@hibpiz.ch',
    gender: 'Female',
    sports: ['cricket', 'football'],
    scores: [24, 35, 18, 16],
    weight: 45,
  },
  {
    age: 37,
    birthday: '7/15/1986',
    name: 'Virgie Cunningham',
    email: 'ezogafa@de.gm',
    gender: 'Male',
    sports: ['football'],
    scores: [17, 35, 43],
    weight: 52,
  },
  {
    age: 48,
    birthday: '5/14/1961',
    name: 'Alexander Holt',
    email: 'han@mu.pe',
    gender: 'Male',
    sports: ['cricket', 'football', 'TT'],
    scores: [24, 30, 16],
    weight: 55,
  },
  {
    age: 53,
    birthday: '11/15/1963',
    name: 'Derek Dawson',
    email: 'polril@now.de',
    gender: 'Male',
    sports: ['cricket', 'hockey'],
    scores: [20, 15, 38, 23],
    weight: 49,
  },
  {
    age: 34,
    birthday: '7/24/1964',
    name: 'Cynthia Cobb',
    email: 'wujjarpob@jecimpar.gu',
    gender: 'Female',
    sports: ['cricket'],
    scores: [41, 17, 28],
    weight: 51,
  },
  {
    age: 33,
    birthday: '10/26/1982',
    name: 'Isabella Atkins',
    email: 'ononuzas@givhoz.ca',
    gender: 'Female',
    sports: ['cricket', 'football', 'hockey', 'TT'],
    scores: [14, 38, 29, 45, 20],
    weight: 49,
  },
  {
    age: 47,
    birthday: '10/12/1978',
    name: 'Katharine Bryan',
    email: 'zo@pebi.sa',
    gender: 'Male',
    sports: ['TT', 'hockey', 'khokho'],
    scores: [27, 20, 34],
    weight: 58,
  },
  {
    age: 41,
    birthday: '1/28/1991',
    name: 'Beatrice Fleming',
    email: 'ufufsa@pujizren.tk',
    gender: 'Female',
    sports: ['football', 'khokho'],
    scores: [30, 20, 15, 29, 43],
    weight: 47,
  },
  {
    age: 26,
    birthday: '3/23/1998',
    name: 'Tom Fields',
    email: 'wasodjow@ofaba.gf',
    gender: 'Female',
    sports: ['khokho'],
    scores: [37, 29, 18, 43, 49],
    weight: 50,
  },
  {
    age: 33,
    birthday: '11/14/1960',
    name: 'Steve Ortega',
    email: 'dupus@ca.ls',
    gender: 'Female',
    sports: ['cricket', 'football', 'hockey'],
    scores: [12, 15, 20],
    weight: 51,
  },
  {
    age: 24,
    birthday: '1/5/1994',
    name: 'Suraj Kumar',
    weight: 50,
    gender: 'Male',
    sports: ['football', 'cricket', 'TT'],
  },
]);
```

Insert above data into database to perform below queries:-

- Find all males who play cricket.
  > db.users.find({gender:'Male',sports:'cricket'})
- Update user with extra golf field in sports array whose name is "Steve Ortega".
- Find all users who play either 'football' or 'cricket'.
- Find all users whose name includes 'ri' in their name.
