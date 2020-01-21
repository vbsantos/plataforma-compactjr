# HTML

## Básico

### Paragraphs

O código HTML é formado por elementos como:

- **Head**: Não visual.
  - **title**: Aparece na guia do navegador.
- **Body**: Componentes visuais.
  - **p**: Marca um parágrafo.
  - **br**: Pula linha.

Exemplo:

```html
<html>
  <head>
    <title>Paragraphs</title>
  </head>
  <body>
    <p>Isso é um paragrafo.</p>
    <p>Nesse paragrafo<br />pula linha.</p>
  </body>
</html>
```

### Text Formatting

```html
<html>
  <head>
    <tile>Text Formatting</tile>
  </head>
  <body>
    <p>This is regular text</p>
    <p><b>This is bold text</b></p>
    <p><big>This is big text</big></p>
    <p><i>This is italic text</i></p>
    <p><small>This is small text</small></p>
    <p><strong>This is strong text</strong></p>
    <p><sub>This is subscripted text</sub></p>
    <p><sup>This is superscripted text</sup></p>
    <p><ins>This is inserted text</ins></p>
    <p><del>This is deleted text</del></p>
  </body>
</html>
```

### Headings, Lines, Comments

Seis níveis de título:

```html
<html>
  <head>
    <title>Headings, Lines, Comments</title>
  </head>
  <body>
    <h1>titulo 1</h1>
    <h2>titulo 2</h2>
    <h3>titulo 3</h3>
    <hr />
    <!--Comentário: Linha Horizontal-->
    <h4>titulo 4</h4>
    <h5>titulo 5</h5>
    <h6>titulo 6</h6>
  </body>
</html>
```

## Intermediário

### Attributes

Informações adicionais aos elementos.

```html
<html>
  <head>
    <title>Attributes</title>
  </head>
  <body>
    <!--Mesma hierarquia de títulos deste documento-->
    <h1>HTML</h1>
    <h2>Intermediário</h2>
    <h3>Attributes</h3>
    <!--Exemplo de "HTML attributes"-->
    <p align="center">This text is aligned to center.</p>
    <!--Exemplo usando medida em pixels-->
    <hr width="50px" />
    <!--Exemplo usando medida em porcentagem-->
    <hr width="50%" />
    <!--Exemplo usando mais de um atributo-->
    <hr width="10%" align="right" />
  </body>
</html>
```

### Images

Insere uma imagem na pagina, contém atributos.

```html
<html>
  <head>
    <title>Images</title>
  </head>
  <body>
    <!--No caso da imagem não poder sem mostrada no site, o atributo "alt" 
		especifica um texto que descreve a imagem. Esse atributo é obrigatório.-->
    <img src="tree.jpg" height="150px" width="150px" alt="" />
    <img src="tree.jpg" height="50%" width="50%" alt="" />
    <!-- Navegadores como o IE exibem borda, a não ser que especifique. -->
    <img src="tree.jpg" height="150px" width="150px" border="1px" alt="" />
  </body>
</html>
```

### Links

Ao clicar em "Learn Playing" você é redirecionado para "<http://www.sololearn.com">

```html
<html>
  <head>
    <title>Links</title>
  </head>
  <body>
    <a href="http://www.sololearn.com"> Learn Playing </a>
    <!--Giving a "_blank" value to your attribute will have the link open in
		a new window or new tab.-->
    <a href="http://www.sololearn.com" target="_blank"> Learn Playing </a>
  </body>
</html>
```

### Lists

```html
<html>
  <head>
    <title>Lists</title>
  </head>
  <body>
    <p>
      Cores que eu mais gosto:
    </p>
    <!--Lista Numerada-->
    <ol>
      <li>Red</li>
      <li>Blue</li>
      <li>Green</li>
    </ol>
    <p>
      Outras cores que também são legais:
    </p>
    <!--Lista Normal-->
    <ul>
      <li>Purple</li>
      <li>Pink</li>
      <li>Black</li>
    </ul>
  </body>
</html>
```

### Table

Tabelas são definidas usando "table". Linhas são definidas utilizando "tr" (table rows) e colunas são definidas utilizando "td" (table data).

#### Atributos

- **border** (não suportado em html 5)
- **align**
- **bgcolor**: Cor de fundo da célula
  - Entretanto é recomendado utilizar CSS.
- **colspan**: Expandir a célula por mais de 1 coluna.
- **rowspan**: Expandir a célula por mais de 1 linha.

```html
<html>
  <head>
    <title>Table</title>
  </head>
  <body>
    <h1 align="center"><span>My Coding Schedule</span></h1>
    <hr />
    <br />
    <table border="2" align="center">
      <tr>
        <th>Day</th>
        <th>Mon</th>
        <th>Tue</th>
        <th>Wed</th>
        <th>Thu</th>
        <th>Fri</th>
      </tr>
      <tr>
        <td>08:00 - 08:30</td>
        <td class="selected">Learn</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td>09:00 - 10:00</td>
        <td></td>
        <td class="selected">Practice</td>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td>01:00 - 01:30</td>
        <td></td>
        <td></td>
        <td class="selected">Play</td>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td>03:45 - 05:00</td>
        <td></td>
        <td></td>
        <td></td>
        <td class="selected">Code</td>
        <td></td>
      </tr>
      <tr>
        <td>06:00 - 06:15</td>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td class="selected">Discuss</td>
      </tr>
    </table>
  </body>
</html>
```

## Advanced

### Inline and Block Elements

Em HTML os elementos são definidos como "**block-level**" ou "**inline**".

"**Block-level**" começam de uma nova linha (pode conter elementos inline).

"**Inline**" normalmente aparecem sem quebra de linha (não pode conter elemento block-level).

O elemento `<div>` é comumente usado como container para outros elementos HTML.

```html
<html>
  <body>
    <h1>Headline</h1>
    <!--Nesse caso foi utilizado em conjunto com CSS-->
    <div style="background-color:green; color:white; padding:20px;">
      <p>Some paragraph text goes here.</p>
      <p>Another paragraph goes here.</p>
    </div>
  </body>
</html>
```

### Forms

Usado para coletar informação dos usuários.

#### Atributos

- **action**: Aponta para a pagina que vai carregar depois do usuário submeter o "form" (normalmente o "form" é submetido à um site ou servidor).
- **method**: Especifica o método HTTP (**GET** or **POST**) que será usado quando o "form" for submetido.
  - Quando você usa **GET**, os dados estarão visíveis no endereço da página.
  - E o **POST** é usado quando o "form" contém informações sensíveis como senha.
- **input**: Especifica o tipo de dado.
- **name**: Especifica um nome para o "form".
- **type**: text, password, radio, checkbox, submit...

```html
<html>
  <head>
    <title>Forms</title>
  </head>
  <body>
    <form>
      <!--The <input> tag has no end tag-->
      <input type="text" name="username" /><br />
      <input type="password" name="password" />
      <input type="radio" name="gender" value="male" />Male<br />
      <input type="radio" name="gender" value="female" />Female<br />
      <input type="checkbox" name="gender" value="1" />Male<br />
      <input type="checkbox" name="gender" value="2" />Female<br />
      <!--submits a form to its action attribute-->
      <input type="submit" value="Submit" />
      <!--After the form is submitted, the data should be processed
			on the server using a programming language, such as PHP.-->
    </form>
  </body>
</html>
```

### Colors

![img](https://api.sololearn.com/DownloadFile?id=2468)

```html
<html>
  <head>
    <title>first page</title>
  </head>
  <body bgcolor="#000099">
    <h1>
      <font color="#FFFFFF">White headline</font>
    </h1>
  </body>
</html>
```

### Frames

> The \<frame> tag is not supported in HTML5.

---

## HTML5

### Introduction to HTML5

Ao escrever arquivos HTML5 deve-se adicionar "**\<!DOCTYPE HTML>** " no início.

Novos elementos em HTML5 incluem: `<article>, <aside>, <audio>, <canvas>, <datalist>, <details>, <embed>, <footer>, <header>, <nav>, <output>, <progress>, <section>, <video>`, e mais.

New in HTML5:

- The Web Forms 2.0 specification allows for creation of more powerful forms and more compelling user experiences.
- Date pickers, color pickers, and numeric stepper controls have been added.
- Input field types now include email, search, and URL.
- PUT and DELETE form methods are now supported.
- **Integrated API** (Application Programming Interfaces)
  - Drag and Drop
  - Audio and Video
  - Offline Web Applications
  - History
  - Local Storage
  - Geolocation
  - Web Messaging

### Content Models

In HTML, elements typically belonged in either the block level or inline content model. HTML5 introduces **seven** main content models.

- Metadata: Content that sets up the presentation or behavior of the rest of the content. These elements are found in the **head** of the document. _Elements:_ `\<base>, \<link>, \<meta>, \<noscript>, \<script>, \<style>, \<title>`
- Embedded: Content that imports other resources into the document. _Elements:_ `\<audio>, \<video>, \<canvas>, \<iframe>, \<img>, \<math>, \<object>, \<svg>`
- Interactive: Content specifically intended for user interaction. _Elements:_ \<a>, `\<audio>, \<video>, \<button>, \<details>, \<embed>, \<iframe>, \<img>, \<input>, \<label>, \<object>, \<select>, \<textarea>`
- Heading: Defines a section header. _Elements:_ `\<h1>, \<h2>, \<h3>, \<h4>, \<h5>, \<h6>, \<hgroup>`
- Phrasing: This model has a number of inline level elements in common with HTML4. _Elements:_ `\<img>, \<span>, \<strong>, \<label>, \<br />, \<small>, \<sub>`, and more.
- Flow content: Contains the majority of HTML5 elements that would be included in the normal flow of the document.
- Sectioning content: Defines the scope of headings, content, navigation, and footers. _Elements_: `\<article>, \<aside>, \<nav>, \<section>`

The various content models overlap in certain areas, depending on how they are being used.

![img](https://api.sololearn.com/DownloadFile?id=2546)

> The same element can belong to more than one content model.
>
> The HTML5 content models are designed to make the markup structure more meaningful for both the browser and the web designer.

### HTML5 Page Structure

![img](https://api.sololearn.com/DownloadFile?id=2471)

> You may not need some of these elements, depending on your page structure.

### Header, nav & footer

The `header` element is appropriate for use inside the body tag.

The `nav` tag represents a section of a page that links to other pages or to certain sections within the page. This would be a section with navigation links.

```html
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">About us</a></li>
  </ul>
</nav>
```

> Not all of the links in a document should be inside a \<nav> element. **The \<nav> element is intended only for major blocks of navigation links**. Typically, the \<footer> element often has a list of links that don't need to be in a \<nav> element.

The `footer` element is also widely used. Generally we refer to a section located at the very bottom of the web page as the footer.

> The following information is usually provided between these tags:
>
> - Contact Information
> - Privacy Policy
> - Social Media Icons
> - Terms of Service
> - Copyright Information
> - Sitemap and Related Documents

### Article, section & aside

The `article` is a self-contained, independent piece of content that can be used and distributed separately from the rest of the page or site. This could be a forum post, a magazine or newspaper article, a blog entry, a comment, an interactive widget or gadget, or any other independent piece of content.

```html
<article>
  <h1>The article title</h1>
  <p>Contents of the article element</p>
</article>
```

> When an \<article> element is nested, the inner element represents an article related to the outer element. For example, blog post comments can be \<article> elements nested in the \<article> representing the blog post.

The `section` is a logical container of the page or `article`. Sections can be used to divide up content within an article. For example, a homepage could have a section for introducing the company, another for news items, and still another for contact information.

Each `section` should be identified, typically by including a heading (`h1`-`h6` element) as a child of the element.

```html
<article>
  <h1>Welcome</h1>
  <section>
    <h1>Heading</h1>
    <p>content or image</p>
  </section>
</article>
```

> If it makes sense to separately syndicate the content of a \<section> element, use an \<article> element instead.

The `aside` is a secondary or tangential content which could be considered separate from but indirectly related to the main content. This type of content is **often represented in sidebars**. When an `aside` tag is used within an `article` tag, the content of the `aside` should be specifically related to that article.

```html
<article>
  <h1>Gifts for everyone</h1>
  <p>This website will be the best place for choosing gifts</p>
  <aside>
    <p>Gifts will be delivered to you within 24 hours</p>
  </aside>
</article>
```

> When an <aside> tag is used outside of an <article> tag, its content should be related to the surrounding content.

### Áudio

```html
<audio controls autoplay loop>
  <source src="audio.mp3" type="audio/mpeg" />
  <source src="audio.ogg" type="audio/ogg" />
  Audio element not supported by your browser.
</audio>
```

### Vídeo

```html
<video controls autoplay loop>
  <source src="video.mp4" type="video/mp4" />
  <source src="video.ogg" type="video/ogg" />
  Video is not supported by your browser
</video>
```

### Progress Bar

```html
Status: <progress min="0" max="100" value="35"></progress>
```

### Web Storage

```javascript
//Storing a Value:
localStorage.setItem("key1", "value1");

//Getting a Value:
alert(localStorage.getItem("key1")); //this will print the value

//Removing a Value:
localStorage.removeItem("key1");

//Removing All Values:
localStorage.clear();
```

> The same syntax applies to the session storage

### Geolocation API

Geolocation is much more accurate for devices with GPS, like smartphones and the like.

The Geolocation API’s main method is getCurrentPosition, which retrieves the current geographic location of the user's device.

```javascript
navigator.geolocation.getCurrentPosition();
```

Parameters:

- **showLocation (mandatory)**: Defines the callback method that retrieves location information.
- **ErrorHandler(optional)**: Defines the callback method that is invoked when an error occurs in processing the asynchronous call.
- **Options (optional)**: Defines a set of options for retrieving the location information.

User location can be presented in two ways: **Geodetic** and **Civic**.

1. The geodetic way to describe position refers directly to latitude and longitude.
2. The civic representation of location data is presented in a format that is more easily read and understood by the average person.

Each parameter has both a geodetic and a civic representation:

![img](https://api.sololearn.com/DownloadFile?id=2472)

> The getCurrentPosition() method returns an object if it is successful. The latitude, longitude, and accuracy properties are always returned.

### Drag&Drop API

The drag and drop feature lets you "grab" an object and drag it to a different location. To make an element draggable, just set the **draggable** attribute to true:

```html
<img draggable="true" />
```

> Any HTML element can be draggable.

The API for HTML5 drag and drop is event-based.

...

---

### SVG

**SVG** stands for **S**calable **V**ector **G**raphics, and is used to draw shapes with HTML-style markup.

It offers several methods for drawing paths, boxes, circles, text, and graphic images.

> SVG is not pixel-based, so it can be magnified infinitely with no loss of quality.

```html
<img src="image.svg" alt="" height="300" />
```

#### Drawing a Circle

```html
<svg width="2000" height="2000">
  <circle cx="80" cy="80" r="50" fill="green" />
</svg>
```

- **cx** pushes the center of the circle further to the right of the screen
- **cy** pushes the center of the circle further down from the top of the screen
- **r** defines the radius
- **fill** determines the color of our circle
- **stroke** adds an outline to the circle

#### Drawing a other shapes

`<rect>` defines a rectangle:

```html
<svg width="2000" height="2000">
  <rect width="300" height="100" x="20" y="20" fill="green" />
</svg>
```

\<line> defines a line segment:

```html
<svg width="400" height="410">
  <line
    x1="10"
    y1="10"
    x2="200"
    y2="100"
    style="stroke:#000000; stroke-linecap:round;
        stroke-width:20"
  />
</svg>
```

\<\***\*polyline\*\***> defines shapes built from multiple line definitions:

```html
<svg width="2000" height="500">
  <polyline
    style="stroke-linejoin:miter; stroke:black;
        stroke-width:12; fill: none;"
    points="100 100, 150 150, 200 100"
  />
</svg>
```

The `<ellipse>` is similar to the `<circle>`, with one exception:
You can independently change the horizontal and vertical axes of its radius, using the **rx** and **ry** attributes.

```html
<svg height="500" width="1000">
  <ellipse cx="200" cy="100" rx="150" ry="70" style="fill:green" />
</svg>
```

The `<polygon>` element is used to create a graphic with at least three sides. The polygon element is unique because it automatically closes off the shape for you.

```html
<svg width="2000" height="2000">
  <polygon
    points="100 100, 200 200, 300 0"
    style="fill: green; stroke:black;"
  />
</svg>
```

### Shape Animations

SVG animations can be created using the `<animate>` element.

The example below creates a rectangle that will change its position in 3 seconds and will then repeat the animation twice:

```html
<svg width="1000" height="250">
  <rect width="150" height="150" fill="orange">
    <animate
      attributeName="x"
      from="0"
      to="300"
      dur="3s"
      fill="freeze"
      repeatCount="2"
    />
  </rect>
</svg>
```

**attributeName**: Specifies which attribute will be affected by the animation
**from**: Specifies the starting value of the attribute
**to**: Specifies the ending value of the attribute
**dur**: Specifies how long the animation runs (duration)
**fill**: Specifies whether or not the attribute's value should return to its initial value when the animation is finished (Values: "remove" resets the value; "freeze" keeps the “to value”)
**repeatCount**: Specifies the repeat count of the animation

> To repeat the animation indefinitely, use the value "**indefinite**" for the repeatCount attribute.

The `<path>` element is used to define a path.

The following commands are available for path data:
**M**: moveto
**L**: lineto
**H**: horizontal lineto
**V:** vertical lineto
**C**: curveto
**S**: smooth curveto
**Q**: quadratic Bézier curve
**T**: smooth quadratic Bézier curveto
**A:** elliptical Arc
**Z**: closepath

Define a path using the **d** attribute:

```html
<svg width="500" height="500">
  <path d="M 0 0 L200 200 L200 0 Z" style="stroke:#000;  fill:none;" />
</svg>
```

> All of the above commands can also be expressed with lower case letters. When capital letters are used, it indicates absolute position; lower case indicates relative position.

### Canvas

The HTML canvas is used to draw graphics that include everything from simple lines to complex graphic objects.

The \<**canvas**> element is defined by:

```html
<canvas id="canvas1" width="200" height="100"> </canvas>
```

The \<**canvas**> element is only a container for graphics. You must use a script to actually draw the graphics (usually JavaScript).

The \<**canvas**> element must have an **id attribute** so it can be referred to by JavaScript:

```html
<html>
  <head></head>
  <body>
    <canvas id="canvas1" width="400" height="300"></canvas>

    <script>
      var can = document.getElementById("canvas1");
      var ctx = can.getContext("2d");
    </script>
  </body>
</html>
```

**getContext()** returns a drawing context on the canvas.

#### Coordinates

The HTML canvas is a two-dimensional grid.
The upper-left corner of the canvas has the coordinates (0,0).

X coordinate increases to the right.
Y coordinate increases toward the bottom of the canvas.

![img](https://api.sololearn.com/DownloadFile?id=2556)

> The <canvas> element is only a container for graphics.

#### Drawing Shapes

The **fillRect(x, y, w, h)** method draws a "filled" rectangle, in which w indicates width and h indicates height. The default fill color is black.

A black 100\*100 pixel rectangle is drawn on the canvas at the position (20, 20):

```javascript
let c = document.getElementById("canvas1");
let ctx = c.getContext("2d");
ctx.fillRect(20, 20, 100, 100);
```

The **fillStyle** property is used to set a color, gradient, or pattern to fill the drawing.Using this property allows you to draw a green-filled rectangle.

```javascript
var canvas = document.getElementById("canvas1");
var ctx = canvas.getContext("2d");
ctx.fillStyle = "rgba(0, 200, 0, 1)";
ctx.fillRect(36, 10, 22, 22);
```

The canvas supports various other methods for drawing:

**Draw a Line**
moveTo(x,y): Defines the starting point of the line.
lineTo(x,y): Defines the ending point of the line.

**Draw a Circle**
beginPath(): Starts the drawing.
arc(x,y,r,start,stop): Sets the parameters of the circle.
stroke(): Ends the drawing.

**Gradients**
createLinearGradient(x,y,x1,y1): Creates a linear gradient.
createRadialGradient(x,y,r,x1,y1,r1): Creates a radial/circular gradient.

**Drawing Text on the Canvas**
Font: Defines the font properties for the text.
fillText(text,x,y): Draws "filled" text on the canvas.
strokeText(text,x,y): Draws text on the canvas (no fill).

> There are many other methods aimed at helping to draw shapes and images on the canvas.

## Canvas vs. SBG

**Canvas**

\- Elements are drawn programmatically
\- Drawing is done with pixels
\- Animations are not built in
\- High performance for pixels-based drawing operations
\- Resolution dependent
\- No support for event handlers
\- You can save the resulting image as .png or .jpg
\- Well suited for graphic-intensive games

**SVG**
\- Elements are part of the page's DOM (Document object model)
\- Drawing is done with vectors
\- Effects, such as animations are built in
\- Based on standard XML syntax, which provides better accessibility
\- Resolution independent
\- Support for event handlers
\- Not suited for game applications
\- Best suited for applications with large rendering areas (for example, Google Maps)

> You can actually use both SVG and canvas on the same page, if needed. However, you cannot just draw SVG onto a canvas, or vice-versa.

## Canvas Transformations

...

## HTML5 FORMS

```html
<form>
  <label>Your name:</label>
  <input id="user" name="username" type="text" />
</form>
```

> Use the novalidate attribute to avoid form validation on submissions.

- placeholder
- autofocus

> The required attribute tells the browser that the input is required.

```html
<form autocomplete="off">
  <label for="e-mail">Your e-mail address: </label>
  <input name="Email" type="text" required />
  <input type="submit" value="Submit" />
</form>
```

**HTML5 added several new input types:**
\- color
\- date
\- datetime
\- datetime-local
\- email
\- month
\- number
\- range
\- search
\- tel
\- time
\- url
\- week

**New input attributes in HTML5:**
\- autofocus
\- form
\- formaction
\- formenctype
\- formmethod
\- formnovalidate
\- formtarget
\- height and width
\- list
\- min and max
\- multiple
\- pattern (regexp)
\- placeholder
\- required
\- step

> Input types that are not supported by old web browsers, will behave as input type text.

### Search Box

```html
<input id="mysearch" name="searchitem" type="search" />
```

> You must remember to set a name for your input; otherwise, nothing will be submitted.

The \<**datalist**> tag can be used to define a list of pre-defined options for the search field:

```html
<input id="car" type="text" list="colors" />
<datalist id="colors">
  <option value="Red"> </option>
  <option value="Green"> </option>
  <option value="Yellow"> </option>
</datalist>
```

\<**option**> defines the options in a drop-down list for the user to select.

> The ID of the datalist element must match with the list attribute of the input box.

Some other new input types include email, url and tel:

```html
<input id="email" name="email" type="email" placeholder="example@example.com" />
<br />
<input id="url" name="url" type="url" placeholder="example.com" />
<br />
<input id="tel" name="tel" type="tel" placeholder="555.555.1211" />
```

These are especially useful when opening a page on a modern mobile device, which recognizes the input types and opens a corresponding keyboard matching the field's type:

![img](https://api.sololearn.com/DownloadFile?id=2570)

> These new types make it easier to structure and validate HTML forms.
