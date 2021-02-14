# Introductory HTML and JavaScript

![html js css image](https://journocode.com/wp-content/uploads/2016/06/htmlCssJS-1140x515.jpg)

## HTML

In all kinds of documents, structure is very important in helping readers to understand the messages you are trying to convey and to navigate around the document. So, in order to learn how to write web pages, it is very important to understand how to structure documents.

**What HTML**?

HTML describes the structure of a web page and it's a tags language so every tag describe it's content

### HTML describes the Structure of Pages

To describe the structure of a web page, a code is added to the words we want to appear on the page.

```html
<html>
<body>
    <h1>This is the Main Heading</h1>
    <p>This text might be an introduction to the rest of
        the page. And if the page is a long one it might
        be split up into several sub-headings.<p>
    <h2>This is a Sub-Heading</h2>
    <p>Many long articles have sub-headings so to help
        you follow the structure of what is being written.
        There may even be sub-sub-headings (or lower-level
        headings).</p>
    <h2>Another Sub-Heading</h2>
    <p>Here you can see another sub-heading.</p>
</body>
</html>
```

The HTML code (in blue) is made up of characters that live inside angled brackets — these are called HTML elements. Elements are usually made up of two tags: an opening tag and a closing tag. (The closing tag has an extra forward slash in it) and every tag can have one or more attribute. Each HTML element tells the browser something about the information that sits between its opening and closing tags and the attributes provide additional information about the contents of an element.

The attribute appear on the opening tag of the element and are made up of two parts: a **name** and a **value**, separated by an equals sign.

```html
<p lang="en-us">Paragraph in English</p>
 ```

 So this means that this `<p>` language is English.

### Body, Head & Title

#### body

Everything inside The `<body>` element is shown inside the main browser window.

#### Head

Before the `<body>` element you will often see a `<head>` element. This contains information about the page (rather than information that is shown within the main part of the browser window). You will usually find a `<title>` element inside the `<head>` element.

#### Title

The contents of the `<title>` element are either shown in the top of the browser, above where you usually type in the URL of the page you want to visit, or on the tab for that page (if your browser uses tabs to allow you to view multiple pages at the same time).

### Creating a Web Page on a PC

To create a web page on a PC, you can use code editor like VSC, Notepad++, XCode, Atom, etc., or you can use the text editor that came with the OS by creating a file  with *.html* extension and writing the code inside it.

## Extra Markup

### Doctypes

Because there have been several versions of HTML, each web page should begin with a DOCTYPE declaration to tell a browser which version of HTML the page is using Html5 must have Doctypes in the beginning file like below

```html
<!DOCTYPE html>
```

### Comments in HTML

If you want to add a comment to your code that will not be visible in the user's browser, you can add the text between these characters:

```html
<!-- comment goes here -->
```

### ID Attribute

Every HTML element can carry the id attribute. It is used to uniquely identify that element from other elements on the page. Its value should start with a letter or an underscore (not a number or any other character). It is important that no two elements on the same page have the same value for their id attributes (otherwise the value is no longer unique).

```html
<p id="mainParagraph"></p>
```

### Class Attribute

Every HTML element can also carry a class attribute. Sometimes, rather than uniquely identifying one element within a document, you will want a way to identify several elements as being different from the other elements on the page.

```html
<p class="paragraph">paragraph1</p>
<p class="paragraph">paragraph2</p>
```

### Block Elements

Some elements will always appear to start on a new line in the browser window like h1, p, ul, and li.

```html
<ul>
    <li>Science: 21 Nov - 20 Feb 2010/11</li>
    <li>Architecture: 6 Mar - 15 May 2011</li>
    <li>History: 29 May - 21 Aug 2011</li>
    <li>Religion: 28 Aug - 6 Nov 2011</li>
</ul>
```

### Inline Elements

Some elements will always appear to continue on the same line as their neighboring elements like `<a>`, `<b>`, `<em>`, and `<img>` .

### Grouping Text & Elements In a Block

The `<div>` element allows you to group a set of elements together in one block-level box.

```html
<div id="header">
    <img src="images/logo.gif" alt="Anish Kapoor" />
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="biography.html">Biography</a></li>
        <li><a href="works.html">Works</a></li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
</div>
```

### Grouping Article Text & Elements Inline

The `<span>` element acts like an inline equivalent of the `<div>` element. It is used to either:

1. Contain a section of text where there is no other suitable element to differentiate it from its surrounding text
2. Contain a number of inline elements

```html
<p>Anish Kapoor won the Turner Prize in 1991 and exhibited at the <span class="gallery">Tate Modern</span> gallery in London in 2003.</p>
```

### Information About Your Pages

The `<meta>` element lives inside the `<head>` element and contains information about that web page.
It is not visible to users but fulfills a number of purposes such as telling search engines about your page, who created it, and whether or not it is time sensitive. (If the page is time sensitive, it can be set to expire).

The `<meta>` element is an empty element so it does not have a closing tag. It uses attributes to carry the information.

The most common attributes are the name and content attributes, which tend to be used together. These attributes specify properties of the entire page. The value of the name attribute is the property you are setting, and the value of the content attribute is the value that you want to give to this property.

```html
<meta name="description" content="Telephone, email and directions for The Art Bookshop, London, UK" />
```

The value of the name attribute can be anything you want it to be. Some defined values for this attribute that are commonly used are:

- **description**: This contains a description of the page. This description is commonly used by search engines to understand what the page is about and should be a maximum of 155 characters. Sometimes it is also displayed in search engine results.
- **keywords**: This contains a list of comma- separated words that a user might search on to find the page. In practice, this no longer has any noticeable effect on how search engines index your site.
- **robots**: This indicates whether search engines should add this page to their search results or not. A value of noindex can be used if this page should not be added. A value of nofollow can be used if search engines should add this page in their results but not any pages that it links to.

### Escape Characters

There are some characters that are used in and reserved by HTML code. (For example, the left and right angled brackets).

Therefore, if you want these characters to appear on your page you need to use what are termed "escape" characters

![html escape characters image](https://assets.codepen.io/17824/internal/screenshots/pens/puBaf.default.png?fit=cover&format=auto&ha=false&height=360&quality=75&v=2&version=1534879301&width=640)

## HTML5 Layout

HTML5 introduces a new set of elements that allow you to divide up the parts of a page. The names of these elements indicate the kind of content you will find in them. They are still subject to change, but that has not stopped many web page authors using them already.

![html5 layout image](https://kumarsher45.files.wordpress.com/2015/01/website-layout-using-html5.jpg)

## Process & Design

The process of creating a new website includes:

- Understanding the audience the site may attract and what information they will expect to find on it
- Organizing the information so that visitors can find what they are looking for
- Presenting information in a way that helps visitors achieve their goals using design theory
- Making the site more attractive and professional

### Who is the Site For?

Every website should be designed for the target audience—not just for yourself or the site owner. It is therefore very important to understand who your target audience is.

It can be helpful to ask some questions about the people you would expect to be interested in the subject of your site.

#### Target Audience: individuals

- What is the age range of your target audience?
- Will your site appeal to more women or men? What is the mix?
- Which country do your visitors live in?
- Do they live in urban or rural areas?
- What is the average income of visitors?
- What level of education do they have?
- What is their marital or family status?
- What is their occupation?
- How many hours do they work per week?
- How often do they use the web?
- What kind of device do they use to access the web?
  
#### Target Audience: Companies

- What is the size of the company or relevant department?
- What is the position of people in the company who visit your site?
- Will visitors be using the site for themselves or for someone else?
- How large is the budget they control?

### Why People Visit your Website

Your content and design should be influenced by the goals of your users.

#### Key Motivations

- Are they looking for general entertainment or do they need to achieve a specific goal?
- If there is a specific goal, is it a personal or professional one?
- Do they see spending time on this activity as essential or a luxury?

#### Specific Goals

- Do they want general information / research (such as background on a topic / company), or are they after something specific (such as a particular fact or information on a product)?
- Are they already familiar with the service or product that you offer or do they need to be introduced to it?
- Are they looking for time sensitive information, such as the latest news or updates on a particular topic?
- Do they want to discover information about a specific product or service to help them decide whether to buy it or not?
- Do they need to contact you? If so, can they visit in person (which might require opening hours and a map)? Or might they need email or telephone contact details?

### What Your Visitors are Trying to Achieve

It is unlikely that you will be able to list every reason why someone visits your site but you are looking for key tasks and motivations. This information can help guide your site designs.

### How Often People Will Visit Your Site

Some sites benefit from being updated more frequently than others. Some information (such as news) may be constantly changing, while other content remains relatively static.

### Site Maps

The aim is to create a diagram of the pages that will be used to structure the site. This is known as a site map and it will show how those pages can be grouped.

![site map example](https://roundpeg.biz/wp-content/uploads/2019/08/Site-map-510x382.jpg)

### WireFrames

A wireframe is a simple sketch of the key information that needs to go on each page of a site. It shows the hierarchy of the information and how much space it might require.

![wireframe example image](https://online.visual-paradigm.com/repository/images/6ed564b2-63e7-4c3e-acca-73b987f5f3f2/mockups-wireframe-design/landing-page-layout.png)

### Getting your message across using design

The primary aim of any kind of visual design is to communicate. Organizing and prioritizing information on a page helps users understand its importance and what order to read it in.

- Content
- Prioritizing
- Organizing

**Content**:

Web pages often have a lot of information to communicate. For example, the pages of online newspapers will have information that does not appear on every page of the print equivalent:

- A masthead or logo
- Links to navigate the site
- Links to related content and other popular articles
- Login or membership options
- Ability for users to comment
- Copyright information
- Links to privacy policies, terms and conditions, advertising information, RSS feeds,subscription options

**Prioritizing**:

If everything on a page appeared in the same style, it would be much harder to understand.

By making parts of the page look distinct from surrounding content, designers draw attention to (or away from) those items.

Designers create something known as a visual hierarchy to help users focus on the key messages that will draw people's attention, and then guide them to subsequent messages.

**Organizing**:

Grouping together related content into blocks or chunks makes the page look simpler (and easier to understand).

Users should be able to identify the purpose of each block without processing each individual item.

By presenting certain types of information in a similar visual style (such as using the same style for all buttons or all links), users will learn to associate that style with a particular type of content.

**Visual hierarchy**:

Most web users do not read entire pages. Rather, they skim to find information. You can use contrast to create a visual hierarchy that gets across your key message and helps users find what they are looking for.

Visual hierarchy refers to the order in which your eyes perceive what they see. It is created by adding visual contrast between the items being displayed. Items with higher contrast are recognized and processed first.

You can use the **size**, **color** or the **style** to grab users' attention.

![Visual hierarchy example image](https://www.awwwards.com/awards/images/2014/11/understanding-fitbit.jpg)

### Designing Navigation

Site navigation not only helps people find where they want to go, but also helps them understand what your site is about and how it is organized. Good navigation tends to follow these principles...

![navigation example image](https://csharpcorner.azureedge.net/UploadFile/rohatash/creating-dropdown-menu-in-bootstrap/Images/Dropdown%20menu.jpg)

## JavaScript & jQuery

![javascript image](http://crowdforthink.com/assets/uploads/blogs/d432ce51653c4558fc49e6f6ba3ca0c0.jpg)

The JavaScript makes web pages more interactive by:

1. Access content: You can use JavaScript to select any element, attribute, or text from an HTML page.
2. Modify content: You can use JavaScript to add elements, attributes, and text to the page, or remove them.
3. Program rules: You can specify a set of steps for the browser to follow (like a recipe), which allows it to access or change the content of a page.
4. React to events: You can specify that a script should run when a specific event has occurred.
5. JavaScript can reload the content of page without reload the page itself and filter data.

## The ABC of programming

There is some key concepts in computer programming that is important to be familiar with.

### Script

A script is a series of instructions that a computer can follow to achieve a goal.

#### WRITING A SCRIPT

To write a script, you need to first state your goal and then list the tasks that need to be completed in order to achieve it.

Start with the big picture of what you want to achieve, and break that down into smaller steps.

1. **Define The Goal First**: You need to define the task you want to achieve. You can think of this as a puzzle for the computer to solve.

2. **Design The Script**: To design a script you split the goal out into a series of tasks that are going to be involved in solving this puzzle. This can be represented using a flowchart.

3. **Code each Step**: Each of the steps  needs to be written in a programming language that the computer understands. In our case, this is JavaScript.

You can use  a flowchart to represent to simplify and organize the steps.

#### From steps to code

Every step for every task shown in a flowchart needs to be written in a language the computer can understand and follow. Just like learning any new language, you need to get to grips with the:

1. **Vocabulary**: The words that computers understand
2. **Syntax**: How you put those words together to create instructions computers can follow

You need to learn to "think" like a computer because they solve tasks in different ways than you or I might approach them.

For example, when you look at the picture on the left how do you tell which person is the tallest? A computer would need explicit, step-by-step instructi0ns, such as:

1. Find the height of the first person
2. Assume he or she is the "tallest person"
3. Look at the height of the remaining people one- by-one and compare their height to the "tallest person" you have found so far
4. At each step, if you find someone whose height is greater than the current "tallest person", he or she becomes the new "tallest person"
5. Once you have checked all the people, tell me which one is the tallest

### How computers fit in with word around them?

Computer has no predefined concept of what a real life object (car ,hotel, etc..), so programmers create a very different kind of model, especially for computers. Programmers make these models using data.

#### OBJECTS & PROPERTIES

**OBJECTS (THINGS)**:

In computer programming, each physical thing in the world can be represented as an **object**.

For example if we have a hotel and two car. Programmers might say that there is one **instance** of the hotel object, and two **instances** of the car object.

Each object can have its own:

- Properties
- Events
- Methods

Together t hey create a working model of that object.

**PROPERTIES (CHARACTERISTICS)**:

Both of the cars share common characteristics. In fact, all cars have a make, a color, and engine size. Programmers call these characteristics the **properties** of an object.

Each property has a **name** and a **value**, and each of these name/value pairs tells you something about each individual instance of the object.

#### EVENTS

In the real world, people interact with objects. These interactions can change the values of the properties in these objects.

An **event** is the computer's way of sticking up its hand to say, "Hey, this just happened!"

For example, in a car a driver will typically use at least two pedals. The car has been designed to respond differently when the driver interacts with each of the different pedals:

- The accelerator makes the car go faster
- The brake slows it down

Programmers choose which event s they respond to. When a specific event happens, that event can be used to trigger a specific section of the code.

#### METHODS

Methods represent things people need to do with objects. They can retrieve or update the values of an object's properties.

They are like questions and instruction s that:

- Tell you something about that object (using information stored in its properties)
- Change t he value of one or more of that object's properties

The code for a method can contain lots of instructions that together represent one task.

#### PUTTING IT ALL TOGETHER

Computers use data to create models of things in the real world. The events, methods, and properties of an object all relate to each other: Events can trigger methods, and methods can retrieve or update an object's properties.

**Web browsers are programs built using objects**: Web browsers create similar models of the web page they are showing and of the browser window that the page is being shown in.

- **Window object**: A model of a computer with a browser open on the screen.
- **Document object**: Each window is modelled using a document object.

Using the document object, you can access and change what content users see on the page and respond to how they interact with it.

Like other objects that represent real-world things, the document object has:

- **Properties**: Properties describe characteristics of the current web page (such as the title of the page).
- **Methods**: Methods perform tasks associated with the document currently loaded in the browser (such as getting information from a specified element or adding new content).
- **Events**: You can respond to events, such as a user clicking or tapping on an element.

### HOW HTML, CSS, & JAVASCRIPT FIT TOGETHER

Web developers usually talk about three languages that are used to create web pages: HTML, CSS, and JavaScript.

Where possible, aim to keep the three languages in separate files, with the HTML page linking to CSS and JavaScript files.

Each language forms a separate **layer** with a different purpose.

- **Content layer** (*.html*): This is where the content of the page lives. The HTML gives the page structure and adds semantics.
- **Presentation layer** (*.css*): The CSS enhances the HTML page with rules that state how the HTML content is presented (backgrounds, borders, box dimensions, colors, fonts, etc).
- **Behaviour layer** (*.js): This is where we can change how the page behaves, adding interactivity. We will aim to keep as much of our JavaScript as possible in separate files.

These three layers form the basis of a popular approach to building web pages called **progressive enhancement**.

#### CREATING A BAS IC JAVASCRIPT

JavaScript is written in plain text, just like HTML and CSS, so you do not need any new tools to write a script. This example adds a greeting into an HTML page.

```javascript
var today= new Date();
var hourNow = today.getHours();
var greeting ;
if (hourNow > 18) {
    greeting= 'Good evening!';
else if (hourNow > 12) {
    greeting = ' Good afternoon!';
else if (hourNow > 0) {
    greeting = 'Good morni ng!';
else {
    greeting = 'Welcome! ' ;
    document .write( ' <h3>' +greeting+ ' </ h3> ');
```

#### LINKING TO A JAVASCRIPT FILE FROM AN HTML PAGE

When you want to use JavaScript with a web page, you use the HTML `<script>` element to tell the browser it is coming across a script. Its `src` attribute tells people where the JavaScript file is stored.

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Constructive &amp; Co. </title>
        <link rel ="stylesheet " href="css/cOl.css" />
    </head>
    <body>
        <h1>Constructive &amp; Co.</h1>
        <script src="js/add-content.js"></script>
        <p>For all orders and inquiries please call
        <em>SSS-3344</em></p>
    </body>
</html>
```

#### PLACING THE SCRIPT IN THE PAGE

You may see JavaScript in the HTML between opening `<script>` and closing `</script>` tags (but it is better to put scripts in their own fil es).

```html
<!DOCTYPE html >
<html>
    <head>
        <title>Constructive &amp; Co. </title>
        <link rel ="stylesheet" href="css/cOl.css" />
    </head>
    <body>
        <h1>Constructive &amp; Co. </h1>
        <script>
            document.write(' <h3>Welcome!</h3>');
        </script>
        <p>For all orders and inquiries please call
        <em>555-3344</em></p>
    </body>
</html>
```
