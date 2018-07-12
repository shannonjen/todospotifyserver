# Todo API with Spotify

## Deploying to Heroku

1. Specify node version in package.json
```
"engines": {
    "node": "8.8.1"
  }
```
2. Install dotenv
```bash
$ npm instal dotenv
```
3. Add .env file to project root and add environment variables
```
CLIENT_ID = <your client id here>
CLIENT_SECRET = <your client secret here>
```
4. Configure process object and update client variables in app.js
```
require('dotenv').config

var client_id = process.env.CLIENT_ID;
var client_secret = process.env.CLIENT_SECRET;
```
5. Add heroku production script to package.json
```
"heroku-postbuild": "npm install --production"
```
6. Log into heroku via heroku CLI
```
$ heroku login
```
7. Create heroku app
```
$ heroku create
```
8. Commit changes and push to heroku
```
$ git add .
$ git commit -m "Configure for Heroku"
$ git push heroku master
```
9. Set up database
```
$ heroku addons:create heroku-postgresql:hobby-dev
```
10. Run migrations
```
$ heroku run knex migrate:latest
```
11. Run seeds
```
$ heroku run knex seed:run
```
