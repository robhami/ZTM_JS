# ZeroToMastery

Javascript can do the following with the DOM: 

* Change all the HTML elements in the page
* Change all the HTML attributes in the page
* Change all the HTML CSS styles in the page
* Remove existing HTML elements and attributes
* Add new HTML elements and attributes
* Javascript can react to all existing HTML events in the page
* Javascript can create new HTML events in the page

#### DOM Selectors ####

Created HTML with a shopping list and can use following selectors to get elements
```
document.getElementsByTagname("h1");

document.getElementsByClassName("second");

document.getElementsById("first");

document.getElementsByClassName("second")[0];
> <

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
	<li>Tea </li>
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

