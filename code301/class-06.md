# Class 06 - NODE.JS

[<== Main Page](../README.md)
[<== Code 301](../code301/code301.md)

## [What Is Node and When Should I Use It?](https://www.sitepoint.com/an-introduction-to-node-js/)

- What is node.js?
  A JavaScript runtime 

- In your own words, what is Chrome’s V8 JavaScript Engine?
  It compiles into the language that your computer can read.

- What does it mean that node is a JavaScript runtime?
  So it uses the browser to run, but it's not not executing programs in the browser. It is going out to the APIs source and running the application there.

- What is npm?
  Node package manager

- What version of node are you running on your machine?
  v12.20.0

- What version of npm are you running on your machine?
  6.14.8

- What command would you type to install a library/package called ‘jshint’?
  npm install -g jshint

- What is node used for?
  Node runs tools to automate the development of JS applications

## [6 Reasons for Pair Programming](https://www.codefellows.org/blog/6-reasons-for-pair-programming/)

- What are the 6 reasons for pair programming?
  Greater efficiency, engaged collaboration, learn from fellow students, social skills, job interview readiness and work environment readiness

- In your experience, which of these reasons have you found most beneficial?
  Work environment readiness because it prepares you for the job you would work in.

- How does pair programming work?

## Bookmark/Skim

- [Blazing fast Location APIs](https://locationiq.com/)

- [axios](https://www.npmjs.com/package/axios)

- [Making asynchronous programming easier with async and await](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await)

## Things I Want To Know More About About

- Web Request RC

  Front End Client side sends request to Pokemon server (method get)
  Back End Receives response (status with body) from axios
  Second request sent to locationIQ API (method get)
  Receives response (status with body)

- Use the docs on the API site for information

- Writing asynchronous code chosing to use axios and async / await
  import axios from 'axios';

  getPokemon = async () => {
    let pokemonResults = await axios.get('https://pokeapi.co/api/v2/pokemon');
    //wittle in and prove that you can get the data you want with the console logs, proof of llife
    console.log(pokemonResults.data.results);
    this.setState({
      pokemons: pokemonResults.data.results,
      displayPokemon: true,
    })
  }
