# 	yuan.object

## 	Change or Generate

Methods in this section are used to change an existing object (marked with \*) or generate a new object (marked with +).

*	extend +

	Clone the leading object, then inject the members of following objects into the cloned. Finally, return the new object.
	```javascript
	var source  = { name: "Jack", gender: "male" };
	var injection_1 = { age: 22 };
	var injection_2 = { name: "Eric" };

	yuan.object.extend(source, injection_1);
	// RETURN:
	// { name: "Jack", gender: "male", age: 22 }
	// ATTENTION: source NOT changed.

	yuan.object.extend(source, injection_1, injection_2);
	// RETURN:
	// { name: "Eric", gender: "male", age: 22 }
	```

*	expand \*

	Inject the members of following objects into the leading one. The leading object will be changed.
	```javascript
	var source  = { name: "Jack", gender: "male" };
	var injection = { age: 22 };
	yuan.object.expand(source, injection);
	// source is changed to:
	// { name: "Jack", gender: "male", age: 22 }
	```

*	pick +
	```javascript
	var source  = { name: "Jack", gender: "male", age: 22 };
	yuan.object.pick(source, [ "name", "age" ]);
	// RETURN:
	// { name: "Jack", age: 22 }
	```

*	omit +
	```javascript
	var source  = { name: "Jack", gender: "male", age: 22 };
	yuan.object.omit(source, [ "gender" ]);
	// RETURN:
	// { name: "Jack", age: 22 }
	```

##	Analyse An Object

In this section, we will find ways to peep into objects.

*	equalAt

	Compare two objects by key members.
	```javascript
	var foo = { name: "Jack", gender: "male" };
	var bar = { name: "Jack", age: 22 };
	yuan.object.equalAt(foo, bar, [ "name" ]);
	// RETURN: true
	```

*	has
	```javascript
	var source  = { name: "Jack", gender: "male" };
	yuan.object.has(source, "name");
	// RETURN: true
	```

##	Convert to Array

Sometimes, we need transfer an object to an array.

*	by default
	```javascript
	var source  = { name: "Jack", gender: "male" };
	yuan.object.toArray(source);
	// RETURN:
	// [ [ "name", "Jack" ], [ "gender", "male" ] ]
	```

*	with "key" name and "value" name appointed
	```javascript
	var source  = { name: "Jack", gender: "male" };
	yuan.object.toArray(source, "key", "value");
	// RETURN:
	// [ { key: "name", value: "Jack" }, { key: "gender", value: "male" } ]
	```

*	with transfer appointed
	```javascript
	var source  = { name: "Jack", gender: "male" };
	var transfer = function(key, value) { return value; }
	yuan.object.toArray(source, transfer);
	// RETURN:
	// [ "Jack", "male" ]
	```
