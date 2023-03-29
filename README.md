# router-level-middleware

Using the structure given by ExpressJS “Hello World”, you will have to secure the main page: 

```const express = require('express')
const app = express()
const port = 3000
  
app.get('/', (req, res) => res.send('Hello World!'))
  
app.listen(port, () => console.log(`Example app listening at http://localhost:${port}`))
```

# The aim of this exercise is to create a routing middleware that inspects the param in your URL and if there is a token. 

 

Steps: 
- Create a server.js with the Express application. 
- Create a function secure() that needs to apply on a GET route ‘/verify/:token’ (app.get()). 
- Inside the secure function, inspect if there is a param with the name token and a value
- If the token has a value and is longer than 3 characters, continue (i.e. send the message ‘Hello World!’).
- Create a route to manage the case when the token doesn’t exist and send back a response with the HTTP code 403.  
 

# Additional steps
- Create a new database
- Create a new table called token that has an id and a value (type : text) 
- Create a new table called users that has some properties that you can decide. It must have a reference to the id of the token table
-  Insert some users 
- In your NodeJs Server, create routes to :
  - Create a user
  - Create a token for a specific user
  - Create a route GET on endpoint /verify/:token. 
  - The process must :
    - Check if the token is available in the database
    - Check if the token is available on a user
    - if the user is linked to this token –> res.send(“token valid”);
if the token doesn’t exist or no user is linked to that –> res.status(401).send(“invalid token”);
