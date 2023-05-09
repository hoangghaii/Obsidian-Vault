
# Proxy:
- **The syntax to create a proxy**:
```javascript
var proxy = new Proxy(target, handler);
```

*Example*:
```javascript
var colorCode = {
    red: '#ff0000',
    blue: '#0000ff'
};
 
var colorHandler = {
    get: function(obj, prop) {
        var color = '#000000';
        if (prop in obj) {
            color = obj[prop];
        }
        return color;
    }
};
 
var colorProxy = new Proxy(colorCode, colorHandler);
 
colorProxy.green = '#008000';
 
console.log(colorProxy.red); // #ff0000
console.log(colorProxy.green); // #008000
console.log(colorProxy.navy); // #000000

```

# Reflection:
```javascript
var result = Reflect.apply(Math.pow, undefined, [3, 2]); // 9
 
var obj = {x: 1};
var test1 = Reflect.has(obj, 'x'); // true 
var test2 = Reflect.has(obj, 'y'); // false
 
var bucket = {}; 
Reflect.set(bucket, 'capacity', 10); 
console.log(bucket.capacity); // 10
 
function multiply(x, y) {
  this.product = x * y;
}
var args = [6, 7];
var calc = Reflect.construct(multiply, args);
console.log(calc.product); // 42
 
var person = {
  name: 'Jack',
  age: 38
};
Reflect.deleteProperty(person, 'age');
console.log(person.name, person.age); // Jack undefined
 
var container = {a: 1, b: 20};
console.log(Reflect.get(container, 'b')); // 20
```
