## Example of Function declearation :-
1) Function declearation can hoisted
2) It can override 
4) non primitive always passed by reference 

``` Javascript 
Example 1 :- 
         function helloDouble(somevalue) // 20
         {
             console.log("print"+somevalue); // print 20
             return  somevalue*2+[2]; // 402 concatination happen 

         }
    var val = 20 ;// val = 20
    var result = helloDouble(val); //  from function concepts we know that function has return value so this line explain that we call helloDouble() function and return value of helloDouble function store in result variable 
    // helloDouble(val=20) function call and it's pass 20 value 
    console.log(result typeof result) ; // now "result" variable store the return value of helloDouble() function which is 402 string
    /*OUTPUTE 
    print 20
    402 string */ 

Example 2 :-
    function helloDouble(SomeValue) //function declearation 
    {
        console.log("parint"+SomeValue);
        function innerDouble()
        {
            console.log("result is called from outside ", SomeValue*2);
        }
        return innerDouble();
    }
    var val = 20;
    var result = helloDouble(val);
    console.log(result, type of result) ;
    result && (typeof result === "function")&& result ();




Example 3:-
         var mainFn = function()
         {
             console.log ("Print D");
         }
             function doTask(){
                 console.log("print task" );
             }
        var do Task 2 
        doTask ();
        doTask 2 = function () {
            console.log("print task 2");
        }



Example 4:-
        function helloDouble(somevalue){
            console.log("Print"+somevalue);        
             function innerDouble(){
                 console.log (somevalue*2); 
             }
             return innerDouble;
            var val = 20 ;
            var result = helloDouble(val) // its is holdes the reference of innerDouble function 
            console.log (result, typeof result);
            result ();
    /* OUTPUTE 
        print 20 ;
        [function innerDouble] function
        40 */
Example 5:-


```

## Example with function assingment :-
 ``` JavaScript 
 var LogicBoard = function(param) // anonymus function // function assingment 
 {
      console.log ("Logic Board", Param) ; // print 
 }
  var board = "i386" ; //  variable declearation 
  LogicBoard (board) ; // we pass this board valiue as a parameter to LogicBoard function = i386

var board = "i586" ;//  variable declearation 
  LogicBoard (board) ; //  we pass this board valiue as a parameter to LogicBoard function = i586

 var board = "i786" ; // variable declearation 
  LogicBoard (board) ; //  we pass this board valiue as a parameter to LogicBoard function = i786

var newLogicBoard = LogicBoard ; //  new LogicBoard variable is create which hold a reference of LogicBoard object 
 var board = "8 core " ;// variable declearation 
 newLogicBoard (board); //  we pass this board valiue as a parameter to LogicBoard function = "8 core" 
 var newB = "Anuja" ;
 var gameBoard = newLogicBoard ; // gameBoard holds reference of newLogicBoard and  newLogicBoard holds reference of  LogicBoard 
 gameBoard (newB) // we pass this board valiue as a parameter to LogicBoard function = "Anuja"
/* OUTPUTE :-
Logic Board "i386"
Logic Board "i586"
Logic Board "i786"
Logic Board "8 core"
```


## Passing function as a reference :-
```JavaScript 
const Print = function (value) // function assingment 
{
    console.log ("printing =>" , value ) ; // printing value = 1500
}
const betterPrint = function (value) // function assingment 
{
    console.log ("betterprinting =>" , value ) ; // betterprinting => 750 
}

const goodPrint = function (value) // function assingment
{
    console.log ("goodprinting =>" , value ) ; // goodPrinting => 3000 
}

const CompleteTask = function (a,b, param) 
{}
    const c = a*b ; // 1) 300*5 = 1500
    // 2)  150*5 = 750
    // 600*5 = 300
    param && (type of param === "function") && param (c) //  truthy && truthy && truthy  go to first print()
    // truthy && truthy && betterPrint()
    //truthy && truthy && goodPrint()
}
var a = 300 ;
var b =5;

CompleteTask(300,5,print) ; // inline function call CompleteTask function with 3 inline parameters 300,5, print() function here we pass funtion as a parameter as we know that function is a object so we pass reference of print () 
CompleteTask(150,5,betterprint) ;// inline function call CompleteTask function with 3 inline parameters 150,5, betterprint() function here we pass funtion as a parameter as we know that function is a object so we pass reference of betterprint () 
CompleteTask(600,5,goodprint) ;//inline function call CompleteTask function with 3 inline parameters 600,5, goodprint() function here we pass funtion as a parameter as we know that function is a object so we pass reference of goodprint () 

//  first time it's hold 300,5, param holds a reference of Print() function.   // 2) function assingment  second time it's hold 150,5, param holds a reference of betterPrint() function.
//function assingment  first time it's hold 600,5, param holds a reference of Print() goodfunction.
```
## Passing Two parameters :- 
```JavaScript
const Print = function (value) 
{
    console.log ("Printing =>" , value) ;
}
const betterPrint2 = funtion (value)
{
    console.log ("betterPrinting =>" , value )
}
const CompleteTask = function (a,b,next, param) 
// (300,5, reference of betterPrint(),reference of print ())
{
    const c = a*b ; // 300*5 = 1500
    next && (typeof next === "function")&& next(c); // first truthy && truthy && truthy exicute  next (c) [reference betterPrint()]
    param && (typeof next === "function")&& param(c); // first truthy && truthy && truthy exicute  next (c) [reference Print()]

}
var a = 300 ;// it will first declear and assigned variable a = 300
var b = 5 ; // it will first declear and assigned variable b = 5
const CompleteTask = function (300,5,betterprint, print ) 

/* call CompleteTask function and pass parameters like 300 and 5 and pass reference of betterPrint() and print () . Now  betterPrint() function reference pass first so it will exicute betterPrint() then print()*/
/* OUTPUTE 
betterPrinting => 1500 
Printing => 1500 */
```

## Functiion as a parameter and Function Returning function :-

```JavaScript
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
const executeFn = operate (add) ; // function assigment // call operate function 
console.log (typeof executeFn,executeFn ) ;
/*  operate() now operate() function pass add() function as a reference */ 
/* OUTPUTE :-
 function [Function : add] */

Example 2 :-
           function add (a,b) //(1,3)
        {
            const c = a+b ; // c = (1+3) 4 
          return c ; a// its return 4 
        }
    function operate (operation) //
    {
        let localfn ;
        if {operation && (typeof operation === "function")}
        {
            localfn = operation ;
        }
        else 
        {
            localfn = function () // this is colled 
         }
    return localfn ;
   }
  const executeFn = operate (add) ; // call  operate function pass reference of add()
  var d = executeFn (1,3) ; // it is indirectly pointing to add() and it is pass by reference 
  console.log (d) ;
  /* OUTPUTE :- 
  4*/
  ```



                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         