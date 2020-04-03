# From W3 schools

sequence of characters that forms a search pattern

##### Syntax: #####
/pattern/modifiers

```

var str = "Visit W3 schools";
var patt = /w3 schools/i;
var result = str.match(patt);

alert(result)

<W3 Schools

```
#### Uses String Methods ####

Often used with: 

##### search() #####
```
var str = "Visit W3Schools";
var n = str.search(/w3schools/i);

```

##### replace() #####

```
var str = "Visit Microsoft!";
var res = str.replace(/microsoft/i, "W3Schools");
```

##### Modifiers #####

- i= case insenstive
- g= global match (find all matches rather than stopping at 1st match)
- m= multiline matching (check multiple lines)

##### Brackets ######

Used to find a range of characters: 

- [abc] Find any of charaters in brackets
- [0-9] Find any of digits between the brackets
- (x|y) Find any of the alternatives separated with |

##### Metacharacters #####
- \d Find digit
- \s Find whitespace character
- \b  Find a match at the begining of a word like this: \bWORD, or at the end of a word like this: WORD\b
- \uxxxx Find the unicode chracter specified by the hexadecimal number xxxx

#### Quantifiers ####

- n+ Matches any string that contains at least one n
- n* Matches any string that contains zero or more occurences of n
- n? Matches any string that contains zero or one occurences of n




Using test()
The test() method is a RegExp expression method.

It searches a string for a pattern, and returns true or false, depending on the result.

The following example searches a string for the character "e":

Example

```
var patt = /e/;
patt.test("The best things in life are free!");
```

Since there is an "e" in the string, the output of the code above will be:

true

Dont have to use variable: 
```
/e/.test("The best things in life are free!");
```

Using exec()
The exec() method is a RegExp expression method.

It searches a string for a specified pattern, and returns the found text as an object.

If no match is found, it returns an empty (null) object.

The following example searches a string for the character "e":

```
/e/.exec("The best things in life are free!");
```
