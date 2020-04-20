# ZeroToMastery

Objects are data structures and also collections of properties

```
var user = {

  name: "John",
  age: 34,
  hobby: "Soccer",
  isMarried: false,

};

var list ={"apple", "bannana", "orange"}
```

Objects have properties and values. Arrays have index and values.

To get values of properties: 

```
>user.name
<"john"

```

To add properties to object: 

```
>user.favouriteFood="Spinach";
<"spinach"

```
To change values of an object:

```
>user.isMarried = true;
<true

>user
<
var user = {

  name: "John",
  age: 34,
  hobby: "Soccer",
  isMarried: false,
  favouriteFood: "Spinach"

};

```

Can add array inside object:

```
var user = {

  name: "John",
  age: 34,
  hobby: "Soccer",
  isMarried: false,
  favouriteFood: "Spinach",
  spells: ["abrakadabra","shazam", "boo"]
};

```

Can add object inside array: 

```
var list = [
  {username: "andy",
  password: "secret"
  },
   {username: "jess",
  password: "123"
  },
];  

```

 Calling array values inside object: 
 
``` 
 >user.spells
 <["abrakadabra","shazam", "boo"]
 
 >user.spells[1]
 <"shazam"
 
 ```
 
 Calling object inside array: 
 
 ```
 >list[0].password;
 <"secret"

```
Add function to object and call it: 

```
var user = {

  name: "John",
  age: 34,
  hobby: "Soccer",
  isMarried: false,
  favouriteFood: "Spinach",
  spells: ["abrakadabra","shazam", "boo"]
  shout: function() {
    console.log("ahhhhhhh!");
  }
};

>user.shout()
<ahhhhhhhhhh!

```

A function inside an object is a method. So shout is a method of user. 

For arrays method would be like
``
list.pop()

console.log()
```

console is an object, log is a function. If you call console you get a bunch of methods (functions). 

```
>console
<console {debug: ƒ, error: ƒ, info: ƒ, log: ƒ, warn: ƒ, …}

```
Create empty objects and lists: 

```
user2= {};

>user2;
<{}

list2=[];

>list2
<[]

>list[0]
<undefined

```
#### Null ####

```
>var emptyObj={}
<undefined

>var nullObj=null;
<undefined

>emptyObj
<{}

>nullObj
<null
```

Cannot add anything to null but can to empty object: 

```
>nullObj.name="Andy";
<VM548:1 Uncaught TypeError: Cannot set property 'name' of null
    at <anonymous>:1:13
(anonymous) @ VM548:1


>emptyObj.name="Andy";
<"Andy"

>emptyObj
<{name: "Andy"}

```
