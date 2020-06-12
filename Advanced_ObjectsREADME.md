# Advanced Objects 

### Reference types ###

In console (note arrays are objects): 

```
> [] === []
< false

> [1] === [1]
< false
```


```
var object1={value:10};
var object2=object1;
var object3={value:10};
```
In console:

```

>object 1 === object 2
<true

>object 1 === object 3
< false
```
This is because object is a unique reference (i.e. reference type). This is because you create new object 3 in "new box" and that box is different to object 1. The value is the same but not the reference.

Until now all types e.g. 1, true, null, boolean, are all defined by programming language (i.e. JS). These are primitive types (i.e. langauge tells what they are)

Whereas a reference type, is a non primitive type not defined by programming language but created by programmer. Programmer creates new object that is like an address that is unique. 
 
### Context ###
gets confused with scope. 

Its where we are inside object. 

```
>console.log(this);
<window
```
"this" means what is the object we are in now

If you create: 

```
function a() {
	console.log(this);
}
```
In console:

```
>a()
<window
```
function a is still in window.
However:

```
const object4={
	a: function () {
		console.log(this);
	}

}

```
In console: 

```
>object 4a
<{a:f}

```
This returns object4 as "this". 

Context is important with instantiation- where you make a copy of an object and reuse the code. 

### Instantiation ###

#### Class ####
A class is something I want to make a copy of name of class (e.g. Player) needs to have capital letter at start. 

#### Constructor ####
Every time you make a copy of the class. The first thing that gets run is the constructor function. This will create the listed properties (e.g. name and type) on the "Player" object.

#### Method ####
Create a method such as 'introduce()' that console.logs a template string (using backticks as per standard template) that uses name and type from constructor. 


```
class Player {
	constructor (name,type) {
		console.log('player', this);
		this.name = name;
		this.type = type;
	}
	introduce(){
		console.log(`Hi I am ${this.name}, I'm a ${this.type}`);
	}
}
```
To copy a class (i.e. player) use extends, because class have to do  a constructor. 

When we extend we need call constructor function from other class (e.g. player). 

This is done using 'super' plus properties we want to pass. Then can add function within to use this (i.e. play()).  

```
class Wizard extends Player {
	constructor(name,type) {
		
		super(name,type)
		console.log('wizard', this);
		
	}
	play() {
		console.log(`WEEE I'm a ${this.type}`);
	}
}
```
Use 'new' keyword to create new variable with parameters in brackets. 

This will then get it to go to Wizard class.

Then constructor in Wizard class. It then goes to constructor in Wizard class and see 'super'. This takes us to constructor of player and runs it and attaches it to the WIZARD then runs introduce function. 

If go to wizard1 and say play I get "WEEE I'm a Healer", because Shelley is a healer.

```
const wizard1 = new Wizard ('Shelly', 'Healer');
const wizard2 = new Wizard ('Shawn', 'Dark Magic');
```
Console.logs show that Wizard is created and player is created: 

```

player 
Wizard
name: "Shelly"
type: "Healer"
__proto__: Player
constructor: class Wizard
play: ƒ play()
__proto__: Object

wizard 
Wizard
name: "Shelly"
type: "Healer"
__proto__: Player
constructor: class Wizard
play: ƒ play()
__proto__: Object

player 
Wizard
name: "Shawn"
type: "Dark Magic"
__proto__: Player
constructor: class Wizard
play: ƒ play()
__proto__: Object

wizard 
Wizard
name: "Shawn"
type: "Dark Magic"
__proto__: Player
constructor: class Wizard
play: ƒ play()
__proto__: Object

```

To run functions: 

```
wizard1.play()
script.js:33 WEEE I'm a Healer
undefined
wizard2.play()
script.js:33 WEEE I'm a Dark Magic
undefined
wizard1.introduce()
script.js:20 Hi I am Shelly, I'm a Healer
undefined
wizard2.introduce()
script.js:20 Hi I am Shawn, I'm a Dark Magic
undefined
```
