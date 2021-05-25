# JAVASCRIPT
## introduction of javascript :-
<p> JavaScript is the world's most popular programming language. </p>
<p> JavaScript is the programming language of the Web.</p>
<p> JavaScript is easy to learn.</p>
<p> This tutorial will teach you JavaScript from basic to advanced.</p>
<p> JavaScript is a fun and flexible programming language. It’s one of the core technologies of web development and can be used on both the front-end and the back-end.</p>
</p> Javascript built up on four piller.</p>

- Variables
- Functions
- Object
- Arrays

## Javascript variable :- 
<p> Variables are containers where we can store values, JavaScript variables hold primitive and non-primitive both values. The value stored in variable can be changed during program execution .</p>

## Naming of variables :-
- variable name can begin only with a letter or underscore ( _ ).
- variable names can contain letters(a-z/A-Z), numbers(0-9) and dollar sign($).
- variable names can not contain any space or tabs.
- variable names are case-sensitive 
```Javascript
        var place1 = "Hassan";
        let _phoneNumber = 9147500;
        const name$ = "Anuja";
        const NAME$ = "Mona"; //name$ and NAME$ are different variables - case sensitive
        let country name = "INDIA" //error -can not contain spaces
```
## Data types:-
JavaScript is Dynamically typed language  over time.hese language can receive different data types over times , in JavaScript variables can receive different data types on runtime
## THERE ARE TWO TYPES OF JAVASCRIPT  DATATYPE :-
- |PRIMITIVE:- |
  |---|

    - String
    - Number
    - Undefined
    - Null
    - Symbol
    - Boolean(true/false)

- | NON PRIMITIVE:-|
  |---|
       
    - Array
    - Object 
    
     <b>string :- </b>
```JavaScript
    var name = "React"
``` 
 <b> number :- </b>
```JavaScript
    var price = 100.89
```
   <b> boolean :- </b>
```JavaScript
    var isVerified = true
```
###  Non - primitive data types
 <b> array :- </b>
```Javascript
    let bankAccount = ["Indian Bank", "Andheeri", 1000.256, "oct"];
```
<b>object </b> - key:value pairs mapping 
```Javascript
    let bankAccount = { name: "Bank of baroda", amount: 10000.256, openedMonth: "may"}
```

## Ways to declare a variable
- var (ES5)
-  let and const(ES6)

<p>Note: <strong>typeof </strong>   operator returns a string indicating the data type of the variable </p>

```Javascript
    var coins = 1
    typeof a //returns type of the value variable 'coins' holds 
    "number"

    coins = true
    typeof a
    "boolean"

    coins = []
    typeof a 
    "object"

    coins = null
    typeof a 
    "object"

    var coins = "Javascript" //redeclaration of same variable allowed when var keyword is used
    typeof a 
    "string"
 ```
## Difference between Null and Object :-
```Javascript
var test 
console.log (test); // underfined its means we are not assingning the value into this test variable container 

var test = Null
console.log (test)// object null means we are assingning the value into test variable 
console.log (type of Null) // object it is mistake of javascript 
console.log (type of undefined) // undefined 
console.log(null===undefined) // False
console.log (null==undefined) //True
console.log(Null===Null)//True
console.log (Null==Null)//True
console.log(!null)// true
console.log(!!null)//false
```
### VAR (ES 5):- var has functional scope , var can be reassigned and redeclare 
 ```Javascript
 1.  var local // golbal variable
console.log(local); //undefined
local =30; //assinged undefined to 30
function hello(){
    console.log("hello",local);  // local variable inside scope is undefined
    var local =20;// var can hoissted to neaest function block again its reassinged local veriavle under the scope to 20
    }
hello();// call hello function
console.log (local) ; // 30 as it is access global local veriable 

2. var local // golbal variable
console.log(local); //undefined
local =30; //assinged undefined to 30
function hello(){
    console.log("hello",local);  // as there is no varaile declear on functional scope as is directly access to global scope value will be 30
     local =20;// as it is accessing global so global variable value will be change 30 to 20
    }   
hello();// call hello function
console.log (local) ; // 20 */

3. var local;
console.log(local) //undefined
local = 30 ; // change golable local variable undefined to 30
function hello (){
    console .log ("hello",local); // var local hoisted and value is undefined so output is undefined
    var local =20;// scope local value change undefined to 20
    }
hello () // call hello func
console.log (local) ; //30*/

4. var local ;
console.log (local) ; // undefined
local=30;
function hello(){
    var local;
    console.log("hello",local) ;// undefined
    local =20;
    function inside(){
        console.log("inside",local) ; //in will print 20 as if it is assess local variable inside the functional scope 
        local=50; 
    }
    console.log("hello 2",local); // 20
    inside();
}
local =40;
hello();
console.log(local); //40

 5.  var num ;
   console.log("1", num);  //undefined
       num = 30;
   function fuNumber() {                    
     console.log("3", num);   //undefined       
     function innerFun() {
         console.log("5",num)      //60
     }
    console.log("4", num)   //undefined
     var num = 60;    //get hoisted  
    innerFun();
    
 }
console.log("2",num)   //30
 fuNumber();
 console.log("6", num);  //30
 ```
 ## LET (ES6) :- Lexical scope  and reassinged but not redeclear 
 ``` Javascript
  1. let num ; //  let variable deaclear
 console.log("1", num);   //undefined
 num = 30; //reassinged value of let variable 
 function fuNumber() {
    let num = 60; 
    console.log("3", num);      //60  functional scope its access let variable which is inside fuNumber()
    function innerFun() { 
        console.log("5",num)     //60 // it will assess let variable as inner function itself have no let variable so it will access its nearest parent location
     }
     console.log("4", num)    //60
                
     innerFun();
    
 }
 console.log("2",num)  //30
 fuNumber();
 console.log("6", num);  

 2 . let num ;
console.log("1", num);   //undefined
 num = 30;
 function fuNumber() { 
    console.log("3", num);      //30
    function innerFun() {
        let num = 70; 
        console.log("4", num)    //70
        function innerToInner() {
            console.log("5", num)     //70 
      }
        innerToInner()
    }
    innerFun();
    console.log("6",num)    //30
    } 
 console.log("2",num)  //30
 fuNumber();
 console.log("7", num); //30

 3. let local;
  console.log (local);//undefined
  local= 30; // global variable value change  undefined to 30
  function hello(){
      // function scope => local scope 
      function inside (){
          let local ;
          console.log ("inside", local);// undefined
          local =50;
          console.log ("inside 1", local); // 50
      }
    let local ;
    console.log ("hello",local); // undefined
    local =20 ;
    console.log("hello 2",local); // 20
    inside();
    local ="world";
    console.log("hello 5" , local);//world
  }
  local = 40;// reassinged to 40
  hello();// call hello function 
  console.log(local); //40
```
### Const (ES6) :-  const declear only one time if  we declear const it automatically locked memory location 
 ``` Javascript
 const num =30;   //error         Missing initializer in const declaration
 console.log("1", num);   
  function fuNumber() {
      num = 60;             //error doesn't reassign the const value
   console.log("3", num);      
    function innerFun() {
         let num = 70; 
         console.log("5",num)     
    }
    console.log("4", num)           
    innerFun();
     console.log("6",num)    
}
 console.log("2",num)  //30
 fuNumber();
 console.log("7", num);
```
### Difference Between LET, VAR ,CONST :-
|var|let|const|
|---|---|---|
|ES5|ES6|ES6|
|redeclaration of variable allowed|redeclaration not allowed|redeclaration not allowed|
|re-initialisation allowed|re-initialisation not allowed|re-initialisation not allowed|
|re-assignment of value to variable allowed|re-assignment of value to variableallowed|re-assignment of value to variable not allowed|
|functional/global scope|lexical/block scope|lexical/block scope|
|Hoisted|not hoisted|not hoisted|

