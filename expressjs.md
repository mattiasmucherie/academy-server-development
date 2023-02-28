# Express js

## Create your first expressjs application

To create your first expressjs application, start by opening a new folder inside your preferred code editor and opening the terminal. Then, run `npm init` inside the terminal and answer the questions as you see fit.

Next, add express to your application using `npm install --save express nodemon`.

Create a new file named server.js inside the folder, and import expressjs into it as follows:

```javascript
const express = require("express");
const app = express();

app.all("/", (req, res) => {
  res.send("Hello world");
});
// Add routes

app.listen(3000, () => {
  console.log(`Server is now listening on port ${3000}`);
});
```

You can add additional routes to your application as needed.

To make it easier to start the server and automatically reload changes during development, you can configure the script section of your package.json file with `"serve": "nodemon server.js"`. This allows you to start the server with `npm run serve` in the terminal, and `nodemon` will watch for changes to files in your project and automatically reload the server.

## Add a route that returns a random number

In your Express application that you created earlier, add a new route `/number` that returns a random number. When a user sends a GET request to the `/number` endpoint, the server should generate and respond with a random number.

So when calling `http://localhost:3000/number` you should get a number as a response.

Does it work? If not, why?

> hint! If the server doesn't respond with a random number, make sure to check the order in which you added your routes. Keep in mind that the order of routes matter in Express.

## Add a route that returns a string

Create an Express.js application with two new routes `/test1` and `/test2`. Both should respond to GET requests.

In the first route, use `res.send()` to send the string "Brights" as a response.

In the second route, use `res.send()` to send an HTML page containing the following code as a response:

```html
<html>
  <body>
    <h1>Brights</h1>
  </body>
</html>
```

Once the routes are implemented, test them from a browser by navigating to `http://localhost:3000/test1` and `http://localhost:3000/test2`. Make sure you can see the expected responses.

Optionally, try replacing `res.send()` with `res.end()` in both routes and see what differences it makes in the responses.

## Add a route that returns a object

Add a new endpoint to your Express application with the route `/book` that returns an object as a response.

Create an object that represents a book and add properties like title, author, and year. Use `res.send()` to send the book object as the response.

Test this endpoint by visiting the route in your browser. Take note of the headers that Express sends back in the response.

Next, create another endpoint with the route `/books` that returns an array of book objects as the response, similar to the `/book` endpoint.

Send the response with `res.send()` and test it in your browser. Does the response differ from the `/book` response?

## Use query parameters

In express, query parameters can be accessed through the `req.query` object instead of manually parsing the query string.

Add a new GET endpoint at `/hello`. If the query parameter `name` is provided, respond with the string `"Hello <name>!"` where `<name>` is the value of the `name` query parameter.

For example, if the request is made to `http://localhost:3000/hello?name=Zaphod`, the server should respond with the text "Hello Zaphod!".

If the `name` query parameter is not provided, respond with the text "Hello sunshine, hope you're doing well!".

Try to modify the endpoint to handle multiple `name` query parameters in the URL, for example: `http://localhost:3000/hello?name=Zaphod&name=Trillian&name=Slartibartfast`.

What happens to the query parameters? Can you modify the endpoint so that it greets each name individually, like this:

```
Hello Zaphod!
Hello Trillian!
Hello Slartibartfast!
```

## Is it monday or friday?

Create an endpoint, for example: `/weekday`, that responds with a message based on the current day of the week. If it is Monday, the response should be "Oooh noooez, it's Monday" and if it's Friday the response should be "Oh yeah, it's Friday baby".

Add a URL parameter, for example: `/weekday/:day`, that responds with different messages based on the day provided in the URL. For example, if the user visits `http://localhost:3000/weekday/friday`, the response should be "Oh yeah, it's Friday baby", and if the user visits `http://localhost:3000/weekday/monday`, the response should be "Oooh noooez, it's Monday".

## Get places!

Create a new endpoint in your Express project, for example, `app.get("/places")`, that fetches data as JSON from `https://academy-api.vercel.app/api/places.json`. Use `fetch` (if on NodeJs 18, check by writing in the terminal `node -v`) to fetch the data and return it with res.send(). Make sure to set the appropriate headers for the type of data being returned.

If the endpoint returns a response other than 200, you should handle it accordingly.

## Get the images

Create a new folder named "images" inside your ExpressJS project.

Copy the images you want to serve into the images folder.

Use `express.static` to serve static files from the images folder. Check out the documentation on this link: https://expressjs.com/en/starter/static-files.html.

## Get the users

Since you have a json-file ready with persons from an earlier exercise, copy that file into the same directory as the express project. Then, create a GET endpoint that will return the content of the file as a JSON response when called. To achieve this, create an endpoint with the URL `/users/`.

It's important to note that you shouldn't have to read the file from the disk every time a request to `/users` is made. There are several ways to solve this problem, so think about a solution that works best for you. If you get stuck or want to reflect on your solution, don't hesitate to ask the teacher for help.

## Get the users again

Create a new endpoint in your ExpressJS project called `/users/:name` that accepts a parameter called `name`. This parameter will be used to filter the users data.

When this endpoint is called, respond with a JSON array that only contains the names from the data that match the `name` parameter.

Make sure to properly handle cases where there are no matches found for the `name` parameter.

## Add to the users

Create a new POST endpoint `/users` that can receive a new user. So if a user of your API calls `/users` with the POST method and the BODY contains a name and email you'll add it to your users data.

Add the possibility that if the user defines the `Content-Type: application/json` the endpoint reads the JSON body instead of using post data.

Example:

```console
{
    "name": "Ford",
    "email": "ford@ford.com"
}
```

> Hint: look at the express.json() middleware.

```javascript
app.use(express.json()); // for parsing application/json
```
