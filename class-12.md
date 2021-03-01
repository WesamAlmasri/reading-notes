# Docs for the HTML Canvas Element & Chart.js

![canvas image](https://i.ytimg.com/vi/3GqUM4mEYKA/maxresdefault.jpg)

## Canvas

### Basic usage of canvas

The HTML `<canvas>` tag is used to draw graphics, on the fly, via scripting (usually JavaScript). HTML5 element `<canvas>` gives you an easy and powerful way to draw graphics using JavaScript. It can be used to draw graphs, make photo compositions or do simple (and not so simple) animations.

```html
<canvas id = "tutorial" width = "100" height = "100"></canvas>
```

You can easily find that `<canvas>` element in the DOM using getElementById() method as follows

```html
var canvas = document.getElementById("mycanvas");
```

```html
<!DOCTYPE HTML>

<html>
   <head>
   
      <style>
         #tutorial{border:1px solid red;}
      </style>
   </head>
   
   <body>
      <canvas id = "tutorial" width = "100" height = "100"></canvas>
   </body>
</html>
```

### The rendering context

The `<canvas>` element creates a fixed-size drawing surface that exposes one or more rendering contexts, which are used to create and manipulate the content shown. In this tutorial, we focus on the 2D rendering context.

The canvas is initially blank. To display something, a script first needs to access the rendering context and draw on it. The `<canvas>` element has a method called `getContext()`, used to obtain the rendering context and its drawing functions. `getContext()` takes one parameter, the type of context.

```javascript
var canvas = document.getElementById('tutorial');
var ctx = canvas.getContext('2d');
```

### Drawing shapes with canvas

#### The grid

Beloq, you see this canvas with the default grid overlayed. Normally 1 unit in the grid corresponds to 1 pixel on the canvas. The origin of this grid is positioned in the top left corner at coordinate (0,0). All elements are placed relative to this origin. So the position of the top left corner of the blue square becomes x pixels from the left and y pixels from the top, at coordinate (x,y).

![canvas grid image](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes/canvas_default_grid.png)

#### Drawing rectangles

There are three functions that draw rectangles on the canvas:

- **`fillRect(x, y, width, height)`**: Draws a filled rectangle.
- **`strokeRect(x, y, width, height)`**: Draws a rectangular outline.
- **`clearRect(x, y, width, height)`**: Clears the specified rectangular area, making it fully transparent.

Each of these three functions takes the same parameters. `x` and `y` specify the position on the canvas (relative to the origin) of the top-left corner of the rectangle. `width` and `height` provide the rectangle's size.

```javascript
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.fillRect(25, 25, 100, 100);
    ctx.clearRect(45, 45, 60, 60);
    ctx.strokeRect(50, 50, 50, 50);
  }
}
```

![example image](https://media.prod.mdn.mozit.cloud/attachments/2012/07/09/245/abd4f1e1c012f5d3b636cd1b852b074c/Canvas_rect.png)

#### Drawing paths

A path is a list of points, connected by segments of lines that can be of different shapes, curved or not, of different width and of different color. A path, or even a subpath, can be closed. To make shapes using paths, we take some extra steps:

- First, you create the path.
- Then you use drawing commands to draw into the path.
- Once the path has been created, you can stroke or fill the path to render it.

Here are the functions used to perform these steps:

- **`beginPath()`**: Creates a new path. Once created, future drawing commands are directed into the path and used to build the path up.
- **`Path methods`**: Methods to set different paths for objects.
- **`closePath()`**: Adds a straight line to the path, going to the start of the current sub-path.
- **`stroke()`**: Draws the shape by stroking its outline.
- **`fill()`**: Draws a solid shape by filling the path's content area.

For example, the code for drawing a triangle would look something like this:

```javascript
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.moveTo(75, 50);
    ctx.lineTo(100, 75);
    ctx.lineTo(100, 25);
    ctx.fill();
  }
}
```

**Note**: When the current path is empty, such as immediately after calling beginPath(), or on a newly created canvas, the first path construction command is always treated as a moveTo(), regardless of what it actually is. For that reason, you will almost always want to specifically set your starting position after resetting a path.

![triangle example image](https://media.prod.mdn.mozit.cloud/attachments/2015/01/18/9847/55a2b8b8e4ed4a33ffe023e5cbedb0a9/triangle.png)

#### Moving the pen

One very useful function, which doesn't actually draw anything but becomes part of the path list described above, is the `moveTo()` function. You can probably best think of this as lifting a pen or pencil from one spot on a piece of paper and placing it on the next.

**`moveTo(x, y)`**: Moves the pen to the coordinates specified by `x` and `y`.

When the canvas is initialized or `beginPath()` is called, you typically will want to use the `moveTo()` function to place the starting point somewhere else. We could also use `moveTo()` to draw unconnected paths. Take a look at the smiley face below.

```javascript
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
     var ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.arc(75, 75, 50, 0, Math.PI * 2, true); // Outer circle
    ctx.moveTo(110, 75);
    ctx.arc(75, 75, 35, 0, Math.PI, false);  // Mouth (clockwise)
    ctx.moveTo(65, 65);
    ctx.arc(60, 65, 5, 0, Math.PI * 2, true);  // Left eye
    ctx.moveTo(95, 65);
    ctx.arc(90, 65, 5, 0, Math.PI * 2, true);  // Right eye
    ctx.stroke();
  }
}
```

![example image](https://media.prod.mdn.mozit.cloud/attachments/2012/07/09/252/804dd546c6267e6391c4e3a87f922e33/Canvas_smiley.png)

Below a table contains some of the drawing methods you can use with canvas

| Method                                                   | description                                                                                                                                                                                           |
| -------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `lineTo(x, y)`                                           | Draws a line from the current drawing position to the position specified by `x` and `y`                                                                                                               |
| `arc(x, y, radius, startAngle, endAngle, anticlockwise)` | Draws an arc which is centered at (`x`, `y`) position with `radius` r starting at startAngle and ending at endAngle going in the given direction indicated by anticlockwise (defaulting to clockwise) |
| `arcTo(x1, y1, x2, y2, radius)`                          | Draws an arc with the given control points and radius, connected to the previous point by a straight line.                                                                                            |
| `quadraticCurveTo(cp1x, cp1y, x, y)`                     | Draws a quadratic Bézier curve from the current pen position to the end point specified by `x` and `y`, using the control point specified by `cp1x` and `cp1y`                                        |
| `bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)`            | Draws a cubic Bézier curve from the current pen position to the end point specified by `x` and `y`, using the control points specified by (`cp1x`, `cp1y`) and (`cp2x`, `cp2y`)                       |
| `rect(x, y, width, height)`                              | Draws a rectangle whose top-left corner is specified by (`x`, `y`) with the specified `width` and `height`                                                                                            |

### Path2D objects

**`Path2D()`**: The `Path2D()` constructor returns a newly instantiated Path2D object, optionally with another path as an argument (creates a copy), or optionally with a string consisting of SVG path data.

```javascript
new Path2D();     // empty path object
new Path2D(path); // copy from another Path2D object
new Path2D(d);    // path from SVG path data
```

All path methods like `moveTo`, `rect`, `arc` or `quadraticCurveTo`, etc., which we got to know above, are available on Path2D objects.

The Path2D API also adds a way to combine paths using the `addPath` method. This can be useful when you want to build objects from several components, for example.

**`Path2D.addPath(path [, transform])`**: Adds a path to the current path with an optional transformation matrix.

**Example**:

```javascript
function draw() {
  var canvas = document.getElementById('canvas');
  if (canvas.getContext) {
    var ctx = canvas.getContext('2d');

    var rectangle = new Path2D();
    rectangle.rect(10, 10, 50, 50);

    var circle = new Path2D();
    circle.arc(100, 35, 25, 0, 2 * Math.PI);

    ctx.stroke(rectangle);
    ctx.fill(circle);
  }
}
```

![example image](https://media.prod.mdn.mozit.cloud/attachments/2015/01/18/9851/2a2e7589207b3967d48c3ea929561efc/path2d.png)

### Applying styles and colors

If we want to apply colors to a shape, there are two important properties we can use: `fillStyle` and `strokeStyle`.

- **`fillStyle = color`**: Sets the style used when filling shapes.
- **`strokeStyle = color`**: Sets the style for shapes' outlines.

**Color** is a string representing a CSS `<color>`, a gradient object, or a pattern object.  By default, the stroke and fill color are set to black (CSS color value `#000000`).

```javascript
/ these all set the fillStyle to 'orange'

ctx.fillStyle = 'orange';
ctx.fillStyle = '#FFA500';
ctx.fillStyle = 'rgb(255, 165, 0)';
ctx.fillStyle = 'rgba(255, 165, 0, 1)';
```

#### A fillStyle example

```javascript
function draw() {
  var ctx = document.getElementById('canvas').getContext('2d');
  for (var i = 0; i < 6; i++) {
    for (var j = 0; j < 6; j++) {
      ctx.fillStyle = 'rgb(' + Math.floor(255 - 42.5 * i) + ', ' +
                       Math.floor(255 - 42.5 * j) + ', 0)';
      ctx.fillRect(j * 25, i * 25, 25, 25);
    }
  }
}
```

![A fillStyle example image](https://media.prod.mdn.mozit.cloud/attachments/2013/06/24/5417/e352ec307d004a83b2df969b9f33539f/Canvas_fillstyle.png)

#### A strokeStyle example

```javascript
  function draw() {
    var ctx = document.getElementById('canvas').getContext('2d');
    for (var i = 0; i < 6; i++) {
      for (var j = 0; j < 6; j++) {
        ctx.strokeStyle = 'rgb(0, ' + Math.floor(255 - 42.5 * i) + ', ' +
                         Math.floor(255 - 42.5 * j) + ')';
        ctx.beginPath();
        ctx.arc(12.5 + j * 25, 12.5 + i * 25, 10, 0, Math.PI * 2, true);
        ctx.stroke();
      }
    }
  }
```

![A strokeStyle example image](https://media.prod.mdn.mozit.cloud/attachments/2012/07/09/253/c4e071f91f9aa7e0d29ff8696d37a27c/Canvas_strokestyle.png)

#### Transparency

In addition to drawing opaque shapes to the canvas, we can also draw semi-transparent (or translucent) shapes. This is done by either setting the `globalAlpha` property or by assigning a semi-transparent color to the stroke and/or fill style.

**`globalAlpha = transparencyValue`**:Applies the specified transparency value to all future shapes drawn on the canvas. The value must be between `0.0` (fully transparent) to `1.0` (fully opaque). This value is 1.0 (fully opaque) by default.

```javascript
// Assigning transparent colors to stroke and fill style

ctx.strokeStyle = 'rgba(255, 0, 0, 0.5)';
ctx.fillStyle = 'rgba(255, 0, 0, 0.5)';
```

### Line styles

There are several properties which allow us to style lines.

- **`lineWidth = value`**: Sets the width of lines drawn in the future.
- **`lineCap = type`**: Sets the appearance of the ends of lines.
- **`lineJoin = type`**: Sets the appearance of the "corners" where lines meet.
- **`miterLimit = value`**: Establishes a limit on the miter when two lines join at a sharp angle, to let you control how thick the junction becomes.
- **`getLineDash()`**: Returns the current line dash pattern array containing an even number of non-negative numbers.
- **`setLineDash(segments)`**: Sets the current line dash pattern.
- **`lineDashOffset = value`**: Specifies where to start a dash array on a line.

### Gradients

We create a CanvasGradient object by using one of the following methods. We can then assign this object to the `fillStyle` or `strokeStyle` properties.

- **`createLinearGradient(x1, y1, x2, y2)`**: Creates a linear gradient object with a starting point of (`x1`, `y1`) and an end point of (`x2`, `y2`).
- **`createRadialGradient(x1, y1, r1, x2, y2, r2)`**: Creates a radial gradient. The parameters represent two circles, one with its center at (`x1`, `y1`) and a radius of r1, and the other with its center at (`x2`, `y2`) with a radius of `r2`.
- **`createConicGradient(angle, x, y)`**: Creates a conic gradient object with a starting angle of `angle` in radians, at the position (`x`, `y`).

```javascript
var lineargradient = ctx.createLinearGradient(0, 0, 150, 150);
var radialgradient = ctx.createRadialGradient(75, 75, 0, 75, 75, 100);
```

- **`gradient.addColorStop(position, color)`**: Creates a new color stop on the gradient object. The position is a number between `0.0` and `1.0` and defines the relative position of the color in the gradient, and the color argument must be a string representing a CSS `<color>`, indicating the color the gradient should reach at that offset into the transition.

```javascript
var lineargradient = ctx.createLinearGradient(0, 0, 150, 150);
lineargradient.addColorStop(0, 'white');
lineargradient.addColorStop(1, 'black');
```

**Example**:

```javascript
function draw() {
  var ctx = document.getElementById('canvas').getContext('2d');

  // Create gradients
  var lingrad = ctx.createLinearGradient(0, 0, 0, 150);
  lingrad.addColorStop(0, '#00ABEB');
  lingrad.addColorStop(0.5, '#fff');
  lingrad.addColorStop(0.5, '#26C000');
  lingrad.addColorStop(1, '#fff');

  var lingrad2 = ctx.createLinearGradient(0, 50, 0, 95);
  lingrad2.addColorStop(0.5, '#000');
  lingrad2.addColorStop(1, 'rgba(0, 0, 0, 0)');

  // assign gradients to fill and stroke styles
  ctx.fillStyle = lingrad;
  ctx.strokeStyle = lingrad2;

  // draw shapes
  ctx.fillRect(10, 10, 130, 130);
  ctx.strokeRect(50, 50, 50, 50);

}
```

![linear gradient example image](https://media.prod.mdn.mozit.cloud/attachments/2012/07/09/235/4e37c6eb94025fddda9899e61484bf1f/Canvas_lineargradient.png)

### Patterns

n one of the examples on the previous page, we used a series of loops to create a pattern of images. There is, however, a much simpler method: the `createPattern()` method.

**`createPattern(image, type)`**: Creates and returns a new canvas pattern object. `image` is a CanvasImageSource (that is, an HTMLImageElement, another canvas, a `<video>` element, or the like. `type` is a string indicating how to use the image.

The **`type`** specifies how to use the image in order to create the pattern, and must be one of the following string values:

- **repeat**: Tiles the image in both vertical and horizontal directions.
- **repeat-x**: Tiles the image horizontally but not vertically.
- **repeat-y**: Tiles the image vertically but not horizontally.
- **no-repeat**: Doesn't tile the image. It's used only once.

```javascript
var img = new Image();
img.src = 'someimage.png';
var ptrn = ctx.createPattern(img, 'repeat');
```

**Example**:

```javascript
function draw() {
  var ctx = document.getElementById('canvas').getContext('2d');

  // create new image object to use as pattern
  var img = new Image();
  img.src = 'https://mdn.mozillademos.org/files/222/Canvas_createpattern.png';
  img.onload = function() {

    // create pattern
    var ptrn = ctx.createPattern(img, 'repeat');
    ctx.fillStyle = ptrn;
    ctx.fillRect(0, 0, 150, 150);

  }
}
```

![exaple image](https://media.prod.mdn.mozit.cloud/attachments/2012/07/09/222/bcf90d24adf679755d47e6e2adf31afa/Canvas_createpattern.png)

### Shadows

Using shadows involves just four properties:

- **`shadowOffsetX = float`**: Indicates the horizontal distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.
- **`shadowOffsetY = float`**: Indicates the vertical distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.
- **`shadowBlur = float`**: Indicates the size of the blurring effect; this value doesn't correspond to a number of pixels and is not affected by the current transformation matrix. The default value is 0.
- **`shadowColor = color`**: A standard CSS color value indicating the color of the shadow effect; by default, it is fully-transparent black.

```javascript
function draw() {
  var ctx = document.getElementById('canvas').getContext('2d');

  ctx.shadowOffsetX = 2;
  ctx.shadowOffsetY = 2;
  ctx.shadowBlur = 2;
  ctx.shadowColor = 'rgba(0, 0, 0, 0.5)';

  ctx.font = '20px Times New Roman';
  ctx.fillStyle = 'Black';
  ctx.fillText('Sample String', 5, 30);
}
```

![example image](https://media.prod.mdn.mozit.cloud/attachments/2012/07/09/2505/4ad031cfcc26e20bf8ba97e8be3e0761/shadowed-string.png)

### Drawing text

The canvas rendering context provides two methods to render text:

- **`fillText(text, x, y [, maxWidth])`**: Fills a given text at the given (`x`,`y`) position. Optionally with a maximum width to draw.
- **strokeText(text, x, y [, maxWidth])**:Strokes a given text at the given (`x`,`y`) position. Optionally with a maximum width to draw.

```javascript
function draw() {
  var ctx = document.getElementById('canvas').getContext('2d');
  ctx.font = '48px serif';
  ctx.fillText('Hello world', 10, 50);
}
```

### Styling text

There are some more properties which let you adjust the way the text gets displayed on the canvas:

- **`font = value`**: The current text style being used when drawing text. This string uses the same syntax as the CSS font property. The default font is `10px sans-serif`.
- **`textAlign = value`**: Text alignment setting. Possible values: `start`, `end`, `left`, `right` or `center`. The default value is `start`.
- **`textBaseline = value`**: Baseline alignment setting. Possible values: `top`, `hanging`, `middle`, `alphabetic`, `ideographic`, `bottom`. The default value is `alphabetic`.
- **`direction = value`**: Directionality. Possible values: `ltr`, `rtl`, `inherit`. The default value is `inherit`.

```javascript
ctx.font = '48px serif';
ctx.textBaseline = 'hanging';
ctx.strokeText('Hello world', 0, 100);
```

![chart js image](https://miro.medium.com/max/1200/1*eCoqJKb-QnoxWFPsjyqU0g.png)

## Chart.js

Chart.js can be used with ES6 modules, plain JavaScript and module loaders.

### Creating a Chart

It's easy to get started with Chart.js. All that's required is the script included in your page along with a single `<canvas>` node to render the chart.

```html
<canvas id="myChart" width="400" height="400"></canvas>
<script>
var ctx = document.getElementById('myChart').getContext('2d');
var myChart = new Chart(ctx, {
    type: 'bar',
    data: {
        labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
        datasets: [{
            label: '# of Votes',
            data: [12, 19, 3, 5, 2, 3],
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)',
                'rgba(54, 162, 235, 0.2)',
                'rgba(255, 206, 86, 0.2)',
                'rgba(75, 192, 192, 0.2)',
                'rgba(153, 102, 255, 0.2)',
                'rgba(255, 159, 64, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)',
                'rgba(54, 162, 235, 1)',
                'rgba(255, 206, 86, 1)',
                'rgba(75, 192, 192, 1)',
                'rgba(153, 102, 255, 1)',
                'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1
        }]
    },
    options: {
        scales: {
            yAxes: [{
                ticks: {
                    beginAtZero: true
                }
            }]
        }
    }
});
</script>
```

![charts example image](https://camo.githubusercontent.com/f54be96d257e75036674938bf133b6359da66739aeac422d4601c560c94418a3/68747470733a2f2f63646e2e6d6f732e636d732e66757475726563646e2e6e65742f533562696377506538766250396e74336977417777692e6a7067)

### Accessible Charts

Chart.js charts are rendered on user provided canvas elements. Thus, it is up to the user to create the canvas element in a way that is accessible. The canvas element has support in all browsers and will render on screen but the canvas content will not be accessible to screen readers.

By setting the `role` and `aria-label`, this canvas now has an accessible name.

```html
<canvas id="goodCanvas1" width="400" height="100" aria-label="Hello ARIA World" role="img"></canvas>
```

This canvas element has a `text` alternative via fallback content.

```html
<canvas id="okCanvas2" width="400" height="100">
    <p>Hello Fallback World</p>
</canvas>
```

### Chart type

The types of charts that you can use:

- Line
- Bar
- Radar
- Doughnut and Pie
- Polar area
- Bubble
- Scatter

### Line

![line chart example image](https://camo.githubusercontent.com/9212ba4ba50b79e88112651c15e120aceb84f54022a7ae37088c7ff72d0716e0/68747470733a2f2f63646e2e77616c6c7374726565746d6f6a6f2e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031392f30342f4c696e652d43686172742d4578616d706c65732e706e67)

### Bar

![bar chart example image](https://camo.githubusercontent.com/023a98cad2013cc5c3e6ed7b459517a2fac3d2285d56a074a32cc84511df3684/68747470733a2f2f6368617274696f2e636f6d2f6173736574732f6466643539662f7475746f7269616c732f6368617274732f67726f757065642d6261722d6368617274732f633166646536303137353131626265663762613962623234356131313363303766386666333231373361376330643734326134653165616331393330613363352f67726f757065642d6261722d6578616d706c652d312e706e67)

### Radar

![radar chart example image](https://camo.githubusercontent.com/0287221eeeb19a4c0b699b671e4e3c3ab7f2f7cacdc9fc8022d5574d07ce52e9/68747470733a2f2f7777772e7265736561726368676174652e6e65742f70726f66696c652f4173747269645f42756963612f7075626c69636174696f6e2f3332373734363330372f6669677572652f666967342f41533a36373235353936383330383432393140313533373336323133323339332f5370696465722d7765622d706c6f742d73686f77696e672d7468652d61726f6d617469632d70726f66696c652d6f662d7468652d636f6d62696e6174696f6e732d44412d73616d706c65732d696e636c7564696e672e706e67)

### Doughnut and Pie

![doughnut and Pie chart example image](https://camo.githubusercontent.com/2dd05b6171b61913b4c7a262f7813bfe5bf0d146aeef2b58ad0f8f497bba6b9c/68747470733a2f2f7777772e616d6368617274732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031332f31312f64656d6f5f3132395f6e6f6e652e706e67)

### Polar area

![Polar area chart example image](https://camo.githubusercontent.com/72bcb1a2378c4512c3b23f646a9835c7b3ef9e012e71481143c9f9655e7ad49a/68747470733a2f2f706e702e6769746875622e696f2f73702d6465762d66782d636f6e74726f6c732d72656163742f6173736574732f506f6c61724172656143686172742e706e67)

### Bubble

![Bubble chart example image](https://camo.githubusercontent.com/00d682a926d424e3c1c36fc44edade3d0843a27822c6740692db438d5a8b98fa/68747470733a2f2f6432736c6377336b697036716d6b2e636c6f756466726f6e742e6e65742f6d61726b6574696e672f626c6f672f3230313751342f686f772d746f2d6d616b652d612d627562626c652d63686172742d696e2d657863656c2f627562626c652d63686172742d74656d706c6174652e706e67)

### Scatter

![Scatter chart example image](https://camo.githubusercontent.com/c282dee7b426f4c4e9dd3a6419af0f40a0162e0877bf210f5e348fc82704c64a/68747470733a2f2f75706c6f61642e77696b696d656469612e6f72672f77696b6970656469612f636f6d6d6f6e732f7468756d622f612f61662f536361747465725f6469616772616d5f666f725f7175616c6974795f63686172616374657269737469635f5858582e7376672f3132303070782d536361747465725f6469616772616d5f666f725f7175616c6974795f63686172616374657269737469635f5858582e7376672e706e67)
