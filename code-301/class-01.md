# RESPONSIVE WEB DESIGN and FLOATS

## Responsive Web Design

Responsive web design is the practice of building a website suitable to work on every device and every screen size, no matter how large or small, mobile or desktop.

![Responsive design image](https://learn.shayhowe.com/assets/images/courses/advanced-html-css/responsive-web-design/food-sense.png)

## Responsive vs. Adaptive vs. Mobile

Responsive and adaptive web design are closely related, and often transposed as one in the same. Responsive generally means to react quickly and positively to any change, while adaptive means to be easily modified for a new purpose or situation, such as change. With responsive design websites continually and fluidly change based on different factors, such as viewport width, while adaptive websites are built to a group of preset factors. A combination of the two is ideal, providing the perfect formula for functional websites. Which term is used specifically doesn’t make a huge difference.

## Flexible Layouts

Responsive web design is broken down into three main components, including flexible layouts, media queries, and flexible media. The first part, flexible layouts, is the practice of building the layout of a website with a flexible grid, capable of dynamically resizing to any width. Flexible grids are built using relative length units, most commonly percentages or `em` units. These relative lengths are then used to declare common grid property values such as `width`, `margin`, or `padding`.

### Flexible Grid

Using the flexible grid formula we can take all of the fixed units of length and turn them into relative units.

Taking the flexible layout concept, and formula, and reapplying it to all parts of a grid will create a completely dynamic website, scaling to every viewport size. For even more control within a flexible layout, you can also leverage the `min-width`, `max-width`, `min-height`, and `max-height` properties.

The flexible layout approach alone isn’t enough. At times the width of a browser viewport may be so small that even scaling the the layout proportionally will create columns that are too small to effectively display content. Specifically, when the layout gets too small, or too large, text may become illegible and the layout may begin to break. In this event, media queries can be used to help build a better experience.

## Media Queries

Media queries were built as an extension to media types commonly found when targeting and including styles. Media queries provide the ability to specify different styles for individual browser and device circumstances, the width of the viewport or device orientation for example. Being able to apply uniquely targeted styles opens up a world of opportunity and leverage to responsive web design.

### Initializing Media Queries

There are a couple different ways to use media queries, using the `@media` rule inside of an existing style sheet, importing a new style sheet using the `@import` rule, or by linking to a separate style sheet from within the HTML document. Generally speaking it is recommend to use the `@media` rule inside of an existing style sheet to avoid any additional HTTP requests.

```html
<!-- Separate CSS File -->
<link href="styles.css" rel="stylesheet" media="all and (max-width: 1024px)">
```

```css
/* @media Rule */
@media all and (max-width: 1024px) {...}

/* @import Rule */
@import url(styles.css) all and (max-width: 1024px) {...}
```

Each media query may include a media type followed by one or more expressions. Common media types include `all`, `screen`, `print`, `tv`, and `braille`. The HTML5 specification includes new media types, even including `3d-glasses`. Should a media type not be specified the media query will default the media type to `screen`.

### Logical Operators in Media Queries

Logical operators in media queries help build powerful expressions. There are three different logical operators available for use within media queries, including `and`, `not`, and `only`.

Using the `and` logical operator within a media query allows an extra condition to be added, making sure that a browser or devices does both a, b, c, and so forth. Multiple individual media queries can be comma separated, acting as an unspoken or operator. The example below selects all media types between `800` and `1024` pixels wide.

```css
@media all and (min-width: 800px) and (max-width: 1024px) {...}
```

The `not` logical operator negates the query, specifying any query but the one identified. In the example below the expression applies to any device that does not have a color screen. Black and white or monochrome screens would apply here for example.

```css
@media not screen and (color) {...}
```

The `only` logical operator is a new operator and is not recognized by user agents using the HTML4 algorithm, thus hiding the styles from devices or browsers that don’t support media queries. Below, the expression selects only screens in a portrait orientation that have a user agent capable of rending media queries.

```css
@media only screen and (orientation: portrait) {...}
```

### Height & Width Media Features

One of the most common media features revolves around determining a height or width for a device or browser viewport. The height and width may be found by using the `height` and `width` media features. Each of these media features may then also be prefixed with the min or max qualifiers, building a feature such as `min-width` or `max-width`.

The `height` and `width` features are based off the height and width of the viewport rendering area, the browser window for example. Values for these height and width media features may be any length unit, relative or absolute.

```css
@media all and (min-width: 320px) and (max-width: 780px) {...}
```

### Orientation Media Feature

The `orientation` media feature determines if a device is in the `landscape` or `portrait` orientation. The `landscape` mode is triggered when the display is wider than taller, and the `portrait` mode is triggered when the display is taller than wider. This media feature plays a large part with mobile devices.

```css
@media all and (orientation: landscape) {...}
```

### Aspect Ratio Media Features

The `aspect-ratio` and `device-aspect-ratio` features specifies the `width`/`height` pixel ratio of the targeted rendering area or output device. The `min` and `max` prefixes are available to use with the different aspect ratio features, identifying a ratio above or below that of which is stated.

```css
@media all and (min-device-aspect-ratio: 16/9) {...}
```

### Resolution Media Feature

The `resolution` media feature specifies the resolution of the output device in pixel density, also known as dots per inch or DPI. The `resolution` media feature does accept the `min` and `max` prefixes. Additionally, the `resolution` media feature will accept dots per pixel (`1.3dppx`), dots per centimeter (`118dpcm`), and other length based resolution values.

```css
@media print and (min-resolution: 300dpi) {...}
```

## Mobile First

One popular technique with using media queries is called mobile first. The *mobile first* approach includes using styles targeted at smaller viewports as the default styles for a website, then use media queries to add styles as the viewport grows.

The operating belief behind mobile first design is that a user on a mobile device, commonly using a smaller viewport, shouldn’t have to load the styles for a desktop computer only to have them over written with mobile styles later. Doing so is a waste of bandwidth. Bandwidth that is precious to any users looking for a snappy website.

A breakout of mobile first media queries might look at bit like the following.

```css
/* Default styles first then media queries */
@media screen and (min-width: 400px)  {...}
@media screen and (min-width: 600px)  {...}
@media screen and (min-width: 1000px) {...}
@media screen and (min-width: 1400px) {...}
```

Additionally, downloading unnecessary media assets can be stopped by using media queries. Generally speaking, avoiding CSS3 shadows, gradients, transforms, and animations within mobile styles isn’t a bad idea either. When used excessively, they cause heavy loading and can even reduce a device’s battery life.

```css
/* Default media */
body {
  background: #ddd;
}
/* Media for larger devices */
@media screen and (min-width: 800px) {
  body {
    background-image: url("bg.png") 50% 50% no-repeat;
  }
}
```

## Viewport

### Viewport Height & Width

Using the `viewport` meta tag with either the `height` or `width` values will define the height or width of the viewport respectively. Each value accepts either a positive integer or keyword. For the `height` property the keyword `device-height` value is accepted, and for the `width` property the keyword `device-width` is accepted. Using these keywords will inherit the device’s default height and width value.

For the best results, and the best looking website, it is recommend that you use the device defaults by applying the `device-height` and `device-width` values.

```html
<meta name="viewport" content="width=device-width">
```

![media query demo](https://learn.shayhowe.com/assets/images/courses/advanced-html-css/responsive-web-design/with-viewport.png)

### Viewport Scale

To control how a website is scaled on a mobile device, and how users can continue to scale a website, use the `minimum-scale`, `maximum-scale`, `initial-scale`, and `user-scalable` properties.

```html
<meta name="viewport" content="initial-scale=2">
```

![media query demo](https://learn.shayhowe.com/assets/images/courses/advanced-html-css/responsive-web-design/viewport-scale.png)

### Viewport Resolution

Letting the browser decide how to scale a website based off any viewport scale values usually does the trick. When more control is needed, specifically over the resolution of a device, the `target-densitydpi` value may be used. The `target-densitydpi` viewport accepts a handful of values including `device-dpi`, `high-dpi`, `medium-dpi`, `low-dpi`, or an actual DPI number.

Using the `target-densitydpi` viewport value is rare, but extremely helpful when pixel by pixel control is needed.

```html
<meta name="viewport" content="target-densitydpi=device-dpi">
```

### Combining Viewport Values

The `viewport` meta tag will accept individual values as well as multiple values, allowing multiple viewport properties to be set at once. Setting multiple values requires comma separating them within the `content` attribute value. One of the recommended viewport values is outlined below, using both the `width` and i`nitial-scale` properties.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

![media query demo](https://learn.shayhowe.com/assets/images/courses/advanced-html-css/responsive-web-design/with-viewport.png)

## Flexible Media

The final, equally important aspect to responsive web design involves flexible media. As viewports begin to change size media doesn’t always follow suit. Images, videos, and other media types need to be scalable, changing their size as the size of the viewport changes.

One quick way to make media scalable is by using the `max-width` property with a value of `100%`. Doing so ensures that as the viewport gets smaller any media will scale down according to its containers width.

```css
img, video, canvas {
  max-width: 100%;
}
```
