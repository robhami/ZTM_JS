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


class Wizard extends Player {
	constructor(name,type) {
		
		super(name,type)
		console.log('wizard', this);
		
	}
	play() {
		console.log(`WEEE I'm a ${this.type}`);
	}
}

const wizard1 = new Wizard ('Shelly', 'Healer');
const wizard2 = new Wizard ('Shawn', 'Dark Magic');
