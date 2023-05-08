
- **Prototypes**:
```javascript
// define the Vehicle contructor
function Vehicle(make, model){
	this.make = make;
	this.model = model;
}

// in the Vehicle prototype you define properties and methods

// application of all vehicles is transportation:
Vehicle.prototype.application = 'transportation';
 
// methods of the Vehicle prototype:
Vehicle.prototype.start = function() {
    console.log(this.make + ' ' + this.model + ' starts');
};
Vehicle.prototype.drive = function() {
    console.log(this.make + ' ' + this.model + ' drivess');
};
Vehicle.prototype.stop = function() {
    console.log(this.make + ' ' + this.model + ' stops');
};

```

-  **Inheritance**:
```javascript
function Vehicle(make, model) {
    this.make = make;
    this.model = model;
}
Vehicle.prototype.application = 'transportation';
Vehicle.prototype.start = function() {
    console.log(this.make + ' ' + this.model + ' starts');
};
Vehicle.prototype.drive = function() {
    console.log(this.make + ' ' + this.model + ' drives');
};
Vehicle.prototype.stop = function() {
    console.log(this.make + ' ' + this.model + ' stops');
};
 
// create an instance of the Vehicle -> this is inheritance
var volkswagen = new Vehicle('Volkswagen', 'Golf');
volkswagen.start(); // Volkswagen Golf starts
volkswagen.drive(); // Volkswagen Golf drives
volkswagen.stop(); // Volkswagen Golf stops
```

- **`Prototypes` & `Inheritance`**:
```javascript
var ferrari = new Vehicle('Ferrari', 'LaFerrari');
 
// here you define custom drive() method for the ferrari object:
ferrari.drive = function() {
    console.log(this.make + ' ' + this.model + ' drives very fast');
};
ferrari.drive(); // Ferrari LaFerrari drives very fast
```

- **Dynamic prototypes**:
	- Nếu bạn thêm một thuộc tính hoặc một phương thức vào một nguyên mẫu, thì tất cả các đối tượng kế thừa từ nguyên mẫu này đều có quyền truy cập vào thuộc tính hoặc phương thức đó. Điều này tự động xảy ra ngay cả khi bạn thêm thuộc tính hoặc phương thức vào nguyên mẫu sau khi bạn đã tạo đối tượng.
```javascript
var porsche = new Vehicle('Porsche', '911 Turbo');
Vehicle.prototype.accelerate = function() {
    console.log(this.make + ' ' + this.model + ' accelerates');
};
porsche.start();
porsche.drive();
porsche.accelerate(); // Porsche 911 Turbo accelerates
```

- **Properties and prototypes**:
```javascript
Vehicle.prototype.light = "abc";
 
Vehicle.prototype.turnOnTheLight = function() {
    if (this.light === "abc") {
        this.light = "def";
        console.log(this.make + ' ' + this.model + ' - the light is now on');
    } else {
        console.log(this.make + ' ' + this.model + ' - the light is already on');
    }
};

const per = new Vehicle("Peugeot","308");
console.log(per.light); // abc
console.log(per.hasOwnProperty('light')); // false
per.turnOnTheLight();
console.log(per.hasOwnProperty('light')); // true
console.log(per.light); // def
```