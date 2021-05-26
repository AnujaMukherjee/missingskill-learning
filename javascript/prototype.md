## Prototype:-
<p> When we create multiple of and this multiple object have a common similarity that time we add that comman similarity to the class or function constructor by the prptotype key word 


```JavaScript
//Function as Constructor Function/Class/Prototype
function Person(name, age) {
    this.name = name;
    this.age = age;
}

let anujaObject = new Person("Anuja", 23); 
let jackyObject = new Person("Rima", 22);
console.log(anujaObject, RimaObject)
//{name:Anuja,age:23}
//{name:Anuja,age:22}
//Smart Way, thanks to "prototype"
Person.prototype.skill = "JavaScript"; // adding property
Person.prototype.welcomeMessage = function (){ // adding method 
    return ("Welcome "+ this.name);
}

let aninditaObject = new Person("Anindita", 24);

console.log(anujaObject.skill); //JavaScript
console.log(RimaObject.skill); // Javascript
console.log(aninditaObject.skill);// Javascript

console.log(anujaObject.welcomeMessage()); // welcome Anuja
console.log(RimaObject.welcomeMessage()); // welcome Rima
console.log(aninditaObject.welcomeMessage()); // welcome Anindita



//Adding properties and methods to a Construstor Function itself and NOT to individual objects (This is where prototype comes in)
function Person(fname, lname, age) {
    this.fname = fname;  //vip
    this.lname = lname; // vip
    this.age = age; //vip
}
Person.prototype.skill = 'JavaScript'; 
Person.prototype.getName = function () {
    return (this.fname +" "+ this.lname);
}
Person.prototype.getAge = function () {
    return this.age;
}
let anujaObject = new Person("Anuja", "Mukherjee", 23);
let RimaObject = new Person("Rima","Mukherjee", 22);

console.log(anujaObject.getName()) // Anuja Mukherjee
console.log(anujaObject.getAge()) // 23
console.log(anujaObject.skill) // JavaScript
console.log(RimaObject.getName()) // Rima Mukherjee
console.log(RimaObject.getAge()) // 22
console.log(RimaObject.skill) // JavaScript

//Another Example
function Calculator(initial) {
    this.total = initial;
    this.sum = function(num) {
        this.total = this.total + num;
        return this.total;
    }
}
Calculator.prototype.subt = function(num) {
    this.total = this.total - num;
    return this.total;
}

Calculator.prototype.brand = 'Casio';

let abc = new Calculator(5);

let sumResult = abc.sum(1)
let subtResult = abc.subt(2)

console.log(sumResult) // 6
console.log(subtResult) // 4
```


```JavaScript
//Prototype is used to provide additional property to all the objects created from a constructor function.

function Person (name,age) {
    this.name = name;
    this.age = age;
    this.skill = "Quantum Mehanics"
    this.post = "Product Engineer"
    //_proto_: {}
}

const anujaObject = new Person("Anuja",23);
const rimaObject = new Person("Rima",22);

// // checking the prototype value
// console.log(Person.prototype); // output=> {}    because as of now there is nothing in the prototype

Person.prototype.skill = "JavaScript"
Person.prototype.post = "Full Stack Web Developer"

console.log(Person.prototype);  // { skill: 'JavaScript', post: 'Full Stack Web Developer' }
console.log(Person.prototype.skill); // JavaScript
console.log(Person.prototype.post); // Full Stack Web Developer
console.log(Person.skill); //undefined because we can only access Vip members or class predefined member only the  help of object here we can only access with anujaObject 
console.log(anujaObject.skill); // Quantum Mechanics
console.log(Person.post); //undefined because we can only access Vip members or class predefined member only the  help of object here we can only access with anujaObject 
console.log(anujaObject.post); // Product Engineer




Inheritance Concept:-

function Person (name,age) {
    this.name = name;
    this.age = age;
    //_proto_: {}
}

const anujaObject = new Person("Anuja",23);
const rimaObject = new Person("rima",22);

Person.prototype.skill = "JavaScript"
Person.prototype.post = "Full Stack Web Developer"

//anujaObject skill is inherit  from Person function constructor 
console.log(anujaObject.skill); // JavaScript because It inherits from Person ka (prototype), and there is no  skill key value pair inside theperson class so it's take prototype value 
console.log(anujaObject.post); // Full Stack Web Developer 
// this post is also inherit from person  class it will first check that in person class it self is there any key value pair present in post name if not then it's take from  proto:{} prototype 
//rimaObject skill ar post ta inherit korlo from Person
console.log(rimaObject.skill); // JavaScript because It inherits from Person ka (prototype), and there is no  skill key value pair inside theperson class so it's take prototype value 
console.log(rimaObject.post); // Full Stack Web Developer 
// this post is also inherit from person  class it will first check that in person class it self is there any key value pair present in post name if not then it's take from  proto:{} prototype



Changing Prototype:- 

function Person(name, age) {
    this.name = name;
    this.age = age;
    //_proto_: {}
}

Person.prototype.skill = "JavaScript"

let anujaObject = new Person("Anuja", 23);
let sidObject = new Person("Sidhartha", 30);

console.log(anujaObject.skill) // JavaScript
console.log(sidObject.skill) // JavaScript
Person.prototype.skill = "NodeJS" // Updation Happens Here

let RimaObject = new Person("Rima", 22);


console.log(anujaObject.skill) // NodeJS
console.log(sidObject.skill) // NodeJS
console.log(RimaObject.skill) // NodeJS


Prototype Chaining:-
function Person() {
    this.skill = 'Quantum Mechanics'
    //_proto_: {
    //     skill = 'JavaScript';
    //     age = 23
    // }
}

// adding property 
Person.prototype.skill = 'JavaScript';
Person.prototype.age = 23

const anujaObject = new Person();

console.log(anujaObject.skill); // Quantum Mechanics  skill is in vip class so first prority alwayds vip class
console.log(anujaObject.age); // 23 // age is not in vip class (function constructor itsself) so it's prit the value inside proto 
```