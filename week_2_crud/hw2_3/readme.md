# Homework 2.3

## Homework: Homework 2.3 (Manual Validation Version)

Download and uncompress the folder.

`cd hw2_3`

"You should see four files in the 'blog' directory: app.js, users.js, posts.js and sessions.js. There is also a 'views' directory which contains the templates for the project and a 'routes' directory which contains our express routes."

"We have removed parts of the code that uses the Node.js driver to query MongoDB from users.js and marked the area where you need to work with "TODO: hw2.3". You should not need to touch any other code. The database calls that you are going to add will add a new user upon sign-up and validate a login by retrieving the right user document."


Install dependency and run `app.js`

```
cd blog
npm install
node app.js
```

The changes that we implemented are in the file [users.js](blog/users.js)

```
this.addUser = function(username, password, email, callback) {
...
// TODO: hw2.3
  //callback(Error("addUser Not Yet Implemented!"), null);
  users.insert(user,function(err,inserted){
    if(err)return callback(err, null);
    callback(null, user);
  });
```

```
this.validateLogin = function(username, password, callback) {
...
// TODO: hw2.3
  //callback(Error("validateLogin Not Yet Implemented!"), null);
  users.findOne({_id: username}, function(err, user){
    if(err) return callback(err, null);
    callback(null, user);
  });
```

## Answer

With the `app.js` running

Run in other console the  `validate.js` script
```
cd validate
npm install
node validate.js
Successfully created user
Successfully logged out
Successfully logged in
Blog validated successfully!
Your validation code is: A7foYWqTpKqRftI2d1D8
```

