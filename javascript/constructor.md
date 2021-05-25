## Constructor :- 
constructor is a block of code which is similar to method. It is called when a class is created.It is a special type of method which is used to initialize the object.

Every time when an  object is created using the new() keyword, at least one constructor is called.
 <p>The time of creating object constructor name and class name always same
 <p> while creating a object of a particular class so the time of creating object we pass the value , but in normal method  first we access that method then we pass the value 
 <p> below example we check that function Birds() is a constructor of Bird class and function setColor() is normal method of Bird class  so when we access of function Birds() constructor that time creating object of Bird class we pass value directly int parrot = new Birds("meethu")  but when we try to access  setColor() this way we can access " parraot.setColor("Green")

~~~JavaScript
class Birds {
    int noOfLegs = 2;
    int noOfWings = 2;
    string color;
    string name;
    function Birds(name) {
        this.name = name
    }
    function setColor(color) {
        this.color = color;
    }

    function fly(){
        //how to fly
    }
}

int parrot = new Birds("meethu");
int crow = new Birds("golu");
parrot.setColor("Green")
crow.setColor("Black")
~~~
## Function Constructor :-
In JavaScript, a constructor function is used to create objects. In Below Example 'Person' is called function constructor because  we know that time of creating object  we directly pass the value Every time when an  object is created using the new() keyword, at least one constructor is called . Here we create 'anuja' object  from Person class and pass two values 

```JavaScript
//Function Construstor
function Person(name, age){
    this.name = name;
    this.age = age;
}




let anuja = new Person("Anuja Mukherjee", 23);
let sid = new Person("Siddhartha Chakraborty", 30);

console.log(anuja);
console.log(sid);
// anuja = {name: "Anuja Mukherjee", age: 23} 
// sid = { name:"Siddhartha Chakraborty", age:30}
// This are the two object under Function Person class so we call  Function Person as function constructor 
```

## Method inside Function Constructor :-
we can create  normal method in  function constuctor like here we create welcomeMessage() methid 
```JavaScript
/Function Construstor
function Person(name, age){
    this.name = name;
    this.age = age;

    this.welcomeMessage = function () {
        // let arr = [];
        // arr.push("Welcome ")
        // arr.push(this.name)
        // return arr;
        return ("Welcome "+ this.name);
    }
}

let anuja = new Person("Anuja Mukherjee", 23);
let result = anuja.welcomeMessage();
let sid = new Person("Siddhartha Chakraborty", 30);
let Rima = new Person("Rima Mukherjee, 22);

console.log(anuja.name);
console.log(result);
console.log(sid);
console.log(Rima );
/* outpute:- 
Anuja Mukherjee 
Function[ function : WelcomeMessage]
// sid = { name:"Siddhartha Chakraborty", age:30}
// Rima = { name:"Rima Mukherjee ", age:22} */

```
## Difference Between Literal Object  and Function :- 
Literal Object  is used to creating Single Object. In Literal Object we find the concept of call by reference 

Function Constructor is used to Create Multiple object . 

Below example we can check that first we create a <B> Literal Object </B> name anuja and sid and we pass reference of anuja in anujaXerox and add post ,so this post key update in both anuja and anujaXerox

next example we create  person function constructor and we create anuja ,sid object of person class now if we add any keyword in any object it will not effect the other objects as there is no call by reference concept 
```JavaScript

//Literal Notation for Creating an Object 
let anuja = {
    name: "Anuja Mukherjee",
    age : 23,
    skill: "JavaScript",
    welcomeMessage: function(){
        return ("Welcome " + this.name)
    }
}
let anujaXerox = anuja;
anujaXerox.post = "Backend"
console.log(anuja)
console.log(anujaXerox)
let sid = {
    name: "Siddhartha Chakraborty",
    age : 30,
    skill: "Banking",
    welcomeMessage: function(){
        return ("Welcome " + this.name)
    }
}
console.log(sid)

/* outpute :-
{name: Anuja Mukherjee , age:23, skill: JavaScript, welcomeMessage : function[function: welcomeMessage],post: Backend}

{name: Anuja Mukherjee , age:23, skill: JavaScript, welcomeMessage : function[function: welcomeMessage],post: Backend}
 
 {name: Siddhartha Chakraborty , age:30, skill: Banker , welcomeMessage : function[function: welcomeMessage]}
 */
// (Function Constructor)
function Person(name, age, skill){
    this.name = name;
    this.age = age;
    this.skill = skill;
    this.welcomeMessage = function (){
        return ("Welcome " + this.name)
    }
}

let anuja = new Person("Anuja Mukherjee", 23, "JavaScript");
let anujaXerox = new Person("Anuja Mukherjee", 23, "JavaScript");
let sid = new Person("Sidhartha Chakrabory", 30, "Banking");
anujaXerox.post = "Backend";
anujaXerox.welcomeMessage = function () {
    return ("Welcome "+this.name)
}

console.log("Original",anuja)
console.log("Anothoer",anujaXerox) 
/* Outpute :-
{name: Anuja Mukherjee,age:23,skill: javascript welcomeMessage : function[function: welcomeMessage] }
{name: Anuja Mukherjee,age:23,skill: javascript welcomeMessage : function[function: welcomeMessage], post: Backend }
{name: Siddhrtha Chakraborty,age:30,skill:Bankar,welcomeMessage : function[function: welcomeMessage] } */
```
## Adding Properties And Methods in an Object
Adding properties and method in Function Constructor 
```JavaScript 
        // constructor function
function Person () {
    this.name = name;
    this.age = age ;
}

// creating objects
let person1 = new Person("Anuja Mukherjee",23);
let person2 = new Person("Sidhartha Chakraborty",30);

// adding property to person2 object
person2.gender = 'male'; // adding inreal life object 

// adding method to person1 object
person1.greet = function () {
    console.log('hello');
}

person1.greet();   // hello

// Error code
// person2 doesn't have greet() method
person2.greet();
```
## Literal Notaiton and its Real Meaning:-
```JavaScript
Example 1 :-
let AnujaObject = {
    name: "Anuja Mukherjee,
    age: 233
}
function Object(name, age) {
    this.name = name;
    this.age = age;
}
let AnujaObject = new Object("Anuja",23) 

Example 2:-
let obj = {}  //genaral notation
let obj = new Object() // compiler understand  here obj is object of Object class
Example 3:-
let name = "Anuja";  
let name = new String("Anuja"); //Compiler understand  here name is object of String class

Example 3:-
let sum = 100; 
let sum = new Number(100); // Compiler understand  here sum is object of Number class

Example 4:-
let fact = true;
let fact = new Boolean(true) // fact is object of boolen class
```