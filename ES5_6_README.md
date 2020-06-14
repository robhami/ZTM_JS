## ES5 & 6 ##


### Let ###
used instead of var

```
const player ="Bobby";
let experience = 180;
let wizardLevel = false; 

if (experience > 90) {

	let wizardLevel = true;
	console.log('inside', wizardLevel);
}

console.log('outside',wizardLevel);
```
In console: 
```
inside true
outside false
```
This creates own scope (block scope) inside curly brackets. Whereas var would change outside var when inside changed. 

### Const ###

Can change let and var variables but cannot change const variable:

```
>experience
<180
>experience=80;
<80
>experience
<80
>player
<"Bobby"
>player="Fred"
<VM160:1 Uncaught TypeError: Assignment to constant variable.
    at <anonymous>:1:7

```
Use 'const' if using variable that won't change
For variable that changes use 'let'.


Note that when const applied to objects it only locks name of object, not values and properties: 

```
const obj = {player: "Bobby",
experience: 180,
wizardLevel: false }

>obj =55
<VM251:1 Uncaught TypeError: Assignment to constant variable.
    at <anonymous>:1:5

>obj.wizardLevel =true;
<true

```

### Destructuring ###

To get objects values/properties. We would need to do: 

```
const obj = {player: "Bobby",
experience: 180,
wizardLevel: false }

const player = obj.player;
const experience = obj.experience;
let wizardLevel = obj.wizardLevel;

```
Can use destructuring to more efficiently assign variables.

```
>const { player, experience} = obj;
<undefined
>player
<"Bobby"
>experience
<180
```

Basically, saying take the properties in curly brackets for 'obj' and create individual const variables. Same can be done for let: 

```

let {wizardLevel} = obj;

```

### Object properties ###

Square brackets can be used to declare properties. Get from a another variable (i.e. name) or do sum in (1+2=3)

```
const name = 'john snow'

const obj = {
  [name]: 'hello',
  [1 +2]: 'hihi'
}


obj
{3: "hihi", john snow: "hello"}
}

```
Sometimes you want to add variables to an object. You may also want property to match value.
```

const a ="Simon";
const b= true;
const c = {};

const obj = {
  a:a,
  b:b,
  c:c
}
<undefined
>a
<"Simon"
>b
<true
>c
<{}

```
A quicker way if property and value are the same is: 
```
const obj= {a, b, c}
```

### Template strings ###

```
const name = "Sally"
const age = 34;
const pet = "horse"
const greeting = "Hello " + name + " you/'re great" + greeting + "!"

const greetingBest = `Hello ${name} you seem to be ${age-10}. What a lovely ${pet} you have`;

>greetingBest
<"Hello Sally you seem to be 24. What a lovely horse you have"
```

### Default arguments ###

If value not given then uses default arguments/parameters from function brackets:
```
function greet (name='', age=30, pet='cat') {
  return `Hello ${name} you seem to be ${age-10}. What a lovely ${pet} you have`;
}

>greet()
<"Hello  you seem to be 20. What a lovely cat you have"

>greet("John",50,"dog")
<"Hello John you seem to be 40. What a lovely dog you have"

```

### Symbol ###

```
let sym1 = Symbol();
let sym2 = Symbol('foo');
let sym3 = Symbol('foo');

let sym1 = Symbol();
let sym2 = Symbol('foo');
let sym3 = Symbol('foo');

<undefined
>sym1
<Symbol()
>sym2
<Symbol(foo)
>sym3
<Symbol(foo)
>sym2===sym3
<false

```

Symbols used because they create completely unique types. So they will never conflict. 
Mainly used as an identifier for object properties. 
Because if you have thousands of them you dont want them to collide and be the same ones becuase you'll get bugs.

### Arrow functions ###

```
function add (a, b) {
  return a + b;
}

const add = (a, b) => a + b;

```
If you have single return you can put it on one line. 
