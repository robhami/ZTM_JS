## Advanced Arrays ##

Can do For Loop & ForEach Loops over arrays.  See below for For Each loop, 
```javascript
const array =[1,2,10,16];

const newArray =array.forEach((num) => {

	(num*2);

})

<undefined
>console.log(newArray);
<undefined

```
Need to push to new array to return something: 

```javascript
const double =[];

const newArray =array.forEach((num) => {

	double.push(num*2);

})

console.log("forEach: ", double);
```

### Map ###

Can loop and it will automatically push to a new copy array with same name. With map you will always have a returned element. 
For Each can iterate and will not return unless told to. 
```javascript
const mapArray = array.map((num) => {
	console.log (num*2);
	return num*2;
});

<2
4
20
32


>console.log(mapArray);
<[2, 4, 20, 32]

```
This is a pure function as it has to return an element. Also data is not mutated to another array name. 

Can also shorten if you only have single parameter with an arrow function (remove "{", "return" and "brackets"):

```javascript
const mapArray = array.map(num =>num*2);

console.log ("mapArray: ",mapArray);

```

### Filter ###

Filter array with condition. This again returns new array with same name

```javascript
const filterArray = array.filter(num => num>5);

console.log ("Filter: ", filterArray);

<Filter:  (2) [10, 16]
```


### Reduce ###

Accumulator is somewhere we can store what happens in body of function. 
Accumulator is defined as parameter after function. 
Reduce loops through adding each number to the accumulator:  
```javascript
const reduceArray = array.reduce ((accumulator, num) => {

	return accumulator + num;

	},1)

console.log(reduceArray);

<29

```
