# Class 08 - Access Control

[<== Main Page](../README.md)
[<== Code 401](../code401/code401.md)

## Readings

- When is Basic Authorization used vs. Bearer Authorization?

- What does the JSON Web Token package do?

- What considerations should we make when creating and storing a SECRET?

## Additional Resources

- [Role Based Access Control](https://www.youtube.com/watch?v=C4NP8Eon3cA)

- [5 steps to simple role-based access control (RBAC)](https://www.csoonline.com/article/3060780/5-steps-to-simple-role-based-access-control.html)

- [Role-based access control](https://en.wikipedia.org/wiki/Role-based_access_control)

## Videos

## Vocab

- encryption

- token

- bearer

- secret

- JSON Web Token

## Bookmark/Skim

Which 3 things had you heard about previously and now have better clarity on?
Which 3 things are you hoping to learn more about in the upcoming lecture/demo?
What are you most excited about trying to implement or see how it works?

## Things I Want To Know More About

- curried functions

- Class notes

  - We have the token, now what? 

    - GET /catCreation, bearerAuth(Users), acl('read'), (req, res) 
    req.headers.authorization = 'Bearer headers.payload.signature'

    - Authorization route
    POST /create, bearerAuth(Users), acl('create'), (req, res) => {}

- serer.js/app.js

- routes.js
  should be modularized

- acl.js or permissions.js is a middleware document
'use strict'

// we are going to want to access [permissions, capabilities of users]

module.exports = (capability) => {
// middleware code runs here
    return (req, res, next) => {
        // we have access to whatever capability is
        //we are expecting bearerAuth has put correct user object in user request
        // inspect users capabilities - does it match what they were saved with
        // if good, pass next()
        // maybe use try catch here?
        // handle rejections and errors
        try {
            console.log(' capability', req.user.capabilities);
            if( req.user.capabilities.includes(capability)) {
                next();
            }
            else {
                next('Access Denied');
            }

        } catch (e) {
            next('Invalid Login');
        }
    }
}


- usermodel.js

const userModel = bottom of 
role: { type: DataTypes.ENUM('user', 'writer', 'editor', 'admin'), defaultValue: 'user' },

capabilities: {
    type: DataTypes.VIRTUAL,
    get() {
        const acl = {
            user: ['read'],
            writer: ['read', 'write'],
            editor: ['read', 'create', 'update'],
            admin: ['read', 'create', 'update', 'delete']
        };
        return acl[this.role];
    }
}


- route for get route
authRouter.get('/create', bearerAuth(Users),  acl('create'), (req, res) => {
  res.status(200).send('you can create');
})

authRouter.get('/read', bearerAuth(Users),  acl('read'), (req, res) => {
    res.status(200).send('you can read');
})

authRouter.get('/update', bearerAuth(Users),  acl('update'), (req, res) => {
    res.status(200).send('you can update');
})

authRouter.get('/delete', bearerAuth(Users),  acl('delete'), (req, res) => {
    res.status(200).send('you can delete');
})


/*
User1 -> { "username":"zork", "password": "bestboi", "role":"admin"}
  - basic em9yazpiZXN0Ym9p
  - bearer 

User2 -> { "username":"lemi", "password": "mowboi", "role":"admin"}
  - basic bGVtaTptb3dib2k=
  - bearer 

User3 -> { "username":"Darek", "password": "zoolander", "role":"writer"}
  - basic RGFyZWs6em9vbGFuZGVy
  - bearer 

User4 -> { "username":"joker", "password": "harley", "role":"editor"}
  - basic am9rZXI6aGFybGV5
  - bearer 

*/

