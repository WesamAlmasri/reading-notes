# Update/Delete

![html forms](https://camo.githubusercontent.com/819fbe496f2b424922b7e7fbb7e6f0cb42016dfc46ba6410c428dcb860ca8489/68747470733a2f2f6361726565726b61726d612e636f6d2f626c6f672f77702d636f6e74656e742f75706c6f6164732f323032302f30332f68746d6c2d666f726d732e6a7067)

## Client/server architecture

![client server arch](https://camo.githubusercontent.com/6fbe138d465d7fbdf77d2ef0f55b109d7d23d7a580c46e724ca8ec038ad20df9/68747470733a2f2f646576656c6f7065722e6d6f7a696c6c612e6f72672f66696c65732f343239312f636c69656e742d7365727665722e706e67)

At it's most basic, the web uses a client/server architecture that can be summarized as follows. a client (usually a web browser) sends a request to a server (most of the time a web server like Apache, Nginx, IIS, Tomcat, etc.), using the HTTP protocol. The server answers the request using the same protocol.

An HTML form on a web page is nothing more than a convenient user-friendly way to configure an HTTP request to send data to a server. This enables the user to provide information to be delivered in the HTTP request.

## On the client side: defining how to send the data

![client server connection](https://camo.githubusercontent.com/402f4c16f80b75ffcdc38f7e1e77959b39216df5dd9bb8fe4d8b8bb5e05c084f/68747470733a2f2f322e62702e626c6f6773706f742e636f6d2f2d59334934654e557a6474302f56465441324367494e79492f41414141414141415537772f7a555959475574315a5f342f73313630302f646966666572656e63655f6265747765656e5f6765745f616e645f706f73745f6d6574686f642e706e67)

The `<form>` element defines how the data will be sent. All of its attributes are designed to let you configure the request to be sent when a user hits a submit button. The two most important attributes are `action` and `method`.

The `action` attribute defines where the data gets sent. Its value must be a valid relative or absolute URL. If this attribute isn't provided, the data will be sent to the URL of the page containing the form — the current page.

```html
<form action="https://example.com">
```

```html
<form action="/somewhere_else">
```

The names and values of the non-file form controls are sent to the server as **name=value** pairs joined with ampersands. The action value should be a file on the server that can handle the incoming data, including ensuring server-side validation. The server then responds, generally handling the data and loading the URL defined by the action attribute, causing a new page load (or a refresh of the existing page, if the action points to the same page).

How the data is sent depends on the method attribute.

The `method` attribute defines how data is sent. The HTTP protocol provides several ways to perform a request; HTML form data can be transmitted via a number of different methods, the most common being the `GET` method and the `POST` method

To understand the difference between those two methods, let's step back and examine how HTTP works. Each time you want to reach a resource on the Web, the browser sends a request to a URL. An HTTP request consists of two parts: a header that contains a set of global metadata about the browser's capabilities, and a body that can contain information necessary for the server to process the specific request.

### GET method

![get method](https://camo.githubusercontent.com/635d4410466777dd92ecb3d3bb0b4d9450a0686b3e6eed237eecc51132466bc5/68747470733a2f2f646f63706c617965722e6e65742f646f63732d696d616765732f34342f31343432383336352f696d616765732f706167655f31342e6a7067)

The `GET` method is the method used by the browser to ask the server to send back a given resource: "Hey server, I want to get this resource." In this case, the browser sends an empty body. Because the body is empty, if a form is sent using this method the data sent to the server is appended to the URL.

```html
<form action="https://www.foo.com" method="GET">
    <div>  
        <label for="say">What greeting do you want to say?</label>
        <input name="say" id="say" value="Hi">
    </div>
    <div>
        <label for="to">Who do you want to say it to?</label>
        <input name="to" id="to" value="Mom">
    </div>
    <div>
        <button>Send my greetings</button>
    </div>
</form>
```

### Post method

![post method](https://camo.githubusercontent.com/900c15f0103a025e75c2298b4d461b38027f34babb8927b2c83fb566f97bf649/68747470733a2f2f7777772e6775727539392e636f6d2f696d616765732f323031332f30342f706f73745f666f726d5f7375626d697373696f6e2e706e67)

Sends the form-data as an HTTP post transaction

```html
<form action="/action_page.php" method="post">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname"><br><br>
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname"><br><br>
  <input type="submit" value="Submit">
</form>
```
