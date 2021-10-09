# Class 04 - Data Modeling

[<== Main Page](../README.md)
[<== Code 401](../code401/code401.md)

## Readings

- Name 3 advantages to Test Driven Development

  Modularization, or smaller more manageable code blocks. Developers use TDD so debugging time goes down. Since code blocks are smaller, maintenance is easier. [What are the advantages of test-driven development?](https://fortegrp.com/test-driven-development-benefits/)

- In what case would you need to use beforeEach() or afterEach() in a test suite?

  When you have something that needs to run either before or after each test in the suite. [What is the difference between `before()` and `beforeEach()`?](https://stackoverflow.com/questions/21418580/what-is-the-difference-between-before-and-beforeeach)

- What is one downside of Test Driven Development

  Takes 15-30% longer to develop. See advantages reference link.

- What’s the primary difference between ES6 Classes and Constructor/Prototype Classes?

  "The most important difference between class- and prototype-based inheritance is that a class defines a type which can be instantiated at runtime, whereas a prototype is itself an object instance." [As a JS Developer, This Is What Keeps Me Up at Night](https://www.toptal.com/javascript/es6-class-chaos-keeps-js-developer-up)

- Why REST?

  It is very flexible and can be run with just about any protocol (normally used with HTTP), without having to install libraries or software. [What is a RESTful API?](https://www.mulesoft.com/resources/api/restful-api)
  
## Additional Resources

- [SQL vs NoSQL Database Differences Explained with few Example DB](https://www.thegeekstuff.com/2014/01/sql-vs-nosql-db/?utm_source=tuicool)

- [Keep is Simple: Easy To Understand Data Modeling Concepts](https://www.essentialsql.com/get-ready-to-learn-sql-7-simplified-data-modeling/)

- [Sequelize API](https://sequelize.org/master/)

## Videos

[SQL vs NoSQL vs MySQL vs MongoDB](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y)

## Vocab

- functional programming, software development using functions and logic.

- object-oriented programming (OOP), software development around objects rather than function.

- class, a blueprint for creating an object in javascript.

- super, calls the parents class

- this, complicated. sometimes global, sometimes class. sometimes, function.

- Test Driven Development (TDD), software development cycle where you write test and only write code when tests fail

- Jest, open source javascript testing framework

- Continuous Integration (CI), means merging developers' working branches multiple times a day, so it is small workable chunks rather than one big merge of their work.

- REST, Representational State Transfer, It is very flexible and can be run with just about any protocol (normally used with HTTP), without having to install libraries or software.

- Data Model, organizes elements of data and shows how they relate to each other.

## Bookmark/Skim

- Which 3 things had you heard about previously and now have better clarity on?

- Which 3 things are you hoping to learn more about in the upcoming lecture/demo?

  - Learning a little more about sequelize.
  - 

- What are you most excited about trying to implement or see how it works?

## Things I Want To Know More About

- Class notes

  - create a class collection and don't create CRUD in server.js anymore

- create anew repo from vscode

  - git checkout main
  git pull

  git init
  touch index.js .env
  mkdir __test__ src config 
  cd src ; error-handlers models routes middleware 
  cd error-handlers ; 404.js 500.js ; cd ..
  ls -l
  touch server.js

  cd models
  touch cat.schema.js dog.schema.js

  'use strict'

  const dogs = (sequelize, DataTypes) => sequelize.define('Dogs', {
      name: {
          type: DataTypes.STRING,
          allowNull: false,
      },
      hasAllLimbs: {
          type: DataTypes.BOOLEAN,
          allowNull: false,
      },
      color: {
          type: DataTypes.STRING,
      }
  });

  module.export = dogs;

  const cats = (sequelize, DataTypes) => sequelize.define('Cats', {
      age: {
          type: DataTypes.INTEGER,
          allowNull: false,
      },
      name: {
          type: DataTypes.STRING,
          allowNull: false,
      },
      color: {
          type: DataTypes.STRING,
      }
  });

  module.export = cats;

  // models/index.js
  require('dotenv').config();
  const POSTGRES_URI = process.env.DATABASE_URL;
  let sequelize = process.env.NODE_ENV === 'test' ? new Sequelize('sqlite::memory:') : new Sequelize(POSTGRES_URI);
  const { Sequelize, DataTypes } = require('sequelize');

  // import schemas & collection
  const Collection = require('./lib/collection.js);
  const catSchema = require('./cat.schema.js');
  const dogSchema = require('./dog.schema.js');

  // turn schema into sequelize model
  // instantiate sequelize
  const sequelize = new Schema(DATABASE_URL, sequlizeOptions);
  const catModel = catSchema(sequelize, DataTypes);
  const dogModel = dogSchema(sequelize, DataTypes);
  
  // turns models into collections
  const catCollection = new Collection(catModel);
  const dogCollection = new Collection(dogModel);

  // export
  module.exports = {
      db: sequleize,
      // once create collection.js change to catCollection, dogCollection
      Cat: catModel,
      Dog: dogModel,
};

//routes
//cat.js
'use strict'

const express = require('express');

const { Cat } = require('../models/index.js);
const { Dog } = require('../models/index.js);

const router = express.Router();

// REST route declarations
router.post('/cat', createCat);
router.get('/cat', getACat);
router.get('/cat/:id', getOneCat);
router.put('/cat/:id', updateCat);
router.delete('/cat/:id', deleteCat);

// RESTful Route Handlers
// update with cat stuff

async function getCat (req,res) {
    let cats = await catCollection.read();
    res.status(200).json(cats);
}

async function getOneClothes (req,res) {
    const id = parseInt(req.params.id);
    let theClothes = await Clothes.findOne({ where: { id } });
    res.status(200).json(theClothes);
}

async function createClothes (req,res) {
    let obj = req.body;
    let newClothes = await Clothes.create(obj)
    res.status(200).json(newClothes);
}

async function updateClothes (req,res) {
    const id = parseInt(req.params.id);
    const obj = req.body;
    let clothes = await Clothes.findOne({ where: { id } });
    let updatedClothes = await clothes.update(obj);
    res.status(200).json(updatedClothes);
}

async function deleteClothes (req,res) {
    const id = parseInt(req.params.id);
    let deletedClothes = await Clothes.destroy({ where: { id } });
    res.status(200).json(deletedClothes);
}

module.exports = router;


// do dog REST

// server.js
const express = require('express');
const morgan = require('morgan');

const app = express();

// Error handlers, Routes, and our own modules
const notFoundHandler = require('./error_handlers/404.js');
const errorHandler = require('./error_handlers/500.js');

// const catRoutes = require('./routes/cat.js');
const dogRoutes = require('./routes/dog.js');

// Global Middleware
app.use(morgan('dev')); // This is a 3rd party logger
app.use(express.json());

// Use our routes
// app.use(catRoutes);
app.use(dogRoutes);

// Error handlers -- need to be define last!!
app.use('*', notFoundHandler);
app.use(errorHandler);

// Export an object with the express app and start method
module.exports = {
    server: app,
    start: port => {
        if (!port) { throw new Error('Missing Port'); }
        app.listen(port, () => console.log(`Listening on port ${port}`));
    },
};

make .env with port and db_url

// make a collection class - CRUD handler
mkdir either util or lib
touch collection.js

'use strict'

/** Collection interface, this provides an abstraction for behaviors we expect an APPI data would want to peforem, regardless
**/

class Collection {
    constructor(model) {
        this.model = model;
    }
    async create(json) {
        try {
            let record = await this.model.create(json);

            return record;
        } catch (e) {
            console.error('Error creating data for model : ' + this.model.name);
            return e;
        }
    }

// checking for an id. if id then get 1, if no id, then get all.
    async read(id) {
        let record = null;
        if (id) {
            options['where'] = { id };
            records = await this.model.findOne(options);
        } else {
            records = await this.model.findAll(options);
        }
        return record;
    } catch (e) {
        console.error('Error reading data for model : ' + this.model.name);
        return e;
    }

// 
    async update(id, json) {
        try {
            // throw new Error like next()
            if (!id) throw new Error('No record id prvided : ${this.model.name} ` );
            let record = await this.model.findOne({ where: { id } });
            let updatedRecord = await record.update(json);
            return updatedRecord;
        } catch (e) {
            console.error('Error updating mode : ' this.model.name);
            return e;
        }

    }

    async delete(id) {
        try {
            if (!id) throw new Error('No record id prvided : ${this.model.name} ` );

            let deletedRecord = await this.model.destroy({ where: { id } });
            return deletedRecord;  
        } catch (e) {
            console.error('Error deleting data for model : ' + this model.name);
            return e;
        }
    }
}

module.exports = Collection;

lost track of notes around 8:48 pm. or 2 hrs 18 minutes ish on video. 


## Thursday 10/7
