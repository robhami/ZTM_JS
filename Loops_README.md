# ZeroToMastery- Loops

Loops are handy, if you want to run the same code over and over again, each time with a different value.

Often this is the case when working with arrays:

```
var todos = [
"clean room",
"brush teeth",
"exercise",
"study Javascript",
"eat healthy"
];

```

#### FOR LOOP ####

Loops through a block of code a number of times.

```
for (var i=0; i<todos.length; i++) {

//add ! to array

	todos[i]=todos[i]+"!";
  
//add ! to console log output

	console.log (todos[i]+"!");
}

```
Remove last item of array with pop
```
var todosLength=todos.length;

for (var i=0; i<todosLength; i++) {

	todos.pop();
	
}

console.log (todos);
```

#### WHILE LOOP ####
Loops through a block of code while a specified condition is true.
Need to increase or decrease variable used in the condition otherwisw loop never ends and it crashes. 

##### Counting Up #####
```
var counterOne=0;

while(counterOne<10) {

	console.log(counterOne);
	counterOne++
}
```

##### Counting Down #####

```
var counterOne=10;

while(counterOne>0) {

	console.log(counterOne);
	counterOne--
}

var counterTwo = 10
```

#### DO WHILE LOOP ####
also loops through a block of code while a specified condition is true
However it exceutes code block once before checking if condition is true. So will always execute once even if condition is false. 

```
do {
	console.log(counterTwo);
	counterTwo--;
} while (counterTwo>0);

```

#### FOREACH LOOP ####
Added (ES5)
Lists each item in array and does function on them.

*array.forEach(function(currentValue, index, arr), this Value)*

* function	Required. A function to be run for each element
* currentValue	Required. The value of the current element
* index		Optional. The array index of the current element
* arr		Optional. The array object the current element belongs to
* thisValue	Optional. A value to be passed to the function to be used as its "this" value.If this parameter is empty, the value 			"undefined" will be passed as its "this" value

```
for (var i=0; i<todosLength; i++) {

	console.log (todos[i],i);

}

todos.forEach(function(todo,i){
	console.log(todo,i);

})
	
```
