# ZeroToMastery - DOM Events

Put JS src link at bottom of page

##### addEventListener #####
```
var button = document.getElementsByTagname("button")[0];

button.addEventListener("click", function () {
  console.log("CLICK!!!!!");
})

```
First value in bracket is event listening for, second is what to do. 

Need to add zero index because getElementsByTagname returns an array. If you don't you'll get an error: 
```
VM979:1 Uncaught TypeError: document.getElementsByTagname is not a function
```
Other examples: 

```
button.addEventListener("mouseleave", function () {
  console.log("CLICK!!!!!");
})

button.addEventListener("mouseenter", function () {
  console.log("CLICK!!!!!");
})

```
Can get other events from website, need to add link:

##### Create Element & Create Text Node then append to Element #####

Below will create new list element and append a TextNode to it:
```
var button = document.getElementById("enter");
var input = document.getElementById("userInput");
var ul = document.querySelector("ul");

button.addEventListener("click", function () {
  if (input.value.length>0)  {                            
    var li =document.createElement("li");
    li.appendChild(document.createTextNode(input.value));
    ul.appendChild(li);
    input.value = "";
    }
});
```

To add event if use return to enter in input box. Function automatically receives a parameter (event) that is the keypress value 

```
input.addEventListener("keypress", function (event){
   if (input.value.length>0 && event.keyCode === 13)  {                            
    var li =document.createElement("li");
    li.appendChild(document.createTextNode(input.value));
    ul.appendChild(li);
    input.value = "";
    }
  }
```

Wrote code in class can create link to it.

[Link](https://github.com/robhami/ZeroToMastery/blob/master/DOM_Events_Code_Script)
