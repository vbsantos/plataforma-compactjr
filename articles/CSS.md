# CSS

## The Basics

### Inline, Embedded and External CSS file

#### Inline

```html
<!--CSS code as HTML element attribute-->
<p style="color:white; background-color:gray;">
    This is an example of inline styling.
</p>
```

#### Embedded/Internal CSS

```html
<html>
   <head>
      <!--CSS code start-->
      <style>
      p {
         color:white;
         background-color:gray;
      }
      </style>
      <!--CSS code end-->
   </head>
   <body>
      <p>This is my first paragraph. </p>
      <p>This is my second paragraph. </p>
   </body>
</html>
```

#### External CSS file

O CSS pode ser utilizado integrado no HTML, entretanto não é indicado, assim como qualquer interface gráfica ela pode ser feita em um arquivo separado (.css) e integrada ao HTML da seguinte maneira:

```html
<html>
 <head>
        <title>External CSS file</title>
        <!--O arquivo "example.css" terá todas as informações 
		referentes ao estilo, quanto o HTML terá somente o conteúdo 
		do site propriamente dito-->
   <link rel="stylesheet" href="example.css">
 </head>
 <body>
    <p>This is my first paragraph.</p>
     <p>This is my second paragraph. </p>
     <p>This is my third paragraph. </p>
 </body>
</html>
```

E dentro do arquivo example.css poderiamos ter:

```css
p {
   color:white;
   background-color:gray;
}
```

Resultando em uma página assim:

![img](https://api.sololearn.com/DownloadFile?id=2583)

> Both relative and absolute paths can be used to define the **href** for the CSS file. In our example, the path is relative, as the CSS file is in the same directory as the HTML file.

### CSS Rules and Selectors

#### Syntax

CSS is composed of style rules that the browser interprets and then applies to the corresponding elements in your document.
A style rule has three parts: **selector**, **property**, and **value**.

Por exemplo, a cor do título pode ser definida como:

```css
h1 {color: orange;}
```

Onde:

![img](https://api.sololearn.com/DownloadFile?id=2584)

The selector points to the HTML element you want to style.

>The declaration block contains one or more declarations, separated by semicolons. Each declaration includes a property name and a value, separated by a colon.

#### Type Selector

This selector targets element types on the page.

```css
p {
   color: red;
   font-size:130%;
}
```

#### ID Selectors

**id selectors** allow you to style an HTML element that has an **id** attribute, regardless of their position in the document tree. Here is an example of an id selector:

```html
<div id="intro">
   <p> This paragraph is in the intro section.</p>
</div>
<p> This paragraph is not in the intro section.</p>
```

```css
#intro {
   color: white;
   background-color: gray;
}
```

> To select an element with a specific id, use a hash character, and then follow it with the id of the element.

#### Class Selectors

Class selectors work in a similar way. The major difference is that <strong>IDs can only be applied once per page</strong>, while classes can be used as many times on a page as needed.

In the example below, both paragraphs having the class "first" will be affected by the CSS:

```html
<div>
   <p class="first">This is a paragraph</p>
   <p> This is the second paragraph. </p>
</div>
<p class="first"> This is not in the intro section</p>
<p> The second paragraph is not in the intro section. </p>
```

```css
.first {font-size: 200%;}
```

>To select elements with a specific class, use a period character, followed by the name of the class.
>Do **NOT** start a class or id name with a number!

#### Descendant Selectores

These selectors are used to select elements that are descendants of another element. When selecting levels, you can select as many levels deep as you need to.

For example, to target only \<em> elements in the first paragraph of the "intro" section:

```html
<div id="intro">
   <p class="first">This is a <em> paragraph.</em></p>
   <p>This is the second paragraph.</p>
</div>
<p class="first">This is not in the intro section.</p>
<p>The second paragraph is not in the intro section.</p>
```

```css
#intro .first em { /* em -> ênfase (itálico) */
    /* Esse bloco cria uma regra para todos os elementos em
 ênfase do primeiro parágrafo da introdução */
 color: pink;
 background-color:gray;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2992)

> The descendant selector matches all elements that are descendants of a specified element.

### Style Cascade and Inheritance

#### Cascade

The final appearance of a web page is a result of different styling rules.

The three main sources of style information that form a cascade are:

- The stylesheet created by the **author of the page**
- The **browser's default styles**
- Styles specified **by the user**

> CSS is an acronym for Cascading Style Sheets.

#### Inheritance

Inheritance refers to the way properties flow through the page. A child element will usually take on the characteristics of the parent element unless otherwise defined.

```html
<html>
  <head>
   <!--Nesse bloco alteramos a cor e fonte de todos os
		elementos dentro de <body>-->
   <style>
   body {
    color: green;
    font-family: Arial;
   }
   </style>
  </head>
  <body>
   <p>This is a text inside the paragraph.</p>
  </body>
</html>
```

> Since the paragraph tag (child element) is inside the body tag (parent element), it takes on any styles assigned to the body tag.

---

## Work with Text

### font-family

The font-family property specifies the font for an element.
There are two types of font family names:

- **font family**: a specific font family (like Times New Roman or Arial)
- **generic family**: a group of font families with a similar look (like Serif or Monospace)

![img](https://api.sololearn.com/DownloadFile?id=2721)

>Separate each value with a **comma** to indicate that they are alternatives.
>If the name of a font family is more than one word, it must be in quotation marks: **"Times New Roman"**.
> The font-family property should hold several font names as a "fallback" system. When specifying a web font in a CSS style, add more than one font name, in order to avoid unexpected behaviors. If the client computer for some reason doesn't have the one you choose, it will try the next one.

### font-size

```css
p.small {
   font-size: small;
}
p.medium {
   font-size: medium;
}
p.large {
   font-size: large;
}
p.xlarge {
   font-size: x-large;
}
```

> Keywords are useful if you do not want the user to be able to increase the size of the font because it will adversely affect your site's appearance.

Setting the font size in pixel values (**px**) is a good choice when you need pixel accuracy, and it gives you full control over the text size.

The **em** size unit is another way to set the font size (**em** is a relative size unit).

`em = pixels / 16`

> Try different combinations of text size and page zooming in a variety of browsers to ensure that the text remains readable.

### font-style

The font-style property is typically used to specify italic text.

```css
p.normal {
   font-style: normal;
}
p.italic {
   font-style: italic;
}
p.oblique {
   font-style: oblique;
}
```

> The HTML \<i\> tag will produce exactly the same result as the **italic font style**.

### font-weight

```css
p.light {
   font-weight: lighter;
}
p.bold {
   font-weight: bold;
}
p.bolder {
   font-weight: bolder;
}
```

> The HTML \<strong\> tag also makes the text **bold**.

### font-variant

```css
p.normal {
   font-variant: normal;
}
p.small {
   font-variant: small-caps;
}
```

> Not every font supports CSS font-variant, so be sure to test before you publish.

### color

```css
p.example {
   color: green;
}
```

### text-align

#### horizontally

```css
p.left {
   text-align: left;
}
p.right {
   text-align: right;
}
p.center {
   text-align: center;
}
```

> When text-align is set to "**justify**", each line is stretched so that every line has equal width, and the left and right margins are straight (as in magazines and newspapers).

#### vertically

The vertical-align property sets an element's vertical alignment. Commonly used values are **top**, **middle**, and **bottom**.

```css
td.top {
   vertical-align: top;
}
td.middle {
   vertical-align: middle;
}
td.bottom {
   vertical-align: bottom;
}
```

The vertical-align property also takes the following values: **baseline**, **sub**, **super**, **%** and **px** (or pt, cm).

```css
span.baseline {
    vertical-align: baseline;
}
span.sub {
    vertical-align: sub;
}
span.super {
    vertical-align: super;
}
span.pixel {
    vertical-align: -10px;
}
```

Vertical align property does not act the same way for all elements.
For example, some additional CSS styling is needed for div elements.

```css
.main {
    height: 150px; width: 400px;
    background-color: LightSkyBlue;
    display: inline-table;
}
.paragraph {
    display: table-cell;
    vertical-align: middle;
}
```

> **display: inline-table;** and **display: table-cell;** styling rules are applied to make the vertical-align property work with divs

### text-decoration

Commonly used values are:
**none** - The default value, this defines a normal text
**inherit** - Inherits this property from its parent element
**overline** - Draws a horizontal line above the text
**underline** - Draws a horizontal line below the text
**line-through** - draws a horizontal line through the text (substitutes the HTML \<s\> tag)

```css
p.none {
   text-decoration: none;
}
p.inherit {
   text-decoration: inherit;
}
p.overline {
   text-decoration: overline;
}
p.underline {
   text-decoration: underline;
}
p.line-through {
   text-decoration: line-through;
}
```

Another value of text-decoration property is **blink** which makes the text blink.

```css
text-decoration: blink;
```

> This value is valid but is deprecated and most browsers ignore it.

### text-indent

The text-indent property specifies how much horizontal space should be left before the beginning of the first line of the text. Property values are **length** (px, pt, cm, em, etc.), **%**, and **inherit**.

```css
p {
   text-indent: 60px;
}
```

> Negative values are allowed. The first line will be indented to the left if the value is negative.

### text-shadow

The text-shadow property adds shadow to text.
It takes four values: the first value defines the distance of the shadow in the **x (horizontal) direction**, the second value sets the distance in the **y (vertical) direction**, the third value defines the **blur** of the shadow, and the fourth value sets the **color**.

```css
h1 {
    color: blue;
    font-size: 30pt;
    text-shadow: 5px 2px 4px grey;
    /* x y blur-radius color */
}
```

In the example above, we created a shadow using the following parameters:
**5px** – the X-coordinate
**2px** – the Y-coordinate
**4px** – the blur radius
**grey** – the color of the shadow

> To add more than one shadow to the text, add a comma-separated list of shadows.

The example below creates a blue drop-shadow, two pixels higher than the main text, one pixel to the left of it, and with a 0.5em blur:

```css
h1 {
   font-size: 20pt;
   text-shadow: rgba(0,0,255,1) -1px -2px 0.5em;
}
```

### text-transform

The text-transform CSS property specifies how to capitalize an element's text. For example, it can be used to make text appear with each word capitalized.

```css
p.capitalize {
   text-transform: capitalize;
}
p.uppercase {
   text-transform: uppercase;
}
p.lowercase {
   text-transform: lowercase;
}
```

> The value **none** will produce no capitalization effect at all.

### letter-spacing

The letter-spacing property specifies the **space between characters** in a text. The values can be set as:

- **normal** defines the default style with no extra space between characters
- **length** defines an extra space between characters using measurement units like px, pt, cm, mm, etc.
- **inherit** inherits the property from its parent element

```css
p.normal {
   letter-spacing: normal;
}
p.positive {
   letter-spacing: 4px;
}
p.negative {
   letter-spacing: -1.5px;
}
```

### word-spacing

The word-spacing property specifies the **space between words** in a text. Just like the letter-spacing property, you can set the word-spacing values as **normal**, **length**, and **inherit**.

```css
p.normal {
   word-spacing: normal;
}
p.positive {
   word-spacing: 20px;
}
p.negative {
   word-spacing: -5px;
}
```

### white-spacing

The white-space property specifies how white-space inside an element is handled. The values can be set as **normal**, **inherit**, **nowrap**, etc.

The **nowrap** value makes the text continue on the same line until a \<br\> tag is encountered, and also collapses all sequences of whitespace into a single whitespace.

The white-space property also supports other values:
**pre** - text will only wrap on line breaks and white space
**pre-line** - text will wrap where there is a break in code, but extra white space is still ignored
**pre-wrap** - text will wrap when necessary, and on line breaks

Here is an example in which all three values are used:

```css
p {
   white-space: nowrap;
}
p.pre {
   white-space: pre;
}
p.preline {
   white-space: pre-line;
}
p.prewrap {
   white-space: pre-wrap;
}
```

> **Pre-wrap** value behaves as the **pre** value, except that it adds extra line breaks to prevent the text breaking out of the element's box.

---

## Properties

### Box Model (margin & padding)

All HTML elements can be considered as boxes. The CSS box model represents the design and layout of the site. It consists of **margins**, **borders**, **paddings**, and the actual **content**.

The properties work in the same order: **top**, **right**, **bottom**, and **left**.

The image below illustrates the box model:

![img](https://api.sololearn.com/DownloadFile?id=2613)

> The term "box model" is used when talking about design and layout.
> The box model is also used to calculate the actual width and height of the HTML elements.

![img](https://api.sololearn.com/DownloadFile?id=3013)

>When you set the width and height properties of an element with CSS, you set the width and height of the content area.
>When setting a background-color to a box, it covers the content area, as well as the **padding**.

![img](https://api.sololearn.com/DownloadFile?id=3014)

> To summarize, Total element height = height + top padding + bottom padding + top border + bottom border + top margin + bottom margin

### Border

In order to add a border to the element, you need to specify the **size**, **style**, and **color** of the border.

```css
p {
   padding: 10px;
   border: 5px solid green;
}
```

The properties for the border can be set separately.

```css
p.first {
   padding: 10px;
   border-style: solid;
   border-width: 2px;
   border-color: blue;
}
```

> None of the border properties will have any effect unless the **border-style** property is set.

#### border-style

The default value of border-style is **none**, which defines no border.

```css
p.none {border-style: none;}
p.dotted {border-style: dotted;}
p.dashed {border-style: dashed;}
p.double {border-style: double;}
p.groove {border-style: groove;}
p.ridge {border-style: ridge;}
p.inset {border-style: inset;}
p.outset {border-style: outset;}
p.hidden {border-style: hidden;}
```

> In CSS, it is possible to specify different borders for different sides, using the following properties: border-top-style, border-right-style, border-bottom-style, and border-left-style for the corresponding sides.

### Width and Height

To style a \<div\> element to have a total width and height of **100px**:

```css
div {
   border: 5px solid green;
   width: 90px;
   height: 90px;
}
```

> The total width and height of the box will be the 90px+5px (border)+5px(border) = 100px;

The width and height of an element can be also assigned using **percents.**

```css
div {
   border: 5px solid green;
   width: 100%;
   height: 90px;
}
```

To set the minimum and maximum height and width of an element, you can use the following properties:

**min-width** - the minimum width of an element
**min-height** - the minimum height of an element
**max-width** - the maximum width of an element
**max-height** - the maximum height of an element

```css
p.first {
   border: 5px solid green;
   min-height: 100px;
}
p.second {
   border: 5px solid green;
   max-width: 100px;
}
```

### background-color

```css
body {
   background-color: #C0C0C0;
}
h1 {
   background-color: rgb(135,206,235);
}
p {
   background-color: LightGreen;
}
```

### background-image

```css
body {
   background-image: url("css_logo.png");
   background-color: #e9e9e9;
}
```

> The **url** specifies the path to the image file. Both relative and absolute paths are supported.
> By default, a background-image is placed at the top-left corner of an element, and is repeated both vertically and horizontally to cover the entire element.

![img](https://api.sololearn.com/DownloadFile?id=2626)

Background-image can be set not only for the whole page, but for individual elements, as well.

> To specify more than one image, just separate the URLs with **commas**.

```css
.hero-image {
  background-image: url("photographer.jpg"); /* The image used */
  background-color: #cccccc; /* Used if the image is unavailable */
  height: 500px; /* You must set a specified height */
  background-position: center; /* Center the image */
  background-repeat: no-repeat; /* Do not repeat the image */
  background-size: cover; /* Resize the background image to cover the entire container */
}
```

### background-repeat

The background repeat property specifies how background images are repeated. A background image can be repeated along the **horizontal axis**, the **vertical axis**, **both axes**, or **not repeated at all**.

The **repeat-x** will repeat a background image only **horizontally**.

```css
body {
   background-image: url("css_logo.png");
   background-repeat: repeat-x;  
}
```

The **repeat-y** will repeat a background-image only **vertically**.

> If you want the image to be shown only **once**, use the **no-repeat** value.

When you set the background-repeat property to **inherit**, it will take the same specified value as the property for the element's parent.

```css
body {
   background-image: url("css_logo.png");
   background-repeat: repeat-x;
}
p {
   background-image: url("css_logo.png");
   background-repeat: inherit;
   margin-top: 100px;
   padding: 40px;
}
```

### background-attachment

The background-attachment property sets whether a background image is fixed or scrolls with the rest of the page.
Even if an element has a scrolling mechanism, a "fixed" background doesn't move with the element.

```css
body {
   background-image: url("css_logo.png");
   background-repeat: no-repeat;
   background-attachment: fixed;
}
```

You can also set the background-attachment to **inherit** or **scroll**.

When you set the background-attachment to **scroll**, the background image will scroll with the rest of the content.

```css
body {
   background-image: url("css_logo.png");
   background-repeat: no-repeat;
   background-attachment: scroll;
}
```

### List

The CSS list properties allow us to set different list item markers. In HTML, there are two types of lists:
**unordered lists** (\<ul>) - the list items are marked with bullets
**ordered lists** (\<ol>) - the list items are marked with numbers or letters
With CSS, lists can be styled further, and images can be used as the list item marker.
One of the ways is to use the **list-style-type** property, which can be set to **circle**, **square**, **decimal**, **disc**, **lower-alpha**, etc.

```css
ol.lower-alpha {
   list-style-type: lower-alpha;
}
ul.circle {
   list-style-type: circle;
}
ul.square {
   list-style-type: square;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2634)

> Some of the values are for unordered lists, and some for ordered lists.

There are also other list properties, such as:
**list-style-image** - specifies an image to be used as the list item marker.
**list-style-position** - specifies the position of the marker box (inside, outside).

In the example below, we use an image as the list item marker, and specify the position to be inside of the content flow.

```css
ul {
   list-style-image: url("logo.jpg");
   list-style-position: inside;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2635)

> "list-style-position: **outside**" is the default value.

The **list-style** property is a shorthand property for setting list-style-type, list-style-image and list-style-position. It is used to set all of the list properties in one declaration:

```css
ul {
   list-style: square outside none;
}
```

ou:

```css
ul {
   list-style-type: square;
   list-style-position: outside;
   list-style-image: none;
}
```

> If one of the property values are missing, the default value for the missing property will be inserted, if any.

### Tables

#### border-collapse

The **border-collapse** property specifies whether the table borders are collapsed into a single border or separated as default. If the borders are separate, the **border-spacing** property can be used to change the spacing.

```css
table {
   border-collapse: separate;
   border-spacing: 20px 40px;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2637)

#### caption-side

The **caption-side** property specifies the position of a table caption. The values can be set as **top** or **bottom**.

```css
caption {
   caption-side: top;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2638)

#### empty-cells

The **empty-cells** property specifies whether or not to display borders and background on empty cells in a table.
Possible values are:
**show**: the borders of an empty cell are rendered
**hide**: the borders of an empty cell are not drawn

```css
table {
   border-collapse: separate;
   empty-cells: hide;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2639)

#### table-layout

The **table-layout** specifies how the width of table columns is calculated. The possible values are:
**auto** - when column or cell width are not explicitly set, the column width will be in proportion to the amount of content in the cells that make up the column
**fixed** - when column or cell width are not explicitly set, the column width will not be affected by the amount of content in the cells that make up the column.

The table layout is set to **auto** by default.

```css
table {
   border-collapse: separate;
   width: 100%;
   border: 1px solid gray;
}
td {
   border: 1px solid gray;
}
table.auto {
   table-layout: auto;
}
table.fixed {
   table-layout: fixed;
}
```

<img src="https://api.sololearn.com/DownloadFile?id=2640" alt="img" />

### Links

Links can be styled with any CSS property (e.g., color, font-family, background, etc.).
In addition, links can be styled differently, depending on what state they are in. The following pseudo selectors are available:
**a:link** - defines the style for normal unvisited links
**a:visited** - defines the style for visited links
**a:active** - a link becomes active once you click on it
**a:hover** - a link is hovered when the mouse is over it

The example below creates a link that will change the style when the mouse is moved over it.

>When setting the style for several link states, there are some order rules
>
>- a:hover **MUST** come after a:link and a:visited
>- a:active **MUST** come after a:hover
One of the most common uses of CSS with links is to **remove the underline**. In the example below, the **text-decoration** property is used to remove the underline.

```css
a:link {
   text-decoration: none;
}
```

>The following properties are used to control the look and feel of links:
>**border:none** - removes border from images with links
>**outline:none** - removes the dotted border on clicked lines in IE

### Mouse Cursor

CSS allows you to set your desired cursor style when you mouse over an element. For example, you can change your cursor into a hand icon, help icon, and much more, rather than using the default pointer.

In the example below, the mouse pointer is set to a help icon when we mouse over the span element:

```html
<span style="cursor:help;">
   Do you need help?
</span>
```

There are numerous other possible values for the **cursor** property, such as:
**default** - default cursor
**crosshair** - cursor displays as crosshair
**pointer** - cursor displays hand icon
The list of possible values is quite long. The image below demonstrates the various available styles:

![img](https://api.sololearn.com/DownloadFile?id=2983)

> CSS allows you to set your desired cursor style when you mouse over an element.

Usually, the appearance of the mouse cursor is altered to provide a more interesting experience for website visitors. However, choosing the wrong cursor style can be misleading, as well, if the cursor value is set to **default**, users may not "see" the links.

---

## Positioning and Layout

### Display

#### block

Every element on a web page is a rectangular box.The **display** property determines how that rectangular box behaves. A block element is an element that takes up the fullest width available, with line breaks before and after.
The style rules in the following example display the inline \<span\> elements as block-level elements:

```css
span {
   display: block;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2647)

#### inline

An **inline** element only takes up as much width as necessary, and does not force line breaks.

```css
p {
   display: inline;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2648)

> Setting the display property of an element only changes how the element is displayed, not what kind of element it is. So, an inline element with **display:block** is not allowed to have other block elements inside it.

#### none

**display:none** hides an element, so it does not take up any space. The element will be hidden, and the page will be displayed as if the element is not there.

```css
h1 {
   display: none;
}
```

> There are plenty of other display values, such as **list-item**, **table**, **table-cell**, **table-column**, **grid**, etc. Just play with values to see the difference.

### visibility

The **visibility** property specifies whether an element is visible or hidden. The most common values are **visible** and **hidden**.

Hiding an element can be done by setting the display property to "none" or the visibility property to "hidden". However, notice that these two methods produce different results:
**visibility:hidden** hides an element, but it will still take up the same space as before. The element will be hidden, but it will still affect the layout:

```css
div.hidden {
   visibility: hidden;
}
/*or*/
div.hidden {
   display: none;
}
```

### Position

The CSS positioning properties allow you to position an element. It can also place an element behind another, and specify what should happen when an element's content is too big.

Elements can be positioned using the top, bottom, left, and right properties. However, these properties will not work unless the **position** property is set first. They also work differently depending on the positioning method.

#### Static

HTML elements are positioned **static** by default. A static positioned element is always positioned according to the normal flow of the page.

```css
p.position_static {
   position: static;
   top: 30px;
   right: 5px;
   color: red;
}
```

> Static positioned elements are not affected by the top, bottom, left, and right properties.

#### Fixed

An element with a fixed position is positioned relative to the browser window, and will not move even if the window is scrolled.
The position can be specified using one or more of the properties **top**, **right**, **bottom**, and **left**.
In the example below, the paragraph is fixed to 30px from the top and 5px from the right.

```css
p.position_fixed {
   position: fixed;
   top: 30px;
   right: 5px;
   color: red;
}
```

> Fixed positioned elements are removed from the normal flow. The document and other elements behave like the fixed positioned element does not exist.
> Fixed positioned elements can overlap other elements.

#### Relative

A relative positioned element is positioned relative to its normal position.
The properties **top**, **right**, **bottom**, and **left** can be used to specify how the rendered box will be shifted.

```css
p {
   width: 350px;
   border: 1px black solid;
   position: fixed;
}
span {
   background: green;
   color: white;
   position: relative;
   top: 150px;
   left: 50px;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2996)

The content of relatively positioned elements can be moved and overlap other elements, but the reserved space for the element is still preserved in the normal flow.

>This value cannot be used for **table cells**, **columns**, **column groups**, **rows**, **row groups**, or **captions**.

#### Absolute

An absolute position element is positioned relative to the first parent element that has a position other than static. If no such element is found, the containing block is \<html>.

Absolutely positioned elements are removed from the normal flow. The document and other elements behave like the absolutely positioned element does not exist.

Absolutely positioned elements can overlap other elements.

### Floating

With CSS float, an element can be pushed to the left or right, allowing other elements to wrap around it.
Float is often used with images, but it is also useful when working with layouts.
The values for the float property are **left**, **right**, and **none**.
Left and right float elements in those directions, respectively. **none** (the default) ensures that the element will not float.
Below is an example of an image that is floated to the right.

```css
img {
   float: right;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2655)

> Elements are floated horizontally, meaning that an element can only be floated left or right, not up or down.

If you place several floating elements one after the other, they will float next to each other if there is enough room.
As an example, in a print layout, images may be set into the page such that text wraps around them as needed.

```css
img {
   float: left;
   width: 120px;
   margin-right: 10px;
}
p {
   width: 120px;
   float: left;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2656)

### Clear

Elements that come after the floating element will flow around it. To avoid this, use the clear property. The **clear** property specifies the sides of an element where other floating elements are not allowed to be.

```css
.floating {
   float: right;
}
.clearing {
   clear: both;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2658)

### Overflow

**overflow** property specifies the behavior that occurs when an element's content overflows the element's box.

There are four values for the overflow property: **visible** (the default value), **scroll**, **hidden**, and **auto**.

The value **scroll** results in clipped overflow, but a scrollbar is added, so the rest of the content may be seen.

```css
div {
   width: 150px;
   height: 150px;
   background-color: LightBlue;
   float: left;
   overflow: scroll;
}
```

> The code above will produce both **horizontal** and **vertical** scrollbars:

**auto** - If overflow is clipped, a scroll-bar should be added to make it possible to see the rest of the content.
**hidden** - The overflow is clipped, and the rest of the content will be invisible.

```css
div {
   width: 150px;
   height: 150px;
   background-color: LightBlue;
   float: left;
   overflow: hidden;
}
```

> The default value for the overflow property is **visible**.

### z-index

The **z-index** property specifies the stack order of an element (which element should be placed in front of, or behind, the others).

```css
.blue {
   background-color: #8EC4D0;
   margin-bottom: 15px;
   width: 120px;
   height: 120px;
   color: #FFF;
}
.red {
   background-color: #FF4D4D;
   position: relative;
   width: 120px;
   height: 120px;
   color: #FFF;
   margin-top: -50px;
   margin-left: 50px;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2662)

>The red box overlaps the blue box, because it was placed **later** in the HTML markup.
>The **z-index** property can change this order.

Assigning a higher z-index value to the blue div and a lower z-index value to the red div will result in the following:

```css
.blue {
   z-index: 3;
   position: relative;
}
.red {
   z-index: 2;
   position: relative;
}
```

![img](https://api.sololearn.com/DownloadFile?id=2663)

> The z-index works **only** on positioned elements (position:absolute, position:relative, or position:fixed).

---

## CSS3 Basics
