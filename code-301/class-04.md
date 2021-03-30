# Responsive Web Design and Regular Expressions

## Responsive Layouts with CSS Grid

![css grid](https://i.ytimg.com/vi/68O6eOGAGqA/maxresdefault.jpg)

### CSS Grid Layout Module

#### Grid Layout

The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.

![grid layout image](https://camo.githubusercontent.com/a34d4baa8ffb1dd08be1c198c596dcf8251bd371e73247235ea07b8ac0f29462/68747470733a2f2f69302e77702e636f6d2f7777772e6373737363726970742e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031372f30352f6d757572692e706e673f6669743d3630302532433435302673736c3d31)

#### Grid Elements

A grid layout consists of a parent element, with one or more child elements.

![grid elements image](https://camo.githubusercontent.com/09574fd23bf55274416be9eb3327a78d871e23fb02eab3f742e04d68465e393a/68747470733a2f2f757365722e6f632d7374617469632e636f6d2f75706c6f61642f323031382f30352f32382f313532373530363832333835365f703263342d322e706e67)

```html
<div class="grid-container">
  <div class="grid-item">1</div>
  <div class="grid-item">2</div>
  <div class="grid-item">3</div>
  <div class="grid-item">4</div>
  <div class="grid-item">5</div>
  <div class="grid-item">6</div>
  <div class="grid-item">7</div>
  <div class="grid-item">8</div>
  <div class="grid-item">9</div>
</div>
```

#### Display Property

An HTML element becomes a grid container when its `display` property is set to `grid` or `inline-grid`.

```css
.grid-container {
  display: grid;
}

.grid-container {
  display: inline-grid;
}
```

#### Grid Columns

The vertical lines of grid items are called columns.

![grid columns](https://camo.githubusercontent.com/d0266d30f46780a9fdb3818bdd2124a8c503d987ce6d2f9fb74d27fc6d177601/68747470733a2f2f7777772e77337363686f6f6c732e636f6d2f6373732f677269645f636f6c756d6e732e706e67)

#### Grid Rows

![grid rows](https://camo.githubusercontent.com/f6084c12ba5db47c9c38eeafc45a55370a780ec716ca93a901f26dc109dd81db/68747470733a2f2f7777772e77337363686f6f6c732e636f6d2f6373732f677269645f726f77732e706e67)

#### Grid Gaps

The spaces between each column/row are called gaps.

![grid gaps](https://camo.githubusercontent.com/bfe132c086c339141cfc9ed4b7737d3f5dbf01afd243c06ea3566f70e63f6971/68747470733a2f2f7777772e77337363686f6f6c732e636f6d2f6373732f677269645f676170732e706e67)

```css
.grid-container {
  display: grid;
  grid-column-gap: 50px;
}

.grid-container {
  display: grid;
  grid-row-gap: 50px;
}

.grid-container {
  display: grid;
  grid-gap: 50px 100px;
}

.grid-container {
  display: grid;
  grid-gap: 50px;
}
```

#### Grid Lines

The lines between columns are called column lines.

The lines between rows are called row lines.

![grid lines](https://camo.githubusercontent.com/a6380c12b7b51f41ad52310a790312180460fa39335e20de0cc528327ab454b1/68747470733a2f2f7777772e77337363686f6f6c732e636f6d2f6373732f677269645f6c696e65732e706e67)

```css
.item1 {
  grid-column-start: 1;
  grid-column-end: 3;
}

.item1 {
  grid-row-start: 1;
  grid-row-end: 3;
}
```

## JavaScript RegExp Reference

![JavaScript RegExp Reference](https://camo.githubusercontent.com/198b182bf8988c9f274de204c5ed687e35c250d53658e1f1215a27c1803a12e6/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f313032342f312a7451303148324c4874596c6b4a5874686774444b77412e6a706567)

### RegExp Object

A regular expression is an object that describes a pattern of characters.

Regular expressions are used to perform pattern-matching and "`search-and-replac`e" functions on text.

`var patt = /w3schools/i`

/**w3schools/i** is a regular expression. **w3schools** is a pattern (to be used in a search). **i** is a modifier (modifies the search to be case-insensitive).

![RegExp](https://camo.githubusercontent.com/39c1920e3e53827d19e7df090da985b94700c5ceb7c5e3c3e6eee244381b8a0b/68747470733a2f2f696d6167652e736c696465736861726563646e2e636f6d2f72656765782d3135313230343038323732352d6c7661312d617070363839312f39352f726567756c61722d65787072657373696f6e2d696e2d6a6176617363726970742d342d3633382e6a70673f63623d31343439353634373136)

![patterns](https://camo.githubusercontent.com/350ad0b3bea2a34b4b5f13bc52432a3b0092fe8694a6d0b2bb7794177f4ad238/68747470733a2f2f7777772e636f646570726f6a6563742e636f6d2f4b422f65787072657373696f6e2f313036333035322f32303135313133302d726567756c61722d65787072657373696f6e2d7061747465726e2e706e67)

![matching in html](https://cdn.tutsplus.com/net/uploads/legacy/404_regularExpressions/images/htmltag.jpg)

![character sets](https://camo.githubusercontent.com/9a043cabb8523985649d6a6a8fbea8da3bb39b91e2a70d7dd4c01f770a9655fe/68747470733a2f2f736c696465706c617965722e636f6d2f736c6964652f313538353939392f352f696d616765732f31392f4368617261637465722b536574732b546f2b6d617463682b616e792b6f6e652b6f662b612b7365742b6f662b706f737369626c652b636861726163746572732532432b7573652b7468652b7371756172652b627261636b6574732b746f2b737572726f756e642b7468656d2533412e6a7067)
