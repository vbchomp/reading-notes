# Class 01 - Node Ecosystem, TDD, CI/CD

[<== Main Page](../README.md)
[<== Code 401](../code401/code401.md)

## Readings

- Describe (in plain English) what Array.map() does

  Mapping over an array will take each item in the array and evaluate it against criteria, then create a new array with results that evaluated true from original array. For example - the first array has 2, 4, 6 and you want to double each number. Second array would be 4, 8, 12. And the first array would be unchanged.

- Describe (in plain English) what Array.reduce() does

  Reduce gives you back a single value eacah time it is called. If it is used for a sum, it will give you the sum of two numbers. 

- Provide code snippets showing how to use superagent() to fetch data from a URL and log the result

[5 ways to make HTTP requests in Node.js](https://blog.logrocket.com/5-ways-to-make-http-requests-in-node-js/)

```javascript

const superagent = require('superagent');

(async () => {
  try {
    const res = await superagent.get('https://jsonplaceholder.typicode.com/users');
    const headerDate = res.headers && res.headers.date ? res.headers.date : 'no response date';
    console.log('Status Code:', res.statusCode);
    console.log('Date in Response header:', headerDate);

    const users = res.body;
    for(user of users) {
      console.log(`Got user with id: ${user.id}, name: ${user.name}`);
    }
  } catch (err) {
    console.log(err.message); //can be console.error
  }
})();

```

- With normal Promise .then() syntax

```javascript

  .then(res => {
    const headerDate = res.headers && res.headers.date ? res.headers.date : 'no response date';
    console.log('Status Code:', res.statusCode);
    console.log('Date in Response header:', headerDate);

```

- Again with async / await syntax

```javascript

  (async () => {
    try {
      const res = await fetch('https://jsonplaceholder.typicode.com/users');
      const headerDate = res.headers && res.headers.get('date') ? res.headers.get('date') : 'no response date';
      console.log('Status Code:', res.status);
      console.log('Date in Response header:', headerDate);

```

- Explain promises as though you were mentoring a Code 301 level student

  Promises tell the stack that there is is another task that needs to be done. It does not matter how long the task takes to get done. But when the task is done, please send it back to me and I can deal with the results.

- Are all callback functions considered to be Asynchronous? Why or Why Not?

  No. Some are blocking or synchronous and only exceute during the exceution of a higher-order function that uses the call back. [Everything About Callback Functions in JavaScript](https://dmitripavlutin.com/javascript-callback/)
  
## Additional Resources

## Videos

## Bookmark/Skim

## Things I Want To Know More About

- Class notes

- Node JS

// person.js

const person = {};

person.walk = function() {
    return 'walkin';
}

module.exports = person;

another module can import and use that function or object

const human = 

- don't upload your node_modules to github. put in dotenv