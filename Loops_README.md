# ZeroToMastery

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

Counting Up
```
var counterOne=0;

while(counterOne<10) {

	console.log(counterOne);
	counterOne++
}
```

Counting Down

```
var counterOne=10;

while(counterOne>0) {

	console.log(counterOne);
	counterOne--
}

var counterTwo = 10
```

#### DO WHILE LOOP ####

```
do {
	console.log(counterTwo);
	counterTwo--;
} while (counterTwo>0);

```




```
var todos = [

	"clean room",
	"brush teeth",
	"exercise",
	"study JavaScript",
	"eat healthy"

];

var todosLength=todos.length;

for (var i=0; i<todosLength; i++) {

	console.log (todos[i],i);

}

todos.forEach(function(todo,i){
	console.log(todo,i);


})
	
