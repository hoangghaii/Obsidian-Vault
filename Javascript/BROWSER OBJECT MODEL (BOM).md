- **The window object**:

- *The global scope*
```javascript
var x = 10;
function displayX() {
    alert('The x is: ' + x);
}
 
alert(window.x); // 10
window.displayX(); // The x is: 10
 
//The result is the same for:
alert(x); // 10
displayX(); // The x is: 10
```

```javascript
var z = 30;
delete window.z;  // this returns false and do not delete the z property
console.log(window.z); // 30
 
window.t = 40;
delete window.t; // returns true
console.log(window.t); // undefined
```

- *Window size*
```javascript
// read-only
var pageHeight = window.innerHeight;
var windowHeight = window.outerHeight;

// can change
window.resizeTo(600, 400); // resize to 600 x 400
window.resizeBy(200, 100); // resize to 800 x 500
```

- *Window position*
```javascript
var left = window.screenX; 
var top = window.screenY;

window.moveTo(10, 20); // move the window to the position x = 10, y = 20
window.moveBy(50, 30); // move the window right by 50 pixels and down by 30 pixels
```

- **Dialog boxes**
```javascript
alert("welcome to the website");

var confirmed = confirm("Are you sure to delete this item?");
console.log(confirmed) // true / false

var favorite = prompt("Your favorite programming language:");
console.log(favorite) // trả về dữ liệu đã nhập nếu người dùng nhấp vào OK và null nếu không.
```