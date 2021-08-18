# Class 11 - Authentication

[<== Main Page](../README.md)
[<== Code 301](../code301/code301.md)

## [What is OAuth? How the open authorization framework works](https://www.csoonline.com/article/3216404/what-is-oauth-how-the-open-authorization-framework-works.html)

- What is OAuth? *"secure, third-party, user-agent, delegated authorization"*

- Give an example of what using OAuth would look like.

  When you could log on to Netlify using your GitHub credentials.

- How does OAuth work? What are the steps that it takes to authenticate the user?

- What is OpenID? Is a SSO application that voouches for the identity of users.

## [Authentication and Authorization Flows](https://auth0.com/docs/flows)

- What is the difference between authorization and authentication?

  Authentication verifies who the user is and authorization verifies what they have access to.

- What is Authorization Code Flow?

  Exchanges an Authorization code for a token on the server side.

- What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?

  Since the Auth code for token can be intercepted, PKCE, uses a transform value (code challenge) to retrieve the auth code.

- What is Implicit Flow with Form Post?

  The app requests token using OpenID Connect.

- What is Client Credentials Flow?

  Use Client ID and Client secret to authenticate machine to machine and receive token.

- What is Device Authorization Flow?

  Uses client ID to start authentication and receive token.

- What is Resource Owner Password Flow?

  Only to be used on trusted applictaions. Username and password provided and stored on backend are exchanged for access token. Use if Authorization Code Flow cannot be used.

## Bookmark/Skim

- [Auth0 React SDK for Single Page Apps](https://auth0.com/docs/libraries/auth0-react)

## Things I Want To Know More About

- Code review from Thursday night

  Make sure once you clone the server repo, you do *npm i* to install *cors, express, axios, dotenv*

- What exactly does axios do? I know it is middleware. Hexx called it the carrier pigeon that carries the data back. Does it actually store data?

- For starter code, just run, then start fixing the errors one by one.

- Learning how to change git remote origin

  git status

  git add .
  git commit -m " "
  git push origin branchname

<!-- copied the git ssh clone from github -->
  git remote set-url origin <git repo> 

<!-- gives status -->
  git remote -v

  git push origin main

---

- Class 11 Notes on Debugging

  axios needs to be installed using npm i
  need to set up PORT on .env, make sure to put in .gitignore

  run code and start with first error and fix it. Then get next error and fix it. See first part video from 8/14/21 to see debugging.

- Lab 11

  Auth0 documentation is amazing. This app is single page React app.
