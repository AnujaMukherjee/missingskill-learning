## There are 3 Types of JavaScript Oparator arato
- Arithmatic Oparator
- Logical Oparator
- Ternary Oparator 

### Arithmatic Oparator :-
In JavaScript "+" oparator is use for concatination 
``` Javascript 
1.Var num =10;
var value ="hello";
var result =  num + value ; // '10hello'

2.  var a = "5";
 var b = 10;
 console.log(a + b);   //510

3.  var a = 5;
 var b = 10;
 console.log(a+b)   //15
 
4.  var a = "5";
 var c = 20;
 var b = 10;
 console.log(a +b+c);   //51020  here first concatination will happen as a variable add first 
5.var a = "5";
 var c = 20;
 var b = 10;
 console.log( b+c+a);   //305  first addition will done then with the result of addition concatination happen 

6.  var a = "5"; // parseInt its convert string to integer explisite type casting 
 var c = 20;
 var b = 10;
 console.log(parseInt(a)+b+c);   //35

7. var a = 7.065;
var b = 10;
var c = 20;
 console.log(parseInt(a)+b+c); // 37 it will convert 7.065 decimal pint to whole number and then add  it is the drawback parseInt

8.  var a = "5";
 var c = 20;
 var b = 10;
 console.log(Number(a) + b + c);   // 35 using number   constructor class 

9.  var a = "5.068";
 var c = 20;
 var b = 10;
 console.log(Number(a) + b + c);   //35.068 using number decimal point addition can happen it explicitly conver string to number 
```
* AS we know that if there is any string present "<strong><b>+</b></strong>" oparator in javascript is concatinate but ather oparators like <b>-,%,* ==,===,/</b> the preform acordingly there are property. 
``` JavaScript
Example 1:-
 var a = "5.068";
var c = 20;
var b = 10;
 console.log(Number(a) + b + c);   //35.068

Example 2:-
 var a = "5";
 var c = 20;
 var b = 10;
 console.log(a*b*c);   //1000

Example 3:-
var a = "5"; 
var c = 20;
 var b = 10; 
console.log(a/b/c);   //0.025

Example 4:- 
 var a = "5";
 var c = 20;
  var b = 10;
  console.log(a%b%c);   //5
```
## Boolen :-
```javaScript
Var booked =true; //in javaScript we always consider true as 1
var cost = 100
Var ABC  = true +100; // 101

var booked =true
var const =true
booked +cost // 2

var cost = False 
var booked =true 
cost + booked // 0+1 = 1 = true
cost * booked // 0*1 = 0 = False

1. undefined + undefined // NAN
2. undefined +True // NAN
3 .undefined +2 //NAN
4. undefined / undefined // NAN
5. null+null // 0
6. undefined / null // NAN
7. null / null // NAN
8. null +true // 1
9. null - true // -1
10. null - undefined // NAN 
11. "A" - undefined // NAN
12. "A"+ undefined // Aundefined
```
### Logical Oparator:-
 #### &&
<p>true && false => false </p>
<p>false && false => false </p>
<p>false && true => false </p>
</p>true && true => true </p>

#### ||
<p> false || true => true </p> 
<p>  true || false => true </p>
<p> true  || true => true </p>
<p> false || false => false </p>

<p>Number => 0,NAN => false (Falsy Value)</p>
</p>string => " " => Falsy Value => false</p>
</p>undefined => Falsy value => false </p>
<p> Null => falsy value => false

```JavaScript
Example 1. 
 var y = 6 , z =7 ;
 y && z (truthy && truthy => true if both are true then it will print second value )// 7

Example 2. 
var y = 0 var z = 7 
y && z (false && truthy => false if anyone is false then print first value  )// 0

Example 3.
console.log (!!NAN,!!NAN, NAN===NAN)// false,false,false

Example 4.
console.log (!!NAN,!!NAN, !!NAN==!!0)// false,false,true

Example 5.
console.log (!!{},!!{},{}=={})// false,false,false(it is false because  both object create difference memory location)

Example 6.
2 && 5 && 7 && 34[all are true print right side value ]

Example 7.
If(34 && 7 && 5 && 34)
{
  console.log ("he")
} // he 

Example 8.
 var food = "samosa"
 var my_fav = food;
 if (my_fav || "Chips" ) {// as here is   || oparator 
   console.log("My faviourite")    //My faviourite    any 1 condition is true it consider true
} else {
    console.log("Not faviourite") 
}

Example 9.
 var food = "samosa"
 var my_fav = food;
 if (my_fav && "Chips" ) {// as here is &&  ooparator 
   console.log("My faviourite")   
} else {
    console.log("Not faviourite") // Not faviourite
  
}
```
### Ternary Oparator :-
```Javascript 
Example 9.
var a = "Anuja"; //truthy
var a = !a && "Hello sona wellcome" || "!Sorry your not Anuja"; // falsey && truthy => falsey || truthy => truthy (if truthy then print right most value )
 console.log(res)    //!Sorry your not Anuja

Example 10.
var a = "Anuja"; //truthy
var a = a && "Hello sona wellcome" || "!Sorry your not Anuja"; // truthy && truthy => truthy  || truthy => truthy (if truthy then print right most value )
 console.log(res)    //!Sorry your not Anuja
 ```


















