# EJS

![ejs image](https://images.g2crowd.com/uploads/product/image/social_landscape/social_landscape_f9dd821cb48125c63c64b6f5c7552372/ejs.png)

## EJS Templating

**EJS** simply stands for **Embedded JavaScript templates**, and we can use it both **server-side** or **client-side**. At this story, we’ll focus on the server-side.

### Basic Syntax(Tags)

1. `<%` 'Scriptlet' tag, for control-flow, no output
2. `<%=` Outputs the value into the template (HTML escaped)
3. `<%-` Outputs the unescaped value into the template

**Example**:

```javascript
<% if (message) { %>
  <h2><%= message.name %></h2>
<% } %>
```

### Partials

In this section we’ll learn how to use `<%- include(‘’)-%>` tag.

![ejs include image](https://camo.githubusercontent.com/d67ea586d527ae7813145d152211d32356f6935f3000d4b8fee96dad9f612114/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f3336382f312a4d6d704c517156465a517561326f6e51306a6d6b63412e706e67)

**Project structure:**

```terminal
startEJS
|--public
|--views
  |--pages
     |--home.ejs
  |--template
     |--head.ejs
     |--nav.ejs
     |--footer.ejs 
|--index.js
|--package.json
```

**Install express and ejs:**

```terminal
npm i express --save
npm i ejs --save 
```

**index.js file:**

```javascript
const express = require('express')

var path = require('path');

const app = express();

const port = 3000;

// view engine setup
app.set('views', path.join(__dirname, 'views'));
app.set('view engine', 'ejs');

//setup public folder
app.use(express.static('./public'));
app.get('/',function (req, res) {
    res.render('pages/home')
});

app.listen(port, () => console.log(`MasterEJS app Started on port ${port}!`));
```

**home.ejs:**

```javascript
<%- include('../template/head')-%>
    <body class="text-center">
        <div class="cover-container d-flex w-100 h-100 p-3 mx-auto flex-column">
            <%- include('../template/nav')-%>
            <main role="main" class="inner cover">
                <h1 class="cover-heading">MasterEJS</h1>
                <p class="lead">This is a sample app to Master EJS view template engine with Expressjs and Node.js framework</p>
                <p class="lead">
                    <a href="https://medium.com/@pkoulianos/master-ejs-template-engine-with-node-js-and-expressjs" class="btn btn-lg btn-secondary">Read More At Medium</a>
                </p>
            </main>
            <%- include('../template/footer')-%>
        </div>
    </body>
</html>
```

EJS uses `<%- include(‘’)-%>` tag to include HTML from other files, in our app, we have the HTML templates at `/views/template` folder.

![include ejs](https://camo.githubusercontent.com/2ff396bdef0f0757b730e5fd771aa6a84d390a341b76d9f90c55ffa89bcf306b/68747470733a2f2f692e737461636b2e696d6775722e636f6d2f704b314f372e706e67)

### Render Links

```javascript
//array with items to send
var items = [
    {name:'node.js',url:'https://nodejs.org/en/'},
    {name:'ejs',url:'https://ejs.co'},
    {name:'expressjs',url:'https://expressjs.com'},
    {name:'vuejs',url:'https://vuejs.org'},
    {name:'nextjs',url:'https://nextjs.org'}
];
res.render('pages/links',{
    links:items
})
```

**EJS** is a great template view engine for fast production environments and with a very smooth learning curve.
