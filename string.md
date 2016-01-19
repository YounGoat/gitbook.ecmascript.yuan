# yuan.string

## String Format

*	C style (printf) format
	```javascript
	yuan.string.format("Hello %s! My name is %s.", "Jack", "Eric");
	// OUTPUT:
	// Hello Jack! My name is Eric.
	```

* 	Simple template format
	```javascript
	var template = "Hello %{#name}! My name is %{#myname}.";
	var data = {
		"name": "Jack",
		"myname": "Eric"
	};
	yuan.string.formatT(template, data);
	```
