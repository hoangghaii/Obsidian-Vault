- **Inserting Nodes**:
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
