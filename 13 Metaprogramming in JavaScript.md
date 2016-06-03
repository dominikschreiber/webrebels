# Metaprogramming in JavaScript
Mikael Brevik ([@mikaelbrevik](https://twitter.com/@mikaelbrevik))

- meta == self-referential/reflexive ("about itself")
- `eval("Math.pow(5, 2)")` is metaprogramming (because we write a program that writes a program)
- examining properties of objects at runtime (`Object.keys()`) is metaprogramming
- defining new properties of objects at runtime (`Object.defineProperty()`) is metaprogramming
- change operations on properties of objects at runtime (javascript proxies) is metaprogramming
- use cases for a proxy
	- tracing/logging/debugging
```javascript
function traced(obj) {
	return new Proxy(obj, {
		get (target, prop) {
			let result = Reflect.get(target, prop);
			console.log(`get ${prop} as ${result}`);
			return result;
		}
	})
}
```
	- counting method accesses
	- flexible array accessors (negative indices, index ranges, ...)
	- auto-creating apis (based on function names, e.g. `div8`, `pow3`)
	- developer-friendly apis (meaningful error messages based on levenshtein distance, e.g. `".dib" does not exist. did you mean ".div"?`)
	- custom syntax/clojures multi-method
- see https://github.com/mikaelbr/proxy-fun