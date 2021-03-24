# Forms and Events

![html forms image](https://744025.smushcdn.com/1245953/wp-content/uploads/2020/03/html-forms.jpg?lossy=1&strip=1&webp=1)

## HTML FORMS

HTML Forms are required, when you want to collect some data from the site visitor. For example, during user registration you would like to collect information such as name, email address, credit card, etc.

The HTML `<form>` tag is used to create an HTML form and it has following syntax −

```html
<form action = "Script URL" method = "GET|POST">
   form elements like input, textarea etc.
</form>
```

### FHow Forms Work

1. A user fills in a form and then presses a button to submit the information to the server.
2. The name of each form control is sent to the server along with the value the user enters or selects.
3. The server processes the information using a programming language such as PHP, C#, VB.net, or Java. It may also store the information in a database.

A form may have several form controls, each gathering different information. The server needs to know which piece of inputted data corresponds with which form element.

### Form Attributes

Fllowing is a list of the most frequently used form attributes:

**action** Backend script ready to process your passed data.

**method** Method to be used to upload data. The most frequently used are GET and POST methods.

**target** Specify the target window or frame where the result of the script will be displayed. It takes values like _blank,_self, _parent etc.

**enctype** You can use the enctype attribute to specify how the browser encodes the data before it sends it to the server. Possible values are :

- *application/x-www-form-urlencoded* − This is the standard method most forms use in simple scenarios.
- *mutlipart/form-data* − This is used when you want to upload binary data in the form of files like image, word file etc

![html form example image](https://disenowebakus.net/en/images/articles/forms-html-examples-styles-css-for-controls.jpg)

### HTML Form Controls

There are different types of form controls that you can use to collect data using HTML form −

- Text Input Controls
- Checkboxes Controls
- Radio Box Controls
- Select Box Controls
- File Select boxes
- Hidden Controls
- Clickable Buttons
- Submit and Reset Button

#### Text Input Controls

There are three types of text input used on forms:

- **Single-line text input controls** − This control is used for items that require only one line of user input, such as search boxes or names. They are created using HTML `<input>` tag.
- **Password input controls** − This is also a single-line text input but it masks the character as soon as a user enters it. They are also created using HTMl `<input>` tag.
- **Multi-line text input controls** − This is used when the user is required to give details that may be longer than a single sentence. Multi-line input controls are created using HTML `<textarea>` tag.

![text input image](https://static.javatpoint.com/htmlpages/images/html-textfield-control.png)

**Example** Here is a basic example of a single-line text input used to take first name and last name:

```html
<!DOCTYPE html>
<html>
   <head>
      <title>Text Input Control</title>
   </head>
   <body>
      <form >
         First name: <input type = "text" name = "first_name" />
         <br>
         Last name: <input type = "text" name = "last_name" />
      </form>
   </body>
</html>
```

#### Attributes

Following is the list of attributes for `<input>` tag for creating text field.

`type` Indicates the type of input control and for text input control it will be set to text.

`name` Used to give a name to the control which is sent to the server to be recognized and get the value.

`value` This can be used to provide an initial value inside the control.

`size` Allows to specify the width of the text-input control in terms of characters.

`maxlength` Allows to specify the maximum number of characters a user can enter into the text box.

#### Password input controls

This is also a single-line text input but it masks the character as soon as a user enters it. They are also created using HTML `<input>` tag but `type` attribute is set to `password`.

```html
<!DOCTYPE html>
<html>
   <head>
      <title>Password Input Control</title>
   </head>
   <body>
      <form >
         User ID : <input type = "text" name = "user_id" />
         <br>
         Password: <input type = "password" name = "password" />
      </form>
   </body>
</html>
```

![login form gif](https://camo.githubusercontent.com/d669f6e25392fd0a29ab79ecc2286132fdcdd8d1389309942de4fcade73d8916/68747470733a2f2f63646e2e6472696262626c652e636f6d2f75736572732f3430383030312f73637265656e73686f74732f333532343039322f6c6f67696e2d666f726d2e676966)

#### Multiple-Line Text Input Controls

This is used when the user is required to give details that may be longer than a single sentence. Multi-line input controls are created using HTML `<textarea>` tag.

```html
<!DOCTYPE html>
<html>
   <head>
      <title>Multiple-Line Input Control</title>
   </head>
   <body>
      <form>
         Description : <br />
         <textarea rows = "5" cols = "50" name = "description">
            Enter description here...
         </textarea>
      </form>
   </body>
</html>
```

Attributes `name` Used to give a name to the control which is sent to the server to be recognized and get the value. `rows` Indicates the number of rows of text area box. `cols` Indicates the number of columns of text area box.

#### Checkbox Control

Checkboxes are used when more than one option is required to be selected. They are also created using HTML `<input>` tag but `type` attribute is set to **checkbox**.

```html
<!DOCTYPE html>
<html>
   <head>
      <title>Checkbox Control</title>
   </head>
   <body>
      <form>
         <input type = "checkbox" name = "maths" value = "on"> Maths
         <input type = "checkbox" name = "physics" value = "on"> Physics
      </form>
   </body>
</html>
```

#### Select Box Control

A select box, also called drop down box which provides option to list down various options in the form of drop down list, from where a user can select one or more options.

```html
<!DOCTYPE html>
<html>
   <head>
      <title>Select Box Control</title>
   </head>
   <body>
      <form>
         <select name = "dropdown">
            <option value = "Maths" selected>Maths</option>
            <option value = "Physics">Physics</option>
         </select>
      </form>
   </body>
</html>
```

![select input image](https://www.htmlgoodies.com/img/2010/05/HTML-Forms-From-Basics-to-Style-The-Rest-of-the-Input-Fields-Figure2.gif)

#### File Upload Box

If you want to allow a user to upload a file to your web site, you will need to use a file upload box, also known as a file select box. This is also created using the `<input>` element but `type` attribute is set to **file**.

```html
<!DOCTYPE html>
<html>
   <head>
      <title>File Upload Box</title>
   </head>
   <body>
      <form>
         <input type = "file" name = "fileupload" accept = "image/*" />
      </form>
   </body>
</html>
```

![file input image](http://swatelier.info/at/screen/formFile1.png)

#### Button Controls

There are various ways in HTML to create clickable buttons. You can also create a clickable button using `<input>` tag by setting its `type` attribute to **button**. The `type` attribute can take the following values:

```html
<!DOCTYPE html>
<html>
   <head>
      <title>File Upload Box</title>
   </head>
   <body>
      <form>
         <input type = "submit" name = "submit" value = "Submit" />
         <input type = "reset" name = "reset"  value = "Reset" />
         <input type = "button" name = "ok" value = "OK" />
         <input type = "image" name = "imagebutton" src = "/html/images/logo.png" />
      </form>
   </body>
</html>
```

![button input](https://d2h0cx97tjks2p.cloudfront.net/blogs/wp-content/uploads/sites/2/2020/07/HTML-Button-DF.jpg)

## HTML - Lists

HTML offers web authors three ways for specifying lists of information. All lists must contain one or more list elements. Lists may contain −

- UnOrdered list
- Ordered list
- Description Lists

### Ordered Lists

- `<ol>` The ordered list is created with the `<ol>` element.
- `<li>` Each item in the list is placed between an opening `<li>` tag and a closing `</li>` tag.(The li stands for list item.)

### UnOrdered List

- `<ul>` The unordered list is created with the `<ul>` element.
- `<li>` Each item in the list is placed between an opening `<li>` tag and a closing `</li>` tag. (The li stands for list item.)

```html
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
```

![html lists](https://www.w3.org/wiki/images/5/5e/Referenc.gif)

### Description Lists

A description list is a list of terms, with a description of each term. The `<dl>` tag defines the description list, the `<dt>` tag defines the term (name), and the `<dd>` tag describes each term:

```html
<dl>
  <dt>Coffee</dt>
  <dd>- black hot drink</dd>
  <dt>Milk</dt>
  <dd>- white cold drink</dd>
</dl>
```

![description list image](https://flylib.com/books/4/324/1/html/2/images/fig03_09.jpg)

## HTML - Tables

The HTML tables allow web authors to arrange data like text, images, links, other tables, etc. into rows and columns of cells.

The HTML tables are created using the `<table>` tag in which the `<tr>` tag is used to create table rows and `<td>` tag is used to create data cells. The elements under `<td>` are regular and left aligned by default

```html
<!DOCTYPE html>
<html>

   <head>
      <title>HTML Tables</title>
   </head>
   <body>
      <table border = "1">
         <tr>
            <td>Row 1, Column 1</td>
            <td>Row 1, Column 2</td>
         </tr>
         
         <tr>
            <td>Row 2, Column 1</td>
            <td>Row 2, Column 2</td>
         </tr>
      </table>
      
   </body>
</html>
```

Here, the border is an attribute of `<table>` tag and it is used to put a border across all the cells. If you do not need a border, then you can use border = "0".

![html table example image](https://www.homeandlearn.co.uk/WD/images/chapter7/basic_table.gif)

### Table Heading

Table heading can be defined using `<th>` tag. This tag will be put to replace `<td>` tag, which is used to represent actual data cell. Normally you will put your top row as table heading as shown below, otherwise you can use `<th>` element in any row. Headings, which are defined in `<th>` tag are centered and bold by default.

```html
<!DOCTYPE html>
<html>

   <head>
      <title>HTML Table Header</title>
   </head>
   <body>
      <table border = "1">
         <tr>
            <th>Name</th>
            <th>Salary</th>
         </tr>
         <tr>
            <td>Ramesh Raman</td>
            <td>5000</td>
         </tr>
         
         <tr>
            <td>Shabbir Hussein</td>
            <td>7000</td>
         </tr>
      </table>
   </body>
   
</html>
```

![html table with heading image](https://static.javatpoint.com/htmlpages/images/html-table-width.png)

### Cellpadding and Cellspacing Attributes

There are two attributes called **cellpadding** and **cellspacing** which you will use to adjust the white space in your table cells. The cellspacing attribute defines space between table cells, while cellpadding represents the distance between cell borders and the content within a cell.

```html
<!DOCTYPE html>
<html>

   <head>
      <title>HTML Table Cellpadding</title>
   </head>
   <body>
      <table border = "1" cellpadding = "5" cellspacing = "5">
         <tr>
            <th>Name</th>
            <th>Salary</th>
         </tr>
         <tr>
            <td>Ramesh Raman</td>
            <td>5000</td>
         </tr>
         <tr>
            <td>Shabbir Hussein</td>
            <td>7000</td>
         </tr>
      </table>
   </body>
</html>
```

### Colspan and Rowspan Attributes

You will use **colspan** attribute if you want to merge two or more columns into a single column. Similar way you will use rowspan if you want to merge two or more rows.

```html
<!DOCTYPE html>
<html>
   <head>
      <title>HTML Table Colspan/Rowspan</title>
   </head>
   <body>
      <table border = "1">
         <tr>
            <th>Column 1</th>
            <th>Column 2</th>
            <th>Column 3</th>
         </tr>
         <tr>
            <td rowspan = "2">Row 1 Cell 1</td>
            <td>Row 1 Cell 2</td>
            <td>Row 1 Cell 3</td>
         </tr>
         <tr>
            <td>Row 2 Cell 2</td>
            <td>Row 2 Cell 3</td>
         </tr>
         <tr>
            <td colspan = "3">Row 3 Cell 1</td>
         </tr>
      </table>
   </body>
</html>
```

### Table Header, Body, and Footer

Tables can be divided into three portions − a **header**, a **body**, and a **foot**. The head and foot are rather similar to headers and footers in a word-processed document that remain the same for every page, while the body is the main content holder of the table.

The three elements for separating the head, body, and foot of a table are:

- `<thead>` − to create a separate table header.
- `<tbody>` − to indicate the main body of the table.
- `<tfoot>` − to create a separate table footer.

A table may contain several `<tbody>` elements to indicate different pages or groups of data. But it is notable that `<thead>` and `<tfoot>` tags should appear before `<tbody>`

```html
<!DOCTYPE html>
<html>
   <head>
      <title>HTML Table</title>
   </head>
   <body>
      <table border = "1" width = "100%">
         <thead>
            <tr>
               <td colspan = "4">This is the head of the table</td>
            </tr>
         </thead>   
         <tfoot>
            <tr>
               <td colspan = "4">This is the foot of the table</td>
            </tr>
         </tfoot>
         <tbody>
            <tr>
               <td>Cell 1</td>
               <td>Cell 2</td>
               <td>Cell 3</td>
               <td>Cell 4</td>
            </tr>
         </tbody>
         
      </table>
   </body>
</html>
```

![html table elements image](https://camo.githubusercontent.com/243353e8c65e66880adbde5f157f788fe56b1b04b15fa3e7af358b88c00260d5/68747470733a2f2f74656d706c617465666f722e6e65742f77702d636f6e74656e742f75706c6f6164732f323031392f30392f48544d4c2d5461626c652d4353532d5461626c652e6a7067)

### Table Borders

To specify table borders in CSS, use the `border` property.

The example below specifies a black border for `<table>`, `<th>`, and `<td>` elements:

```css
table, th, td {
  border: 1px solid black;
}
```

### Collapse Table Borders

The `border-collapse` property sets whether the table borders should be collapsed into a single border:

```css
table {
  border-collapse: collapse;
}

table, th, td {
  border: 1px solid black;
}
```

### Striped Tables

For zebra-striped tables, use the `nth-child()` selector and add a `background-color` to all even (or odd) table rows:

![striped table image](https://camo.githubusercontent.com/98d795acc4652b57a8f387d61724195a78a5b591a1806cab8fb8616637179626/68747470733a2f2f656e637279707465642d74626e302e677374617469632e636f6d2f696d616765733f713d74626e253341414e6439476352433558392d566666395275497055424442714570573632366e67553136476c4c374d63753458545666426f6e736354344226757371703d434155)

```css
tr:nth-child(even) {background-color: #f2f2f2;}
```

![javascript image](https://res.cloudinary.com/practicaldev/image/fetch/s--ohpJlve1--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://res.cloudinary.com/drquzbncy/image/upload/v1586605549/javascript_banner_sxve2l.jpg)

## JavaScript Form Event

![javascript events image](https://www.edureka.co/blog/wp-content/uploads/2019/09/Events-in-JavaScript.jpg)

A form event is fired when a form control receive or loses focus or when the user modify a form control value such as by typing text in a text input, select any option in a select box etc. Here're some most important form events and their event handler.

### The Focus Event (onfocus)

This event occurs when an element gets focused on a web page. The `onfocus` event handler is used to handle this event.

The following example will highlight the background of text input in green color when it receives the focus.

![focus event image](https://camo.githubusercontent.com/64827d783b9ab21ebfe40bbb96f3658948ac918c6f864bb8b4cf57cfeafd53e1/68747470733a2f2f692e737461636b2e696d6775722e636f6d2f4d654b777a2e676966)

```html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <title> JavaScript Handling the Focus Event </title>
</head>
<body>
    <script>
        function highlightInput(elm){

            elm.style.background = "lightgreen";

        }    
    </script>
    <input type="text" onfocus="highlightInput(this)">
    <button type="button">Button</button>
</body>
</html>
```

### The Blur Event (onblur)

This event occurs when the user takes the focus away from a form element. The `onblur` event handler is used to handle this event.

![blur event image](https://user-images.githubusercontent.com/4082216/45522897-f6978200-b793-11e8-99ce-7a5f34c2e042.gif)

```html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <title> JavaScript OnBlur Event </title>
</head>
<body>
 <input type="text" onblur="alert('Text input loses focus!')">
 <button type="button">Submit</button>
</body>
</html>
```

### The Change Event (onchange)

This event occurs when the value of a form element is changed. The `onchange` event handler is used to handle this event.

![onchange event image](https://camo.githubusercontent.com/e68103f04a34c5fd348b4fb2917bf0b41343a6474add44fe3eb4a4c3fc635dae/68747470733a2f2f342e62702e626c6f6773706f742e636f6d2f2d4f4a4a707452414b4a594d2f57324d7a6f534c5f7573492f41414141414141414670412f77444b79316b645566424d4d7569644e6159436e6e4235306f314f466f50576b77434c63424741732f73313630302f2532353430496e70757454776f57617942696e64696e672e676966)

```html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <title> JavaScript OnChange Event </title>
</head>
<body>
   <select onchange="alert('You have changed the selection!');">
    <option>Select</option>
    <option>OnePlus</option>
    <option>Samsung</option>
    </select>
  <p><strong>Note:</strong> Select any option in select box to see how it works.</p>
</body>
</html>
```

### The Submit Event (onsubmit)

The submit event occurs when the submit button is clicked. The `onsubmit` event handler is used to handle this event.

![onsubmitt event image](https://camo.githubusercontent.com/6f2d93b0fd4592b5ed18e29cb9f64a3e8f1ad8059daed62e661b5813fc29a1e8/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f323536302f312a4751327836306d797273667454634c587a4659394c672e676966)

```html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <title> JavaScript OnSubmit Event </title>
</head>
<body>
  <form action="../index.php" method="post" onsubmit="alert('Form data will be submitted to 
  the server!');">
     <label>First Name:</label>
     <input type="text" name="first-name" required>
     <input type="submit" value="Submit">
  </form>
</body>
</html>
```
