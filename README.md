# ZeroToMastery
ES10

FLAT
.flat() 
method used on nested arrays

const array = [1,2,[3,4,[5]]]

>array.flat()

<[1,2,3,4,Array(1)]]

Only flattens one level

Put number of levels to flatten in brackets

>array.flat(2)

<[1,2,3,4,5]

Can also be used to clean array 

e.g. 
const entries =['bob','sally',,,,,,,,,,,'cindy']

>entries.flat()

<['bob','sally','cindy']

FLATMAP

flatMap()

combines map and flat

>const entriesmap = entries.flatMap(x=>x+' wilson')

<["bob wilson", "sally wilson", "cindy wilson"]

TRIM
used to cut whitespace characters, either start or end.

const userEmail = '       eddytheeagle@gmail.com       '

>userEmail.trimStart().trimEnd();

<eddytheeagle@gmail.com 

FROM ENTRIES
converts an array to an object

>userProfiles =[['commanderTom',23],[derekZlander,40],['hansel',18]]

>ObjectfromEntries(userProfiles)

<{commanderTom':23,
derekZlander:40
'hansel':18}
