## C Style Format

###	Simple placeholder
```javascript
	// String
	yuan.string.format("Hello %s! My name is %s.", "Jack", "Eric");
	// OUTPUT:
	// Hello Jack! My name is Eric.

	// Number
	yuan.string.format("Jack is %d years old.", 10);
	```

### Size-fixed placeholder
```javascript
	yuan.string.format("Name: %10s", "Jack");
	// OUTPUT:
	// Name: ______Jack

	yuan.string.format("Name: %-10s", "Jack");
	// OUTPUT:
	// Name: Jack______
	```

### Size-fixed placeholder, what happens when string size exceeds
```javascript
	yuan.string.format("%3s", "abcdefg");
	// OUTPUT:
	// abc

	yuan.string.format("%-3s", "abcdefg");
	// OUTPUT:
	// abc
	```

### Size-fixed placeholder and cutter
```javascript
	yuan.string.format("%7.3s", "abcdefg");
	// OUTPUT:
	// ____abc

	yuan.string.format("%-7.3s", "abcdefg");
	// OUTPUT:
	// abc____
	```

###	Integer placeholder

| Placeholder   | Number        | Output  | Remark
| ------------- | ------------- | ------- | ----------
| %d            | 10.01         |      10 | integer
| %+d           | 10.01         |     +10 | with +/- sign
| %,d           | 10000         |  10,000 | with thousand signals
| %4d           | 100           |    100_ | size fixed
| %06d          | 100           |  000100 | size fixed, with leading 0
| %-4d          | 100           |    _100 | right aligned, size fixed
| %-4d          | 10000         |    _1e4 | scientific notation (SN) when size exceeds
| %-2d          | 10000         |      __ | whitespaces when size exceeds (event in SN)
| %+-2d         | 10000         |      _+ | only +/- sign when size exceeds (event in SN)

ATTENTION: Here the underline sign _ represents <SPACE>.
