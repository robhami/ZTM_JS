# ZeroToMastery

##Debugging


```
const flattened =[[0, 1], [2, 3], [4, 5]].reduce( 
  (a, b) => a.concat(b), []);
  
  ```
Code above assigning a nested array to a variable. Reduce - Subtract the numbers in the array, starting from the beginning. 
a is the accumulator (initial value), b is value of current element (the nested arrays)

```
const flattened =[[0, 1], [2, 3], [4, 5]].reduce( 
  (accumulator, array) => 
  console.log('array', array);
  console.log('accumulator', accumulator)
  return accumulator.concat(array), []);
  
  ```
  
  concat joins to or more arrays, values are arrays to join. Add console.logs in to see what accumulator and array is. Also need
  to add return as it won't auto return from => now console.logs added.
  
  This returns: 

```
  array (2) [0, 1]
  VM217:4 accumulator []
  VM217:3 array (2) [2, 3]
  VM217:4 accumulator (2) [0, 1]
  VM217:3 array (2) [4, 5]
  VM217:4 accumulator (4) [0, 1, 2, 3]
 ``` 
 
 This is just adding each nested array to the empty array. i.e. we are unnesting it or flattening it. 
 
 can also use debug instead of console.log.
 
 ```
 const flattened =[[0, 1], [2, 3], [4, 5]].reduce(

  (a, b) => {
    debugger;
  a.concat(b)
  }
  , []);
  
  
 This pauses it at the debugger but shows accumulator and array: 
 
  const flattened =[[0, 1], [2, 3], [4, 5]].reduce(

  (a, b) => { a=[], b= (2) [0,1]
    debugger;
  a.concat(b)
  }
  , []);
  
  can use step over to go to next line. Also shows variables in scope on right and context (i.e. this value).
  
  
  
  
 
 
