```JavaScript

Example 1:-
/*;(function(callback,next){
     return function (value){
          callback(value,next);
     } 
}) (function(p1,p2){
     p2(p1);
}, function (p3) {
     console.log("printing =>",p3) ;
}) ("i am js developer ") */

let iifeFn = function (callback, next) {
    return function (value) {
        callback(value, next);
    }
}
let callback = function (value, next) {
    next(value);
}
let next = function (value) {
    console.log("printing =>", value);
}
let returnedFn = iifeFn(callback, next);
returnedFn("i am js developer");
/* Step 1 :- first is a iife function  in this iife function we pass two parameters  one is the reference of a callback function and other is a  reference of next function 
 Step 2 :-  iifethis iffe function is return onther function which is store inside returnFn 
 step 3 :- now returnfn call with the value of ("i am js developer") and its was catch by the function(value)
 step 4 :- inside function(value when we pass ("i am js developer") it is called and this function exicute .This function again call a call bac function with value and next parameters
 step 5 :- call back exicute with value =("i am js developer") and next function reference 
 step 6:- call back function now call  next function with the value and print it */   
Example 2:-
/*;(function(callback,next){
     return function (value){
          callback(value,next);
     } 
}) (function(p1,p2){
     p2(p1);
}, function (p3) {
     console.log("printing =>",p3) ;
}) ("Final Values ") */

var decon = function (callback,next){
    return function (value)
    {
        callback(value,next)
    }
} ;

var first  = function (p1,p2){
             p2(p1) ;
}

var second = function (p3) {
    console.log ("printing =>", p3) ;
}

var third = decon (first, second) 
    
third("Final value") ;








































































