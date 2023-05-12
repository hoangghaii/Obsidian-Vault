- **Local Storage**
```javascript
// set item
localStorage.name = 'Name'
localStorage['name'] = 'Name'
localStorage.setItem('name', 'Name')

// get item
var name = localStorage.name
var name = localStorage['name']
var name = localStorage.getItem('name')

// delete item
localStorage.removeItem('name')

// delete all items
localStorage.clear()
```

- **Session Storage**
	The sessionStorage API is the same as the localStorage.

- **Cookies**
```javascript
// set item
document.cookie = 'company=Infomaster';
document.cookie = 'departament=Accounting';
document.cookie = 'team=Taxes';
document.cookie = 'system=' + encodeURIComponent('Business Intelligence');

// get item
var allCookies = document.cookie;
var chunks = allCookies.split('; ');
var cookies = [];
for (var i = 0; i < chunks.length; i++) {
    var chunk = chunks[i];
    var keyValue = chunk.split('=');
    var name = keyValue[0];
    var value = decodeURIComponent(keyValue[1]);
    cookies[name] = value; 
}
var system = cookies['system']; 
// returns 'Business Intelligence'
```