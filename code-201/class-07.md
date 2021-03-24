# Object-Oriented Programming, HTML Tables

![html tables image](https://d2h0cx97tjks2p.cloudfront.net/blogs/wp-content/uploads/sites/2/2020/07/Html-Tables.jpg)

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

![html table elements image](https://camo.githubusercontent.com/243353e8c65e66880adbde5f157f788fe56b1b04b15fa3e7af358b88c00260d5/68747470733a2f2f74656d706c617465666f722e6e65742f77702d636f6e74656e742f75706c6f6164732f323031392f30392f48544d4c2d5461626c652d4353532d5461626c652e6a7067)

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

![javascript oop image](https://i.morioh.com/2020/02/29/d963763934d4.jpg)

## Functions, Methods, and Objects

### JavaScript Objects

In JavaScript, an object is data, with properties and methods.

When you declare a JavaScript variable like this:

`var message="Hello World!";`

You create a JavaScript String object.

The String object has a built-in property called length. For the string above, length has the value 12.

The String object also have several built-in methods.

#### Accessing Object Properties

**`objectName.propertyName`**

```javascript
var message = "Hello world!";
var messageLength = message.length; //12
```

#### Accessing Object Methods

**`objectName.methodName()`**

```javascript
var message = "Hello world!";
var newMessage = message.toUpperCase(); //HELLO WORLD!
```

#### Object Method

```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```

#### Creating an object: constructor notation

The **new** keyword and the object constructor create a blank. You can then add properties and methods to the object.

First, you create a new object using a combination of the **new** keyword and the **Object()** constructor function.

```javascript
var hotel = new Object();

hotel.name = 'Quey';
hotel.rooms = 40;
hotel.booked = 25;

hotel.checkAvailability = function(){
    return this.rooms - this.booked;
};
```

#### Creating many objects: constructor notaion

Object constructor can use a function as a **template** for creating object. First, create the template with the object's properties and methods.

```javascript
function Hotel (name, rooms, booked){
    this.name = naem;
    this.rooms = rooms;
    this.booked = booked;

    this.checkAvailability = function(){
        return this.rooms - this.booked;
    }
```

You create **instances** of the object using the constructor function.

To add a property, you use the dot notation as you seen before.

To delete a property, you use the keyword **delete**, and then use dot notation to identify the property or method you want to remove from the object.

```javascript
var quayHotel = new Hotel('Quay', 40, 25);
var parkHotel = new Hotel('Park', 120, 77);
```

#### ADDING AND REMOVING PROPERTIES

Once you have created an object (using literal or constructor notation), you can add new properties to it.

```javascript
var hotel = {
    name : 'Park' ,
    rooms : 120,
    booked : 77.
} ;

hotel.gym = true;
hotel.pool = false;
delete hotel .booked;

var elName = document .getEl ementByld('hotelName');
elName.textContent = hotel . name;

var elPool = document.getElementByid('pool');
elPool.className = ' Pool: ' + hotel.pool;

var elGym = document .getEl ementByld('gym');
elGym.className = 'Gym: ' + hotel.gym;
```

#### THIS (IT IS A KEYWORD)

The keyword **this** is commonly used inside functions and objects. Where the function is declared alters what this means. It always refers to one object, usually the object in which the function operates.

**A FUNCTION IN GLOBAL SCOPE**:

When a function is created at the top level of a script (that is, not inside another object or function), then it is in the **global scope** or **global context**.

The default object in this context is the window object. so when this is used inside a function in the global context it refers to the window object.

Below, **this** is being used to return properties of the window object

```javascript
function windowSize() {
    var width= this.innerWidth;
    var height = this.innerHeight;
    return [height, width];
}
```

**GLOBAL VARIABLES**:

All global variables also become properties of the **window** object. so when a function is in the global context, you can access global variables using the **window** object, as well as its other properties.

Here, the **`showWidth()`** function is in global scope, and `**this.width**` refers to the width variable:

```javascript
var width = 600; 
var shape = {width: 300};

var showWidth = function(){
    document .write(this.width);
}
showWidth();
```

**A METHOD OF AN OBJECT**:

When a function is defined inside an object, it becomes a method. In a method, **this** refers to the containing object.

**FUNCTION EXPRESSION AS METHOD**:

If a named function has been defined in global scope, and it is then used as a method of an object, **this** refers to the object it is contained within.
