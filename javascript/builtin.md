## BUILT IN  OBJECT :-
 in javaScript there are 6 built in objects :-

- String 
- Array
- Date
- Object
- Math
- Number 

## String Constructor :-

The String constructor is used to create a new String object. When called instead as a function, it performs type conversion to a primitive string, which is usually more useful.

- Length :- number of characters in a string .
- trim(fn):- remove trailing spaces .
- split (fn) :- split the string using delimiter, returns new array 
- replace (fn):- replace all the value used as delimeter .
- toUpperCase (fn):-converts all string into uppercase.
- toLowerCase (fn):- convert all string into lowercase.
## string Length:->
The length property of a String object contains the length of the string, in UTF-16 code units. length is a read-only data property of string instances.

 ## Example :-
 ~~~JavaScript
 const str = 'my name is anuja. i love, coding and traveling:';

console.log(`${str} ${str.length}`);
// expected output: 'my name is anuja. i love, coding and traveling:' 44"
~~~~

## String.trim():->
The trim() method removes whitespace from both ends of a string.  but not the middile sapce .

```JavaScript 

const greeting = '   Hello world!   ';

console.log(greeting);
// output: "   Hello world!   ";

console.log(greeting.trim());
//  output: "Hello world!";
```
## String.Split() :-> 
Split() methods divides the string into a order of substring and returns it into a new array
``` JavaScript
const str = 'The quick brown fox jumps /over /the /lazy/ dog.';
const abc = str.split('/')
console.log(abc)
// outpute:- 
abc = ["The quick brown fox jumps ", "over ", "the ", "lazy", " dog."] 
```

## String.toLowerCase():->
The toLowerCase() method returns the calling string value converted to lower case.

```Javascript
const sentence = 'The quick Brown fox Jumps over the Lazy dog.';

console.log(sentence.toLowerCase());
// outpute: "the quick brown fox jumps over the lazy dog."
```
## String.toUpperCase():->
The toUpperCase() method returns the calling string value converted to uppercase (the value will be converted to a string if it isn't one).

```JavaScript
const sentence = 'my name is anuja mukherjee';

console.log(sentence.toUpperCase());
// output: "MY NAME IS ANUJA MUKHERJEE".
```

## String.replace():->
The string.replace()  function replace the substring with other string which we pass in function and also he replace first substring .
```Javascript
const p = "My name is Anuja . and Anuja love traveling ;

console.log(p.replace('Anuja', 'Mona '));
//  output: "My name is Mona . and Anuja love traveling"
```


## Array Constructor :-
- length : last index + 1 ;
- push : adds value at the end of an array .
- pop : removes value at the end of an array .
- unshift : adds value at the begining of an array .
- shift : removes value from begining of an array 
- concat : joins two or more array .
- join : converts array into string using delimeter, default to ','
- forEach : iterates through all the item of an array 
- map : iterates through all the items of an array and returns the new array with same length .
- filter: iterates through all the items of  an array and based on condition returns the same length .
- indexOf: finds the index number of a value if not present then it returns -1 
- includes : checks for existance of the item , return boolen .
- isArray : static method check whether value is an array . 


## Filtter Function :-
```JavaScript
Example 1:-
const arr2 = [undefined,{},"true",true,{key:"key"},null,0,'',[],'false']
const filterData = arr2.filter(function(item){
    return (item && typeof item === 'object' && !Array.isArray(item))
})
console.log(filterData);


Example 2 :- 
    const array1 = [1,4,9,16];
    const filteredArray = array1.filter(function(item)
    {return(item>5)}) 
    console.log(filteredArray);

/*outpute:-
filteredArray[9,16]
*/

Example 3 :-

function filter(arr,cb){
  		  let result = [];
          const length = arr.length ;
          for(var i=0; i< length; i++){
              const item = arr[i] ;
              const returnedValue = cb(item);
              if(returnedValue){
                  result.push(item)
              }
          }
          return result;
     }
   
const arr = [1,2,3,4,5,6,7,8,9];
let result = filter(arr, function(eachElementOfArray){
  return (eachElementOfArray>5)
});
console.log(result);
/*outpute:-
[6,7,8,9]
```
## MAP():-
```javaScript
Example 1:-
 function map (arr,cb){
     const length = arr.length

 for(var i=0;i<length; i++){
     console.log(item)
 })

Example 2:-
        function map (arr,cb){
    let result = [];
    const length = arr.length;
    for(var i=0; i<length; i++){
      let returnValue = cb(arr[i],i); 
      result.push(returnValue);
    }
  return result;
}
const result = map([1,2,3],function (item,index){
    return (item+index);
});
console.log(result)
/* outpute:-
result [1,3,5] */
Example 3 :- 
        const array1 =[1,4,9,16];
        const arr2 = array1.map(function(item){
            return(item+1);
        });
    console.log(arr2);
/* outpute:-
    arr2 [2,5,10,32] */
```
## forEach() :-
``` javascript 
Example 1:-
function forEach(arr,cb){
    const length = arr.length ;
    const localArr = [];
    for(var i=0 ; i< length; i++){
        const item = arr[i];
        cb(item,i);
    }
}
forEach([1,'',0,true,null,2,{}],function(item,index){
    console.log('cos',item,index)
});
/* outpute :-
 cos 0 2
 cos true 3
 cos null 4
 cos 2 5 
 cos {} 6 */
```
## indexOf() :-
```JavaScript
Example 1:-
function indexOf(arr, value){
     const length = arr.length ;
     for(var i=0 ; i< length; i++){
         const item = arr[i] ;
         if(item === value){
             console.log('Found it',i);
         }
     }
     return -1
}
const found = indexOf([1,4,5,''],'') ;
console.log(found);
/*outpute:-
 found it 3
 */
Example 2 :-
        const array1 =[1,4,9,16];
        const position = array1.indexOf(16);
        console.log(position);
/*outpute:-
  3 */
 ```
## includes():-
```JavaScript
Example 1:-
function includes (arr,value){
     let foundIndex = false ;
     for (var i=0; i< length ; i++){
          const item = arr[i];
          if(item === value){
              foundIndex = true ;
              break ;
          }
     }
     return foundIndex;
}
const final = includes ([1,4,5,'','',23],"4");
console.log(final)
// outpute:- true 
Example 2:-
        const array1 =[1,4,9,17];
        const yesORno = array1.includes(16);
        console.log(yesORno) ;
// outpute:- false 
```
## Push() :-
```JavaScript
Example 1:-
 function push(arr, value){
     const length = arr.length;
     arr[length]= value ;
     return arr;
 }
 let arr =[1,4,5,'','',23];
 arr = push(arr,"hello");
 console.log(arr);
 /* outpute:-
  [1,4,5,'','',23,'hello']
  */
Example 2 :-
        const array1 = [1,4,9,17];
        array1.push(100);
        console.log(array1)
/* array1[1,4,9,17,100] */
```
## isArray():-
``` JavaScript 
 const array1 =[1,4,9,16];
 const name ="Anuja" ;
 const YESorNO = Array.isArray(name);
 console.log(YESorNO);

 ```
 ## Join :-
 ``` JavaScript 
  const array1 = [1,4,9,16];
  const joinedString =array1.join("-");
  console,log(joinedstring);
/* outpute :-
 1-4-9-16 */
 ```
## Slice():- 
slice basicaly used to divide the array 

```JavaScript
const Person = ['Anuja','Rima','Titire','Raj','Sid','Ankur','Ranjini','Anindita']
console.log (animals.silce(2));
// outpute:- 
/*['Titire','Raj','Sid','Ankur','Ranjini','Anindita']
here we are breaking the array from the second position or second index  */

console.log (animals.silce(2,4));
// outpute :- ['Titire','Raj']
/* here we are breaking the array from  second position to (n-1) position  means 2nd position to (4-1 = 3).*/

console.log (animals.silce(1,5));
// outpute :- ['Anuja','Rima','Titire','Raj','Sid']
 /*  here we are breaking the array from  second position to (n-1) position  means 1nd position to (5-1 = 4).
 ```
 ## Splice () :-
 The Splice() Method changes the contents of any array by removing or replacing the content of an array . 
 ``` JavaScript 
 const months = [1,2,3,4,5,6,7,8,9,10]
const newMonths =months.splice(2 ,4 , 'anuja','rima','sid');
console.log(newMonths)
console.log(months) 
// outpute :- newMonths=[3,4,5,6]
//Months=[1,2,'anuja','rima','sid,7,8,9,10]
```
## unshift() :-
 adding element begining of a array . 
 ``` JavaScript 
 var name = ['eiusmod','culpa','ullamoo','dolor','pariature','irure','ex']
 names.unshift ('nate') ;
 names.unshift ('ajsy') ;
 console.log (names);
 // outpute :- ['ajay','nate','eiusomd','culpa','ullamco','dolor','Pariature','irure','ex']
```
##  shift () :-
Remove element of the array .
 ``` JavaScript 
  var name = ['eiusmod','culpa','ullamoo','dolor','pariature','irure','ex']
 names.shift ('eiusmod') ;
 names.shift ('culpa') ;
 console.log (names);
 // outpute :- ['ullamco','dolor','Pariature','irure','ex']
 ```