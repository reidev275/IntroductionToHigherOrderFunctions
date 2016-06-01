- title : Are you still telling the computer how to count?
- description : An introduction to Higher Order Functions
- author : Reid Evans
- theme : Simple
- transition : Fade

***

### An introduction to Higher Order Functions
####[@ReidNEvans](http://twitter.com/reidnevans)
####http://reidevans.tech

***

What is a Higher Order Function?

---

A function that accepts or returns a function

***

Good news! you've probably used them before

* Map
* Done
* Then
* Filter
* Reduce
* FlatMap

***

###Map

* Map
* Select
* fmap
* array_map

---

	['Hello', 'Tombras'].map(function(x) {
		return x.length
	})

	['Hello', 'Tombras'].map(x => x.length)
	// [5,7]

---

	// [string] -> (string -> number) -> [number]
	['Hello', 'Tombras'].map(x => x.length)
	// [5,7]

---

	// [a] -> (a -> b) -> [b]
	// [string] -> (string -> number) -> [number]
	['Hello', 'Tombras'].map(x => x.length)
	// [5,7]

***

###Filter

* Filter
* Where
* array_filter

---

	['Hello', 'Tombras'].filter(x => x.length > 5)
	// ['Tombras']

---

	// [string] -> (string -> bool) -> [string]
	['Hello', 'Tombras'].filter(x => x.length > 5)
	// ['Tombras']

---

	// [a] -> (a -> bool) -> [a]
	// [string] -> (string -> bool) -> [string]
	['Hello', 'Tombras'].filter(x => x.length > 5)
	// ['Tombras']

***

###Reduce

* Reduce
* Aggregate
* fold
* foldr
* array_reduce

---

	[1,2,3,4,5].reduce((accumulator, current) => accumulator + current)
	//15

---

	// [number] -> (number -> number -> number) -> number
	[1,2,3,4,5].reduce((accumulator, current) => accumulator + current)
	//15

---

	// [a] -> (b -> a -> b) -> b
	// [number] -> (number -> number -> number) -> number
	[1,2,3,4,5].reduce((accumulator, current) => accumulator + current)
	//15

***
	
###FlatMap

* Bind
* SelectMany
* >>=

---

	['Hello', 'Tombras'].flatMap(x => x.split())
	// ['H','e','l','l','o','T','o','m','b','r','a','s']

---

	// [string] -> (string -> [string]) -> [string]
	['Hello', 'Tombras'].flatMap(x => x.split())
	// ['H','e','l','l','o','T','o','m','b','r','a','s']

---

	// [a] -> (a -> [b]) -> [b]
	// [string] -> (string -> [string]) -> [string]
	['Hello', 'Tombras'].flatMap(x => x.split())
	// ['H','e','l','l','o','T','o','m','b','r','a','s']

***

But wait, there's more!

***

	$.get( "helloTombras.php" ).done(x => x.length);
	// -------------------------------^
	//12

---

	//Deferred string -> (string -> number) -> Deferred number
	$.get( "helloTombras.php" ).done(x => x.length);
	//12

---
	
	//Deferred a -> (a -> b) -> Deferred b
	//Deferred string -> (string -> number) -> Deferred number
	$.get( "helloTombras.php" ).done(x => x.length);
	//12

---

Done

	Deferred a -> (a -> b) -> Deferred b

Map

	Array a -> (a -> b) -> Array b
	or
	[a] -> (a -> b) -> [b]