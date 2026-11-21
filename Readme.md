# Express.js Basics with Routing

## Section A: Practical Coding Tasks

### 1. Creating an Express.js Route for Home Page

- Write a route in Express.js that serves a `home.html` file.
- Create a new HTML file called `home.html` containing an `<h1>` tag with the message "Welcome to ExpressJs Tutorial".
- Ensure the home page is served when a client accesses the `/home` route.

### 2. Serving JSON Data from a User File

- Modify the `/profile` route to return all details from `user.json` in JSON format.

### 3. Implementing User Authentication

- Modify the `/login` route to accept `username` and `password` as JSON body parameters.
- Read user data from `user.json`.
- If both credentials are valid, return:

```json
{
  "status": true,
  "message": "User Is valid"
}
```

- If the username is invalid, return:

```json
{
  "status": false,
  "message": "User Name is invalid"
}
```

- If the password is invalid, return:

```json
{
  "status": false,
  "message": "Password is invalid"
}
```

### 4. Creating a Logout Route

- Modify the `/logout` route to accept a username as a parameter.
- Return an HTML message displaying `<b>{username} successfully logged out.</b>`.

### 5. Error Handling

- Add error-handling middleware that returns status code 500 with the message "Server Error".

## Section B: Short Answer Questions

### 6. Explain the Purpose of `express.Router()`.

- `express.Router()` helps organize routes into separate files. Instead of putting all the routes in one file, we can group related routes together.
- In this lab, it is used to keep the `/profile`, `/login`, and `/logout` routes in the `users.js` file. This makes the code easier to read and manage.

### 7. Error Handling in Express.js

- Error handling helps catch problems that happen while the application is running. It allows us to send an error message instead of letting the application fail.
- Example:

```javascript
app.use((err, req, res, next) => {
    res.status(500).send('Server Error');
});
```

## Section C: Bonus

### 7. Dynamic Port Binding in Express.js

- This line tells the application which port to run on.
- It first checks if an environment port is available. If there isn't one, it uses port 8081 instead.
- This is useful because some hosting services provide their own port number when an application is running online.