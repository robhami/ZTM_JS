

FUNCTIONS
are blocks of code that perform actions
in built functions exist (e.g. alert(), prompt())

Function name followed by brackets executes (or calls) a function:

e.g. prompt()

alert("hi there!");

Text inside brackets is called arguments, can have multiple arguments

e.g. console.log("Hi There!", How are you")

FUNCTION DECLARATION

function sayHello() {
  console.log("Hello");
}

sayHello();

FUNCTION EXPRESSION

var sayBye = function () {

  console.log("Bye");
}

sayBye();

function sing(){
  console.log("AHHHHHHHH");
  console.log("TEEEEEEEE");
  }
  
 sing();
 
 If i want to change song, i have to edit the function or create new song: 
 
 function sing2() {
  console.log("LAAAAAAAAAAAAAA");
  console.log("DEEEEEEEEEE")
  }
 
 Can add arguments to get around this: 
 
 function sing(song){
  console.log(song);
 }
 
 sing("Laaa dee daaa");
 
 This puts argument into function.
 
 function multiply (a,b) {
  return(a*b);
 }
 
 multiply(5,10)
 
 Must use return when using functions. Otherwise result is undefined. Console.log can be used but it is not a proper return. 
 
 Once you return it ends function. So can't do multiple returns unless you use a IF ELSE statement, e.g. 
 
  function multiply (a,b) {
    if (a>10 || b>10) {
    return "that's too hard";
    } else {
       return a*b;
    }
  }
    
 multiply(5,5)
 
 In JS functions are variables, we are able to assign functions like this:
 
 var a = function multiply (a,b) {
    if (a>10 || b>10) {
    return "that's too hard";
    } else {
       return a*b;
    }
  }
    
  Can call like this: 
  
  a();
  
  Can also do nested functions: 
  
  alert(multiply(3,4));
  
  parameters- are a and b in case above
  arguments- are 3,4 in case above
 
 
