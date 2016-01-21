# yuan.promise

*	create an Promise instance
	```javascript
	// ES6 required.

	function _promise_http_get(url) {
		var onsuccess, onerror;

		// Do something async.
		http
			.get(url, function(res) {
				onsuccess(res);
			})
			.on('error', function(ex) {
				onerror(ex);
			})
			;

		return yuan.promise(onsuccess, onerror);
	};

	var res = yield _promise_http_get(url);
	```
