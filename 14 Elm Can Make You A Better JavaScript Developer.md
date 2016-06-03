# Elm Can Make You A Better JavaScript Developer
Jamison Dance ([@jergason](https://twitter.com/@jergason))

- average JavaScript payload grew from 100kb to 400kb from 2014 to 2015
- base assumption of all browser development: apps are developed in JavaScript
- rethink best practices: Elm
	- functional programming language
	- runs in the browser
	- compiles to JavaScript
- *undefined is not a function*

	```javascript
	function foo(num) {
		if (num > 10) {
			return 'bar'
		}
	}
	console.log(foo(1).toUpperCase())
	```
	
	- runtime errors happen in JavaScript
	- *error tracking* developed in/for JavaScript (track:js, raygun.io, ...)
	- *error preventing* developed in/for JavaScript (eslint, flow, typescript, ...)
	- plug-in type systems have a problem: they can be plugged off
- Elm

	```elm
	foo : Int -> Maybe String
	foo num =
		if num > 10 then Just 'bar'
		else Nothing
	
	bar num =
		case foo num of
			Just str ->
				String.toUpper str
			Nothing ->
				0
	```
	
	- static type system => no runtime errors
	- algebraic data types
	
	```elm
	type Maybe a = Just a | Nothing
	```

- application architecture
	- React: tree of components, data flows down, actions flow up
	- Elm
		- only *stateless functions*
		- only *immutable data*
		- *messages* to pass data around the application (flux is based on elm)
		- decisions are made on the language level => no Elm fatigue
- constraints vs guidelines &ndash; if you write elm the probability is higher that you write a good program
- caveats
	- smaller community
	- "one correct way"
	- server rendering not easy
	- does better when it runs everything
	- still in the early days ("maybe production ready")
