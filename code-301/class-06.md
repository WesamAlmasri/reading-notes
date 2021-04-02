# Node, Express, and APIs

![node js image](https://miro.medium.com/max/1600/1*xdo0UBpyszvD7-7EH4TkIA.png)

## Node.js

Node.js is a very powerful JavaScript-based platform built on Google Chrome's JavaScript V8 Engine. It is used to develop I/O intensive web applications like video streaming sites, single-page applications, and other web applications. Node.js is open source, completely free, and used by thousands of developers around the world.

### What is Node.js?

**Node.js** is a platform built on Chrome's JavaScript runtime for easily building fast and scalable network applications. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient, perfect for data-intensive real-time applications that run across distributed devices.

### Concepts

![node js concepts](https://camo.githubusercontent.com/d75657fab656752eb7900254bf8d0192df003f167cbe09c240afe6ef6afaa60e/68747470733a2f2f7777772e7475746f7269616c73706f696e742e636f6d2f6e6f64656a732f696d616765732f6e6f64656a735f636f6e63657074732e6a7067)

Where to Use Node.js? Below are the areas where Node.js is proving itself as a perfect technology partner.

1. I/O bound Applications
2. Data Streaming Applications
3. Data Intensive Real-time Applications (DIRT)
4. JSON APIs based Applications
5. Single Page Applications

#### Installation on UNIX/Linux/Mac OS X, and SunOS

Based on your OS architecture, download and extract the archive node-v6.3.1-osname.tar.gz into /tmp, and then finally move extracted files into /usr/local/nodejs directory. For example:

```terminal
$cd /tmp
$wget http://nodejs.org/dist/v6.3.1/node-v6.3.1-linux-x64.tar.gz
$tar xvfz node-v6.3.1-linux-x64.tar.gz
$mkdir -p /usr/local/nodejs
$mv node-v6.3.1-linux-x64/* /usr/local/nodejs
```

#### Installation on Windows

Use the MSI file and follow the prompts to install the Node.js. By default, the installer uses the Node.js distribution in C:\Program Files\nodejs. The installer should set the C:\Program Files\nodejs\bin directory in window's PATH environment variable. Restart any open command prompts for the change to take effect.

### Creating Node.js Application

#### Step 1 - Import Required Module

We use the `require` directive to load the http module and store the returned HTTP instance into an http variable as follows −

`var http = require("http");`

#### Step 2 - Create Server

We use the created http instance and call `http.createServer()` method to create a server instance and then we bind it at port 3000 using the listen method associated with the server instance. Pass it a function with parameters request and response. Write the sample implementation to always return "Hello World".

```javascript
http.createServer(function (request, response) {
   // Send the HTTP header 
   // HTTP Status: 200 : OK
   // Content Type: text/plain
   response.writeHead(200, {'Content-Type': 'text/plain'});
   
   // Send the response body as "Hello World"
   response.end('Hello World\n');
}).listen(3000);

// Console will print the message
console.log('Server running at http://127.0.0.1:3000/');
```

The above code is enough to create an HTTP server which listens, i.e., waits for a request over 300 port on the local machine.

#### Step 3 - Testing Request & Response

Let's put step 1 and 2 together in a file called main.js and start our HTTP server as shown below −

```javascript
var http = require("http");

http.createServer(function (request, response) {
   // Send the HTTP header 
   // HTTP Status: 200 : OK
   // Content Type: text/plain
   response.writeHead(200, {'Content-Type': 'text/plain'});
   
   // Send the response body as "Hello World"
   response.end('Hello World\n');
}).listen(2000);

// Console will print the message
console.log('Server running at http://127.0.0.1:3000/');
```

Now execute the main.js to start the server as follows −

`$ node main.js`

Verify the Output. Server has started.

`Server running at http://127.0.0.1:3000/`

Make a Request to the Node.js Server Open `http://127.0.0.1:3000/` in any browser and observe the following result.

![result image](https://camo.githubusercontent.com/df32d9e887f064d5e716e53f65f65287fdf2a5cd0f6d50bd85843ebf22b948ae/68747470733a2f2f7777772e7475746f7269616c73706f696e742e636f6d2f6e6f64656a732f696d616765732f6e6f64656a735f73616d706c652e6a7067)

### Node.js - REPL Terminal

REPL Commands

1. `ctrl + c` − terminate the current command.
2. `ctrl + c` twice − terminate the Node REPL.
3. `ctrl + d` − terminate the Node REPL.
4. `Up/Down Keys` − see command history and modify previous commands.
5. `tab Keys` − list of current commands.
6. `.help` − list of all commands.
7. `.break` − exit from multiline expression.
8. `.clear` − exit from multiline expression.
9. `.save filename` − save the current Node REPL session to a file.
10. `.load filename` − load file content in current Node REPL session.

### Node.js - NPM

NPM comes bundled with Node.js installables after v0.6.3 version. To verify the same, open console and type the following command and see the result −

```terminal
$npm --version
2.7.1
```

#### Installing Modules using NPM

There is a simple syntax to install any Node.js module −

`$ npm install <Module Name>`

For example, following is the command to install a famous Node.js web framework module called express −

`$ npm install express`

Now you can use this module in your js file as following −

`var express = require('express');`

### Using package.json

`Package.json` is present in the root directory of any Node application/module and is used to define the properties of a package. Let's open `package.json` of express package present in node_modules/express/

```json
{
   "name": "express",
      "description": "Fast, unopinionated, minimalist web framework",
      "version": "4.11.2",
      "author": {
      
         "name": "TJ Holowaychuk",
         "email": "tj@vision-media.ca"
      },
   
   "contributors": [{
      "name": "Aaron Heckmann",
      "email": "aaron.heckmann+github@gmail.com"
   }, 
   
   {
      "name": "Ciaran Jessup",
      "email": "ciaranj@gmail.com"
   },
   
   {
      "name": "Douglas Christopher Wilson",
      "email": "doug@somethingdoug.com"
   },
   
   {
      "name": "Guillermo Rauch",
      "email": "rauchg@gmail.com"
   },
   
   {
      "name": "Jonathan Ong",
      "email": "me@jongleberry.com"
   },
   
   {
      "name": "Roman Shtylman",
      "email": "shtylman+expressjs@gmail.com"
   },
   
   {
      "name": "Young Jae Sim",
      "email": "hanul@hanul.me"
   } ],
   
   "license": "MIT", "repository": {
      "type": "git",
      "url": "https://github.com/strongloop/express"
   },
   
   "homepage": "https://expressjs.com/", "keywords": [
      "express",
      "framework",
      "sinatra",
      "web",
      "rest",
      "restful",
      "router",
      "app",
      "api"
   ],
   
   "dependencies": {
      "accepts": "~1.2.3",
      "content-disposition": "0.5.0",
      "cookie-signature": "1.0.5",
      "debug": "~2.1.1",
      "depd": "~1.0.0",
      "escape-html": "1.0.1",
      "etag": "~1.5.1",
      "finalhandler": "0.3.3",
      "fresh": "0.2.4",
      "media-typer": "0.3.0",
      "methods": "~1.1.1",
      "on-finished": "~2.2.0",
      "parseurl": "~1.3.0",
      "path-to-regexp": "0.1.3",
      "proxy-addr": "~1.0.6",
      "qs": "2.3.3",
      "range-parser": "~1.0.2",
      "send": "0.11.1",
      "serve-static": "~1.8.1",
      "type-is": "~1.5.6",
      "vary": "~1.0.0",
      "cookie": "0.1.2",
      "merge-descriptors": "0.0.2",
      "utils-merge": "1.0.0"
   },
   
   "devDependencies": {
      "after": "0.8.1",
      "ejs": "2.1.4",
      "istanbul": "0.3.5",
      "marked": "0.3.3",
      "mocha": "~2.1.0",
      "should": "~4.6.2",
      "supertest": "~0.15.0",
      "hjs": "~0.0.6",
      "body-parser": "~1.11.0",
      "connect-redis": "~2.2.0",
      "cookie-parser": "~1.3.3",
      "express-session": "~1.10.2",
      "jade": "~1.9.1",
      "method-override": "~2.3.1",
      "morgan": "~1.5.1",
      "multiparty": "~4.1.1",
      "vhost": "~3.0.0"
   },
   
   "engines": {
      "node": ">= 0.10.0"
   },
   
   "files": [
      "LICENSE",
      "History.md",
      "Readme.md",
      "index.js",
      "lib/"
   ],
   
   "scripts": {
      "test": "mocha --require test/support/env 
         --reporter spec --bail --check-leaks test/ test/acceptance/",
      "test-cov": "istanbul cover node_modules/mocha/bin/_mocha 
         -- --require test/support/env --reporter dot --check-leaks test/ test/acceptance/",
      "test-tap": "mocha --require test/support/env 
         --reporter tap --check-leaks test/ test/acceptance/",
      "test-travis": "istanbul cover node_modules/mocha/bin/_mocha 
         --report lcovonly -- --require test/support/env 
         --reporter spec --check-leaks test/ test/acceptance/"
   },
   
   "gitHead": "63ab25579bda70b4927a179b580a9c580b6c7ada",
   "bugs": {
      "url": "https://github.com/strongloop/express/issues"
   },
   
   "_id": "express@4.11.2",
   "_shasum": "8df3d5a9ac848585f00a0777601823faecd3b148",
   "_from": "express@*",
   "_npmVersion": "1.4.28",
   "_npmUser": {
      "name": "dougwilson",
      "email": "doug@somethingdoug.com"
   },
   
   "maintainers": [{
      "name": "tjholowaychuk",
      "email": "tj@vision-media.ca"
   },
   
   {
      "name": "jongleberry",
      "email": "jonathanrichardong@gmail.com"
   },
   
   {
      "name": "shtylman",
      "email": "shtylman@gmail.com"
   },
   
   {
      "name": "dougwilson",
      "email": "doug@somethingdoug.com"
   },
   
   {
      "name": "aredridel",
      "email": "aredridel@nbtsc.org"
   },
   
   {
      "name": "strongloop",
      "email": "callback@strongloop.com"
   },
   
   {
      "name": "rfeng",
      "email": "enjoyjava@gmail.com"
   }],
   
   "dist": {
      "shasum": "8df3d5a9ac848585f00a0777601823faecd3b148",
      "tarball": "https://registry.npmjs.org/express/-/express-4.11.2.tgz"
   },
   
   "directories": {},
      "_resolved": "https://registry.npmjs.org/express/-/express-4.11.2.tgz",
      "readme": "ERROR: No README data found!"
}
```
