# Class 03 - Express REST API

[<== Main Page](../README.md)
[<== Code 401](../code401/code401.md)

## Readings

- Name 3 real world use cases where you’d want to change the request with custom middleware

  If it did not do what you wanted it to say.

- True or false: The route handler is middleware?

  True.

- In what ways can a middleware function end the process and send data to the browser?

  By placing the route before the middleware, the route will happen before the middleware.

- At what point in the request lifecycle can you “inject” middleware?

  There are three ways to add middleware; globally, before a matched request and using an existing route handler.

- What can cause express to error with “Request headers sent twice, cannot start a second response”
  
## Additional Resources

- [Classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

- [Routing](https://expressjs.com/en/guide/routing.html)

- [Learn to Use the New Router in ExpressJS 4.0](https://scotch.io/tutorials/learn-to-use-the-new-router-in-expressjs-4)

## Videos

## Vocab

- Middleware, Enables applications to connect.

- Request Object, is the entry point for a library or application at a URL.

- Response Object, is the object returned from APIs.

- Application Middleware, provides services specific to that application.

- Routing Middleware, provides services specific just to that route.

- Test Driven Development takes coding, tesing an design to develop code.

- Behavioral Testing tests the internal code and infrastructure of software.

## Bookmark/Skim

- Which 3 things had you heard about previously and now have better clarity on?

- Which 3 things are you hoping to learn more about in the upcoming lecture/demo?

  - TESTING!!!!!!
  - WHy did my dev branch of heroku deployed lab 3 not work, but the main branch did?
  - TESTING!!!!

- What are you most excited about trying to implement or see how it works?

## Things I Want To Know More About

- Class notes

## Setting up Basic Express Server

index.js
'use strict';
// external modules
require('dotenv').config;
// const server = require('./server.js');

server.js
'use strict';

//3rd Party Dependcies (modules)
const express = require('express');

// our own modules
const notFoundHandler = require('./handlers/404.js');
const errHandler = require('./handlers/500.js');
const logger = require('./middleware/logger.js');
const validator = require('./middleware/validate.js');

// instantiate express
const app = express();

// Global Middleware
app.use(logger);
app.use(express.json);

// our own Routes w/ route validator middleware
app.get('/person', validator, (req, res) => {
    const person = {
        name: req.query.name,
    }
    res.status(200).json(person)
})

app.use('*', notFoundHandler);
app.use(errHandler);

module.exports = {
    server:app,
    start: port => {
        if (!port) { throw new Error('Missing Port'); }
        app.listen(port, () => console.log(`Listening on port ${port}`));
    },
};

// Create a GET route

// Create a GET route that uses Query Parameters

// Create a GET route that uses URL Parameters

// Create a POST route

/handlers/404.js

'use strict'

module.exports = (req, res, next) => {

}

npm test

/__test__/server.test.js
'use strict'

const { server } = require('../src/server.js');
const supertest = require('supertest');
const mockRequest = supertest(server);

describe('web server', () => {
  
  it('should respond with a 404 invlaid route', () => {

    return mockRequest
    .get('/foo')
    .then(results => {
        expect (results.status).toBe(404);

        });
    })
  
  it('should respond with a 404 on an invalid method', async () => {
      const response = await mockRequest.get('/foo');
      expect(response.status).toBe(404);
  })

})

/middleware/logger.js
'use strict'
// all middleware has access to the request
// lets simply log out some data

module.exports = (req, res, next) => {
    console.log('Request', req.method, req.path, req.body, req.query);
    next();
}

/middleware/validater.js
'use strict'

module.exports = req, res, next) => {
    console.log('Hello!');
    next();
}

npm jest supertest

package.json
scripts "start": " node index.js"
test


## another 404 handler

function handle404(req, res, next) {
    const errorObject = {
        status: 404,
        message: 'Sorry'
    };
    res.status(404).json(errorObject);
}

## another 500 handler

module.exports = function (err, req, res, next) {
    const error = err.message ? err.message : err;

    const errorObject = {
        status: 500;
        message: error
    };
    res.status()
}

## people.js  for People record
const People = (sequelize, DataType) = sequelize.define('People', {
    firstName: {
        type: DataTypes.STRING,
        allowNull: false,
    },
    lastName: {
        type: DataTypes.STRING,
    }
});

module.exports = People;

## models/index.js

//connect to db depending POSTGRES-URI or DATABASE_URL
const DATABASE_URL = process.env.NODE_ENV === 'test' ? 'sqlite:memory' : process.env.DATABASE_URL;
const { Sequelize, DataTypes } = require('sequelize');

// if i'm not deploying out, i don't care about 
let sequelizeOptions = process.env.NODE_ENV === 'production' ? {
    dialectOptions: {
        ssl: {
            require: true,
            rejectUnauthorized: false,
        }
    }
}
: {};

let sequelize = new Sequelize(DATABASE_URL, sequelizeOptions);

// define schemas/models
const people = require('people.js');

module.exports = {
    db: sequelize,
    People: people(sequleize, DataTypes),
};

## routes
const express = require('express');
const { People } require('../models/people.js);

const route = express.Route();

//RESTful Route Declarations
router.get('/people', getPeople);
router.get('/people/:id', getOnePerson);

//RESTful ROuter Handler also called Route Callbacks
async function getPeople(req, res) {
    let allPeople = await People.findAll();
    res.status(200).json(allPeople);
}

async function getOnePerson(req, res) {
    const id = parseInt(req.params.id);
    let person = await People.findOne({ where:{ id: id } });
    res.status(200).json(person);
}

async function createPerson(req, res) {
    let personData = req.body;
    let person = await People.create(personData);
    res.status(200).json(person);
}

async function updatePerson(req, res) {
    const id = parseInt(req.params.id);
    const personData = req.body;
    let person = await People.findOne({ where: { id: id } });
    let updatedPerson = await person.updated(personData);
    res.status(200).json(updatedPerson);
}

async function deletePerson(req, res) {
    let id parseInt(req.params.id);
    let deletedPerson = await People.destroy({ where: { id: id } });
    res.status(200).json(deletedPerson);
}

module.exports = router;

// put in server.js routes
app.use(personRouter);

## NPM Scripts
mkdir config
touch config.json
has development, production and test enviornments username, pw, db, host address, and dialect variables to spin up testing environments
sqlite will need you to npm

in package.json
scripts

###
.env
DATABASE_URL=postgres://localhost:5432/databasename