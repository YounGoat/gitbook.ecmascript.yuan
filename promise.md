# yuan.promise

*	create an Promise instance
	```javascript
	// ES6 required.

	function _promise_http_get(url) {
		var callbacks = {};

		// Do something async.
		http
			.get(url, function(res) {
				callbacks.onsuccess(res);
			})
			.on('error', function(ex) {
				callbacks.onerror(ex);
			})
			;

		return yuan.promise(callbacks);
	};

	var res = yield _promise_http_get(url);
	```
