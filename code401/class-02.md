# Class 02 - Express

[<== Main Page](../README.md)
[<== Code 401](../code401/code401.md)

## Readings

- What’s the difference between PUT and PATCH?

  A PUT request will send all the fields and a PATCH will only send the fields that need to be updated. [Difference Between PUT and PATCH Request](https://www.geeksforgeeks.org/difference-between-put-and-patch-request/)

- Provide links to 3 services or tools that allow you to “mock” an API for development like json-server

  [Mock API Server Online Testing & API Mocking Guide](https://stoplight.io/mock-api-guide/basics/)
  [API Mocking and Virtualization](https://swagger.io/solutions/mocking-and-virtualization/)
  [Mocking API calls with Jest](https://www.loupetestware.com/post/mocking-api-calls-with-jest)

- Compare and contrast Swagger and APIDoc.js [Which tool to choose for API docs — my recommendations](https://idratherbewriting.com/learnapidoc/pubapis_which_tool_to_choose.html) [npm trends](https://www.npmtrends.com/apidoc-vs-apidoc-swagger-vs-swagger) [apiDocjs vs Swagger Inspector](https://stackshare.io/stackups/apidocjs-vs-swagger-inspector)

  I'm thinking APIDOC.js is the better option from these sites.

- Which HTTP status codes should be sent with each type of (un)successful API call?

  100s are Informational
  200s are Successes
  300s are Redirects
  400s are Client Errors
  500s are Server Errors

- Compare and contrast SOAP and ReST [SOAP vs REST. What's the Difference?](https://smartbear.com/blog/soap-vs-rest-whats-the-difference/) 
  
  Representational State Transfer is a set of guidelines that are more flexible and can be used to more easily than SOAP.

  Simple Object Access Protocol is a more complicated protocol and uses XML.
  
## Additional Resources

- [Express Node Introduction](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction)

- [What is NPM?](https://docs.npmjs.com/about-npm)

- [TDD](https://www.agilealliance.org/glossary/tdd/#q=~(infinite~false~filters~(postType~(~'page~'post~'aa_book~'aa_event_session~'aa_experience_report~'aa_glossary~'aa_research_paper~'aa_video)~tags~(~'tdd))~searchTerm~'~sort~false~sortDirection~'asc~page~1))

- [Professional Guides: Continuous Integration Continuous Delivery](https://www.youtube.com/watch?v=xSv_m3KhUO8)

## Videos

## Vocab

- Webserver [What is a web server?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_web_server) 

  Hardware server is a computer that hosts the files needed for other computers to connect to the internet.

  Software server is a computer that controls how the other computers access the internet.

- Express [Express](https://expressjs.com/) 

  Express is a middleware that sort of controls how node features work.

- Routing

- WRRC

## Bookmark/Skim

- Which 3 things had you heard about previously and now have better clarity on?

  - Classes and inheritance


- Which 3 things are you hoping to learn more about in the upcoming lecture/demo?

  - Classes and inheritance
  - NPM

- What are you most excited about trying to implement or see how it works? 
    The mock API tools look kind of interesting.


## Things I Want To Know More About

- Class notes

  - need to work ahead on labs since it seems like they will be unlocked ahead of time.

  Callback is event that does something that returns something. 

- Express routing

  - event driven system
  - `app.get('/thing', (req, res) => {})`
  - this is the same pattern we see in Vanilla JS, jQuery
  - 'When a get event happens in our server, on a "/thing", run this function...'
  - The request Object
  - `(req,..)`
  - /:parameters
  - 



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