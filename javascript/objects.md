## OBJECT :-
 Object is a non-primitive data type in JavaScript. It is like any other variable, the only difference is that an object holds multiple values.oject can hold primitive , non-primitive, method() . 
 ``` JavaScript
 cost user ={
     "id" : "5f6a22c5a6015ee205fd8fd9",
     "index" :4 ,
     "isActive": false,
     "balance",$1,134,72",
     "picture": "http://placehold.it/ 32*32",
     "age":23,
     "tags":["aim","game","gem","len"] ,
     "friends": [{"id":0,"name":"Fletcher Battle"},]
                  {"id":1,"name":"Theresa Kline"},
                  {"id":2,"name":"Patel Health"},],
 }

1) // printing all the tages
 console.log(user.tags) 
// outputes:-["aim","game","gem","len"]


2)// printing isActive 
 console.log (isActive)
// outpute:-false 

3) //printing   3rd element of tags array inside user object 
 console.log (user.tags[3])
 // outpute:-len 

4) // printing friends 
console.log ("friends") ;
// outpute:- {"id":0,"name":"Fletcher Battle"},]
                //  {"id":1,"name":"Theresa Kline"},
                // {"id":2,"name":"Patel Health"}

5) //printing primitive object :-
var keys = object.keys(user) ;
var new_user ={}
keys.forEach (function(key))
{
    var value = user[key];
}
if(typeof value!=="object")
{
    new_user[key] = value ;
}
})
console.log(new_user);

// outpute :-
/*[id:- 5f6a22c5a6015ee205fd8fd9,
index:- 4,
isActive: false,
balance: '$1,134,72 ,
picture: "http:// placehold.it/32*32 
age : 23
] */
```
## method () :-
 JavaScrpit method() is an object property that has function value . 
 ``` JavaScript 
 // accessing method and property
 Example 1:-
const person = {
    name: 'Anuja',
    greet: function() { 
        console.log('hello'); }
};

// accessing property
person.name; // Anuja

// accessing method
person.greet(); // hello

Example 2:-
let user ={
    user ={
     "id" : "5f6a22c5a6015ee205fd8fd9",
     "index" :4 ,
     "isActive": false,
     "balance",$1,134,72",
     "picture": "http://placehold.it/ 32*32",
     "age":23,
     "tags":["aim","game","gem","len"] ,
     "friends": [{"id":0,"name":"Fletcher Battle"},]
                  {"id":1,"name":"Theresa Kline"},
                  {"id":2,"name":"Patel Health"},],
    "getIndex" : function() {
          return this.Index ;
    }
    "getIndex": function(){
         return this.tags ;
    }
    "getPrimitive": function(){
         return this.primitive ;
    }
    
 }
console.log(user.getIndex())
// accessing method()
 // outpute:- 4
 ```
 ## This :-
 To access a property of an object in a method of the same object, you need to use the this keyword. If we want to access property  within the object then we use "this" keyword.
 ```JavaScript
 const person = {
    name: 'Anuja',
    age: 23,
    fullname: function() { 
        return this.name + " Mukherjee"
    }
};

console.log(person.fullname());
// outpute :- Anuja Mukherjee 
```