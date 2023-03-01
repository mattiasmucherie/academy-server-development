# Cors and proxy exercises

## Create a new expressjs project

Create a new project using expressjs, follow the steps below and name your project "github-users":

1. Create a folder
1. Open your terminal or command prompt in that folder
1. Run the command "npm init -y" to create a new npm package file with default settings.
1. Run the command "npm install express axios cors nodemon --save" to install the necessary packages for your expressjs project, including express, axios, cors, and nodemon.
1. After the installation is complete, your new expressjs project is ready to use with the name "github-users".

---

## Get places from academy-api.vercel.app

Like in a previous task when we used the endpoint https://academy-api.vercel.app/api/places.json, we should now do the same thing but with the endpoint https://academy-api.vercel.app/api/slowplaces.json. It is really slow though, so what you want to do is fetch the data and cache it.

You should do the following steps:

1. Use the endpoint https://academy-api.vercel.app/api/slowplaces.json with the HTTP GET method to get the data. However, since the endpoint is slow, you should cache the data for subsequent requests.
1. Define a new route in your Express application with a path of `"/places2/"` using the HTTP GET method.
1. Create a new data type that can store the response from the `/slowplaces.json` endpoint, and use it to cache the data.
1. When a request is made to the `/places2/` endpoint, check if the data is already cached. If so, retrieve it from the cache and return it to the client. If not, fetch the data from the API, store it in the cache, and return it to the client.
1. Make sure that subsequent requests to the "/places2/" endpoint are fast by returning the cached data.

Ensure to add error handling and any other necessary features to meet your requirements.

When another request to your endpoint/route is done, it should be ⚡-fast.

---

## Nobel prizes

Create an endpoint in your Express project that retrieves data from the Nobel Prize API. Follow these steps:

1. Use the endpoint https://api.nobelprize.org/2.1/nobelPrizes with the HTTP GET method to get the Nobel Prize winners data.
1. Define a new route in your Express application with a path of "/prizes" using the HTTP GET method.
1. When a request is made to the `/prizes` endpoint, fetch the data from the API and send it back as a response. Also, cache the data to improve the performance of subsequent requests.
1. Add a search parameter to the `/prizes` endpoint, so if a user requests your API with `/prizes/:year`, only data from that year is returned in the response.
1. Implement other ways to filter the data in the response, based on your requirements.

Your final endpoint should look something like `app.get("/prizes/:year", (req, res))` to enable searching by year.

Ensure to add error handling and any other necessary features as per your requirements.

## Get users from github

We can fetch information about users from github in JSON-format. The endpoint is https://api.github.com/users/[user]

To retrieve user information from the GitHub API, follow these steps:

1. Use the endpoint https://api.github.com/users/[user] with the HTTP GET method to get information about a specific user. Replace [user] with the actual username of the user you want to retrieve information about.
1. Define a new route in your Express application with a path of `/git/:user` using the HTTP GET method. The `:user` part of the path is a parameter that allows you to get information about any user.
1. When a request is made to the `/git/:user` endpoint, check if the requested user's data is already available in your application's cache. If so, retrieve it from the cache and send it back as a response. If not, fetch the data from the GitHub API, store it in the cache, and send it back as a response.
1. Create a suitable data type, such as an object, to store the fetched data about each user. This allows you to avoid calling the GitHub API multiple times for the same user.
1. _As a bonus task, explore other endpoints that you can call for a user and add relevant endpoints to your project._

Ensure to add error handling and any other necessary features as per your requirements.

---

## REST API - Create a "phonebook" with all your friends

Build a REST API to manage a phonebook of all your friends using Express.js. Each friend's information should include the following attributes:

| Key          | Value Type |
| ------------ | ---------- |
| name         | string     |
| address      | string     |
| zipCode      | number     |
| city         | string     |
| phoneNumber  | number     |
| email        | string     |
| birthday     | Date       |
| personalNote | string     |
| userId       | number     |

The following endpoints should be available in your API:

```javascript
app.get("/friends"); // Retrieve a list of all friends
app.get("/friends/:userId"); // Retrieve a friend by userId
app.post("/friends"); // Add a new friend, the request body should be JSON
app.put("/friends/:userId"); // Update a friend's information with userId, the request body should be JSON
app.delete("/friends/:userId"); // Delete a friend by userId
```

> hint: Have a look at how to post/put json-data to expressjs. `app.use(express.json())` and `req.body`

Make sure you set up your Express application to use the express.json() middleware to handle JSON data in the request body.

Use Postman or a similar tool to test your endpoints.

_Bonus tasks:_

1. Implement a persistent data store to keep the list of friends even if the server is restarted.
1. Use the multer middleware to enable image upload for each friend. When requesting information about a friend with app.get("friend/:userId"), include a link to the image in the response.

---

## Create a web page that fetches data

Create a web page that allows visitors to browse the different endpoints of your API and fetch data from them. You can use Bootstrap or create a custom web page.

The web page should have a user interface that makes it easy to use all the endpoints you have created in your project. Visitors should be able to interact with the web page to make requests to the API and display the response data in a user-friendly way.

_Bonus: Make sure the web page is responsive and works well on different screen sizes and devices._

---

## Ok, now what?

Take some time to explore the concept of middleware in Express and how it can be used to enhance the functionality of your API.
Additionally, investigate how you can [integrate EJS](https://blog.logrocket.com/how-to-use-ejs-template-node-js-application/) as a template engine to create a website alongside your API.

Once you have some understanding of these concepts, create a website that uses your API to fetch and display data. Use EJS to render the data in a user-friendly format.

If you need further guidance on the architectural setup, let me know and I'll provide some advice.
