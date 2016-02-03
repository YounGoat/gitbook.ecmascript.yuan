# yuan.array

## Generate A New Array

*	map

	Convert an array to another one or something else.
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

*	uniq

	Filter continuously repeated items in an array.
	```javascript
	yuan.array.uniq( [ 1, 1, 2, 3 ] );
	// RETURN: [ 1, 2, 3 ]

	yuan.array.uniq( [ 1, 2, 1, 3 ] );
	// RETURN: [ 1, 2, 1, 3 ]
	```

	Self defined comparison function is supported.
	```javascript
	yuan.array.uniq( [ 1, 2, 4, 8 ], function(a, b) {
		return (a % 2) == (b % 2);
	});
	// RETURN: [ 1, 2 ]
	```
