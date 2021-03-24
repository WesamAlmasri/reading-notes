# More CSS Layout

![css lauout image](https://image.shutterstock.com/image-vector/website-layout-vector-icon-600w-711243937.jpg)

## Layout

### Key Concepts in Positioning Elements

#### Building Blocks

CSS treats each HTML element as if it is in its own box. This box will either be a block-level box or an inline box.

Block-level boxes start on a new line and act as the main building blocks of any layout, while inline boxes flow between surrounding text. You can control how much space each box takes up by setting the width of the boxes (and sometimes the height, too). To separate boxes, you can use borders, margins, padding, and background colors.

![inline and block element image](https://res.cloudinary.com/practicaldev/image/fetch/s--1AHNQEX1--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/cvmm4upglik4tgf4azse.png)

![inline and block tags element image](https://www.differencebetween.com/wp-content/uploads/2018/02/Difference-Between-Block-and-Inline-Elements-fig-1.png)

#### Containing Elements

If one block-level element sits inside another block-level element then the outer box is known as the **containing** or **parent** element.
It is common to group a number of elements together inside a `<div>` (or other block-level) element. For example, you might group together all of the elements that form the header of a site (such as the logo and the main navigation). The `<div>` element that contains this group of elements is then referred to as the containing element.

### Controlling the Position of Elements

CSS has the following **positioning schemes** that allow you to control the layout of a page: normal flow, relative positioning, and absolute positioning. You specify the positioning scheme using the position property in CSS. You can also float elements using the float property.

![controlling the postion of elements image](https://www.internetingishard.com/html-and-css/advanced-positioning/css-positioning-schemes-790d5b.png)

#### Normal flow

Every block-level element appears on a new line, causing each item to appear lower down the page than the previous one. Even if you specify the width of the boxes and there is space  for two elements to sit side-by- side, they will not appear next to each other. This is the default behavior (unless you tell the browser to do something else).

**`position:static`**:

```html
<body>
<h1>The Evolution of the Bicycle</h1>
<p>In 1817 Baron von Drais invented a walking
        machine that would help him get around the
        royal gardens faster...</p>
</body>
```

```css
body {
width: 750px;
font-family: Arial, Verdana, sans-serif;
color: #665544;}
h1 {
background-color: #efefef;
padding: 10px;}
p {
width: 450px;}
```

#### Relative Positioning

This moves an element from the position it would be in normal flow, shifting it to the top, right, bottom, or left of where it would have been placed. This does not affect the position of surrounding elements; they stay in the position they would be in in normal flow.

**`position:relative`**:

```html
<body>
<h1>The Evolution of the Bicycle</h1>
<p>In 1817 Baron von Drais invented a walking
        machine that would help him get around the
        royal gardens faster...</p>
</body>
```

```css
p.example {
position: relative;
top: 10px;
left: 100px;}
```

#### Absolute positioning

This positions the element in relation to its containing element. It is taken out of normal flow, meaning that it does not affect the position of any surrounding elements (as they simply ignore the space it would have taken up). Absolutely positioned elements move as users scroll up and down the page.

**`position:absolute`**:

```html
<body>
<h1>The Evolution of the Bicycle</h1>
<p>In 1817 Baron von Drais invented a walking
        machine that would help him get around the
        royal gardens faster...</p>
</body>
```

```css
h1 {
position: absolute;
top: 0px;
left: 500px;
width: 250px;}
p {
width: 450px;}
```

To indicate where a box should be positioned, you may also need to use **box offset** properties to tell the browser how far from the top or bottom and left or right it should be placed.

#### Fixed Positioning

This is a form of absolute positioning that positions the element in relation to the browser window, as opposed to the containing element. Elements with fixed positioning do not affect the position of surrounding elements and they do not move when the user scrolls up or down the page.

**`position:fixed`**:

```html
<body>
<h1>The Evolution of the Bicycle</h1>
<p class="example">In 1817 Baron von Drais
        invented a walking machine that would help him
        get around the royal gardens faster...</p>
</body>
```

```css
h1 {
position: fixed;
top: 0px;
left: 50px;
padding: 10px;
margin: 0px;
width: 100%;
background-color: #efefef;}
p.example {
margin-top: 100px;}
```

#### Floating Elements

Floating an element allows you to take that element out of normal flow and position it to the far left or right of a containing box. The floated element becomes a block-level element around which other content can flow.

![float element image](https://imgs.developpaper.com/imgs/aff7250eac6064158021aea86dd4ac65.png)

**`float`**:

```html
<h1>The Evolution of the Bicycle</h1>
<blockquote>"Life is like riding a bicycle.
To keep your balance you must keep moving." -
Albert Einstein</blockquote>
<p>In 1817 Baron von Drais invented a walking
machine that would help him get around the royal
gardens faster: two same-size in-line wheels, the
front one steerable, mounted in a frame ... </p>
```

```css
blockquote {
    float: right;
    width: 275px;
    font-size: 130%;
    font-style: italic;
    font-family: Georgia, Times, serif;
    margin: 0px 0px 10px 10px;
    padding: 10px;
    border-top: 1px solid #665544;
    border-bottom: 1px solid #665544;}
```

When you move any element from normal flow, boxes can overlap. The **z-index** property allows you to control which box appears on top.

### Overlapping Elements

**`z-index`**:

When you use relative, fixed, or absolute positioning, boxes can overlap. If boxes do overlap, the elements that appear later in the HTML code sit on top of those that are earlier in the page.

If you want to control which element sits on top, you can use the z-index property. Its value is a number, and the higher the number the closer that element is to the front. For example, an element with a z-index of 10 will appear over the top of one with a z-index of 5.

```css
h1 {
position: fixed;
top: 0px;
left: 0px;
margin: 0px;
padding: 10px;
width: 100%;
background-color: #efefef;
z-index: 10;}
p {
position: relative;
top: 70px;
left: 70px;}
```

### Clearing Float

**`clear`**:

The clear property allows you to say that no element (within the same containing element) should touch the left or right-hand sides of a box. It can take the following values:

**left**: The left-hand side of the box should not touch any other elements appearing in the same containing element.

**right**: The right-hand side of the box will not touch elements appearing in the same containing element.

**both**: Neither the left nor right-hand sides of the box will touch elements appearing in the same containing element.

**none**: Elements can touch either side.

### Creating Multi-Column Layouts with Floats

Many web pages use multiple columns in their design. This is achieved by using a `<div>` element to represent each column. The following three CSS properties are used to position the columns next to each other:

**width**: This sets the width of the columns.

**float**: This positions the columns next to each other.

**margin**: This creates a gap between the columns.

```html
<h1>The Evolution of the Bicycle</h1>
<div class="column1of2">
<h3>The First Bicycle</h3>
<p>In 1817 Baron von Drais invented a walking
        machine that would help him get around the
        royal gardens faster: two same-size ...</p>
</div>
<div class="column2of2">
<h3>Bicycle Timeline</h3> ...
</div>
```

```css
.column1of2 {
float: left;
width: 620px;
margin: 10px;}
.column2of2 {
float: left;
width: 300px;
margin: 10px;}
```

### Screen Sizes

Different visitors to your site will have different sized screens that show different amounts of information, so your design needs to be able to work on a range of different sized screens.

![differemt sized screems image](https://i.pinimg.com/originals/75/41/cc/7541ccaac266dfbca8d9ab92e0d83c81.png)

### Screen Resolution

Resolution refers to the number of dots a screen shows per inch. Some devices have a higher resolution than desktop computers and most operating systems allow users to adjust the resolution of their screens.

![screen resolution image](https://www.kirupa.com/html5/images/screens.png)

### Page Sizes

Because screen sizes and display resolutions vary so much, web designers often try to create pages of around 960-1000 pixels wide (since most users will be able to see designs this wide on their screens).

![page size image](https://www.dummies.com/wp-content/uploads/395909.image1.jpg)

### Fixed Width Layouts

Fixed width layout designs do not change size as the user increases or decreases the size of their browser window. Measurements tend to be given in pixels.

![Fixed Width Layout image](https://uploads.sitepoint.com/wp-content/uploads/2011/09/layout-fixed.png)

**Advantages**:

- Pixel values are accurate at controlling size and positioning of elements
- The designer has far greater control over the appearance and position of items on the page than with liquid layouts
- You can control the lengths of lines of text regardless of the size of the user's window
- The size of an image will always remain the same relative to the rest of the page

**Disadvantages**:

- You can end up with big gaps around the edge of a page
- If the user's screen is a much higher resolution than the designer's screen, the page can look smaller and text can be harder to read
- If a user increases font sizes, text might not fit into the allotted spaces
- The design works best on devices that have a site or resolution similar to that of desktop or laptop computers.
- The page will often take up more vertical space than a liquid layout with the same content
  
### Liquid Layouts

Liquid layout designs stretch and contract as the user increases or decreases the size of their browser window. They tend to use percentages

![Liquid Layout iamge](https://uploads.sitepoint.com/wp-content/uploads/2011/09/layout-fluid.png)

**Advantages**:

- Pages expand to fill the entire browser window so there are no spaces around the page
on a large screen.
- If the user has a small window, the page can contract to fit it without the user having to scroll to the side.
- The design is tolerant of users setting font sizes larger than the designer intended (because the page can stretch).

**Disadvantages**:

- If you do not control the width of sections of the page then the design can look very different than you intended, with unexpected gaps around certain elements or items squashed together.
- If the user has a wide window, lines of text can become very long, which makes them harder to read.
- If the user has a very narrow window, words may be squashed and you can end up with few words on each line.
- If a fixed width item (such as an image) is in a box that is too small to hold it (because the user has made the window smaller) the image can overflow over the text

### Layout Grids

Composition in any visual art (such as design, painting, or photography) is the placement or arrangement of visual elements — how they are organized on a page. Many designers use a grid structure to help them position items on a page, and the same is true for web designers.

While a grid might seem like a restriction, in actual fact it:

- Creates a continuity between different pages which may use different designs
- Helps users predict where to find information on various pages
- Makes it easier to add new content to the site in a consistent way
- Helps people collaborate on the design of a site in a consistent way

![960 layout grid image](https://i.ytimg.com/vi/XxhhkvP1w_c/hqdefault.jpg)

### CSS Frameworks

CSS frameworks aim to make your life easier by providing the code for common tasks, such as creating layout grids, styling forms, creating printer-friendly versions of pages and so on. You can include the CSS framework code in your projects rather than writing the CSS from scratch.

**ADVANTAGES**:

- They save you from repeatedly writing code for the same tasks
- hey will have been tested across different browser versions (which helps avoid browser bugs)

**DISADVANTAGES**:

- They often require that you use class names in your HTML code that only control the presentation of the page (rather than describe its content)
- In order to satisfy a wide variety of needs, they often contain more code than you need for your particular web page (commonly referred to as code “bloat”)

### Article Style Sheets

**`@import`**:

Some web page authors split up their CSS style rules into separate style sheets. For example, they might use one style sheet to control the layout and another to control fonts, colors and so on.

There are two ways to add multiple style sheets to a page:

1. Your HTML page can link to one style sheet and that stylesheet can use the **`@import`** rule to import other style sheets.
2. In the HTML you can use a separate `<link>` element for each style sheet.

```html
<!DOCTYPE html>
<html>
<head>
        <title>Multiple Style Sheets - Import</title>
        <link rel="stylesheet" type="text/css"
            href="css/styles.css" />
</head>
<body>
        <!-- HTML page content here -->
</body>
</html>
```

```css
@import url("tables.css");
@import url("typography.css");
body {
color: #666666;
background-color: #f8f8f8;
text-align: center;}
#page {
width: 600px;
text-align: left;
margin-left: auto;
margin-right: auto;
border: 1px solid #d6d6d6;
padding: 20px;}
h3 {
color: #547ca0;}
```
