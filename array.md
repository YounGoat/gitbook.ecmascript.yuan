# yuan.array

None of the methods in this chapter will change the existing array, but some will generate a new array (marked with +).

*	compute

	Calculate with each item in an array, then return the combination of the results, e.g. the sum or the average.

	```javascript
	var persons = [
		{ name: 'Jack', age: 20 },
		{ name: 'Mary', age: 22 },
		{ name: 'Eric', age: 18 }
		];

	yuan.array.compute(persons, 'age', Math.max);
	// 22

	yuan.array.compute(
		persons,
		function(item) { return item.age; },
		Math.min);
	// 18
	```

*	excludeOn +

	```javascript
	var persons = [
		{ name: 'Jack', age: 20, gender: 'male' },
		{ name: 'Mary', age: 22, gender: 'female' },
		{ name: 'Eric', age: 18, gender: 'male' }
		];

	yuan.array.excludeOn(persons, { gender: 'male' });
	// [ { name: 'Mary', age: 22, gender: 'female' } ]

	yuan.array.excludeOn(persons, function(item) {
		return item.age >= 20;
	});
	// [ { name: 'Eric', age: 18, gender: 'male' } ]
	```

*	equal

	To judge whether two objects are equal by each properties.

	```javascript
	yuan.array.equal(foo, bar);
	// true or false
	```

*	exists

	To judge whether there are matching item(s) in an array.

	```javascript
	var persons = [
		{ name: 'Jack', age: 20, gender: 'male' },
		{ name: 'Mary', age: 22, gender: 'female' },
		{ name: 'Eric', age: 18, gender: 'male' }
		];

	yuan.array.exists(persons, { gender: 'male' });
	// true

	yuan.array.exists(persons, function(item) {
		return item.age > 30;
	});
	// false
	```

*	find +

	Get all the matching items in an array.

	ATTENTION: There may be 0, 1 or more than 1 items found, whatever, the result will be an array.

	```javascript
	var persons = [
		{ name: 'Jack', age: 20, gender: 'male' },
		{ name: 'Mary', age: 22, gender: 'female' },
		{ name: 'Eric', age: 18, gender: 'male' }
		];

	yuan.array.find(persons, [ gender: 'female' ]).length;
	// 1

	yuan.array.find(persons, function(item) {
		return age > 18;
	}).length;
	// 2
	```

*	find.first

	With parameters as same as ```find```, it will get the first matching items in an array, starting with item #0.

	ATTENTION: If none found, the result will be __undefined__, not __null__ or anything else.

*	last

	Return the last item in an array.

*	map +

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

*	uniq +

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

*	without +

	Return a new array without specified items.

	ATTENTION: Whatever how many items remained, the result will be an array.

	```javascript
	var persons = [ 'Jack', 'Tom', 'Mary', 'Eric' ];
	yuan.array.find(persons, 'Jack', 'Tom');
	// [ 'Mary', 'Eric' ]
	```
