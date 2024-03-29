A simple backend repo demonstrating the use of Bcrypt for password salting and hashing + JWT (JSON Web Token) for authentication on protected API calls in an Express.js environment

Connects to a mongodb database and authenticates users via salted and hashed passwords, granting a JWT token via a POST (username and password) to the /login url, then requires said token to be sent via Authorization HTTP header (with structure "Bearer TOKEN" where TOKEN is the result of the login API call) to access the protected API call /data, said call will respond with a JSON body of {"data": "This is a secret message"}

The API also handles logic for rate limiting via `express-rate-limit`

requires a .env file with the following content:

`JWT_SECRET = YOUR_SECRET_KEY`

`MONGO_URI = YOUR_MONGO_URI`

and the following MongoDB structure:

`AuthDB.users -> _id, username, password`
