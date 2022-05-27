writeCode

Write code to:-

- create a database named `sports`.
  > use sports
- list all databases present in local mongod server.
  > show dbs
- create 3 collections named `cricket`, `football`, `TT` in sports databse.
  > db.createCollection('cricket')
  > db.createCollection('football')
  > db.createCollection('TT')
- add multiple players in those collections which should have fields like `name`, `age` and `email` and `bid_price`.
  > db.cricket.insertMany([{"player1":"Sachin","name":"Sachin","age":38,"email":"sachin1@gmail.com","bid_price":200}, {"player2":"Virat","name":"Virat","age":30,"email":"abc","bid_price":200}])
  > db.football.insertMany([{"player1":"Sachin","name":"Sachin","age":38,"email":"sachin1@gmail.com","bid_price":200}, {"player2":"Virat","name":"Virat","age":30,"email":"abc","bid_price":200}])
  > db.TT.insertMany([{"player1":"Sachin","name":"Sachin","age":38,"email":"sachin1@gmail.com","bid_price":200}, {"player2":"Virat","name":"Virat","age":30,"email":"abc","bid_price":200}])
- list all collections in sports database.
  > show collections
- rename `TT` collection to `tennis`.

  > db.TT.renameCollection('tennis')

- create a capped collection called `khokho` which should have max 3 documents.

  > db.createCollection('khokho',{capped:true,size:1024,max:3})

  Try inserting more than 3 and see what happens?

  > db.khokho.insertMany([{delhi:32},{mumbai:23},{pune:24},{nagpur:12}])

- check whether a collection is capped or not?
  > db.khokho.isCapped()
  > true
- drop all documents from `football` collection.

  > db.football.drop()
  > true

- delete cricket collection completely.

  > db.cricket.drop()
  > true

- delete sports database.

  > db.cricket.drop()
  > true

- check which database you are connected to ?
  > sports
- connect to test database
  > use test
  > 'switched to db test'
