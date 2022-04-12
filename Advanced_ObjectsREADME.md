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



### Methods (from W3 schools) ###

JavaScript methods are actions that can be performed on objects.

A JavaScript method is a property containing a function definition.

```

var person = {
  firstName: "John",
  lastName : "Doe",
  id     : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};

```

Methods are functions stored as object properties.

#### Accessing Object Methods ####
You access an object method with the following syntax:
```
objectName.methodName()
```
You will typically describe fullName() as a method of the person object, and fullName as a property.

The fullName property will execute (as a function) when it is invoked with ().

This example accesses the fullName() method of a person object:

Example
```
name = person.fullName();
```
If you access the fullName property, without (), it will return the function definition:

Example
```
name = person.fullName;
```

#### Using Built-In Methods

This example uses the toUpperCase() method of the String object, to convert a text to uppercase:

```
var message = "Hello world!";
var x = message.toUpperCase();
```

The value of x, after execution of the code above will be:

HELLO WORLD!

#### Adding a Method to an Object ####

Adding a new method to an object is easy:

Example
```
person.name = function () {
  return this.firstName + " " + this.lastName;
};
```

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

### Classes from NetNinja utube ###

If we want to create multiple versions (instances) of an object. Create a class then have a constructor function to create the new objects. Classes start with a capital letter. Can also have other functions that use values from the constructor.

```
class User {
	constructor (email, name){
		this.email=email
		this.name=name
	}
	login(){
		console.log(this.email, 'just logged in')
	}
	logout(){
		console.log(this.email, 'just logged out')
	}
}

```

new keyword:
-creates a new empty object
-sets the value of 'this to be the new empty object
- calls the constructor method
```
var userOne = new User('ryu@ninjas.com', 'Ryu')
var userTwo = new User('yoshi@marioKorp.com', 'Yoshi')
```
Can also run the functions like so using the new instances:
```
console.log(userOne)
VM144:1 User {email: 'ryu@ninjas.com', name: 'Ryu'}
undefined
console.log(userTwo)
VM186:1 User {email: 'yoshi@marioKorp.com', name: 'Yoshi'}
undefined
```





### Prototype (from W3 schools) ###
Using the prototype Property
The JavaScript prototype property allows you to add new properties to object constructors:

Example
```
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
}

Person.prototype.nationality = "English";
```

The JavaScript prototype property also allows you to add new methods to objects constructors:
```
function Person(first, last, age, eyecolor) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eyecolor;
}

Person.prototype.name = function() {
  return this.firstName + " " + this.lastName;
};
```
### Creating JS Object from W3 schools ###
* Define and create a single object, using object literal
* Define and create a single object, with the keyword new.
* DEfine an object constructor, and the craete objects of the constructed type.
* Can now use (in ES5) Object.create ().
