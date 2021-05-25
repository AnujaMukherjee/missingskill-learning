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








































































