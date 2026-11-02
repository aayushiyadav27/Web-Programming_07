# Web Programming 07 - Student CRUD API

Express + MongoDB (Mongoose) REST API with models, controllers and routes.

## Structure

```
src/
  config/db.js                  MongoDB connection
  models/Student.js             Mongoose schema
  controllers/studentController.js   CRUD logic
  routes/studentRoutes.js       Route definitions
  server.js                     App entry point
postman/Student-API.postman_collection.json
```

## Setup

1. `npm install`
2. Copy `.env.example` to `.env` and set `MONGODB_URI` to your MongoDB Atlas connection string
   (use the database name `studentdb`, e.g. `mongodb+srv://<user>:<password>@webprogramming07.ws5gget.mongodb.net/studentdb?retryWrites=true&w=majority`).
3. In Atlas -> Network Access, add your current IP address.
4. `npm run dev` (or `npm start`). The server runs on port 5000 by default.

## Endpoints

| Method | URL                  | Description         |
|--------|----------------------|---------------------|
| POST   | /api/students        | Create a student    |
| GET    | /api/students        | List all students   |
| GET    | /api/students/:id    | Get one student     |
| PUT    | /api/students/:id    | Update a student    |
| DELETE | /api/students/:id    | Delete a student    |

Example body for POST / PUT:

```json
{
  "name": "Aayushi Yadav",
  "email": "aayushi@example.com",
  "rollNo": "25CSE001",
  "course": "B.Tech CSE",
  "age": 19
}
```

## Testing with Postman

Import `postman/Student-API.postman_collection.json` into the Postman desktop app.
The collection uses a `baseUrl` variable (default `http://localhost:5000`) and saves the
created student's id into `studentId` so the Read/Update/Delete requests work in order.
