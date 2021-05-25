## Copy By Value :-
1. Primitive data types are goes under copy by value 
2. In copy b value we pass primitive data type  so if any change happen inside scope or inside any block scop or any funtional  scop  this  change will not effect the entire program here we pass copy only so change happen only copied value but in vopy by refarence we pass the referance means pass the address of original value we are not passing any copied value so in copy by refrarence if any change happen it will effect the entire code 

-  string 
- Null 
- Ubdefined
- Number
- boolen 
```Javascript 
Example 1:-
    var a = 50;
    var b = a;
    var c = b;
    a = 500;

    console.log(a);  //500
    console.log(b); //50
    console.log(c); //50
    b = 60;
    console.log(b); //60
    console.log(c);   //50
Example 2:
    var a = 50;
    var b = a;
    var c = b;
    a = 100;
    b = 30;
    console.log(a);  //100
    console.log(b); //30
    console.log(c); //50
    console.log(b); //30



 Example 5

 var a = 50;
 var b = a;
 var c = b;
a = 500;
 b = 60;
 console.log(a);  //500
 console.log(b); //60
 console.log(c); //50

 console.log(b); //60




// Example 6

var a = 50;
var b = a;
var c = b;
a = 500;

console.log(a);  //500
console.log(b); //50
console.log(c); //50
b = 60;
console.log(b); //60
console.log(c);   //50