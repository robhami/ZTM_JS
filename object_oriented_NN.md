Everything in JS is an object. 

Objects have properties and methods (things they can do). Methods are functions associated with the object 

```
﻿
var names =['ryu', 'cyrstal','mario']
undefined
names
(3) ['ryu', 'cyrstal', 'mario']
0: "ryu"
1: "cyrstal"
2: "mario"
length: 3


```

names is an object and has a property called length. This can be called as follows: 
```
names.length
3

```
Methods are shown in proto- object:

```
[[Prototype]]: Array(0)
at: ƒ at()
concat: ƒ concat()
constructor: ƒ Array()
copyWithin: ƒ copyWithin()
entries: ƒ entries()
every: ƒ every()
fill: ƒ fill()
filter: ƒ filter()
find: ƒ find()
findIndex: ƒ findIndex()
findLast: ƒ findLast()
findLastIndex: ƒ findLastIndex()
flat: ƒ flat()
flatMap: ƒ flatMap()
forEach: ƒ forEach()
includes: ƒ includes()
indexOf: ƒ indexOf()
join: ƒ join()
keys: ƒ keys()
lastIndexOf: ƒ lastIndexOf()
length: 0
map: ƒ map()
pop: ƒ pop()
push: ƒ push()
reduce: ƒ reduce()
reduceRight: ƒ reduceRight()
reverse: ƒ reverse()
shift: ƒ shift()
slice: ƒ slice()
some: ƒ some()
sort: ƒ sort()
splice: ƒ splice()
toLocaleString: ƒ toLocaleString()
toString: ƒ toString()
unshift: ƒ unshift()
values: ƒ values()
Symbol(Symbol.iterator): ƒ values()
Symbol(Symbol.unscopables): {copyWithin: true, entries: true, fill: true, find: true, findIndex: true, …}
[[Prototype]]: Object
```


WE can use method SORT as follows: 

```
names.sort()
(3) ['cyrstal', 'mario', 'ryu']
```

Another object is the WINDOW object. This is 

```
window.innerWidth
768
```

null, numbers, booleans and strings are primitive types not objects pretty much everything else is. EG a string does not have methods:

```
var name = 'mario'
undefined
name
"mario"
```
However primitive types can still behave like objects. JS can wrap them in an object when we need to. EG JS will wrap a string indie a object temporarily to use a length method on the string: 

```
name.length
5
```
wrapping string in object:
```
var name2=new String ('ryu')
undefined
name2
String {'ryu'}0: "r"1: "y"2: "u"length: 3[[Prototype]]: String[[PrimitiveValue]]: "ryu"

```
WE can create objects in JS and give them methods and properties
