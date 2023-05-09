
- **`slice`** & **`substring`** & **`substr`**
| slice(start, end)         | subtring(start,end)     | substr(start,length) |
	|--------------|-----------|------------|
	| đối số đầu tiên là vị trí bắt đầu | đối số đầu tiên là vị trí bắt đầu      | đối số đầu tiên là vị trí bắt đầu        |
	| đối số thứ hai là vị trí vị trí kết thúc      | đối số thứ hai là vị trí vị trí kết thúc  | đối số thứ hai là độ dài của chuỗi con
	| chuỗi trả về là từ ký tự từ vị trí bắt đầu đến ký tự ngay trước vị trí kết thúc      | chuỗi trả về là từ ký tự từ vị trí bắt đầu đến ký tự ngay trước vị trí kết thúc  | chuỗi trả về là từ ký tự từ vị trí bắt đầu đến ký tự tại vị trí kết thúc
	| có thể nhận đối số âm      | không thể nhận đối số âm  | không thể nhận đối số âm

**Ex**: 
```javascript
var s = 'abcdefghi';
/**
	a -> 0,
	b -> 1,
	c -> 2,
	d -> 3,
	e -> 4,
	f -> 5,
	g -> 6,
	h -> 7,
	i -> 8
*/
    
// slice
var s2 = s.slice(2, 4); // cd
var s3 = s.slice(2); // cdefghi
var s4 = s.slice(-2); // hi
var s5 = s.slice(2, -4); // cde

// substring
var s2 = s.substring(2, 4); // cd
var s3 = s.substring(-2); // abcdefghi
var s4 = s.substring(2, -4); // ab

// substr
var s1 = s.substr(2, 4); // cdef
var s2 = s.substr(2); // cdefghi
```

-  **`for .. in`**:
	- Cho `object`
Ex: 
```javascript
var obj = {x: 5, y: 'abc', z: true};
for (var prop in obj) {
    console.log(prop + " = " + obj[prop]);
}
```

- **`for .. of`**:
	- Cho `arrays`, `maps`, `sets` and others
Ex: 
```javascript
var elements = ['a', 'b', 5, 6];
for (var element of elements) {
console.log(element);
}
//Output:
//a
//b
//5
//6
```

- **`The arguments object`**: 
	- Đối tượng đối số cho phép bạn đọc tất cả các đối số đã truyền trong lệnh gọi hàm. Điều này hữu ích khi số lượng đối số truyền vào khác với số lượng tham số hàm đã xác định, đặc biệt khi nó lớn hơn. Đối tượng đối số giống như một mảng và chứa một danh sách số các đối số theo thứ tự mà chúng được truyền vào.
Ex: 
```javascript
function add(x, y) {
    var result = 0;
    if (arguments.length == 2) {
        result = x + y;
    } else {
        for (let i = 0; i < arguments.length; i++) {
            result = result + arguments[i];
        }
    }
    return result;
}
 
var result = add(3, 5); // 8
var result2 = add(3, 5, 6); //14
```

- **`call()`** & **`apply()`**
	- *Giống*: 
		- Đều là các phương thức của hàm cho phép bạn gọi các phương thức trong các ngữ cảnh khác nhau như thể chúng là các phương thức của các đối tượng khác nhau.
		- Nhận haihay nhiều đối số, đối số đầu tiên trỏ thành giá trị của this, các đối số tiếp theo được chuyển đến các chức năng
	- *Khác*:
| call()         | apply()      |
	|-----------|------------|
	| đối số thứ hai được truyền dạng phần tử|đối số thứ hai được truyền dạng mảng |
	| function.call(thisValue , arg1, arg2, …) | function.call(thisValue [, arg1, arg2, …])
Ex: 
```javascript
var product = {
    unitPrice: 5,
    total: function(quantity) {
        return this.unitPrice * quantity;
    }
};
 
var totalProductPrice = product.total(3); // 15

// Call()
var totalProductPrice2 = product.total.call(product, 3); // 15

var myProduct = {
    unitPrice: 6
};
var totalMyProductPrice = product.total.call(myProduct, 3); // 18

// Apply()
var totalMyProductPrice2 = product.total.apply(myProduct, [3]); // 18
```

- **`map`** & **`set`**:
|          | map()       | set() |
	|-----------|------------|------------|
	|syntax to create| const map = new Map()|const set = new Set() | 
	|propeties and methods| - size <br/> - set(key, value) <br/> - get(key) <br/> - has(value) <br/> - delete(value) <br/> - clear() <br/> - keys() <br/> - values() <br/> - entries() <br/> - foreach | - size <br/> - add(value) <br/> - has(value) <br/> - delete(value) <br/> - clear() <br/> - values() <br/> - entries() <br/> - foreach  |
Ex: 
```javascript
// map
var map = new Map();
map.set('Mon', 'Monday');
map.set('Tue', 'Tuesday');
map.set('Wed', 'Wednesday');
 
console.log(map.size); // 3
 
for (var [key, value] of map) {
    console.log(key + ' => ' + value);
}
// output:
// Mon => Monday
// Tue => Tuesday
// Wed => Wednesday
 
var obj = { x: 1 };
var obj2 = { x: 2 };
 
map.set(obj, obj2);
map.set(0, obj2);
 
console.log(map.has(obj)); // true
console.log(map.get(obj)); // { x: 2 }
console.log(map.get(0)); // { x: 2 }
console.log(map.get(1)); // undefined
 
map.delete(obj);
console.log(map.has(obj)); // false
 
map.forEach(function(value, key) {
  console.log(key + ' => ' + value);
});
// Output:
// Mon => Monday
// Tue => Tuesday
// Wed => Wednesday
// 0 => [object Object]
 
map.clear();
console.log(map.size); // 0

// set
var set = new Set();
set.add('triangle');
set.add('triangle');
set.add('square');
 
console.log(set.size); // 2
set.forEach(function(value) {
  console.log(value);
});
// Output:
// triangle
// square
 
var array = [1, 2];
set.add(array);
 
console.log(set.has(array)); // true
set.delete(array); 
console.log(set.has(array)); // false
 
set.add(3);
set.add({a: 3});
 
var values = set.values();
for (var value of values) {
    console.log(value);
}
// Output:
// triangle
// square
// 3
// { a: 3 }
```

- **`JSON`**: *JavaScript Object Notation* 
- **The `function*` declaration**:
```javascript
function* daysGenerator(){
	var daysList = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday'];
	for (var i = 0; i < daysList.length; i++) {
        yield daysList[i];
    }
}

var daysGen = daysGenerator();
console.log(daysGen.next()); // { value: "Monday", done: false }
```

- **`promise`**
```javascript
var promise = new Promise(function(resolve, reject) {
  // do a work, most likely asynchronous
 
  if (/* successful operation */) {
    resolve('success');
  }
  else {
    reject('failure');
  }
});

promise.then(function(value) {
    // here you define what to do if the promise is fulfilled
}).catch(function(error) {
    // here you define what to do if the promise is rejected
}).finally(function(error) {
    // here you define what to do when the promise is settled
});
```
- **`Object`**:
	- *Create object*:
	```javascript
const obj = {}
		
const obj2 = new Object() // creates an empty object, equivalent of {}
		
const obj3 = Object.create(Object.prototype) // creates an empty object, equivalent of {}
	```
	- *Checking properties*:
	```javascript
var building = {room : {name : 'living room'}};

if (building.room !== undefined)

if ('room' in building) 

if (building.hasOwnProperty('room')) 
	```
	- Delete properties:
	```javascript
var data = {name : 'Max Doe', age : 33, salary : 3000};
delete data.age;
delete data['salary'];
	```
	- Getter and Setter:
```javascript
var publication = {
    text : 'some interesting text here',
    readingCounter : 0,
    changesCounter : 0,
    get content() {
        this.readingCounter++;
        return this.text;
    },
    set content(text) {
        this.text = text;
        this.changesCounter++;
    }
};
 
console.log(publication.content);
console.log(publication.readingCounter); // 1
publication.content = 'nothing interesting';
console.log(publication.text); // nothing interesting
console.log(publication.changesCounter); // 1
```

[[PROTOTYPE BASED OBJECT ORIENTED PROGRAMMING]]
[[JAVASCRIPT IN WEB BROWSER]]
[[SERVER-SIDE JAVASCRIPT]]
[[METAPROGRAMMING]]
[[CLASSES IN JAVASCRIPT]]
