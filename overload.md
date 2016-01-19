# yuan.overload

```yuan.overload``` makes it possible to design functions with overloaded parameters in ECMAScript.

## Create Overloaded Function

```javascript
var fn = yuan.overload.Function()
	.overload(
		String,
		function(s) {
			console.log('String fetched.');
		}
	)
	.overload(
		Number,
		function(n) {
			console.log('Number fetched.');
		}
	)
	;

// Continue to overload 
fn.overload()
```
