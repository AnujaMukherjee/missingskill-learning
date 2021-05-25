## scop
### scope are three thyps functional scope , lexical scope , Global scope 
### visual representation of call stack :- 

### Functional scope
 in function scope variable will assess thee variable which is declear insidethe function and if any change if any particular function block variable is not declear then it will access variable from his nearest parent funtion 

```Javascript
Example 1:-
        var a = 10;// variable declear and assinged 
        var a = 5; // again variable redeclear and reassinged 
        const b = "ok"; 
        console.log(1,a+b); // 5ok (we consider a variable letest value )
        a=20; // a variable is reassinged
        function hello()
        {
            var a="7";
            console.log (2.2,a+a); 77
            a=3;
        }
        function hello2()
        {
            a=a+a;
            console.log(2.1,a); // as there is no local variable is declear inside this functional scope so it will assess nearest parent functional scope whichi is global now as a=20 so output is 40
        }
        hello2()
        hello();
        console.log (3,a); //40
        a=10;
        console.log (4,a)// 10

Example 2:-
    var a=5;
    var b ="6";
    console.log (1,a+(+b))// (1,11)
    a=20;
    function. hello()
    {
        var a = "7"
        console.log (2, a+(+a));(2,17)
        a=3;
    }
function hello2()
{
    var a = a+a;// declear but not intializes with value
    console.log (2.1,a); (2.1, undefined)
    var c;// declear but not initialized
}
    function hello_inside()
    {
        a=5;// it will assess nearest parent function which is hello2 and update it with 5
        console.log("inside",a)(inside ,5)
        c=9;// here c is intialized with 9 and this c variable again asscess c from his parent function which is hello 2 and update the value from undefined to 9
    }
console.log("outside",c);//(outside , undefined)
hello_inside();
console.log("outside",c);// (outside ,9)
}
hello 2();
hello ();
console.log (3,a);//(3,20)
a=10;
console.log(4,a);//(4,10)

Example 3:-
    var a =5;
    var b="6";
    console .log (1, a+(+b));//(1,11)
    function hello()
    {
        var a ="7";
        console.log (2,(+a)+(+a));
        a=3;
    }
    function hello 2(){
        var a= a+a ;
        console.log (2.1,a);//(2.1 , undefined)
        var c=11;
            function hello_inside()
            {
                a=5;
                console.log("inside",a);(inside ,5)
                c=9+b;
            }
        console.log ("outside",c) ; // (outside undefined)
        hello_inside();
        console.log("outside 2",c) // (outside 2 , 96)
    }
    hello 2();
    hello ();
    console.log (3,a); //(3,5)
```
## Lexical  Scope :- 
<p> In lexical scope  variable life span will be inside the block </p>
<p>anything inside a {} called lexical scope </p>

```Javascript
Example 1:-
    let a=4;
    var b ;
    if (a) { // block or lexical scope  truthy value
        b=9;
    let a =9; // let value declear ans assinged
    console.log(a+b); // 18
    b=(a+b); // b=18
    }
function hello ()
{
    let b=5 ;
    if(a){// as a= 4 truthy value candition statisfied go inside if block 
        console.log(a+b); //5+4 =9  as a is not declear inside hello function so it will access glabal a 
        b=20;
    }
    else
    {
        let b;
    }
    console.log(b); //20
}
hello ()

Example 2 .
    let a = 4; // variable declearation 
    var b ; // var declearation but not assinged  so b = undefined 
    if (a) // truthy value so it's condition statisfy enter into block 
    {
        b=9 ; // as b is not assinged  inside the block so its access nearest parent scope which is global "b". Now we change the value undefined to 9 b=9 
        let a=9; // this time we have "a" which is declear inside the  block scop 
        console.log (a+b) // 9+9 = 18 
        b =(a+b); //b =18 
    }
    function hello ()
    {
        let b =5 ;
        if (a){ // truthy value
            let b =5;// now b=5 this "b" is inside the block 
            if (a) // truthy value 
            {
                console.log (a+b) ; // access global "a" as "a" is not declear  inside the function scope and block scope "b" is  declear inside block scope  now 4+5 = 9 
                let b = 20 ;
            
            else {
                let b ;
            }
        console.log (b);  //  20
        }
    hello ()
/* OUTPUTE 2:-
18
9 
20 */
Example 3 .
    Let a = 4 ; // we declear  "a" function a=4 ; with let variable let , "let" can't hoisted 
    var b ; // undefined 
    if (a){// truthy value 
        b=9; // we access  global "b" . b = undefined  and b value change to  9 now 
        let a = 9 ; // a is also 9 inside block scope
        console.log (a+b); // 18
    }
    function hello (){
        let b = 5 ; // b=5 "b" has functional scope
        if (a){ // truthy 
            let b =5 ; // b has block scope
            console.log (a+b); // 9
        }
        else
        {
            let b ;
        }
        console.log (b) // 5 
    }
    hello ();
    /* OUTPUTE 4:- 
     18 
     9
     5*/
Example 4 .
    let a = 4 ;
    var b ;
    if (a)
    {
        b =9 ;
        let a =9 ;
        console.log (a+b); // 9+9 = 18
        b=a+b; // b = 18 
    }
    function hello ()
    {
        if (a)
        {
            b = 20 ; // "b" , b has global access it access his nearest parent which is global "b"  glabal "b" is undefined now it's change to 20 
            console.log (a+b); // 20 + it access global a also // 20 +4 = 24
        }
        else {
            let b;
        }
        var  b = 5 
        console .log (b) // 5
    }
    hello ()
    /* OUTPUTE 5:-
    18
    24
    5*/

Example 5.
    let a = 4 ;
    var b ;
    if (a)
    {
        b =9 ;
        let a =9 ;
        console.log (a+b); //18
        b = a+b;
    }
    function hello (){
        if (a)
        {
            b = 20 ;
            console.log (a+b); // 24
        }
        else {
            let b;
        }
        var b  = 5 ;
        console .log (b) // 5
    }
    hello()
    console.log (b); //20

Example 6:-
let a = 4 ;
 const b =40 ;
if (a)
{
    let b  = 9 ;
    let a  = 9 ;
    console.log (a+b)  // 18
    b =a+b ;
}
function hello ()
{
    if (a)
    {
        b = 20 ;
        console.log (a+b); // 24
    }
    else {
        let b;
    }
    var b =5 ;
    console.log (b); // 5
}
hello ();
console.log (b) //40
```
## Global scope :-
A variable declared outside a function, becomes GLOBAL.

A global variable has global scope: All scripts and functions on a web page can access it. 
 ``` javascript
 Example 1:-

    var userName = "Bill";

        function modifyUserName() {
                userName = "Steve";
            };

        function showUserName() {
                alert(userName);
            };

        alert(userName); // display Bill
        
        modifyUserName();
        showUserName();// display Steve
```






