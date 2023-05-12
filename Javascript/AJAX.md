```javascript
// create http request
const httpRequest = new XMLHttpRequest();

// call open() method
httpRequest.open('GET', 'getProdusts');
// POST
// GET
// DELETE
// PUT

//set request header
httpRequest.setRequestHeader('Content-Type', {headerType});
// text/plain
// application/x-www-form-urlencoded
// multipart/form-data
// application/json

// send body

// application/x-www-form-urlencoded
httpRequest.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');

var body = 'name=ProXBook&category=notebook&price=1200';

httpRequest.send(body);

// text/plain
httpRequest.setRequestHeader(Content-Type', 'text/plain');
 
var body = 'A message for the server';
 
httpRequest.send(body);

// multipart/form-data
httpRequest.setRequestHeader(Content-Type', 'multipart/form-data');

var formData = new FormData();
formData.append('file1', file1);
formData.append('file2', file2);
formData.append('file1', name.value);

httpRequest.send(formData);

// application/json
httpRequest.setRequestHeader(Content-Type', 'application/json');

var xml = document.implementation.createDocument("", "data", null); 
// create <data> element
var data = xml.documentElement;
var category = xml.createElement('category'); 
// create <category> element
data.appendChild(category);
category.appendChild(xml.createTextNode('notebook')); 
// add 'notebook' as a content

// xml document: <data><category>notebook</category></data>	

httpRequest.send(xml);
```
