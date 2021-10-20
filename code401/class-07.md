# Class 07 - Bearer Authorization

[<== Main Page](../README.md)
[<== Code 401](../code401/code401.md)

## Readings

- Write the following steps in the correct order:

  - Make a request to a third-party API endpoint
  - Register your application to get a client_id and client_secret
  - Ask the client if they want to sign in via a third party
  - Redirect to a third party authentication endpoint
  - Receive authorization code
  - Make a request to the access token endpoint
  - Receive access token

- What can you do with an authorization code? Sign in once

- What can you do with an access token? Sign in multiple times

- What’s a benefit of using OAuth instead of your own basic authentication? You can sign in once and have your credentials cached so you do not have to sign in again for a while 
  
## Additional Resources

- [What is JWT? JSON Web Token Explained](https://www.youtube.com/watch?v=926mknSW9Lo)

  - Used to digitally sign data and transfer information between two points

  - Compact
  
  - Self-contained, avoids queriyng DB more than once, by creating a token and passing that as verification that information is cerified

  - Contains header (has algorithm for hash and A part of encoding for JWT), payload (claims with user and and B part of encoding of JWT) and signature (uses header and payload and SHA256 and a secret to encode)

- [Introduction to JSON Web Tokens](https://jwt.io/introduction/)

  - Benefits: less verbose (wordy) than XML and more compact than SAML,  

- [If you can decode JWT, how are they secure?](https://stackoverflow.com/questions/27301557/if-you-can-decode-jwt-how-are-they-secure)

## Videos

## Vocab

[IBM Security Verify Access](https://www.ibm.com/docs/en/sva/10.0.0?topic=pcs-client-secret)

- Client ID, unique id for a client

- Client Secret, password that is used in the signature of JWT

- Authentication Endpoint, place where you can get access tokens, like Auth0

- Access Token Endpoint, where you get access tokens

- API Endpoint, servers that you want to visit

- Authorization Code, good for one use

- Access Token, has all the user data, is signed and verified that the user is who they say they are, and allows the user to not have to sign in a million times

## Bookmark/Skim

[jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken)

- Which 3 things had you heard about previously and now have better clarity on?

- Which 3 things are you hoping to learn more about in the upcoming lecture/demo?

- What are you most excited about trying to implement or see how it works?

## Things I Want To Know More About

- Class notes

- User functionality on user models creating an instance hook (beforeCreate) on the user. if had another instance of admins or cats would not have access to the beforeCreate method because it was not created on those models.

- Bearer authorization (JWT token is created) during sign in. You are who you said you are by providing the username andpassword from when you initially signed up. Basic authenication is created at sign-up.

- bearerToken is middleware, app.use would be to use it everywhere. or just use in routes to just use in certain routes.

- Lab 7

  - ACL for the as a website owner, I want our token system to be as secure as possible...

- Review on Monday

  - 