## Array :-
 An Array is a element which can store multiple elements.
 In JavaScript, array is a single variable that is used to store different elements
  ``` JavaScript 
 Example 1 :-
         var data = ["name",true,null,[1,test],{name:"objvalue}, function(){
             console.log("Print"0)
         }]
        var Loopup = data[5];
         Loopup() ;
// outpute :- Prints 

Example 2 :-
        var dat = [
            "name",
            true,
            null,
            [1,"test"],
            {
                name: "objvalue", list[2,3,4,5]
            }
            function () {
                console.log("print")
            }
        ] ;
    var value = data[4]. list;
    console.log(value)
// outpute:-
//{list:[2,3,4,5]}

Example 2 :-
        var dat = [
            "name",
            true,
            null,
            [1,"test"],
            {
                name: "objvalue", list[2,3,4,5]
            }
            function () {
                console.log("print")
            }
        ] ;
    var value = data[4].["list"] [3] ;
    console.log(value) ;
// outpute :- {list: [5]}

Example 3 :-
        var dat = [
            "name",
            true,
            null,
            [1,"test",{user:"links"}],
            {
                name: "objvalue", list[2,3,4,5]
            }
            function () {
                console.log("print"+params)
            }
        ] ;
    var value = data[5] ("same value");
    value() ;
// outpute :- Prints some value 