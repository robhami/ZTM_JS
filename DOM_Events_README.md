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
* Added by RH: Please note that keyCode gave problems when using for calculator as could not detect values where shift keys used (e.g. -=+). Used key instead:

```
userInput.addEventListener("keyup", keyEntry)

 function keyEntry (event) {	
	let numSelect=event.key;
	// console.log("key: ", keyCodeVal);
	
	// let numSelect = String.fromCharCode(keyCodeVal);
	console.log("numSelect: ", numSelect);


	let numKey = /[0-9]/;
	let operator = /[+-/*]/;
	let equalsym = /[=]/;
	let decKey = /[.]/;

	kp = true;
	clearZero();

	if (numKey.test(numSelect)) {
		console.log("valid: ",numSelect);	
		num(numSelect, kp);
	}

	if (operator.test(numSelect)) {
		console.log("valid: ",numSelect);
		opera(numSelect, kp);	

	}

	if (equalsym.test(numSelect)) {
		console.log("valid: ",numSelect);
		kp = true;
		equals(numSelect);	

	}

	if (decKey.test(numSelect)) {
		console.log("valid: ",numSelect);
		dec(numSelect, kp);	

	}

 	scroll();

}
```






Wrote code in class can create link to it.

[Link to code script](https://github.com/robhami/ZeroToMastery/blob/master/DOM_Events_Code_Script)

In the code you saw something interesting:

Event listener syntax : 

```
button.addEventListener("click", addListAfterClick);
input.addEventListener("keypress", addListAfterKeypress);
```

You didn't see the function being called like this as you may have expected: 

```
button.addEventListener("click", addListAfterClick());
input.addEventListener("keypress", addListAfterKeypress(event))
```

This is something called a callback function. When that line of javascript runs, we don't want the addListAfterClick function to run because we are just adding the event listener now to wait for click or keypress. We want to let it know though that we want this action to happen when a click happens. So the function now automatically gets run (gets added the ()) every time the click happens. So we are passing a reference to the function without running it.
