# ZeroToMastery- DOM Selectors

Javascript can do the following with the DOM: 

* Change all the HTML elements in the page
* Change all the HTML attributes in the page
* Change all the HTML CSS styles in the page
* Remove existing HTML elements and attributes
* Add new HTML elements and attributes
* Javascript can react to all existing HTML events in the page
* Javascript can create new HTML events in the page

### DOM Selectors ###

#### getElementsBy ####

Created HTML with a shopping list and can use following selectors to get elements

```
document.getElementsByTagname("h1");
<[h1]

document.getElementsByClassName("second");
<[p.second]
```
Note below only one element (no plural) cos can only be one ID, this returns the full element as opposed to what looks like an array above.
```
document.getElementById("first");
<p id="first">Get it done today</p>
```
To be able to access the above using className I'll have to do second then the zero index of the array:

```
document.getElementsByClassName("second")[0];
><p id="first">Get it done today</p>
```

#### querySelector ####

querySelector() method returns the first element that matches a specified CSS selector(s) in the document. To get all elements use querySelectorAll

```
document.querySelector("h1");
< <h1>Shopping List</h1>

document.querySelector("li");
< <li random="23"> Notebook</li>

```
querySelector selects first item it finds. To get all use querySelectorAll:
```
document.querySelectorAll ("li");
< (6) [li, li, li, li, li, li]
```
Can also do for multiple elements: 
```
document.querySelectorAll ("li","h1");
< (7) [h1, li, li, li, li, li, li]
```

#### getAttribute ####

Need to elect element with query selector first then use getAttribute:

```
document.querySelector("li").getAttribute("random")
<"23"

```

#### setAttribute ####

```
document.querySelector("li").setAttribute("random", "1000")
<undefined

document.querySelector("li");
< <li random="1000">Notebook</li>

```
### Changing Styles ###


#### Change style property ####
```
document.querySelector("h1").style.background = "yellow";
```

Problem is you are effectively writing inline css.


#### Changing class #####

**className**
```
var h1 = document.querySelector("h1");

h1.className ="coolTitle";

```
**classList.add.remove.toggle**

Returns class names of an element. Property is useful to add, remove and toggle.
```

document.querySelector ("li").classList

document.querySelector ("li").classList.add("coolTitle");

document.querySelector ("li").classList.remove("coolTitle");

document.querySelector ("li").classList.add("done");

document.querySelector ("li").classList.toggle("done");

```

#### Parent and child elements ####

Use index to determine which list element (it defaults to first if empty: 

```
document.querySelectorAll("li")[1];
< <li>Chicken</li>
```
Can select an element's parent: 

```
document.querySelectorAll ("li")[1].parentElement;
< <ul>
	<li class="bold red done">Tea </li>
	<li>Chicken </li>
	<li>Soup </li>
	<li>Pies </li>
	<li>More Pies </li>
	<li>Ice Cream </li>
</ul>
```
Or parent of parent: 

```
document.querySelectorAll ("li")[1].parentElement.parentElement;
< <body></body>

document.querySelectorAll ("li")[1].parentElement.parentElement.parentElement;
< <html></html>
```
This gives all the children of the body: 

```
document.querySelectorAll ("li")[1].parentElement.parentElement.children;
< [h1, p#first, p.seconf, ul, first: p#first]
```

Important to cache selectors in variables. Saves memory

```
var h1 = document.querySelector("h1");
```

#### Shopping List Code ####

```
<!DOCTYPE html>
<html>
<head>
	<link rel="stylesheet" type="text/css" href="style.css">
	<title>Dom Events</title>
</head>
<body>
  <h1>Shopping List</h1>
  <p id="first">Get it done Today</p>
  <p class="second">No excuses</p>
<ul>
	<li class="bold red" random="23">Tea </li>
	<li>Chicken </li>
	<li>Soup </li>
	<li>Pies </li>
	<li>More Pies </li>
	<li>Ice Cream </li>
	
</ul>
</body>
</html>
<script type="text/javascript" src="script.js">
	
</script>
```

#### Cool Tile Code ####

```
.coolTitle {
  text-align: center;
  font-family: 'Oswald', Helvetica, sans-serif;
  font-size: 40px;
  transform: skewY(-10deg);
  letter-spacing: 4px;
  word-spacing: -8px;
  color: tomato;
  text-shadow: 
    -1px -1px 0 firebrick,
    -2px -2px 0 firebrick,
    -3px -3px 0 firebrick,
    -4px -4px 0 firebrick,
    -5px -5px 0 firebrick,
    -6px -6px 0 firebrick,
    -7px -7px 0 firebrick,
    -8px -8px 0 firebrick,
    -30px 20px 40px dimgrey;
}

.done {
  text-decoration: line-through;
}
```

