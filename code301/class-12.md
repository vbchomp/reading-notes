# Class 11 - Authentication

[<== Main Page](../README.md)
[<== Code 301](../code301/code301.md)

## [SQL vs NoSQL Database Differences Explained with few Example DB](https://www.thegeekstuff.com/2014/01/sql-vs-nosql-db/?utm_source=tuicool)

- 5 differences between SQL and NoSQL DBs

SQL vs NoSQL
  SQL DBs are relational and NoSQL are non-relational
  SQL DBs are table based and NoSQL are document based key:value pairs
  SQL DBS have a pre-defined schema and NoSQL had dynamic schema
  SQL DBs use SQL to manipulate data and NoSQL uses UnQL
  SQL DBs are scaled by increasing hardware hp and NoSQL is scaled by increasing the database servers in the pool of resources

- What kind of data is a good fit for an SQL database?

  Complex queries

- Give a real world example.

  Store sales transactions

- What kind of data is a good fit a NoSQL database?

  Hierarchical data storage

- Give a real world example.

  JSON

- Which type of database is best for hierarchical data storage?

  NoSQL

- Which type of database is best for scalability?

  SQL databases

## Videos 

- [SQL vs NoSQL or MySQL vs MongoDB](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y)

- What does SQL stand for? Structured Query Language

- What is a realational database?

- What type of structure does a relational database work with?

- What is a ‘schema’?

- What is a NoSQL database?

- How does it work?

- What is inside of a Mongo database?

- Which is more flexible - SQL or MongoDB? and why.

- What is the disadvantage of a NoSQL database?

## Things I Want To Know More About

- touch server.js

  npm i mongoose express cors dotenv
  all other stuff
  const mongoose = require('mongoose');

  const bookSchema = new mongoose.Schema({
    title: {type: String, required: true},
    author: {type: String},
  })

  const BookModel = mongoose.model('books', bookSchema);

  app.get('/books', (request, response) => {
    try{
      let booksdb = await BookModel.find({});
      response.status(200).send(booksdb);
    }
    catch (err) {
      response.status(500).send('dbase err');
    }
  })

  make folder in vscode called db
  in terminal type
  *mongod --dbpath db*




// start the db
// terminal ipAddress = 127.0.0.1 port 27017
// connect to the db
// mongoose.connect('mogodb://127.0.0.1:27017/books',{
//   useNewUrlParser: true,
//   useUnifiedTopology: true
// })
// .then(() => {
//   console.log('Connnected to the database');
     
     // Not normally the best place to put this. but for demonstration it is ok here.
     let newBook = await BookModel.find({});
     if (books.length === 0) {
       await addBook({
         title: "New Book",
         author: "Awesome Author"
       });
     }  

     await newBook.save(); -->

// listen to the port
//   app.listen(3001, () => {
//     console.log('Server up on 3001');
//   });
// });

async function addBook(obj){
  let newBook = new BookModel(obj);
  return await newBook.save();
}

// clears database
async function clear() {
  try{
    await BookModel.deleteMany({});
    console.log('Bombed the DBase');

  }
  catch(err){
    console.log('Error in clearing database');
  }
}
