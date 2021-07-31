# Class 07 - REST

[<== Main Page](../README.md)
[<== Code 301](../code301/code301.md)

## [What Google Learned From Its Quest to Build the Perfect Team](https://www.nytimes.com/2016/02/28/magazine/what-google-learned-from-its-quest-to-build-the-perfect-team.html)

## [How I Explained REST to my Brother](https://gist.github.com/brookr/5977550)

- Who is Roy Fielding? *He helped write the first web servers.*

- Why don’t the techniques that we use today work well when we need to be able to talk to all of the machines in the world? *Because we do not need to talk to all the worlds machines any more, just a small group.*

- What is the HTTP protocol that Fielding and his friends created? *Applies verbs to nouns so that you type an action word and you receive a thing back*

- What does a GET do? *Retrieve information from another system*

- What does a POST do? *Adding something to another system*

- What does PUT do? *Places something in another system*

- What does PATCH do? *A partial update*

## API Keys

- [Geocoding API](https://locationiq.com/)

  Yes, I have my API key.

- [Weather Bit API](https://www.weatherbit.io/)

  Yes, I have my key.

- [Yelp API Docs](https://www.yelp.com/developers/documentation/v3/business_search)

  Yes, I have my key.

- [The Movie DB API Docs](https://developers.themoviedb.org/3/getting-started/introduction)

  Yes, I have my key.

## Things I Want To Know More About

Create a server - normally create on github and clone down.

*npm init*  --installs dependcies

installs a package.json

*touch server.js* --to create server page

--server.js in vscode
'use strict';

console.log('Wazzup!');

--on terminal *npm start* will run server. Should display console.log.

npm i express

--back in vscode

```render-javascript

//in our servers we must use require instead of import.
const express = require('express');

//this is how it is done per the docs.
const app = express();

//specifying what routes our server should be listening for.
app.get('/', (request, response) => {
  // when we get the request we send back the following results
  response.send('Hello, from the outside');
});

app.get('/banana', (request, response) => {
  //when we get that request, we send the following results
  response.send('mmmm, bananas!');
});

//query parameters allow us to send extra information to the backend
//accessed with url created.
app.get('/sayHello', (request, response) => {
  //can access query parameters using request.query
  let name = request.query.name;
  response.send(`Hello, ${name}.`);
});

//if I am getting to catch all other resuests. that catch all must be the last route.
app.get('/*', (request, response) => {
  response.status(404).send('Soemthing went wrong');
});

// tell our server to start listening for requests
app.listen(3001, () => console.log('listening on port 3001'));
```
