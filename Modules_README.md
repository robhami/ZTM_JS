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
  
  Used Common JS with certain syntax
  
 ##### JS file #1 ####
  
  
  ```
  module.exports = function add(a,b){
    return a+b;
  }
  
  ```
 
  
  
  ##### JS file #2 (assuming the JS file #1 is called add.js) ####
  
  ```
  var add = require ("./add");
  ```
  
   can now call add function in JS file #2, if use this common syntax which is actually a MODULE BUNDLER- run before you put website online. Reads thru all JS files, syntax and bundles everything into single file. e.g. 
   
 ```  
   <script src="bundle.js" type='Text/javascript">
   
 ```
  
### E6 Webpack ###

##### JS file #1 #####

```
export const add = (a, b) => a + b;
```
or
```
export default function add() {
  return a +b; 
}
```

##### JS file #2 #####

```
import {add} from './add';
```
or
```
import add from './add';
```

{add} is destructuring from ES5/6  lesson

export default can only export one function, export can do multiple, so with default don't need the {add} brackets. 

Traverses dependancy tree when bundling JS files

With WebPAck can use ES6 in all browsers. Configure this file:

```
module.exports = {
  entry: './app/main.js',
  output: {
    path: './dist',
    filename: 'bundle.js'
    }
  }
  ```
  More stuff on modules: 
  https://hacks.mozilla.org/2018/03/es-modules-a-cartoon-deep-dive/
