# Class 06 - Authentication

[<== Main Page](../README.md)
[<== Code 401](../code401/code401.md)

## Readings

- Explain what a “Singleton” is (in Computer Science terms)
 Only has one instance of the pattern.

- Explain how the Singleton pattern can be used with Node modules, specifically with classes

- If you were tasked with building a middleware system like Express uses, what approach might you take to construct/operate it?
  
## Additional Resources

- [Securing Passwords with Bcrypt Hashing Function](https://thehackernews.com/2014/04/securing-passwords-with-bcrypt-hashing.html)

- [Basic access authentication](https://en.wikipedia.org/wiki/Basic_access_authentication)

- [Authentication Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)

- [node.bcrypt.js](https://www.npmjs.com/package/bcrypt)

## Videos

## Vocab

- Router Middleware
  Middleware used by router 

- Dynamic Module Loading
  
- Singleton Pattern
  Node with only one next pointer

- CRUD -> REST Method Matches
  - CREATE / POST
  - READ / GET
  - UPDATE / PUT
  - DELETE / DELETE

- Mock Testing
  Creating a simulated app, database or server, then teatsing routes and methods.

## Bookmark/Skim

Which 3 things had you heard about previously and now have better clarity on?
Which 3 things are you hoping to learn more about in the upcoming lecture/demo?
What are you most excited about trying to implement or see how it works?

## Things I Want To Know More About

- Class notes

  - WRRC Auth API land

    - Sign up POST route Username/PW client req to server gets encoded then hashed in app.post. Stored in body
    - Sign in POST route username/pw client req to server gets encoded (http symbols taken out) then hashed in app.post. Stored in params.authorization

lab 
- npm i base64
npm i bcrypt

app.js
'use strict'

const express = require('express');
let base64 = require('base-64');
let bcrypt = require('brcrpt');
const { Sequelize, DataTypes } = require('sequelize');

const app = express();

const sequelize = new Sequelize('postgres://localhost:5432/auht_demo');

// make sure to create db in terminal

app.use(express.json());

//create sequelize model

const Users = sequelize.define('User', {
    username: {
        type: DataType.STRING,
        allowNull: false,
    },
    password: {
        type: DataTypes.STRING,
        allowNull: false,
    }
});

app.post('/register', async (req, res) => {
    // res.status(200).send('hello world');


})
