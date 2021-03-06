<div align="center">
  <a href="https://github.com/Hamalkari/Koa-REST-API-Boilerplate" title="Koa REST API Boilerplate">
    <img alt="Koa REST API Template" src="https://habrastorage.org/getpro/habr/post_images/3a9/b5c/98c/3a9b5c98c384865ed6f78994cf9c0444.gif" width="240px" />
  </a>
  <br />
  <h1>Koa REST API Boilerplate</h1>
</div>

[![License][license-image]][license-url]
[![NPM version][npm-img]][npm-url]

## Table of contents
* [Todo](#todo)
* [About the project](#about-the-project)
  * [Technologies](#technologies)
* [About file structure](#about-file-structure)
* [Getting started](#getting-started)
* [Env File](#env-file)
* [Scripts](#scripts)
* [Contact](#contact)
* [License](#license)

## Todo
- [x] Change logger to winston
- [x] Add graceful shutdown server 

## About the project

A simple/structured Koa Boilerplate with basic resourses to start make your api. 

Koa REST API Boilerplate is a basic RESTful API Boilerplate build on top of koa framework.

You can use ES6 and high syntax for developing your REST API.

### Technologies
This template use the following technologies:
* Framework [Koa](https://koajs.com/)
* Winston logger [Winston](https://github.com/winstonjs/winston)
* ORM [Objection](https://vincit.github.io/objection.js/) 
* [Babel](https://babeljs.io/) 
* Airbnb config [Eslint](https://eslint.org/) 
* Code formatter [Prettier](https://prettier.io/)

## About file structure
- file **knexfile.js** - our config for database
- file **app.js** - Here we create server and connect to database
- folder **services** - Global services like mail,passport auth, helpers
- file **db/index.js** - Here we create knex with knexfile config
- folder **config** - Here we import .env file, create config vars and export them
- folder **api** - Here we have our main core for api
- folder **api/utils** - for util function
- folder **api/errors** - Here we define our custrom error classes
- folder **api/schema** - Here we define @hapi/joi schema for validation request
- folder **api/middleware** - This folder includes all the API's global middleware like authentication.
- folder **api/components** - Here we have the heart of our component based API. Each component consists of its own routes, controller, model and service. See the example picture of structure below.
- file **api/server.js** - Here we create koa app and use koa middleware and add our routes to the app.
```
📦src
 ┣ 📂api
 ┃ ┣ 📂components
 ┃ ┃ ┗ 📜.gitkeep
 ┃ ┣ 📂errors
 ┃ ┃ ┣ 📜index.js
 ┃ ┃ ┣ 📜internal-server.js
 ┃ ┃ ┣ 📜invalid-request-body-format.js
 ┃ ┃ ┣ 📜not-found.js
 ┃ ┃ ┗ 📜unknown-endpoint.js
 ┃ ┣ 📂middleware
 ┃ ┃ ┣ 📜body-parser.js
 ┃ ┃ ┣ 📜error.js
 ┃ ┃ ┗ 📜schemaValidator.js
 ┃ ┣ 📂schema
 ┃ ┃ ┗ 📜.gitkeep
 ┃ ┣ 📂utils
 ┃ ┃ ┣ 📜logger.js
 ┃ ┃ ┗ 📜response.js
 ┃ ┣ 📜routes.js
 ┃ ┗ 📜server.js
 ┣ 📂config
 ┃ ┗ 📜index.js
 ┣ 📂db
 ┃ ┣ 📂migrations
 ┃ ┃ ┗ 📜.gitkeep
 ┃ ┣ 📂seeds
 ┃ ┃ ┗ 📜.gitkeep
 ┃ ┗ 📜index.js
 ┣ 📂services
 ┃ ┗ 📜.gitkeep
 ┣ 📜app.js
 ┗ 📜knexfile.js
```

Examle for components structure
```
📦components
 ┣ 📂user
 ┃ ┣ 📜user.controller.js
 ┃ ┣ 📜user.model.js
 ┃ ┣ 📜user.route.js
 ┃ ┗ 📜user.service.js
 ┗ 📜.gitkeep
```
## Getting started
[Here](#scripts) you can read about all the scripts in the package.json and their description.

Let's start, you need to do the following instructions:
1. Clone the repo
```sh
git clone https://github.com/Hamalkari/Koa-REST-API-Boilerplate.git
```
2. Install all NPM packages
```sh
npm install
```
3. Install globaly if you don't have knex and nodemon
```sh
npm install -g knex
npm install -g nodemon
```
4. Rename the [.env-example](/.env-example) file to **.env**. How to change .env file you can read below [here](#env-file)
5. Run the server using command:
```sh
npm run dev
```

## Env file
| Key | Value |
|-----|-------|
| NODE_ENV | Environment for your app developing. |
| PORT | Port on which the server starts.|
| LOG_LEVEL | Level of logger such as ('info','debug')|
| DB_DATABASE | Name of your database. |
| DB_USER | Username of your user database. |
| DB_PASSWORD | Password of your user database. | 
| DB_HOST | Host on which database starts. | 
```sh
NODE_ENV='development'
PORT=5000
LOG_LEVEL='debug'


# DATABASE
DB_DATABASE=name
DB_USER=user
DB_PASSWORD=pasword
DB_HOST='localhost'
```

## Scripts
| Command | Description |
|---------|-------------|
|`npm run dev`| Start the server in the NODE_ENV mode.|
|`npm run build`| Build your app. Make folder **build** with all necessary files.|
|`npm run start`| Start your app. Need in production.|
|`npm run format`| Format your code, beatify code.|
|`npm run lint`| Run eslint on your js files.|
|`npm run knex`| Use this script if you want use knex cli.|
|`npm run knex -- migrate:make your_migrate_name`| Create migrate with your name.|
|`npm run migrate` | Update the database migrations.|
|`npm run rollback` | Rollback the last batch of migrations.|
|`npm run seed`|  Run seed files.|


## Contact
**Ivanov Vyacheslav** - kosha.1997@bk.ru,https://vk.com/id143203503

Project Url - https://github.com/Hamalkari/Koa-REST-API-Boilerplate

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

[license-image]: https://img.shields.io/github/license/Hamalkari/Koa-REST-API-Template
[license-url]: ./license
[npm-img]: https://img.shields.io/npm/v/koa
[npm-url]: https://www.npmjs.com/package/koa
