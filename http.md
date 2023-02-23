# Http exercises

## Http-client in NodeJS

In this exercise, you will be using the `http` module in Node.js to make requests to `icanhazdadjoke.com` and specify that you want the response in `text/plain` format.

To accomplish this, you can refer to the [documentation](https://nodejs.org/dist/latest-v18.x/docs/api/http.html#http_http_request_options_callback) for `http.request` method, which outlines the parameters required for the function call. You will also need to add an event listener to the `response` object in the callback using the `res.on("data", function (data) {})` method. Finally, you should print the data to the console using the `process.stdout.write` method.

If you get stuck, you can refer to the following resource for more information: https://nodejs.org/en/knowledge/HTTP/clients/how-to-create-a-HTTP-request/

## HTTP-server in NodeJS

### 1.

Create a simple HTTP server using the built-in `http` module in Node.js. The server should always respond with the text "Hello, World" to any incoming requests.

You can use the `createServer()` method of the `http` module to create an HTTP server. You will need to listen to the `request` event of the server object to handle incoming requests.

Once you have created the server, you can test it by making a GET request to `http://localhost:<port>` where `<port>` is the port number you used to start the server.

### 2.

Modify the server created in Task 1 to only respond with "Hello, World" when the request URL starts with `/hello`. For all other URLs, the server should respond with a 404 status code and the text "Not found".

You can access the request URL from the `request` object that is passed to the `request` event listener. The `url` property of the request object contains the request URL.

Make sure to always return a response to any incoming requests, even if it's just a 404 status code and a message. You can do this by calling the `end()` method of the `response` object.

### 3.

In the previous task, the function always responded with the same message regardless of the HTTP method used. Refactor the function so that it responds in the same way when a GET request is used. If any other HTTP method is used, ensure that the server responds with a "Method not allowed" message and a status code of 405.

The browser will always send a GET-request, to test other method you can use [Postman](https://www.postman.com/downloads/), curl or [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)

### 4.

Modify the previous task where the server responds with "Hello World" when calling `http://localhost:3000/hello` to take in a GET parameter using a query string. The query string should contain a key-value pair in the format of `key=value`, separated by `&`. For example: `http://localhost:3000/hello?name=Mattias&age=42`.

If the query string contains a `name` key, the server should respond with the text "Hello [name]", where [name] is the value associated with the `name` key.

To read the URL and parse the query string, you can use the following code:

```javascript
const url = new URL(req.url, `http://${req.headers.host}`);
const queryString = url.searchParams;
const name = queryString.get("name");
```

If `name` is not `null` or `undefined`, the server should respond with "Hello [name]". If `name` is `null` or `undefined`, the server should respond with "Hello World".

### 5.

Create a new HTTP endpoint at `http://localhost:3000/pics` that returns a JSON response containing an array with the files inside the `image` folder from earlier exercises.

To send a JSON response, you need to set the `"Content-Type" header to "application/json"`. You can do this using the `res.setHeader()` method.

You also need to convert the array of file names to a JSON string using `JSON.stringify()`, before sending it as the response body using `res.end()`.

```
  res.setHeader(...);
  const jsonFiles = JSON.stringify(files);
  res.end(...);
```

### 5.2 (Bonus)

Extend the previous exercise where we created an endpoint `http://localhost:3000/pics` to return a JSON response containing an array with the files inside the image folder from previous exercises.

Add functionality to filter the images based on a city path specified in the URL.

For example, a request to `http://localhost:3000/pics/berlin/` should only show files from the "berlin" folder in the `images` directory.

Response:

```json
["frank-berlin.jpg", "joe-berlin.jpg", "mary-berlin.jpg"]
```
