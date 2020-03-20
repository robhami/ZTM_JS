# ZeroToMastery- The DOM

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
```
document.querySelector("h1").style.background = "yellow";
```

Problem is you are effectively writing inline css.

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
	<li random="23">Tea </li>
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
