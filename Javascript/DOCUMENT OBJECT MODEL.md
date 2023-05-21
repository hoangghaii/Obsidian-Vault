- **Inserting nodes, apply nodes**:
```javascript
// insertBefore
<div id="container"><span>Text...</span></div>

var spanNode = document.createElement('span');
var textNode = document.createTextNode('Another text 2');
spanNode.insertBefore(textNode, null);
 
var divNode = document.getElementById('container');
var firstChild = divNode.firstChild;
divNode.insertBefore(spanNode, firstChild);
 
// result:
// <div id="container"><span>Another text 2</span><span>Text...</span></div>

// appendChild
<div id="container"><span>Text...</span></div>

var spanNode = document.createElement('span');
var textNode = document.createTextNode('Another text');
spanNode.appendChild(textNode);
 
var divNode = document.getElementById('container');
divNode.appendChild(spanNode);
 
// result:
// <div id="container"><span>Text...</span><span>Another text</span></div>
```

- **Replacing Nodes**
```javascript
<h3>
	<div id="container">
		<span>Text 1</span>
		<span>Text 2</span>
	</div>
</h3>

var divNode = document.getElementById('container');
var lastChild = divNode.lastChild;
var textNode = document.createTextNode('Alternative text');
divNode.replaceChild(textNode, lastChild);
 
// Result:
// <div id="container"><span>Text 1</span>Alternative text</div>
```

- **Removing Nodes**
```javascript
<div id="container">
	<span>Text 1</span>
	Alternative text
</div>
	
var divNode = document.getElementById('container');
divNode.removeChild(divNode.firstChild);
 
// Result:
// <div id="container">Alternative text</div>
```

- **Attributes**
```javascript
<img src="image1.jpg" alt="image">
<a href="http://www.example.net" class="myLink">www.example.net</a>

var image = document.images[0];

// set element id to myImg
image.id = 'myImg';
// using setAttribute
image.setAttribute('id', 'myImg')

// replace image1.jpg to image2.jpg
image.src = 'image2.jpg';
 
var link = document.links[0]

// read URL of the link
var url = link.href;
// using getAttribute
var url = link.getAttribute('href');

// read CSS class of the link
var cssClass = link.className;
// using getAttribute
var url = link.getAttribute('class');


<input type="text" value="" disabled="disabled" id="myField">

// removeAttribute
document.getElementById('myField').removeAttribute('disabled');

// hasAttribute
document.getElementById('myField').hasAttribute('disabled');
// it returns false

// get with dataset
<div id="myDiv" data-category="training">Content...</div>

var category = document.getElementById('myDiv').dataset.category; 
// training

```