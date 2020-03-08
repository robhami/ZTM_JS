# ZeroToMastery

### Inline script ###

Initially used in inline scripts: 

e.g. 

```
<script type ="text/javascript">
  function a() {
    alert('a')
  }
  
   function b() {
    alert('b')
  }
  
   function c() {
    alert('c')
  }
  </script>
  ```
  
  Issues: 
  
  1. Lack of code reusability- have to retype each time 
  2. Pollution of Global Namespace- e.g. once I use 'a' as a variable in window object, can never use it again
  
  ### Script tags ref separate files ###
  
  Issues:
  1. Every page needs tags at top
  2. Lack of dependency resolution- u r responsible to make sure script added in correct order 
  (e.g. if later entered tag has function called in earlier tag it wont work)
  3. Pollutes Global Namespace still- as all in window object still
  
  
  ### Immediately Invoked Function Execution (IIFE) ###
  

  JS File #1
   
 ```
  var myApp = {}
 
 ```
  
 JS File #2
  
 ```
  
  (function(){
    myApp.add = function(a,b) {
      return a + b;
    }
  })();
  
  ```
  
  () after calls it. This keeps any created variables inside function not in window object, so don't pollute Global Namespace.
  Order of files still an issue. 
  
  ### Browserify ###
  
  JS file #1
  
  
  ```
  module.exports = function add(a,b){
    return a+b;
  }
  
  ```
  
  JS file #2 (assuming
  
  ```
  var add = require ("./add");
  ```
  
  
  
