# Express REST API

## Real world use cases where we’d want to change the request with custom middleware

1. **Authentcation** (to check if the user is logged in and add some information to the request object so that the route hanlders can use this information)
2. **Parameters validation** (to check the validaty of parameters and modify their pattern and locatino in request object)
3. **Cookies accessibility** (to get the cookies from the headers and put them directly in request object or validate them)

### The route handler is middleware and can accept `next()` argument

## The ways that middleware function can end the process and send data to the browser?

By one of these methods

| Method             | Description                                                                           |
| ------------------ | ------------------------------------------------------------------------------------- |
| `res.download()`   | Prompt a file to be downloaded.                                                       |
| `res.end()`        | End the response process.                                                             |
| `res.json()`       | Send a JSON response.                                                                 |
| `res.jsonp()`      | Send a JSON response with JSONP support.                                              |
| `res.redirect()`   | Redirect a request.                                                                   |
| `res.render()`     | Render a view template.                                                               |
| `res.send()`       | Send a response of various types.                                                     |
| `res.sendFile()`   | Send a file as an octet stream.                                                       |
| `res.sendStatus()` | Set the response status code and send its string representation as the response body. |

### The request lifecycle can be “injected” middleware at any point before any route handler.

### Express could raise an error with “Request headers sent twice, cannot start a second response” if the we're already in the Body or Finished state, but some function tried to set a header or statusCode

## Terms

**Middleware**: Literally means anything you put in the middle of one layer of the software and another.

**Request Object**: Object contain values that retrieved by the client browser passed to the server during an HTTP request.

**Response Object**: Object, which contains a server's response to an HTTP request. Every HTTP request sent returns a response from the server (the Response object) which includes quite a bit of information.

**Application Middleware**: Middleware are functions that execute during the lifecycle of a request to the application server.

**Routing Middleware**: Middleware that is for specific route.

**Test Driven Development(TDD)**: Development technique where you must first write a test that fails before you write new functional code.

**Behavioral Testing**: Is a testing of the external behaviour of the program, also known as black box testing. It is usually a functional testing.
