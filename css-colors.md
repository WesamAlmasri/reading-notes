## CSS colors

The color in CSS represents a color in the RGB color space. A color may also include an alpha-channel transparency value, indicating how the color should composite with its background.

A color can be defined in any of the following ways:

* Using a keyword (such as blue or transparent)
  There are 147 predefined color names that are recognized by browsers. For example: DarkCyan

* Using the RGB cubic-coordinate system (via the #-hexadecimal or the `rgb()` and `rgba()` functional notations):
    **RGB values**: These express colors in terms of how much red, green and blue are used to make it up. For example: rgb(100,100,90)
    **hex codes**: These are six-digit codes that represent the amount of red, green and blue in a color, preceded by a pound or hash #

* Using the HSL cylindrical-coordinate system (via the `hsl()` and `hsla()` functional notations):
    The hsl color property has been introduced in CSS3 as an alternative way to specify colors.
    The value of the property starts with the letters hsl , followed by individual values inside parentheses for:
    * **hue**: This is expressed as an angle (between 0 and 360 degrees).
    * **Saturation**: This is expressed as a percentage.
    * **Lightness** This is expressed as a percentage with 0% being white, 50% being normal, and 100% being black.
    * **alpha**: This is expressed as a
    number between 0 and 1.0 . For example, 0.5 represents 50% transparency, and 0.75 represents 75% transparency.

## Control the colors in css

**Foreground Color**

`color`: The color property allows you to specify the color of text inside an element.

**Background Article**

`background-color`: CSS treats each HTML element as if it appears in a box, and the `background-color` property sets the color of the background for that box.

**Contrast**

When picking foreground and background colors, it is important to ensure that there is enough contrast for the text to be legible.

**Opacity**

`opacity`, `rgba`: CSS3 introduces the opacity property which allows you to specify the opacity of an element and any of its child elements. The value is a number between 0.0 and 1.0 (so a value of 0.5 is 50% opacity and 0.15 is 15% opacity).

## Examlpe

```css
body {
        background-color: silver;
        color: white;
        padding: 20px;
        font-family: Arial, Verdana, sans-serif;}
h1 {
        background-color: #ffffff;
        background-color: hsla(0,100%,100%,0.5);
        color: #64645A;
        padding: inherit;}
p {
        background-color: rgb(238,62,128);}

```
