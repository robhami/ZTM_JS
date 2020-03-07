### Advanced Loops

### Previously learnt loops

```
const basket =['apples,'oranges','grapes'];

  for (let i=0; basket.length; i++){
    console.log(basket[i];
  }

  basket.forEach(item=> {

    console.log(item);

  }
```

Also Do and While. 

### FOR OF LOOP
this is iterating- can do over arrays, strings, (i.e. they are iterable)

create variable (item- below) and loop through

```
  for (item of basket){
    console.log(item);
   }
 ```
 
This returns:
  apples
  oranges
  grapes

 
 # FOR IN LOOP
 allows you to see properties of objects
 with objects you are not iterating you are enumerating (object is enumerable if it allows you to see the properties). 

 ```
   const detailedBasket = {
     apples: 5,
     oranges: 10,
     grapes: 1000, 
   }
 
   for (item in detailedBasket) {
    console.log(item)
   }
```

This returns:
  apples
  oranges
  grapes
  <undefined
 
 Cannot use FOR OF LOOP with objects. However can do FOR IN LOOP with arrays & strings
 ```
   for (item in basket) {
    console.log(item)
   }
 ```
 This returns: 
  0
  1
  2
  
  Because arrays are like an object with the following properties:
 ``` 
    basket = {
      0: 'apples',
      1: 'oranges',
      2: 'grapes'
    }
  ```
  
  Can also use the following on objects:
  ```
  Object.keys
  Object.entries
  
  ```
  
