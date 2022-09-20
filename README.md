# Server for a Task Manager App
## John Smilga's (AKA: Coding Addict) course on Node.js and Express.js
- [node-express-course repo](https://github.com/john-smilga/node-express-course)
- [Youtube Video: Node.js Projects](https://www.youtube.com/watch?v=rltfdjcXjmk&list=PLqdjyefATy9tT_XIhljRB8tyfSmTTfQp3&index=1)
- [Youtube Video: Node and Express Tutorial](https://www.youtube.com/watch?v=TNV0_7QRDwY)

## Description
In this course, John Smilga shows how to build servers and apps using Node.js and Express.js.

For the first project, the front-end for a task manager app (to-do list app) was already built by John. Our task was to build a server in Node and Express to route the logic for the site. We also used MongoDB and Mongoose to handle the database for the project.

## Structure
app.js initiates the server on the port after awaiting the connection to the database. It also the combines the routes and middleware.

In the controllers folder, the middleware is defined in tasks.js for the logic of the app.

In the db folder, Mongoose is used in a function to connect to the database.

In the errors folder, custom-error.js contains a custom class, CustomAPIError extends the Error class to construct an error function that is used in our routes to return errors for specific conditions.

In the middleware folder, three .js files contain some widdleware to be used in the app.
- async.js: Contains a function, asyncWrapper, that takes in another function. The asyncWrapper function performs an asyncronous task and wraps the task functions in tasks.js in controllers.
- error-handler.js: Contains a function, errorHandlerMiddleware, which defines the error responses based on the input. If the databse _id property is a valid id, but not found in the database, the response is our custom response message from custom-error.js. Else, the response message is a 500 status code error.
- not-found.js: This constains a function, notFound, which sends a 404 error message if the user tries to go to a route that does not exist.

In the models folder, Task.js utilizes Mongoose to define the schema for the data added to MongoDB, which contain "name" and "completed" properties.

In the public folder, the static files used for the front-end are stored. These were not created by me, but bu John as the setup for the course.

In the routes folder, tasks.js imports the controller functions for each route and assigns them to the HTTP method for the app.
