# HTML Links, JS Functions, and Intro to CSS Layout

![html links image](https://1.bp.blogspot.com/-TZqlIKhGRaQ/VubNV0HuMzI/AAAAAAAAG6c/d7DWNFoX3w87luF3-ye_hE23R7PNRMDgg/s1600/link.png)

## HTML Links

A webpage can contain various links that take you directly to other pages and even specific parts of a given page. These links are known as hyperlinks.

Hyperlinks allow visitors to navigate between Web sites by clicking on words, phrases, and images. Thus you can create hyperlinks using text or images available on a webpage.

### Writing Links

Links are created using the `<a>` element. Users can click on anything between the opening `<a>` tag and the closing `</a>` tag. You specify which page you want to link to using the href attribute.

```html
<a href="http://www.imdb.com">IMDB</a>
```

- The text between the opening `<a>` tag and closing `</a>` tag is known as link text.
- href attributes contains the page the link takes you to

### Linking to another page

When you are linking to other pages within the same site, you do not need to specify the domain name in the URL. You can use a shorthand known as a relative URL.

![html hyperlink image](https://camo.githubusercontent.com/65c676c8f24496712467d44e4120bd716eaa5699a42c8bd70e4a88f80641c554/68747470733a2f2f7777772e636f6d7075746572686f70652e636f6d2f6a6172676f6e2f682f68746d6c2d7461672e676966)

### Directory structure

On larger websites it's a good idea to organize your code by placing the pages for each different section of the site into a new folder. Folders on a website are sometimes referred to as directories.

![Directory structure image](https://camo.githubusercontent.com/4ba849754d270eddb77c92c47a7a3d5ab52d000dea9792730bb4cef5940f19d9/68747470733a2f2f73747579687364657369676e2e66696c65732e776f726470726573732e636f6d2f323031352f30392f6469726563746f72792d737472756374757265312e706e673f773d363536)

**Structure**:

The diagram on the right shows the directory structure for a fictional entertainment listings website called ExampleArts. The top-level folder is known as the root folder. (In this example, the root folder is called examplearts.) The root folder contains all of the other files and folders for a website.

**RelationShips**:

The relationship between files and folders on a website is described using the same terminology as a family tree.

**HomePages**:

The main homepage of a site written in HTML (and the homepages of each section in a child folder) is called index.html.

### Relative URL

Relative URLs can be used when linking to pages within your own website. They provide a shorthand way of telling the browser where to find your files.

### Email Link

'mailto': To create a link that starts up the user's email program and addresses an email to a specified email address, you use the `<a>` element. However, this time the value of the href attribute starts with mailto: and is followed by the email address you want the email to be sent to.

```html
<a href="mailto:myemail@hostname.com"></a>
```

### Opnning links in a new window

`target`: If you want a link to open in a new window, you can use the target attribute on the opening `<a>` tag. The value of this attribute should be _blank

```html
<a href="https://www.mywebsite.com" target="_blank"></a>
```

### Linking specific part on the same page

`#`: At the top of a long page you might want to add a list of contents that links to the corresponding sections lower down. Or you might want to add a link from part way down the page back to the top of it to save users from having to scroll back to the top.

## Layout

![layout image](https://miro.medium.com/max/3392/1*ia4V5qfk6Ki3iWIn-SmErw.png)

A webpage layout is very important to give better look to your website. It takes considerable time to design a website's layout with great look and feel.

Now-a-days, all modern websites are using CSS and JavaScript based framework to come up with responsive and dynamic websites but you can create a good layout using simple HTML tables or division tags in combination with other formatting tags.

### Key ConCepts in positioning eLements

**Building Blocks**:

CSS treats each HTML element as if it is in its own box. This box will either be a block-level box or an inline box

Block-level boxes start on a new line and act as the main building blocks of any layout `<h1>`, `<p>`, `<ul>`, `<li>`, while inline boxes flow between surrounding text `<img>`, `<b>`, `<i>`. You can control how much space each box takes up by setting the width of the boxes (and sometimes the height, too). To separate boxes, you can use borders, margins, padding, and background colors.

![block and inline block example image](https://camo.githubusercontent.com/ec633e4757c67c915d8e1325dfb960ba82609ebbb67944a64ba4e09463c31867/68747470733a2f2f692e6962622e636f2f523335334852642f53637265656e2d53686f742d323032302d30362d30392d61742d31352d34352d32322e706e67)

**Containing Elements**:

If one block-level element sits inside another block-level element then the outer box is known as the containing or parent element.

![Containing Elements example image](https://camo.githubusercontent.com/9fdbf4752db444d03bec01213dbfab9880074e7ae0ffa27ef66cefd9e9dfabb7/68747470733a2f2f692e6962622e636f2f6b67674a6b584e2f53637265656e2d53686f742d323032302d30362d30392d61742d31352d34362d30372e706e67)

### Controlling the Position of Elements

CSS has the following positioning schemes that allow you to control the layout of a page: normal flow, relative positioning, and absolute positioning. You specify the positioning scheme using the position property in CSS. You can also float elements using the float property.

- Normal flow
- Relative Positioning
- Absolute Positioning
- fixed Positioning
- floating elements

**Normal flow**: Every block-level element appears on a new line, causing each item to appear lower down the page than the previous one. Even if you specify the width of the boxes and there is space for two elements to sit side-by- side, they will not appear next to each other. This is the default behavior (unless you tell the browser to do something else).

**Relative Positioning**: This moves an element from the position it would be in normal flow, shifting it to the top, right, bottom, or left of where it would have been placed. This does not affect the position of surrounding elements; they stay in the position they would be in in normal flow.

**Absolute Positioning**: This positions the element in relation to its containing element. It is taken out of normal flow, meaning that it does not affect the position of any surrounding elements (as they simply ignore the space it would have taken up). Absolutely positioned elements move as users scroll up and down the page.

**Fixed Positioning**: This is a form of absolute positioning that positions the element in relation to the browser window, as opposed to the containing element. Elements with fixed positioning do not affect the position of surrounding elements and they do not move when the user scrolls up or down the page

**Floating elements**: Floating an element allows you to take that element out of normal flow and position it to the far left or right of a containing box. The floated element becomes a block-level element around which other content can flow.

![controlling the Position of Elements image](https://camo.githubusercontent.com/0279f43c52d6b7d0ac68417b269b384b53ed509c109c369a77d34ddac7263576/68747470733a2f2f6b6f767368656e696e2e636f6d2f77702d636f6e74656e742f75706c6f6164732f73697465732f352f323031302f30332f706f736974696f6e2d72656c61746976652d342e706e67)

**Article Flow** `position:static`:

In normal flow, each block-level element sits on top of the next one. Since this is the default way in which browsers treat HTML elements, you do not need a CSS property to indicate that elements should appear in normal flow, but the syntax would be: position: static;

**ReLative Posionining** `position:relative`:

Relative positioning moves an element in relation to where it would have been in normal flow. For example, you can move it 10 pixels lower than it would have been in normal flow or 20% to the right.

You then use the offset properties (top or bottom and left or right) to indicate how far to move the element from where it would have been in normal flow.

**Absolute Positioning** `position:absolute`

When the position property is given a value of absolute, the box is taken out of normal flow and no longer affects the position of other elements on the page. (They act like it is not there.) The box offset properties (top or bottom and left or right) specify where the element should appear in relation to its containing element.

**Fixed Positioning** `position:fixed`:

Fixed positioning is a type of absolute positioning that requires the position property to have a value of fixed. It positions the element in relation to the browser window. Therefore, when a user scrolls down the page, it stays in the exact same place. It is a good idea to try this example in your browser to see the effect.

![positioning example image](https://camo.githubusercontent.com/f8adb5a8731c85f64f938e444a5a98939058d3dfb6c5b649b590bf3a237629e4/68747470733a2f2f656e637279707465642d74626e302e677374617469632e636f6d2f696d616765733f713d74626e253341414e64394763514d57437873485258766e70344a66694f4779746f596c5a3836416e316e446d74366b726d724f416e6962536d4f396e4c7526757371703d434155)

**Overlapping Element** `z-index`:

When you use relative, fixed, or absolute positioning, boxes can overlap. If boxes do overlap, the elements that appear later in the HTML code sit on top of those that are earlier in the page, so we can use `z-index` to inforce which elements will appear at the top (the larger the number the element will be at the top).

![z-index image](https://camo.githubusercontent.com/562a97df4ab4b316f8c34067c55c1253d4473fd5f2f976f02320cdccd382662c/68747470733a2f2f656c656d656e746f722e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031372f30362f7a2d696e6465782e706e67)

**Floating** `float`:

The float property allows you to take an element in normal flow and place it as far to the left or right of the containing element as possible.

```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            img {
                float: left;
            }
        </style>
    </head>
    <body>

        <p>
            In this example, the image will float to the left in the paragraph, and the text in the paragraph will wrap around the image.
        </p>

        <p>
            <img src="pineapple.jpg" alt="Pineapple" style="width:170px;height:170px;margin-right:15px;">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus imperdiet, nulla et dictum interdum, nisi lorem egestas odio, vitae scelerisque enim ligula venenatis dolor. Maecenas nisl est, ultrices nec congue eget, auctor vitae massa. Fusce luctus vestibulum augue ut aliquet. Mauris ante ligula, facilisis sed ornare eu, lobortis in odio. Praesent convallis urna a lacus interdum ut hendrerit risus congue. Nunc sagittis dictum nisi, sed ullamcorper ipsum dignissim ac. In at libero sed nunc venenatis imperdiet sed ornare turpis. Donec vitae dui eget tellus gravida venenatis. Integer fringilla congue eros non fermentum. Sed dapibus pulvinar nibh tempor porta. Cras ac leo purus. Mauris quis diam velit.
        </p>

    </body>
</html>
```

![float example image](https://camo.githubusercontent.com/7867b22c850fec06604f8b013991a05dcafbc5a1bc40843c0c13d16c8026a247/68747470733a2f2f7777772e666f726d6765742e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031342f30392f666c6f61742d6c6566742e706e67)

### Screen Size and Reselution

Different visitors to your site will have different sized screens that show different amounts of information, so your design needs to be able to work on a range of different sized screens.

Resolution refers to the number of dots a screen shows per inch. Some devices have a higher resolution than desktop computers and most operating systems allow users to adjust the resolution of their screens

![screen size image](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSg3341UfZXz5fjhQTvYvOsMEm31JVj9cw7VQ&usqp=CAU)

### page sizes

Because screen sizes and display resolutions vary so much, web designers often try to create pages of around 960-1000 pixels wide (since most users will be able to see designs this wide on their screens).

### Fixed width Layouts

Fixed width layout designs do not change size as the user increases or decreases the size of their browser window. Measurements tend to be given in pixels.

**Advantages**:

- Pixel values are accurate at controlling size and positioning of elements
- The designer has far greater control over the appearance and position of items on the page than with liquid layouts
- You can control the lengths of lines of text regardless of the size of the user's window
- The size of an image will always remain the same relative to the rest of the page

**Dissadvantages**:

- You can end up with big gaps around the edge of a page
- If the user's screen is a much higher resolution than the designer's screen, the page can look smaller and text can be harder to read
- If a user increases font sizes, text might not fit into the allotted spaces
- The design works best on devices that have a site or resolution similar to that of desktop or laptop computers
- The page will often take up more vertical space than a liquid layout with the same content.

### Liquid Layouts

Liquid layout designs stretch and contract as the user increases or decreases the size of their browser window. They tend to use percentages.

**Advantages**:

- Pages expand to fill the entire browser window so there are no spaces around the page on a large screen
- If the user has a small window, the page can contract to fit it without the user having to scroll to the side
- The design is tolerant of users setting font sizes larger than the designer intended (because the page can stretch)

**Dissadvantages**:

- If you do not control the width of sections of the page then the design can look very different than you intended, with unexpected gaps around certain elements or items squashed together
- If the user has a wide window, lines of text can become very long, which makes them harder to read
- If the user has a very narrow window, words may be squashed and you can end up with few words on each line
- If a fixed width item (such as an image) is in a box that is too small to hold it (because the user has made the window smaller) the image can overflow over the text

### Layout grids

Composition in any visual art (such as design, painting, or photography) is the placement or arrangement of visual elements — how they are organized on a page. Many designers use a grid structure to help them position items on a page, and the same is true for web designers.

possibLe Layouts: 960 pixeL wide 12 CoLumn grid

### CSS frameworks

CSS frameworks aim to make your life easier by providing the code for common tasks, such as creating layout grids, styling forms, creating printer-friendly versions of pages and so on. You can include the CSS framework code in your projects rather than writing the CSS from scratch.

**Advantages**:

- They save you from repeatedly writing code for the same tasks
- They will have been tested across different browser versions (which helps avoid browser bugs)

**Disadvantages**:

- They often require that you use class names in your HTML code that only control the presentation of the page (rather than describe its content)
- In order to satisfy a wide variety of needs, they often contain more code than you need for your particular web page (commonly referred to as code “bloat”)

### Multiple style sheets

`@import link`:

There are two ways to add multiple style sheets to a page:

1. Your HTML page can link to one style sheet and that stylesheet can use the `@import` rule to import other style sheets.
2. In the HTML you can use a separate `<link>` element for each style sheet.

```css
/ CSS File

@import url("tables.css"); 
@import url("typography.css"); 
body {
    color: #666666; background-color: #f8f8f8; text-align: center;
}
#page {
    width: 600px;
    text-align: left; margin-left: auto; margin-right: auto; border: 1px solid #d6d6d6; padding: 20px;
}
h3 {
  color: #547ca0;
}

<!-- HTML -->

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

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Multiple Style Sheets - Link</title> 
        <link rel="stylesheet" type="text/css" href="css/site.css" />
        <link rel="stylesheet" type="text/css" href="css/tables.css" />
        <link rel="stylesheet" type="text/css"href="css/typography.css" /> 
    </head>
    <body>
        <!-- HTML page content here -->
    </body>
</html>
```

## JavaScript

![javascript image](http://crowdforthink.com/assets/uploads/blogs/f95b8815ecdfedc8ef0d66ac816d5027.png)

### Functions

Functions let you group a series of statements together to perform a specific task. If different parts of a script repeat the same task, you can reuse the function (rather than rep eating the same set of st atements).

### Declaring a function

To create  a function, follow the syntax below:

```javascript
function fuctionName (params,){
    instructions // (you can use params here)
    return returnedValue
}


```

### Calling a function

To call a function just use

```javascript
functionName (params,);
```

If the functoin return some value, you can store the returned value in a variable.

```javascript
var value = functionName (params,);
```

You can return multiple values from the function using an array.

```javascript
function fuctionName (wisth, height, depth){
    var area = width * height;
    var volume = area * depth;
    var size = [area, volume];
    return size;
}

```
