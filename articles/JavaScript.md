---
Autor: Vinícius Bohrer
Curso: Sololearn
---

# JavaScript

## Adding JavaScript to a Web Page

Let's start with adding JavaScript to a webpage.
JavaScript on the web lives inside the **HTML** document. 
In HTML, JavaScript code must be inserted between \<script> and \</script> tags, and can be placed in the HTML page's \<body> and \<head> sections. 

```html
<html>
	<head>
    	<title>JavaScript Overview</title>
    </head>
 	<body>
        <!--Writes "Hello World!" on the browser-->
 		<script>
            //We can use HTML tags to format text in JavaScript
 			document.write("<h1>Hello World!</h1>");
 		</script>
 	</body>
</html> 
```



> Remember that the script, which is placed in the head section, will be executed before the \<body> is rendered. If you want to get elements in the body, it's a good idea to place your script at the end of the body tag.

> The **document.write()** method should be used only for testing. Other output mechanisms appear in the upcoming lessons.

You can place any number of scripts in an HTML document.
Typically, the script tag is placed in the head of the HTML document.

> There is also a \<noscript> tag. Its content will be shown if the client's browser doesn't support JS scripts.

> It's a good idea to place scripts at the bottom of the <body> element.
> This can improve page load, because HTML display is not blocked by scripts loading.

The \<script> tag can take two attributes, **language** and **type**, which specify the script's type:

```html
<script language="javascript" type="text/javascript"> </script>
```

> The **language** attribute is deprecated, and should not be used.

In the example below, we created an alert box inside the script tag, using the **alert()** function:

```html
<html>
 	<head>
 		<title>Alert Box</title>
 		<script type="text/javascript">
 			alert("This is an alert box!");
 		</script>
 	</head>
 	<body>
 	</body>
</html>
```

![img](https://api.sololearn.com/DownloadFile?id=2737)

> The **type** attribute: \<script type="text/javascript"> is also no longer required, as JavaScript is the default HTML scripting language.

## External JavaScript

Scripts can also be placed in **external files**.

External scripts are useful and practical when the same code is used in a number of different web pages.

JavaScript files have the **file extension .js**.

To use an external script, put the name of the script file in the **src** (source) attribute of the \<script> tag.

On the .html file:

```html
<html>
 	<head>
 		<title>external javascript file</title>
 		<script src="demo.js"></script>
 	</head>
 	<body>
 	</body>
</html>
```

On the .js file:

```javascript
alert("This is an alert box!");
// This is a single line comment
/* This can be a multi line comment */
```

> The script will behave as if it were located exactly where the \<script> tag is located.

>Placing a JavaScript in an external file has the following advantages:
>
>- It separates HTML and code.
>- It makes HTML and JavaScript easier to read and maintain.
>- Cached JavaScript files can speed up page loads.
## Basic Concepts

###  Variables and Data types

![img](https://api.sololearn.com/DownloadFile?id=2741)

```javascript
//variables
var x = 10
```

```javascript
//data types
var price = 55.55;
var name = 'John';
//You can use single or double quotes
var text = "My name is John Smith";
var isActive = true;
//The Boolean value of 0 (zero), null, undefined, empty string is false. Everything with a "real" value is true.
var isHoliday = false;
```

![img](https://api.sololearn.com/DownloadFile?id=2746)

> You can use multiple assignment operators in one line, such as:
> x -= y += 9.

![img](https://api.sololearn.com/DownloadFile?id=2748)

```javascript
//Conditional (Ternary) Operator
//Syntax
variable= (condition) ? value1: value2
//Example
var isAdult = (age < 18) ? "Too young": "Old enough";
```

```javascript
var mystring1 = "I am learning ";
var mystring2 = "JavaScript with SoloLearn.";
document.write(mystring1 + mystring2);
```

> Numbers in quotes are treated as strings: "42" is not the number 42, it is a string that includes two characters, 4 and 2.

### Else-if

```javascript
var course = 1;
if (course == 1) {
 	document.write("<h1>HTML Tutorial</h1>");
} else if (course == 2) {
 	document.write("<h1>CSS Tutorial</h1>");
} else {
 	document.write("<h1>JavaScript Tutorial</h1>");
}
```

### Switch

```javascript
var day = 2;
switch (day) {
 	case 1:
 		document.write("Monday");
 		break;
 	case 2:
 		document.write("Tuesday");
 		break;
 	case 3:
 		document.write("Wednesday");
 		break;
 	default:
 		document.write("Another day");
}
```

### Loops

```javascript
for (i=1; i<=5; i++) {
 	document.write(i + "<br />");
}
//---------------------
var i=0;
while (i<=10) {
 	document.write(i + "<br />");
 	i++;
}
//---------------------
var i=20;
do {  
 	document.write(i + "<br />");
 	i++;  
}
while (i<=25); 
```

> **Break**: The break statement "jumps out" of a loop and continues executing the code after the loop.

> **Continue**: The continue statement breaks only one iteration in the loop, and continues with the next iteration.

### Functions

```javascript
function sayHello(name) {
 	alert("Hi, " + name);
}
sayHello("David");
sayHello("Sarah");
sayHello("John");
```

#### Alert Box

An alert box is used when you want to ensure that information gets through to the user. When an alert box pops up, the user must click OK to proceed. Takes a single parameter, which is the text displayed in the popup box.

```javascript
alert("Do you really want to leave this page?"); 
```

![img](https://api.sololearn.com/DownloadFile?id=2760)

> Be careful when using alert boxes, as the user can continue using the page only after clicking OK.

#### Prompt Box

A **prompt box** is often used to have the user input a value before entering a page.
When a prompt box pops up, the user will have to click either OK or Cancel to proceed after entering the input value.
If the user clicks OK, the box **returns the input value**. If the user clicks Cancel, the box returns **null**.

The **prompt()** method takes **two parameters**. 
- The first is the label, which you want to display in the text box.
- The second is a default string to display in the text box (optional).

```javascript
var user = prompt("Please enter your name");
alert(user);
```

![img](https://api.sololearn.com/DownloadFile?id=2762)

> When a prompt box pops up, the user will have to click either "OK" or "Cancel" to proceed after entering an input value. Do not overuse this method, because it prevents the user from accessing other parts of the page until the box is closed.

#### Confirm Box

A **confirm box** is often used to have the user verify or accept something.
When a confirm box pops up, the user must click either OK or Cancel to proceed.
If the user clicks OK, the box returns **true**. If the user clicks Cancel, the box returns **false**.

```javascript
var result = confirm("Do you really want to leave this page?");
if (result == true) {
 	alert("Thanks for visiting");
}
else {
 	alert("Thanks for staying with us");
}
```

![img](https://api.sololearn.com/DownloadFile?id=2991)

The result when the user clicks **OK**:

![img](https://api.sololearn.com/DownloadFile?id=2763)

The result when the user clicks **Cancel**:

![img](https://api.sololearn.com/DownloadFile?id=2764)

> Do not overuse this method, because it also prevents the user from accessing other parts of the page until the box is closed.

## Objects

JavaScript variables are containers for data values. **Objects** are variables too, but they can contain many values.

```javascript
var person = { //These values are called properties
 	name: "John",
    age: 31, 
 	favColor: "green",
    height: 183
}; //Creating a object like that doesn't allows you to create multiple instances, it needs a constructor.
```

> JavaScript objects are containers for **named values**.

This example demonstrates how to access the age of our person object:

```javascript
var person = {name: "John", age: 31, favColor: "green", height: 183};
var x = person.age;
var y = person['age'];
```

```javascript
var course = {name: "JS", lessons: 41};
document.write(course.name.length);
//Outputs 2
```

> Objects are one of the core concepts in JavaScript.

### Constructor

Sometimes, we need to set an "**object type**" that can be used to create a number of objects of a single type.
The standard way to create an "object type" is to use an object **constructor function**.

```javascript
function person(name, age, color) {
  this.name = name;
  this.age = age;
  this.favColor = color;
}
```

The above function (person) is an object constructor, which takes parameters and assigns them to the object properties.

Once you have an object constructor, you can use the **new** keyword to create new objects of the same type.

```javascript
var p1 = new person("John", 42, "green");
var p2 = new person("Amy", 21, "red");

document.write(p1.age); // Outputs 42
document.write(p2.name); // Outputs "Amy"
```

> Don't forget about the second accessing syntax: p1['age'].

### Methods

```javascript
function person(name, age) {
 	this.name = name;  
 	this.age = age;
 	this.changeName = function (name) {
 		this.name = name;
 	}
}

var p = new person("David", 21);
p.changeName("John");
//Now p.name equals to "John"
```

You can also define the function outside of the constructor function and associate it with the object:

```javascript
function person(name, age) {//constructor
 	this.name= name;  
 	this.age = age;
 	this.yearOfBirth = bornYear;
}
function bornYear() {//method
 	return 2016 - this.age;
}
```

As you can see, we have assigned the object's **yearOfBirth** property to the **bornYear** function.
The **this** keyword is used to access the *age* property of the object, which is going to call the method.

> Note that it's not necessary to write the function's parentheses when assigning it to an object.

## Core Objects

### The Array Object

```javascript
var courses = new Array("HTML", "CSS", "JS"); 
var course = courses[0]; // HTML
courses[1] = "C++"; //Changes the second element
document.write(courses[10]); //Outputs "undefined"
```

> This syntax declares an array named **courses**, which stores three values, or elements.

```javascript
var courses = new Array(3);
courses[0] = "HTML";
courses[1] = "CSS";
courses[2] = "JS";
```

>An array is a special type of **object**.
>An array uses **numbers** to access its elements, and an object uses **names** to access its members.

```javascript
var courses = new Array();
courses[0] = "HTML";
courses[1] = "CSS";
courses[2] = "JS";
courses[3] = "C++";
```

> You can add as many elements as you need to.

For greater simplicity, readability, and execution speed, you can also declare arrays using the **array literal** syntax.

```javascript
var courses = ["HTML", "CSS", "JS"];
document.write(courses.length);
//Outputs 3
```

>You can access and modify the elements of the array using the index number, as you did before.
>This last syntax (array literal) is the recommended way to declare arrays.

```javascript
var c1 = ["HTML", "CSS"];
var c2 = ["JS", "C++"];
var courses = c1.concat(c2);
```

> The **concat** operation does not affect the *c1* and *c2* arrays - it returns the resulting concatenation as a new array.

While many programming languages support arrays with named indexes (text instead of numbers), called **associative arrays** JavaScript does not. However, you still can use the named array syntax, which will produce an object. For example:

```javascript
var person = []; //empty array
person["name"] = "John";
person["age"] = 46;
document.write(person["age"]);
//Outputs "46"
```

> As the person array is treated as an object, the standard array methods and properties will produce incorrect results. For example, **person.length** will return 0.

> If you use a named index, JavaScript will redefine the array to a standard object.

### The Math Object

The Math object allows you to perform mathematical tasks, and includes several properties.

![img](https://api.sololearn.com/DownloadFile?id=2767)

```javascript
document.write(Math.PI);
//Outputs 3.141592653589793
```

> Math has no constructor. There's no need to create a Math object first.

The Math object contains a number of methods that are used for calculations:

![img](https://api.sololearn.com/DownloadFile?id=2769)

```javascript
var number = Math.sqrt(4); 
document.write(number);
//Outputs 2
```

> To get a random number between 1-10, use Math.random(), which gives you a number between 0-1. Then multiply the number by 10, and then take Math.ceil() from it:
>
> Math.ceil(Math.random() * 10).

```javascript
var n = prompt("Enter a number", "");
var answer = Math.sqrt(n);
alert("The square root of " + n + " is " + answer);
```

> Math is a handy object. You can save a lot of time using Math, instead of writing your own functions every time.

### The Date Object

The **setInterval()** method calls a function or evaluates an expression at specified intervals (in milliseconds).
It will continue calling the function until **clearInterval()** is called or the window is closed.

```javascript
function myAlert() {
   alert("Hi");
}
setInterval(myAlert, 3000);
```

> This will call the myAlert function every 3 seconds (1000 ms = 1 second).

A date consists of a year, a month, a day, an hour, a minute, a second, and milliseconds.

Using **new Date()**, create a new date object with the **current date and time**.

```javascript
var d = new Date();
//d stores the current date and time
```

The other ways to initialize dates allow for the creation of new date objects from the **specified date and time**.

```javascript
new Date(milliseconds)
new Date(dateString)
new Date(year, month, day, hours, minutes, seconds, milliseconds)

//Fri Jan 02 1970 00:00:00
var d1 = new Date(86400000); 

//Fri Jan 02 2015 10:42:00
var d2 = new Date("January 2, 2015 10:42:00");

//Sat Jun 11 1988 11:42:00
var d3 = new Date(88,5,11,11,42,0,0);
```

> JavaScript dates are calculated in milliseconds from 01 January, 1970 00:00:00 Universal Time (UTC). One day contains 86,400,000 millisecond.

>JavaScript counts months from 0 to 11. January is 0, and December is 11.
>Date objects are static, rather than dynamic. The computer time is ticking, but date objects don't change, once created.

When a Date object is created, a number of **methods** make it possible to perform operations on it.

![img](https://api.sololearn.com/DownloadFile?id=2772)

```javascript
var d = new Date();
var hours = d.getHours();
//hours is equal to the current hour
```

```javascript
//program that prints the current time to the browser once every second.
function printTime() {
  var d = new Date();
  var hours = d.getHours();
  var mins = d.getMinutes();
  var secs = d.getSeconds();
  document.body.innerHTML = hours+":"+mins+":"+secs;
}
setInterval(printTime, 1000);
```

>The **innerHTML** property sets or returns the HTML content of an element. In our case, we are changing the HTML content of our document's body. This overwrites the content every second, instead of printing it repeatedly to the screen.

## DOM & Events

### The DOM

When you open any webpage in a browser, the HTML of the page is loaded and rendered visually on the screen.
To accomplish that, the browser builds the **Document Object Model** of that page, which is an object oriented model of its logical structure.
The DOM of an HTML document can be represented as a nested set of boxes:

![img](https://api.sololearn.com/DownloadFile?id=2773)

> JavaScript can be used to manipulate the DOM of a page dynamically to add, delete and modify elements.

**For example:** `document.body.innerHTML = "Some text";`

As **body** is an element of the DOM, we can access it using the **document** object and change the content of the **innerHTML** property.

> The **innerHTML** property can be used on almost all HTML elements to change its content.

## Selecting Elements

All HTML elements are **objects**. And as we know every object has **properties** and **methods**.
The **document** object has methods that allow you to select the desired HTML element.
These three methods are the most commonly used for selecting HTML elements:

```javascript
//finds element by id
document.getElementById(id) 

//finds elements by class name
document.getElementsByClassName(name) 

//finds elements by tag name
document.getElementsByTagName(name)
```

In the example below, the **getElementById** method is used to select the element with **id="demo"**and change its content:

```javascript
var elem = document.getElementById("demo");
elem.innerHTML = "Hello World!";
```

> The example above assumes that the HTML contains an element with id="demo", for example \<div id="demo">\</div>.

For example, if our HTML page contained three elements with class="demo", the following code would return all those elements as an array:

```javascript
var arr =  document.getElementsByClassName("demo");
//accessing the second element
arr[1].innerHTML = "Hi";
```

Similarly, the **getElementsByTagName** method returns all of the elements of the specified tag name as an array.
The following example gets all paragraph elements of the page and changes their content:

```html
<p>hi</p>
<p>hello</p>
<p>hi</p>
<script>
var arr = document.getElementsByTagName("p");
for (var x = 0; x < arr.length; x++) {
  arr[x].innerHTML = "Hi there";
}
</script>
```

The script will result in the following HTML:

```html
<p>Hi there</p>
<p>Hi there</p>
<p>Hi there</p>
```

### Working with DOM

Each element in the DOM has a set of properties and methods that provide information about their relationships in the DOM:
element.**childNodes** returns an array of an element's child nodes.
element.**firstChild** returns the first child node of an element.
element.**lastChild** returns the last child node of an element.
element.**hasChildNodes** returns true if an element has any child nodes, otherwise false.
element.**nextSibling** returns the next node at the same tree level.
element.**previousSibling** returns the previous node at the same tree level.
element.**parentNode** returns the parent node of an element.

We can, for example, select all child nodes of an element and change their content:

```html
<html>
  <body>
    <div id ="demo">
      <p>some text</p>
      <p>some other text</p>
    </div>

    <script>
     var a = document.getElementById("demo");
     var arr = a.childNodes;
     for(var x=0;x<arr.length;x++) {
       arr[x].innerHTML = "new text";
     }
    </script>

  </body>
</html>
```

> The code above changes the text of both paragraphs to "new text".

## Changing Elements

Once you have selected the element(s) you want to work with, you can change their attributes. 
As we have seen in the previous lessons, we can change the text content of an element using the **innerHTML** property.
Similarly, we can change the attributes of elements.
For example, we can change the **src** attribute of an image:

```html
<img id="myimg" src="orange.png" alt="" />
<script>
var el = document.getElementById("myimg");
el.src = "apple.png";
</script>
```

We can change the **href** attribute of a link:

```html
<a href="http://www.example.com">Some link</a>
<script>
var el = document.getElementsByTagName("a");
el[0].href = "http://www.sololearn.com";
</script>
```

> Practically all attributes of an element can be changed using JavaScript.

### Changing Style

The style of HTML elements can also be changed using JavaScript.
All style attributes can be accessed using the **style** object of the element. 

For example:

```html
<div id="demo" style="width:200px">some text</div>
<script>
  var x = document.getElementById("demo");
  x.style.color = "6600FF";
  x.style.width = "100px";
</script>
```

The code above changes the text **color** and **width** of the div element.

>All CSS properties can be set and modified using JavaScript. Just remember, that you cannot use dashes (-) in the property names: these are replaced with camelCase versions, where the compound words begin with a capital letter. 
>For example: the **background-color** property should be referred to as **backgroundColor**.

## Adding & Removing Elements

Use the following methods to create new nodes:
element.**cloneNode**() clones an element and returns the resulting node.
document.**createElement**(element) creates a new element node. 
document.**createTextNode**(text) creates a new text node.

For example:

```javascript
var node = document.createTextNode("Some new text");
```

This will create a new text node, but it will not appear in the document until you append it to an existing element with one of the following methods:
element.**appendChild(newNode)** adds a new child node to an element as the last child node.
element.**insertBefore(node1, node2)** inserts node1 as a child before node2

Example:

```html
<div id ="demo">some content</div>

<script>
  //creating a new paragraph
  var p = document.createElement("p");
  var node = document.createTextNode("Some new text");
  //adding the text to the paragraph
  p.appendChild(node);

  var div = document.getElementById("demo");
  //adding the paragraph to the div
  div.appendChild(p);
</script>
```

> This creates a new paragraph and adds it to the existing div element on the page.

To remove an HTML element, you must select the parent of the element and use the **removeChild**(node) method.
For example:

```html
<div id="demo">
  <p id="p1">This is a paragraph.</p>
  <p id="p2">This is another paragraph.</p>
</div>

<script>
var parent = document.getElementById("demo");
var child = document.getElementById("p1");
parent.removeChild(child);
</script>
```

This removes the paragraph with id="p1" from the page.

> An alternative way of achieving the same result would be the use of the **parentNode** property to get the parent of the element we want to remove:
> var child = document.getElementById("p1");
> child.**parentNode**.removeChild(child);

To replace an HTML element, the element.**replaceChild**(newNode, oldNode)  is used. For example:

```html
<div id="demo">
  <p id="p1">This is a paragraph.</p>
  <p id="p2">This is another paragraph.</p>
</div>

<script>
var p = document.createElement("p");
var node = document.createTextNode("This is new");
p.appendChild(node);

var parent = document.getElementById("demo");
var child = document.getElementById("p1");
parent.replaceChild(p, child);
</script>
```

## Asynchronous programming: Promises

A **Promise** is a better way for asynchronous programming when compared to the common way of using a **setTimeout**() type of method.

```javascript
setTimeout(function() {
 	console.log("Work 1");
	setTimeout(function() {
 		console.log("Work 2");
 	}, 1000);
}, 1000);
console.log("End");
```

It prints "End", "Work 1" and "Work 2" in that order (the work is done asynchronously). But if there are more events like this, the code becomes very complex.

A **promise** can be created as follows:

```javascript
new Promise(function(resolve, reject) {
 	// Work
 	if (success)
        resolve(result);
    else
        reject(Error("failure"));
});
```

Here, **resolve** is the method for success and **reject** is the method for failure.

For Example:

```javascript
function asyncFunc(work) {
 	return new Promise(function(resolve, reject) {
 		if (work === "")
 			reject(Error("Nothing"));
 		setTimeout(function() {
 			resolve(work);
 		}, 1000);
 	});
}

asyncFunc("Work 1") // Task 1
.then(function(result) {
 	console.log(result);
 	return asyncFunc("Work 2"); // Task 2
}, function(error) {
 	console.log(error);
})
.then(function(result) {
 	console.log(result);
}, function(error) {
 	console.log(error);
});
console.log("End");
```

## Iterator & Generators

```javascript
function* idMaker() {
 	let index = 0;
 	while (index < 5)
 		yield index++;
}
var gen = idMaker();

console.log(gen.next().value);
console.log(gen.next().value);
console.log(gen.next().value);
console.log(gen.next().value);
console.log(gen.next().value);
console.log(gen.next().value); //n aparece
console.log(gen.next().value); //n aparece
```

We can exit and re-enter generator functions later. Their variable bindings (context) will be saved across re-entrances. They are a very powerful tool for asynchronous programming, especially when combined with Promises. They can also be useful for creating loops with special requirements.

We can nest **generator functions** inside each other to create more complex structures and pass them arguments while we are calling them.
The example below will show a useful case of how we can use **generator functions** and **Symbol.iterators** together. 

**Example:**

```javascript
const arr = ['0', '1', '4', 'a', '9', 'c', '16'];
const my_obj = {
  [Symbol.iterator]: function*() {
    for(let index of arr) {
      yield `${index}`;
    }
  }
};
const all = [...my_obj]
  .map(i => parseInt(i, 10))
  .map(Math.sqrt)
  .filter((i) => i < 5)
  .reduce((i, d) => i + d);
console.log(all);
```

We create an object of 7 elements by using **Symbol.iterator** and **generator functions**. In the second part, we assign our object to a constant **all**. At the end, we print its value.

## Extras

### Clipboard access

```javascript
navigator.clipboard.readText().then(
  clipText => document.querySelector(".editor").innerText += clipText);
```

This snippet fetches the text from the clipboard and appends it to the first element found with the class `"editor"`. Since [`readText()`](https://developer.mozilla.org/en-US/docs/Web/API/Clipboard/readText) (and [`read()`](https://developer.mozilla.org/en-US/docs/Web/API/Clipboard/read), for that matter) returns an empty string if the clipboard isn't text, this code is safe.

### Arrow Functions

A principal diferença entre uma função comum e uma *arrow function* é o *this*. quando você cria uma função dentro de uma função o *this* é substituido (naquele escopo), já a *arrow function* não cria nenhum novo *this*.

Outra diferença é que, quando a função é simples, não precisa nem de *return*.

```javascript
var elements = [
  'Hydrogen',
  'Helium',
  'Lithium',
  'Beryllium'
];

elements.map(function(element) { 
  return element.length; 
}); // esta sentença retorna o array: [8, 6, 7, 9]

// A função regular acima pode ser escrita como a arrow function abaixo
elements.map((element) => {
  return element.length;
}); // [8, 6, 7, 9]

// Quando só existe um parâmetro, podemos remover os parênteses envolvendo os parâmetros:
elements.map(element => {
  return element.length;
}); // [8, 6, 7, 9]

// Quando a única sentença em uma arrow function é `return`, podemos remover `return` e remover as chaves envolvendo a sentença
elements.map(element => element.length); // [8, 6, 7, 9]
```

### Destructuring

Pega as propriedades de um objeto ou itens de um array e transforma em variáveis/constantes.

```javascript
function handleMouseMove(event) {
	const clientX = event.clientX;
	const clientY = envent.clientY;
    console.log(clientX, clientY);
}
// Destructuring
function handleMouseMove(event) {
    const {clientX, clientY} = event;
    console.log(clientX, clientY);
}
//ou
function handleMouseMove({clientX, clientY}) {
    console.log(clientX, clientY);
}
```

```javascript
const frutas = ["banana", "uva"];
const fruta1 = frutas[0]; // fruta1 = "banana"
// Destructuring
const [fruta1, fruta2] = frutas // fruta1 = "banana" e fruta2 = "uva"
```

### Rest & Spread

```javascript
//Rest
function showList (empresa, ...funcionarios) {
    console.log(empresa)
    console.log(funcionarios)
}
showList("Transirius", "Edmilson", "Elio", "Motorista")
//empresa = "Transirius" funcionarios = ["Edmilson", "Elio", "Motorista"]
```

```javascript
//Spread
const numeros = [1,2,3,4,5,6,7,8,9,0,54]
console.log(Math.max(...numeros))
```

### Modules

Os módulos servem para quebrar o código em diferentes arquivos, para facilitar a organização e compartilhamento de código comum.

```html
<script type="module" src="./script.js"></script>
```

No arquivo que cria as funções:

```javascript
export function areaQuadrado(l) {
    return l+l;
}
export function perimetroQuadrado(l) {
    return 4 * l;
}
```

No arquivo que usa as funções:

```javascript
import {areaQuadrado, perimetroQuadrado} from "./scripts.js";
console.log(areaQuadrado(4)); //16
```

Outro exemplo:

```javascript
// lib/math.js
export let sum = (x, y) => { return x + y; }
export let pi = 3.14;
```

```javascript
// app.js
import * as math from "lib/math"
console.log(`2p = + ${math.sum(math.pi, math.pi)}`)
```

### Fetch

Envia requisições assíncronas para o servidor. Seve para acessarmos/escrevermos dados em APIs externas.

```javascript
// faz uma requisição (GET) pra uma API de pokemons
const requisicao = fetch("https://www.canalti.com.br/api/pokemons.json");
// a const requisicao é uma promise. Logo, se eu printar na sequência não vai ter a informação ainda
console.log(requisicao); // ainda não vai ter recebido os dados da api
// por isso devemos usar o "then"
```

GET:

```javascript
fetch("https://www.canalti.com.br/api/pokemons.json") // Tem que esperar o retorno da API
	.then(response => response.json()) 			// Não é transformado em json na hora, é assíncrono
	.then(jsonBody => console.log(jsonBody)) 	// por isso tem que por outro "then"
```

POST:

```javascript
const data = {...pokemonData}

const requisicao = fetch("https://www.canalti.com.br/api/addpokemon", {
    method: "POST",
    headers: {
        "Content-Type": "application/json"
    },
    body: JSON.stringufy(data);
})
```



### Consumindo uma API com A.J.A.X. (Asynchronous JavaScript XML)

Referências:

- [Requisições Ajax com JavaScript](https://www.youtube.com/watch?v=il0Dog9Y4xs)

```javascript

```

### Async/Await

Fetch retorna uma **promise**. É possível criarmos ***funções assíncronas***, que irão esperar a **promise** resolver, antes de continuar com o código.

```javascript
async function fetchPokemons(url) {
    const response = await fetch(url);
    const json = await response.json();
    return json;
}

const x = fetchPokemons("https://www.canalti.com.br/api/pokemon.json");

x.then(response => {		// simplesmente console.log retornaria uma promise
    console.log(response);
})
```

### Arrays (Map, Filter, Reduce)

Métodos para iterarmos entre os valores de arrays.

```javascript
const precos = [
    "Crédito",
    "R$ 200",
    "R$ 400",
    "Contas Pagar",
    "R$ 300",
    "Meus dados"
];

// Retorna um array novo -> que contém os itens que o retorno da função é TRUE
const precosFiltro = precos.filter(preco => preco.includes("R$"));
// retorna ["R$ 200","R$ 400","R$ 300"]

// Retorna um array novo -> somente com os números
// se uma string parece um numero (ex "300") adiciona "+" na frente pra virar um número
// ou "Number()"
const precosNumeros = precosFiltro.map(preco => Number(preco.replace("R$ ", "")));
// Retorna [200, 400, 300]

// Retorna um valor único
// acc serve como o acumulador e é o valor que vai ser retornado no fim
const total = precosNumeros.reduce((acc, item) => (acc + item));
// Retorna 900
```

### Expressões

```javascript
const grupoAVenceu = grupoA > 50 && "Grupo A Venceu";
// se "grupoA" fez mais de 50 pontos ele vai pra proxima expressão do AND (&&)
// e aquela string retorna seu valor pra constante "grupoAVenceu"
// se for menor do que 50 grupoAVenceu é igual a FALSE
```

### Classes

```javascript
class SmoothScroll {
  constructor(links) {
    this.linkElements = document.querySelectorAll(links);

    this.addClickEvent();
  }
  handleClick(event) {
    event.preventDefault();
    const href = event.currentTarget.getAttribute("href");
    const section = document.querySelector(href);
    window.scrollTo({
      top: section.offsetTop - (window.innerHeight - section.clientHeight) / 2,
      behavior: "smooth"
    });
  }
  addClickEvent() {
    this.linkElements.forEach(link => {
      link.addEventListener("click", this.handleClick);
    });
  }
}

class ActiveSmoothScroll extends SmoothScroll {
  constructor(links, sections) {
    super(links);

    this.sectionElements = document.querySelectorAll(sections);
    this.handleScroll = this.handleScroll.bind(this);
    this.handleScroll();
    this.activeNavScroll();
  }
  handleScroll() {
    this.sectionElements.forEach((section, i) => {
      if (window.pageYOffset > section.offsetTop - window.innerHeight * 0.5) {
        this.linkElements[i].classList.add("active");
      } else {
        this.linkElements[i].classList.remove("active");
      }
    });
  }
  activeNavScroll() {
    window.addEventListener("scroll", this.handleScroll);
  }
}

const scroll = new ActiveSmoothScroll("a[href^='#']", "section");
```

