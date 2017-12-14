[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# ALCWithMicrosoft
Assessment Solution for the ALC with Microsoft program.

This repository contains a simple demo API built with NodeJS.
The API is used to manage users in a MongoDB database.

### Development
This application was developed using [ExpressJS](http://expressjs.com/). MongoDB was used for persisting data with [Mongoose](https://mongoosejs.com/) as [ORM](https://en.wikipedia.org/wiki/Object-relational_mapping).

### Starting the Application with Docker Compose
1. Install Docker for Windows or Docker for Mac (If you're on Windows 7 install Docker Toolbox: http://docker.com/toolbox).

2. Open a command prompt at the root of the application's folder.

3. Run `docker-compose build`

4. Run `docker-compose up`

5. Navigate to http://localhost:3000 (http://192.168.99.100:3000 if using Docker Toolbox) in your browser to view the site. This assumes that's the IP assigned to VirtualBox - change if needed.

### API Documentation
The API only has one endpoint which is the `/users` endpoint for saving users to the database. The endpoint works with the HTTP verbs: `POST`, `GET`, `PUT`, `DELETE`.

###### POST HTTP Request
-   `POST` /users
-   INPUT:
```x-form-url-encoded
name: John Doe
email: john.doe@gmail.com
password: johndoe
```

###### HTTP Response

-   HTTP Status: `201: created`
-   JSON data
```json
{
  "_id": "59071791b0lkscm2325794",
  "name": "John Doe",
  "email": "john.doe@gmail.com",
  "password": "johndoe",
  "__v": 0
}
```

###### GET HTTP Response
-   `GET` /users

```json
[
    {
        "_id": "59071791b0lkscm2325794",
        "name": "John Doe",
        "email": "john.doe@gmail.com",
        "password": "johndoe",
        "__v": 0
    }
]
```

###### GET HTTP Response
-   `GET` /users/:id

```json
{
    "_id": "59071791b0lkscm2325794",
    "name": "John Doe",
    "email": "john.doe@gmail.com",
    "password": "johndoe",
    "__v": 0
}
```

###### DELETE HTTP Response
-   `DELETE` /users/:id

```json
User John Doe was deleted
```

###### POST HTTP Request
-   `PUT` /users/:id
-   INPUT:
```x-form-url-encoded
name: Jane Doe
email: jane.doe@gmail.com
password: janedoe
```

###### HTTP Response

-   HTTP Status: `200: OK`
-   JSON data
```json
{
  "_id": "59071791b0lkscm2325794",
  "name": "Jane Doe",
  "email": "jane.doe@gmail.com",
  "password": "janedoe",
  "__v": 0
}
```
