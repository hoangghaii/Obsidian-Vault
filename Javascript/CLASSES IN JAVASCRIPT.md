
- **Class declaration**: *(recommended)*
```javascript
class Person {
    constructor(name, surname) {
        this.name = name;
        this.surname = surname;
    }
}

var person = new Person('Jack', 'Smith');
```

<ins>Note</ins>: Có sự khác biệt giữa khai báo hàm và khai báo lớp về mặt cẩu. Các khai báo lớp không được nâng lên và trước tiên bạn phải khai báo một lớp rồi mới có thể sử dụng nó. Nếu không, ReferenceError xảy ra.
```javascript
var test = new Test(); // ReferenceError
 
class Test {}
```

- **Class expression**:
```javascript
var Person = class {
    function constructor(name, surname) {
        this.name = name;
        this.surname = surname;
    }
};

var person2 = new Person('John', 'Smith');

console.log(Person.name); // Person
console.log(person2.name); // John
```

- **Constructor**:
```javascript
class Polygon { 
   constructor(length, width) { 
      this.length = length; 
      this.width = width;
   }
}

// Equivalent using constructor function is as follow:
function Polygon(length, width) { 
      this.length = length; 
      this.width = width;
}
```

- **Prototype Methods**:
```javascript
class Polygon { 
    // ...
    
   area() {
       return this.length * this.width;
   }
} 
 
var polygon = new Polygon(10, 5);
console.log(polygon.area()); // 50

// Equivalent using constructor function is as follow:
Polygon.prototype.area = function() {
    return this.length * this.width;
}
```

- **Static methods**
	- Xác định bằng cách đặt trước tên phương thức bằng từ khóa `static`. 
	- Không thể được gọi thông qua thể hiện của lớp, chúng được gọi trực tiếp thông qua tên lớp.
	- *Static methods* không có tương đương.

```javascript
class Polygon { 
   constructor(length, width) { 
      this.length = length; 
      this.width = width;
   } 
    
   area() {
       return this.length * this.width;
   }
    
   static printDimensions(polygon) {
       console.log('Length: ' + polygon.length + ' Width: ' + polygon.width);
   }
} 
 
var polygon = new Polygon(10, 5);
console.log(Polygon.printDimensions(polygon)); // Length: 10 Width: 5

```

- **Properties**:
	- Các thuộc tính thể hiện bạn phải định nghĩa bên trong các phương thức của lớp.
	- Các thuộc tính nguyên mẫu bạn phải xác định theo cách cũ, bên ngoài nội dung lớp.

```javascript
class Polygon { 
   constructor(length, width) { 
      this.length = length; 
      this.width = width;
   }
}

Polygon.prototype.figure = 'Rectangle';
```

- **Inheritance**:
```javascript
class Employee {
    constructor(name, surname) {
        this.name = name;
        this.surname = surname;
    }
     
    work() {
        console.log(this.name + ' ' + this.surname + ' works.');
    }    
}

// overwrite
class Bricklayer extends Employee {
    work() {
        console.log(this.name + ' ' + this.surname + ' builds houses.');
    }
}
 
var bricklayer = new Bricklayer('John', 'Doe');
bricklayer.work(); 
// output:
// John Doe builds houses.
```

- **The super keyword**:
```javascript
class Electrician extends Employee {
    constructor(name, surname, specialization) {
        super(name, surname); // call the super class constructor
        this.specialization = specialization;
    }
     
    work() {
        super.work(); // call the super class method work()
        console.log(this.name + ' ' + this.surname + ' ' + this.specialization + ' installs electrical equipment.');
    }
}
 
var electrician = new Electrician('Tom', 'Smith', 'Electrical Fitter');
electrician.work(); 
// output:
// Tom Smith works.
// Tom Smith Electrical Fitter installs electrical equipment.
```