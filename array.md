# yuan.array

## Convert An Array to Another One or Something Else

*	map
	```javascript
	function Person(name) {
		this.name = name;
	}

	var persons = [
		new Person('Jack'),
		new Person('Mary'),
		new Person('Eric')
		];

	var names = yuan.array.map(persons, function(item) {
		return item.name;
	});
	// [ 'Jack', 'Mary', 'Eric' ]
	```

	OR, the next code is also effective.
	```javascript
	var names = yuan.array.map(persons, 'name');
	```
