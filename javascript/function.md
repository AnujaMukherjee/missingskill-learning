## Function :->
  * so  in javascript function are behave exactly as object 
  * behavior of javascript :-
     
     - container
     - Hoisted
     - scope (local and Global)
     - object 
     - override 

* Function declearation  can hoisted .
* it act as a container .
* It can override .
* Non  Primitive object  always passed by reference .
* In JavaScript function is first class citizen so  it can assingned itself to a veriable 
* AS function is Nonprimitive (object) so it will always return reference (pass by reference).
*  In javaScript function can return function as well 

## Few example of javaScript ( pass by Value) :-
 Here  we pass the copy of that particular veriable which we wants to pass in fuction as a parameter so inside function if the variable value change it will not effect the entire function . In pass by reference we pass primitive data like string, number 
```JavaScript
Example 1:-
  var sport ="chess" ;
  function PrintSport (sport)
  {
    sport = " Cricket " ;
    console.log ("sport",sport) ;
  }
  printSport (sport);
  console.log("outside sport ", sport);
  /* OUTPUTE :-
    sport Cricket */
Example 2:-
  var sport = "Chess" ;
  var sport2 = " Kabbdi" ;
  function PrintSport(abc)
  {
    abc = "Cricket ";
    console.log ("sport",abc);
  }
  PrintSport (sport);
  PrintSport (sport2);
  console.log ("outside sport", sport);
    console.log ("outside sport", sport2);
  /* OUTPUTE 
   "sport" Cricket ;
   "sport2 Cricket;
  "outside sport" chess
  "outside sport" kabbdi */
  Example 3 :- 
    var sport = "Chess" ;
    var sport2 = " Kabbdi" ;
    function PrintSport(abc) // chess here abc catch " chess" variable copy not direct chess variable 
    {
     console.log ("sport",abc); // printing 
    }
    PrintSport (sport); // sport is a cointer which hold chess value  and this  value pass  to Printsoprt function

    PrintSport (sport2); // sport is a cointer which hold Kabbdi value  and this  value pass  to Printsoprt function
    console.log ("outside sport", sport);
      console.log ("outside sport", sport2);
      /* OUTPUTE :-
       sport , chess 
       sport , kabbdi  
      " outside sport" , chess 
      "outside sport ", kabbdi */
Example 4:-
      var sport = "chess"; // assinged  chess value to sport variable
      var sport2 ="kabbdi"; // assinged  kabbdi value to sport2 variable
      function PrintSport (abc) // abc will catch chess abc = chess
      {
        console.log("sport",abc); // sport , chess | sport , kabbdi
      
      function demand (){
        console.log ("Demand =>",abc); //"Demand" => chess  | "Demand"=> Kabbdi
      }
      demand(); // demand function call 
      }
      PrintSport(sport);//soprt = chess
      PrintSport(sport2); // sport2 = Kabbdi 
      console.log("outside sport",sport); // chess
      console.log("outside sport",sport2); // kabbdi
      /* OUTPUTE :-
      "sport" chess 
      "Demand" => chess
       "sport" Kabbdi 
      "Demand" => Kabbdi 
      "outside sport" chess
        "outside sport" Kabbdi */
  Example 5:-
    var sport = "chess" ; // sport = chess
    var sport2 = "Kabbdi"; // sport2 = kabbdi 
    function PrintSport (sport) // sport = chess
    {
      console.log("sport",abc); // sport , chess 
      function demand (abc) // chess 
      {
        console.log("Demand =>",abc); // "Demand =>" , chess 
        abc = "No Demand"; // now a abc value change to no demand
      demand (abc); // abc = chess ;
      console.log ("value",abc); // chess because it's access the value of PrintSport() function it will not access the function Demand() abc value change to no demand but still  here abc = chess because of functional scope 
    }
    PrintSport(sport) // PrintSport() function call  and pass sport as a parameter where sport = chess
    console.log ("outside sport " , sport);// chess
    console.log ("outside sport " , sport2); // Kabbdi 
    /*
     OUTPUTE 5 :-
     sport chess 
     demand => chess 
     value chess 
     outside sport chess */
  Example 6 :-
    var sport = " chess" ; // var sport is declear and assing with chess
    var sport = 20 ; // now  var has a property var can redeclear and reassinged now var change  chess to 20 
    function PrintSport (sport)
    {
      console.log ("1.sport", sport);  20
          function demand (abc)
          {
            abc = "No Demand " ;
            console.log ("2.Demand =>",abc); // no demand
          }
        demand (sport); // demand function call
        sport =" Football" ;
        console.log ("3.value ", sport);// Football
    }
  PrintSport(sport) // PrintSport function call and pass  copy by value
  console.log ("4.outside sport",sport); //20
  /* OUTPUTE 6:-
   1. sport ,20
   2. Demand => No Demand 
   3. Value Football
   4. Outside sport 20 */
   ```
   ## Few example of javaScript ( pass by reference) :-
 In pass by reference we pass the reference a non primitive data like object we pass the memory address of that object . bascically in  pass by reference we passes object ,function all the non primitive value's memory address so if any value change inside the function it will effect the entire code 
 ~~~ Javascript
Examplw 1:- 
 var mart =
 {
   items:"Grocery",
   checkout: 1,
   open: true 
 } // var mart is  objet which contains ,items , checkout and function 
 var mart2 = mart ; // mart2 = mart means mart2 holds the reference of mart 
 mart2.open = false ; 
 console.log (1,mart);
 function goShoppinh(gmart) // gmart catch the reference of mart2 and gmart also became a object 
 {
   gmart.location="mumbai"; // gmart.location = "mumbai" 
   console.log (2,gmart);
 }
 goShopping(mart2); // np here we pass non primitive (object)   we pass mert2 reference 
 console.log (3,mart2);
/* OUTPUTE 
1. {item : "Grocery", 
    checkout : 1,
    open : false ,
    Location : Mumbai }
2 . Mumbai ;

3 . {item : "Grocery", 
    checkout : 1,
    open : false ,
    Location : Mumbai } */
Example 2:- 
  var mart =
  {
    item :- "Grocerey";
    checkout: 1,
    open : true
  } // var mart is  objet which contains ,items , checkout and function 

  var mart 2 = mart ;
  mart 2.open = false 
  console.log (1, mart);
  function goShopping (gmart) // truthy value inside function 
  {
    gmart = "Mumbai" ;
    console.log (2, gmart) ;
  }
  goShopping (mart2.item) // primitive value   it will pass mart2.item = "Grocerey"
    console.log (3,mart2); 
    /* OUTPUTE
    1. {item : "Grocery", 
      checkout : 1,
      open : false ,
      }
  2. Mumbai 
  3. {
    item :- "Grocerey";
    checkout: 1,
    open : false
    } */
  Example 3:-
    var mart =
    {
      item :- "Grocerey";
      checkout: 1,
        open : true
      cart : [1,2,3,4]
    } // mart is a object which contains item , checkout , open  3 primitives values and cart array non primitive value 
    var mart2 = mart ; // mart 2 holds reference of mart  so if any changes happen in mart2 it will also happen in mart  viseversa also 
    mart2 .open = false ;
    console.log (1,mart) ;
    function goShopping (gmart) // gmart holds the cart reference 
    {
      gmart = "Mumbai" ;
      console.log (2, gmart) ;
    }
    goShopping (mart2.item) // now  in goShopping function its pass only the cart  now cart itself a non primitive value but it will not pass entire  var  reference 
    console.log (3,mart2) ;
    /* OUTPUTE 
  1. {
      item: "Gerocery",
      checkout: 1,
      open: false ,
      cart : [1,2,3,4]
    }
  2. cart : [1,2,3,4,Mumbai] 
  3. {
      item: "Gerocery",
      checkout: 1,
      open: false ,
      cart : [1,2,3,4,Mumbai]
    } */
 ~~~ 

