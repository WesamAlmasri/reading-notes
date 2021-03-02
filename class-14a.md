# CSS Transforms, Transitions, and Animations

![css animation image](https://hackernoon.com/drafts/x84g2geg.png)

## CSS Transforms

![CSS Transforms image](https://www.htmldog.com/figures/transform.png)

It is an alternative ways to size, position, and change elements. The `transform` property comes in two different settings, **two-dimensional** and **three-dimensional**. Each of these come with their own individual properties and values.

### Transform Syntax

The actual syntax for the `transform` property is quite simple, including the transform property followed by the value. The value specifies the transform type followed by a specific amount inside parentheses.

```css
div {
  -webkit-transform: scale(1.5);
     -moz-transform: scale(1.5);
       -o-transform: scale(1.5);
          transform: scale(1.5);
}
```

Notice how the `transform` property includes multiple vendor prefixes to gain the best support across all browsers. The un-prefixed declaration comes last to overwrite the prefixed versions, should a browser fully support the transform property.

### 2D Transforms

Elements may be distorted, or transformed, on both a two-dimensional plane or a three-dimensional plane. Two-dimensional transforms work on the `x` and `y` axes, known as horizontal and vertical axes. Three-dimensional transforms work on both the `x` and `y` axes, as well as the `z` axis. These three-dimensional transforms help define not only the length and width of an element, but also the depth.

The transform property accepts a handful of **different values** as below:

#### 2D Rotate

The `rotate` value provides the ability to rotate an element from 0 to 360 degrees. Using a positive value will rotate an element clockwise, and using a negative value will rotate the element counterclockwise. The default point of rotation is the center of the element, 50% 50%, both horizontally and vertically.

```html
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```

```css
.box-1 {
  transform: rotate(20deg);
}
.box-2 {
  transform: rotate(-55deg);
}
```

#### 2D Scale

Using the `scale` value within the transform property allows you to change the appeared size of an element. The default scale value is 1, therefore any value between .99 and .01 makes an element appear smaller while any value greater than or equal to 1.01 makes an element appear larger.

```css
.box-1 {
  transform: scale(.75);
}
.box-2 {
  transform: scale(1.25);
}
```

It is possible to scale only the height or width of an element using the `scaleX` and `scaleY` values. To scale both the height and width of an element but at different sizes, the `x` and `y` axis values may be set simultaneously. To do so, use the scale transform declaring the `x` axis value first, followed by a comma, and then the `y` axis value.

```css
.box-1 {
  transform: scaleX(.5);
}
.box-2 {
  transform: scaleY(1.15);
}
.box-3 {
  transform: scale(.5, 1.15);
}
```

#### 2D Translate

The `translate` value works a bit like that of relative positioning, pushing and pulling an element in different directions without interrupting the normal flow of the document. Using the translateX value will change the position of an element on the horizontal axis while using the translateY value will change the position of an element on the vertical axis.

As with the scale value, to set both the x and y axis values at once, use the translate value and declare the x axis value first, followed by a comma, and then the y axis value.

```css
.box-1 {
  transform: translateX(-10px);
}
.box-2 {
  transform: translateY(25%);
}
.box-3 {
  transform: translate(-10px, 25%);
}
```

#### 2D Skew

The last transform value in the group, `skew`, is used to distort elements on the horizontal axis, vertical axis, or both. The syntax is very similar to that of the `scale` and `translate` values.

```css
box-1 {
  transform: skewX(5deg);
}
.box-2 {
  transform: skewY(-20deg);
}
.box-3 {
  transform: skew(5deg, -20deg);
}
```

### Combining Transforms

It is common for multiple transforms to be used at once, rotating and scaling the size of an element at the same time for example. In this event multiple transforms can be combined together. To combine transforms, list the transform values within the `transform` property one after the other without the use of commas.

Using multiple `transform` declarations will not work, as each declaration will overwrite the one above it. The behavior in that case would be the same as if you were to set the `height` of an element numerous times.

```css
.box-1 {
  transform: rotate(25deg) scale(.75);
}
.box-2 {
  transform: skew(10deg, 20deg) translateX(20px);
}
```

### Transform Origin

As previously mentioned, the default transform origin is the dead center of an element, both `50%` horizontally and `50%` vertically. To change this default origin position the `transform-origin` property may be used.

The `transform-origin` property can accept one or two values. When only one value is specified, that value is used for both the horizontal and vertical axes. If two values are specified, the first is used for the horizontal axis and the second is used for the vertical axis.

```css
.box-1 {
  transform: rotate(15deg);
  transform-origin: 0 0;
}
.box-2 {
  transform: scale(.5);
  transform-origin: 100% 100%;
}
.box-3 {
  transform: skewX(20deg);
  transform-origin: top left;
}
.box-4 {
  transform: scale(.75) translate(-10px, -10px);
  transform-origin: 20px 50px;
}
```

## CSS Transitions & Animations

![css transition](https://www.freecodecamp.org/news/content/images/size/w2000/2020/10/Untitled--2--1.png)

### Transitions

CSS transitions allows you to change property values smoothly, over a given duration.

- `transition`
- `transition-delay`
- `transition-duration`
- `transition-property`
- `transition-timing-function`

#### How to Use CSS Transition?

To create a transition effect, you must specify two things:

1. the CSS property you want to add an effect to
2. The duration of the effect

Note: If the duration part is not specified, the transition will have no effect, because the default value is 0.

The following example shows a `100px` * `100px` red `<div>` element. The `<div>` element has also specified a transition effect for the width property, with a duration of 2 seconds:

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s;
}
```

You can specify the properity and the duration separetly using `transition-property` and the `transition-duration`

The transition effect will start when the specified CSS property (`width`) changes value.

```css
div:hover {
  width: 300px;
}
```

Notice that when the cursor mouses out of the element, it will gradually change back to its original style.

#### Change Several Property Values

The following example adds a transition effect for both the `width` and `height` property, with a duration of 2 seconds for the width and 4 seconds for the height:

```css
div {
  transition: width 2s, height 4s;
}
```

#### Specify the Speed Curve of the Transition

The `transition-timing-function` property specifies the speed curve of the transition effect.

- `ease` - specifies a transition effect with a slow start, then fast, then end slowly (this is default)
- `linear` - specifies a transition effect with the same speed from start to end
- `ease-in` - specifies a transition effect with a slow start
- `ease-out` - specifies a transition effect with a slow end
- `ease-in-out` - specifies a transition effect with a slow start and end
- `cubic-bezier(n,n,n,n)` - lets you define your own values in a cubic-bezier function

```css
#div1 {transition-timing-function: linear;}
#div2 {transition-timing-function: ease;}
#div3 {transition-timing-function: ease-in;}
#div4 {transition-timing-function: ease-out;}
#div5 {transition-timing-function: ease-in-out;}
```

![CSS Transitions image](https://miro.medium.com/max/900/1*_6MfwckxNfQTca9SiG8MdQ.png)

#### Delay the Transition Effect

The `transition-delay` property specifies a delay (in seconds) for the transition effect.

```css
div {
  transition-delay: 1s;
}
```

Other example:

```css
.box {
  background: #2db34a;
  border-radius: 6px;
  transition-property: background, border-radius;
  transition-duration: .2s, 1s;
  transition-timing-function: linear, ease-in;
}
.box:hover {
  background: #ff7b29;
  border-radius: 50%;
}
```

```css
.box {
  background: #2db34a;
  border-radius: 6px;
  transition: background .2s linear, border-radius 1s ease-in 1s;
}
.box:hover {
  color: #ff7b29;
  border-radius: 50%;
}
```

### Animations

![CSS Animations image](https://miro.medium.com/max/700/1*7Rr1n9DBuy3z7CfxedW7aw.png)

Transitions do a great job of building out visual interactions from one state to another, and are perfect for these kinds of single state changes. However, when more control is required, transitions need to have multiple states. In return, this is where animations pick up where transitions leave off.

#### Animations Keyframes

To set multiple points at which an element should undergo a transition, use the `@keyframes` rule. The `@keyframes` rule includes the animation name, any animation breakpoints, and the properties intended to be animated.

```css
@keyframes slide {
  0% {
    left: 0;
    top: 0;
  }
  50% {
    left: 244px;
    top: 100px;
  }
  100% {
    left: 488px;
    top: 0;
  }
}
```

The animation above is named `slide`, stated directly after the opening `@keyframes` rule. The different keyframe breakpoints are set using percentages, starting at `0%` and working to `100%` with an intermediate breakpoint at `50%`. The keywords from and to could be used in place of `0%` and `100%` if wished. Additional breakpoints, besides `50%`, may also be stated. The element properties to be animated are listed inside each of the breakpoints, `left` and `top` in the example above.

It is important to note, as with transitions only individual properties may be animated. Consider how you might move an element from top to bottom for example. Trying to animate from `top: 0;` to `bottom: 0;` will not work, because animations can only apply a transition within a single property, not from one property to another. In this case, the element will need to be animated from `top: 0;` to `top: 100%;`.

#### Animation Name

nce the keyframes for an animation have been declared they need to be assigned to an element. To do so, the `animation-name` property is used with the animation name, identified from the `@keyframes` rule, as the property value. The a`nimation-name` declaration is applied to the element in which the animation is to be applied to.

```css
.stage:hover .ball {
  animation-name: slide;
}
```

Using the `animation-name` property alone isn’t enough though. You also need to declare an `animation-duration` property and value so that the browser knows how long an animation should take to complete.

#### Animation Duration, Timing Function, & Delay

Once you have declared the animation-name property on an element, animations behave similarly to transitions. They include a duration, timing function, and delay if desired. To start, animations need a duration declared using the `animation-duration` property. As with transitions, the duration may be set in seconds or milliseconds.

A timing function and delay can be declared using the `animation-timing-function` and `animation-delay` properties respectively. The values for these properties mimic and behave just as they do with transitions.

```css
.stage:hover .ball {
  animation-name: slide;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: .5s;
}
```

Example:

```html
<div class="stage">
  <figure class="ball"></figure>
</div>
```

```css
@keyframes slide {
  0% {
    left: 0;
    top: 0;
  }
  50% {
    left: 244px;
    top: 100px;
  }
  100% {
    left: 488px;
    top: 0;
  }
}
.stage {
  height: 150px;
  position: relative;
}
.ball {
    height: 50px;
    position: absolute;
    width: 50px;
}
.stage:hover .ball {
  animation-name: slide;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: .5s;
}
```

#### Animation Iteration

By default, animations run their cycle once from beginning to end and then stop. To have an animation repeat itself numerous times the `animation-iteration-count` property may be used. Values for the `animation-iteration-count` property include either an integer or the `infinite` keyword. Using an integer will repeat the animation as many times as specified, while the `infinite` keyword will repeat the animation indefinitely in a never ending fashion.

```css
.stage:hover .ball {
  animation-name: slide;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: .5s;
  animation-iteration-count: infinite;
}
```

#### Animation Direction

On top of being able to set the number of times an animation repeats, you may also declare the direction an animation completes using the `animation-direction` property. Values for the `animation-direction` property include `normal`, `reverse`, `alternate`, and `alternate-reverse`.

#### Animation Play State

The `animation-play-state` property allows an animation to be played or paused using the `running` and `paused` keyword values respectively. When you play a paused animation, it will resume running from its current state rather than starting from the very beginning again.

```css
.stage:hover .ball {
  animation-name: slide;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: .5s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
.stage:active .ball {
  animation-play-state: paused;
}
```

#### Animation Fill Mode

The `animation-fill-mode` property identifies how an element should be styled either before, after, or before and after an animation is run. The `animation-fill-mode` property accepts four keyword values, including `none`, `forwards`, `backwards`, and `both`.

The `none` value will not apply any styles to an element before or after an animation has been run.

The `forwards` value will keep the styles declared within the last specified keyframe. These styles may, however, be affected by the `animation-direction` and `animation-iteration-count` property values, changing exactly where an animation ends.

The `backwards` value will apply the styles within the first specified keyframe as soon as being identified, before the animation has been run. This does include applying those styles during any time that may be set within an animation delay. The `backwards` value may also be affected by the `animation-direction` property value.

Lastly, the both value will apply the behaviors from both the `forwards` and `backwards` values.

```css
.stage:hover .ball {
  animation-name: slide;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: .5s;
  animation-fill-mode: forwards;
}
.stage:active .ball {
  animation-play-state: paused;
}
```

#### Shorthand Animations

Fortunately animations, just like transitions, can be written out in a shorthand format. This is accomplished with one `animation` property, rather than multiple declarations. The order of values within the `animation` property should be `animation-name`, `animation-duration`, `animation-timing-function`, `animation-delay`, `animation-iteration-count`, `animation-direction`, `animation-fill-mode`, and lastly `animation-play-state`.

```css
.stage:hover .ball {
  animation: slide 2s ease-in-out .5s infinite alternate;
}
.stage:active .ball {
  animation-play-state: paused;
}
```
