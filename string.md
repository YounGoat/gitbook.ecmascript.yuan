# yuan.string

## [C Style Format](string-format.md)

## Simple template format

```javascript
var template = "Hello %{#name}! My name is %{#myname}.";
var data = {
	"name": "Jack",
	"myname": "Eric"
};
yuan.string.formatT(template, data);
```
