# Class 13 - CRUD

[<== Main Page](../README.md)
[<== Code 301](../code301/code301.md)

## [Which HTTP Status Code to Use for Every CRUD App](https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/)

- In your own words, describe what each group of status code represents:
  
  100’s = These codes give information

  200’s = These codes give success messages
  
  300’s = These codes tell you things have moved

  400’s = These codes tell you that something is wrong with the request you sent to the server

  500’s = These codes tell you something is wrong at the server

- What is a status code 202? This is used with async processes and means that the request was accepted and will finish processing later

- What is a status code 308? This is a permanent redirect

- What code would you use if an update didn’t return data to a client?  204

- What code would you use if a resource used to exist but no longer does? 410 Gone

- What is the ‘Forbidden’ status code? The client has authenticated, but does not have authorization to the resources

## Videos

[Build a RESTful API with Node.js, Express & MongoDB - Quick](https://www.youtube.com/channel/UCFbNIlppjAuEX4znoulh0Cw)

- Why do we need to pull our MongoDB database string out of our server and put it into our .env?

- What is middleware? It acts as a carrier pigeon to move data back and forth between front and back end

- What does app.use(express.json()) do?

- What does the /:id mean in a route?

- What is the difference beween PUT and PATCH? PUT updates the entire resource where PATCH only updates parts of the resources

- How do you make a default value in a schema?

- What does a 500 error status code mean? Internal Server Error

- What is the difference between a status 200 and a status 201? 201 has a location header

## Things I Want To Know More About 

- In class review of my code to go over the Auth0 verification of the user email

  