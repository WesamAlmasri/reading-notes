# Images, Color, Text

![Html image](http://softlect.in/wp-content/uploads/HTML/HTML-Image-Tags.png)

## HTML Image

### Adding Images into Web Pages

Images enhance visual appearance of the web pages by making them more interesting and colorful.

The `<img`> tag is used to insert images in the HTML documents. It is an empty element and contains attributes only. The syntax of the `<img>` tag can be given with:

```html
<img src="url" alt="some_text">
```

![html image tag](https://camo.githubusercontent.com/884934f3713fe03fbad6e9be88b09d75f1a7432d4048ebbc890e19ea69a7fb9e/68747470733a2f2f7777772e6d696c746f6e6d61726b6574696e672e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031382f30332f6d6d68746d6c696d67746167343234323433696d6167652d7461672d6578616d706c652e6a7067)

Each image must carry at least two attributes: the `src` attribute, and an `alt` attribute.

The `src` attribute tells the browser where to find the image. Its value is the URL of the image file.

Whereas, the `alt` attribute provides an alternative text for the image, if it is unavailable or cannot be displayed for some reason. Its value should be a meaningful substitute for the image.

```html
<img src="kites.jpg" alt="Flying Kites">
<img src="sky.jpg" alt="Cloudy Sky">
<img src="balloons.jpg" alt="Balloons">
```

Note: Like `<br>` , the `<img>` element is also an empty element, and does not have a closing tag. However, in XHTML it closes itself ending with "/>".

You can also use the `style` attribute to specify width and height for the images. It prevents style sheets from changing the image size accidently, since inline style has the highest priority.

```html
<img src="kites.jpg" alt="Flying Kites" style="width: 300px; height: 300px;">
<img src="sky.jpg" alt="Cloudy Sky" style="width: 250px; height: 150px;">
<img src="balloons.jpg" alt="Balloons" style="width: 200px; height: 200px;">
```

### Using the HTML5 Picture Element

Sometimes, scaling an image up or down to fit different devices (or screen sizes) doesn't work as expected. Also, reducing the image dimension using the width and height attribute or property doesn't reduce the original file size. To address these problems HTML5 has introduced the `<picture>` tag that allows you to define multiple versions of an image to target different types of devices.

```html
<picture>
    <source media="(min-width: 1000px)" srcset="logo-large.png">
    <source media="(max-width: 500px)" srcset="logo-small.png">
    <img src="logo-default.png" alt="My logo">
</picture>
```

The browser will evaluate each child `<source>` element and choose the best match among them; if no matches are found, the URL of the `<img>` element's src attribute is used. Also, the `<img>` tag must be specified as the last child of the `<picture>` element.

![css colors image](https://res.cloudinary.com/practicaldev/image/fetch/s--NRrBgp7M--/c_imagga_scale,f_auto,fl_progressive,h_900,q_auto,w_1600/https://dev-to-uploads.s3.amazonaws.com/i/f5vqq3uckm57x5t9pov8.png)

## CSS Color

### Foreground Color

The `color` property defines the text color (foreground color in general) of an element.

For instance, the `color` property specified in the body selector defines the default text color for the whole page.

![Foreground Color syntax image](https://camo.githubusercontent.com/cb83cbbeeebf7f861d49f14c5c4798d79611e73c800d7175902bbbea77c6c9b0/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f766964656f735f6d786d2f636172657461732f657374727563747572612d6373735f33373136375f315f31313338302e6a7067)

The `color` property normally inherits the color value from their parent element, except the case of anchor elements. For example, if you specify color for the body element it will automatically be passed down to the headings, paragraphs, etc.

### Defining Color Values

Colors in CSS most often specified in the following formats:

1. a color name - like `"red"`
2. a HEX value - like `"#ff0000"`
3. an RGB value - like `"rgb(255, 0, 0)"`

#### Color Keywords

CSS defines the few color keywords which lets you specify color values in an easy way.

These basic color keywords are: aqua, black, blue, fuchsia, gray, green, lime, maroon, navy, olive, purple, red, silver, teal, white, and yellow. The color names are case-insensitive.

```css
h1 {
    color: red;
}
p {
    color: purple;
}
```

#### HEX Color Values

Hex (short for Hexadecimal) is by far the most commonly used method of defining color on the web.

Hex represent colors using a six-digit code, preceded by a hash character, like `#rrggbb`, in which rr, gg, and bb represents the red, green and blue component of the color respectively.

```css
h1 {
    color: #ffa500;
}
p {
    color: #00ff00;
}
```

Note: Hexadecimal or Hex refers to a numbering scheme that uses 16 characters as its base. It uses the numbers 0 through 9 and the letters A, B, C, D, E and F which corresponds to the decimal numbers 10, 11, 12, 13, 14 and 15 respectively.

Tip: If hexadecimal code of a color has value pairs, it can also be written in shorthand notation to avoid extra typing, for example, the hex color value `#ffffff` can be also be written as `#fff`, `#000000` as `#000`, `#00ff00` as `#0f0`, `#ffcc00` as `#fc0`, and so on.

#### RGB Color Values

Colors can be defined in the RGB model (Red, Green, and Blue) using the rgb() functional notation.

```css
h1 {
    color: rgb(255, 165, 0);
}
p {
    color: rgb(0, 255, 0);
}
```

![colors image](https://camo.githubusercontent.com/3133c23337f572c1575dc877a085b51d55095713753c35b027b771f4707f2ba9/68747470733a2f2f692e7974696d672e636f6d2f76692f6f656f765a54674d6a30592f6d617872657364656661756c742e6a7067)

![html image](https://steemitimages.com/p/2FFvzA2zeqoVJ2SVhDmmumdPfnVEcahMce9nMwwksSDdRvPhqU4VzjQrgSYjRsMHdjdVw6J9JYdcE3W5yuq13YmTD2KgAW7SBP6SZJX1xKFVtHRdVnDvqeTwgR8Bx?format=match&mode=fit&width=640)

## Text

### Formatting Text with HTML

HTML provides several tags that you can use to make some text on your web pages to appear differently than normal text, for example, you can use the tag `<b>` to make the text bold, tag `<i>` to make the text italic, tag `<mark>` to highlight the text, tag `<code>` to display a fragment of computer code, tags `<ins>` and `<del>` for marking editorial insertions and deletions, and more.

```html
<p>This is <b>bold text</b>.</p>
<p>This is <strong>strongly important text</strong>.</p>
<p>This is <i>italic text</i>.</p>
<p>This is <em>emphasized text</em>.</p>
<p>This is <mark>highlighted text</mark>.</p>
<p>This is <code>computer code</code>.</p>
<p>This is <small>smaller text</small>.</p>
<p>This is <sub>subscript</sub> and <sup>superscript</sup> text.</p>
<p>This is <del>deleted text</del>.</p>
<p>This is <ins>inserted text</ins>.</p>
```

### Difference between and tag

Both `<strong>` and `<b>` tags render the enclosed text in a bold typeface by default, but the `<strong>` tag indicates that its contents have strong importance, whereas the `<b>` tag is simply used to draw the reader's attention without conveying any special importance.

```html
<p><strong>WARNING!</strong> Please proceed with caution.</p>
<p>The concert will be held at <b>Hyde Park</b> in London.</p>
```

Similarly, both `<em>` and `<i>` tags render the enclosed text in italic type by default, but the `<em>` tag indicates that its contents have stressed emphasis compared to surrounding text, whereas the `<i>` tag is used for marking up text that is set off from the normal text for readability reasons, such as a technical term, an idiomatic phrase from another language, a thought, etc.

```html
<p>Cats are <em>cute</em> animals.</p>
<p>The <i>Royal Cruise</i> sailed last night.</p>
```

**Note**: Use the `<em>` and `<strong>` tags when the content of your page requires that certain words or phrases should have strong emphasis or importance. Also, in HTML5 the `<b>` and `<i>` tags have been redefined, earlier they don't have semantic meaning.

### CSS Text

#### Formatting Text with CSS

CSS provides several properties that allows you to define various text styles such as color, alignment, spacing, decoration, transformation, etc. very easily and effectively.

The commonly used text properties are: `text-align`, `text-decoration`, `text-transform`, `text-indent`, `line-height`, `letter-spacing`, `word-spacing`, and more. These properties give you precise control over the visual appearance of the characters, words, spaces, and so on.

#### Text Color

The color of the text is defined by the CSS color property.

```css
body {
    color: #434343;
}
```

#### Text Alignment

The `text-align` property is used to set the horizontal alignment of the text. Text can be aligned in four ways: to the left, right, centre or justified (straight left and right margins).

```css
h1 {
    text-align: center;
}
p {
    text-align: justify;
}
```

![text alognment image](https://camo.githubusercontent.com/c6df475796106d1a480bbe0ba23832d94ced9032fea34ec9c7712705ca78ea68/68747470733a2f2f7777772e7475746f7269616c72657075626c69632e636f6d2f6c69622f696d616765732f746578742d616c69676e2d696c6c757374726174696f6e2e706e67)

#### Text Decoration

The `text-decoration` property is used to set or remove decorations from text.

This property typically accepts one of the following values: underline, overline, line-through, and none. You should avoid underline text that is not a link, as it might confuse the visitor.

```css
h1 {
    text-decoration: overline;
}
h2 {
    text-decoration: line-through;
}
h3 {
    text-decoration: underline;
}
```

#### Removing the Default Underline from Links

The `text-decoration` property is extensively used to remove the default underline from the HTML hyperlinks. You can further provide some other visual cues to make it stand out from the normal text, for example, using dotted border instead of solid underline.

```css
a {
    text-decoration: none;
    border-bottom: 1px dotted;
}
```

![links format image](https://camo.githubusercontent.com/bbd84ae558bbb22286c3fe0f64aeea9703a5f6f1d6d87e2bab3ceb2ed49235ff/68747470733a2f2f69322e77702e636f6d2f6373732d747269636b732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031362f30392f66616d696c6961722e706e673f73736c3d31)
