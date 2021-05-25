
## IIFE (Immediately invoked function) :- 
 - so in immediately invoked function we can wrapped function into a block 
    
    - (function(){

        console.log ("initialization...") ;
    }) () ;
- IIFE use to create function privite so that we can make this function secure and it will call one at atime 
``` JavaScript 
Example 1 :-
    var outside = (function () // exicutation 
    {
        console.log ("Initialization ..."); //printing 
        function hello (value)
        {
            console.log ("Printing hello", value);
        }
        return hello;

    })() ; // iife function call 
    console.log (typeof outside, outside);
    outside (10);
/* First it will call iife function then it will print console.log ("Initialization...") . After that we check that only one parameter pass in iife function so function hello()  this entire function return and store outside variable. So typeof outside is function [function: hello] .Now  we  call outside () and pass 10 as we know that outside now holds function hello (value) so this 10 catch by  function hello (value )  and "printing hello" 10 

OUTPUTE :- 1 
Intialization...
funtion [function : hello]
printing hello 10 */


Example 2 :- 
     var outside = ( function(userid))
     {
         console.log ("Initialization ......");
        function hello (value)
        {
            console.log("printing hello", value,userid)
        }
        return hello;
     })(30)
    console.log(typeof outside, outside);
    outside(10);
/* First it will call iffe function and pass 30 as a parameter  now function(userid) userid =  holds 30 and print "Initialization..." after that there is no other value remaining that we can pass in iffe function  now entire function hello() store inside "outside" variable as function store in a variable so indirectly it's become function now we call outside() funtion  and pass 10 value it's catch by function hello (value)  now it print "printing hello " , 10 ,30 
 OUTPUTE :-
 Initializattion ----
 function [function :hello]
 printing hello, 10 ,30 */




Example 3:-
        var outside = (function(userid))
        {
            console.log ("Initialization ...");
            let counter = userid ; // closer property 
            function hello (value)
            {
                counter = counter + value ;
                console.log ("Printing hello ", value, counter) ;
            }
        return hello ;
        })(100)
     console.log(typeof outside, outside);
     outside (10);
     outside (10) ;
     outside (30) ;
    outside (50) ;
/* First we pass 100 as a parameter in iife function  it prints "Initialization ..." and we put the value of userid in counter variable . now counter = 100 . after that entire function hello (value) store inside "outside" variable and indirectly it  becomes  outside(). Now type outside function is 
function :[function : hello()]
now we are passing  10 value in outside() , outside() function holds value function hello (value) now 10 is catched by this "value" then as we know that counter is now store 100   so 100+10 = 110 update the value of counter and print . Printing hello , 10 ,110
 next time again we pass 10  same procedure but this time counter value  is update to 110 so 110+10 = 120 
 Printing hello  10, 120 
printing  hello 30, 150 
printing hello  50,200 
 OUTPUTE :_-
  Initialazation... 
  function [function hello()]
  Printing hello 10,110
   Printing hello 10,120
    Printing hello 30,150
     Printing hello 50,200 */

Example 4 :-
    function Print (value)
    {
        console.log ("printing value =>", value);
    }
    
    var outside = (function (next) {
        console.log ("Initialization ....") ;
        function hello (value){
            next (value);
        }
        return hello;
    } )(print);
    console.log ("outside IIFE ", typeof outside, outside) ;
    outside (10);
     outside (20) ;
/* Previous Example we see that everytime we are passing primitive value, pass by value this time  we are passing non primitive value, pass by reference. Now we call iife function pass reference of print(). This is catch by next and indirectly next become function()  which hold reference of  print()
First time it will print ("Initialization .....)
after that there is no value (both primitive and non primitive value passing to the iife function) . so the entire function hello() return to the outside variable and indirectly  outside variable become outside().
Now we are passing outside(10)  its catch by the  hello(value) after entire this hello(value) function with 10 parameter again its call next(value) => next point to print() so it's print  printing value => 10 
 OUTPUTE :-
  Initialization ...
   outside iife function[ function hello()]
  "printing value =>", 10;
  "printing value =>", 20; */
Example 5 :-
    const counter = (function(initial) { // 10 value pass intial = 10 
    return function(step){ // steps  = 30
        let count = initial; // due to closer property it can access his parent property  now count = 10 ; 
        return function() // this entire function return to counter as there in no other inline parameter which we pass in iife function 
        {
             count = count +step; 
            return  {
                initial: initial,
                step: step,
                count: count


            }
        }
    };
})(10)  (30);// 
console.log (counter());
console.log (counter());
console.log (counter());
console.log (counter());
console.log (counter());
 /* when we call counter() its return a object 
 { initial :10 , step: 30, count: 40}
 { initial :10 , step: 30, count: 70}
 { initial :10 , step: 30, count: 100}
 { initial :10 , step: 30, count: 130}
 { initial :10 , step: 30, count: 160} */
Example 6:-

    count counter =(function (para) { //10
    return function(step){ // 20
        let count =para; // closer property count = 10 it will access his parent property 
        return function() // () empty value 
        {
            count = count +step; // 10+ 20 = 30
            return {
                count: count // cit's retuen object  count to counter variable 
            }
        }
    };
})(10)(20)();
console.log(counter); 
/*  outpute :- 
 { count : 30} 

*/
Example 7 :-
    const counter = (function (para) {
    return function (step) {
        let count = para; // closer property 
        return function () {
            count = count + step; // for console.log(step()) // 10+4 = first function call // 14+4 = 18 second function call 
        // for console.log(step2()) // 10+10 = 20 first time call // 20+10 = 30 second time call 
            return {
                count: count
            }


        }
    };

})(10);
const step = counter(4);
const step2 = counter(10);
console.log(step()); // return object only {count:14}
console.log(step()); //{count:18}
console.log(step2()); // {count:20}
console.log(step2()); // {count:30}
/* First we pass   10 as inline parameter "para" catch the value of 10 now its return  function(step) to a counter variable  as there in no other inline parameter so return function(step) store to counter variable . next line we call counter(4)  function(step) exicute step holds 4 value  now because of closer property count = 10  and as there in no other parameter then return function() store to step variable . 
we call counter(10)  function(step) exicute step holds 10 value  now because of closer property count = 10  and as there in no other parameter then return function() store to step2  variable . 

```
## INLINE FUNCTION :-
in inline function instead  passing reference of the other function we can directly pass the function 
``` JavaScript 
var outside  = function (next){
    console.log ("1.Initialization .... ",typeof next , next );
 
    function hello (value ){
        console.log ("3.called hello ");
        next && (typeof next === "function") && next(value)
    }
    return hello ;
 }) (function (value){
     console.log("4. Printing from inline =>",value ) ;
 })
 console.log("2.outside IIFE", type of outside,outside) ;
  outside (10);
   outside (40);
    outside (100);
/* It is a example of Inline funtion so previous example we check that we pass a function reference but here insteade of passing reference we directly pass function . Now  "function(value)"  holds the function which is directly pass as inline parameters  and prints "Intialization ...". function[function]
now it's return entire function hello() and store into outside variiable indirectly outside variable become funtion . Now it will print 2. outside IIFE function [function hello]. Now first we pass the value 10  to function hello (value)  it's enter into the function print  and print 3. called hello  next line is conditional check all the value is truthy and call next(value) function which is nothing but inline function  it's print 4.Printing from inline => 10 
 OUTPUTE :- 
 1. Initialization...  funtion [Function]
 2. outside iife function [function hello]
 3. called hello
 4. printing from inline => 10
 3. called hello
 4. printing from inline => 40
 3. called hello
 4. printing from inline => 100
 */
 ```
 ## Arrow Function :-
 -  Arrow function is specially used when we want to passed some function as parameter.
  - It minimize the code 
  - In Arrow function we Directly removed function key , return
  - used in ES6 
  - Arrow function can't be hoisted 
  ```JavaScript 
Example 1:-
  // Without Arrow :-
   function add (a,b){
        let sum = a+b ;
         return sum ;
   } 
// With Arrow Function :-
 add(a,b) => (a+b);
Example 2:-
// Without Arrow function
const Location ={
     name : 'Mumbai',
     pincode : '400001',
     places:['CST','JUHU','Churchgate']
}
 const getLocation = function (Location)
 {
     return Location.name + "," +Location.pincode ;
 }
 const text = getLocation (Location);
  console.log (text);

// outpute :-Mumbai, 400001

// With Arrow function :-
 const Location ={
     name : 'Mumbai',
     pincode : '400001',
     places : ['CST','CHURCHGATE','JUHU'] ;
 }
const getLocation = Location => (location.name +"," +Location.pincode); // Arrow function 
const text = getLocation(Location) ;
console.log (text);
// outpute :-Mumbai, 400001
Example 3 :-
 var a = () =>{
     console.log ("Arrow a ");
 }
  var b = (param) =>{
     console.log ("Arrow", param);
 }
 b(10);

 var c = param =>{
     console.log ("Arrow", param);
 }
 c("no param");

var d = (param , p2) =>{
    console.log("Arrow" ,param)
}
d("in D arrow fn ")
// outpute:- Arrow a, Arrow 10 ,Arrow No param, Arrow , in D arrow fn 
````
## Function Chaining or Currying :-

Currying is a technique where we  evaluating function with more than one  arguments, into sequence of functions or series of function  with single argument.Instead of taking all arguments at one time, takes first arugemt and return to second function again takes second argument returns to third function this process continue. 
``` JavaScript 
Example 1:-
        ( function (p1{
             return function (p2){
                    return function(p3){
                             return function(p4){
                                    return function (cb){
                                        p1(cb(p2,p3,p4));
                                    }
                                     
                            
                             }

                    }

            }
        }) (function (print){
            console.log (print);
        })(20),(30),(40),(function (p2,p3,p4){
                    return p2+p3+p4 ;
        });
/* OUTPUTE :-
 90 
 (function (print){
            console.log (print); this total function pass to p1 then again 20, 30,40 , will pass to respectively p2,p3,p4 and  (function (print){
            console.log (print); this function pass in cb variable so whenever we call cb funtion addition now and return to p1 , pi it's self poiny print() so it will pringt the additin result */
Example 2 :-
        funtion fnAdd(p1){
             return function (p2){
                 return function (p3){
                      return function(p4){
                           return function (cb){
                               const sum = cb(p2,p3,p4);
                               p1(sum) ;
                           }
                      }
                 }
             }
        }

fnAdd (function (print) {
     console.log (print);
})(20) (30) (40) (function(p2,p3,p4) {
       return p2+p3+p4 ;
}) ;
/* outpute :-
90 */

Example 3 :-
         funtion fnAdd(p1){
             return function (p2){
                 return function (p3){
                      return function(p4){
                           return function (cb){
                               const sum = cb(p2,p3,p4);
                               cb(sum) ;
                           }
                      }
                 }
             }
        }

fnAdd (function(print){
     console.log(print);
}) (20) (30) (function(p2,p3,p4){
     return p2+p3+p4 ;
});
/* OUTPUTE :-
 90
*/



```
## Closer property :- 
<p> <b>in closer property child function has the authority to access his parent function variable </b>

## Higher order function :-

Any function whichtakes function as a parameter or returns a function called higher order function .
``` JavaScript 
Example 1:-
          function add (a,b)
        {
            const c = a+b ;
          return c ;
        }
    function operate (operation) // operation holds reference of add() 
    {
        let localfn ; // variable declearation 
        if (operation && (typeof operation === "function")) //  truthy && truthy condition satisfy 
        {
            localfn = operation ; // localfn holds the reference of operation function and as we know that operation  holds reference of add function so indirectly localfin holds add function reference 
        }
        else 
        {
            localfn = function () // not exicute 
         }
    return localfn ; // it will return add function 
   }
const executeFn = operate (add) 
// function operate (operation) is higher order function as its takes function as a parameter operaation holds a reference of add() function and it's return a function. 
Example 2:-
        var sport = function () {
            var cricket = function (player){
                var ipl = function (team){
                    return team
                }
            return ipl
            }
            return cricket
        }
    var cricket = sport() ;
    var result = Cricket ("Sachin")
    Var final = result("Mumbai Indian");
    console(final)
    var res = sport () ("sachin") ("Delhi DD")
    console log (res)
/* OUTPUTE :-
Cricket is higher order function as it's return ipl which is function
sport is higher order function as it's return Cricket which is function .
```
## PURE FUNCTION :-
if we add any function or add any variable inside the function which change the actual value then that is impure function  
 pure funcion we can't update any value or add any function inside scope 
 ``` JavaScript 
 function add (a,b){
     return a+b ;
 }
  var one = 30;
  var two = 50 ;
  const result = add (one,two);
  console.log (result , one, two)
 ```
 ## Callback function :-
 Call back function is a function where we pass function as a argument to other function and it's invoked to the outer function .
  ``` JavaScript 
Example 1:-
    function AfterWork ()
    {console.log("HURRAY!!!")
        
    }
   function MainWork(noOfWork,callback){
       let WorkDone = 0;
       for(i=0;i<noOfWork;i++){
           WorkDone = WorkDone+i;
       }
       console.log("no of work done",WorkDone)
       callback();
   }
 MainWork(10,AfterWork);
/* OUTPUTE :-
 10
 HURRAY!!! */

Example 2:-
           function FirstWork ()
    {console.log("HURRAY!!!")
        
    }
    
          function SecondWork ()
    {console.log("Anuja!!!")
        
    }
   function MainWork(noOfWork,callback){
       let WorkDone = 0;
       for(i=0;i<noOfWork;i++){
           WorkDone = WorkDone+i;
       }
       console.log("no of work done",WorkDone)
       callback1();
       callback2();
   }
 MainWork(20,FirstWork,SecondWork );

/* OUTPUTE :-
20
HURRAY!!!
Anuja !!! */

Example 3:-
           function FirstWork ()
    {console.log("HURRAY!!!")
        
    }
    
          function SecondWork ()
    {console.log("Anuja!!!")
        
    }
   function MainWork(noOfWork,callback){
       let WorkDone = 0;
       for(i=0;i<noOfWork;i++){
           WorkDone = WorkDone+i;
       }
       console.log("no of work done",WorkDone)
       callback1();
       callback2();
   }
 MainWork(20)
 .then(FirstWork,SecondWork)
 .catch(function() {
      console.log ("first we need to perform MainWork");
 })
 ```
 
