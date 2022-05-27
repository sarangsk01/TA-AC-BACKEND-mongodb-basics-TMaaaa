writeCode

Write code to:-

- create a database named `mountains`
  > use mountains
- a collection inside that database named `himalayas`
- insert 1 document into that collection `{name: 'Dhauldhar range', height: '4000 mtrs'}`
  > mountains> db.himalayas.insert({name: 'Dhauldhar range', height: '4000 mtrs'})
- insert multiple document using insertMany command
  > mountains> db.himalayas.insertMany([{name: 'Dhauldhar range', height: '4000 mtrs'},{name: 'Dhauldhar range', height: '4000 mtrs'}])
- find all documents from mountains
  > mountains> db.himalayas.find()
- find a single document using name
  > mountains> db.himalayas.findOne({name:'Dhauldhar range'})
