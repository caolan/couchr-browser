# couchr-browser

Simple request library for CouchDB. Provides a browser-compatible module
(based on jQuery.ajax), with better CouchDB error reporting and a simpler API
than making XHR requests directly in the browser.

This package is suitable for use with webpack or browserify, and makes use
of the 'events' module.


### Examples

```javascript
var couchr = require('couchr-browser');

couchr.get('http://hostname:port/dbname/docid', function (err, doc) {
    ...
});
```

### Methods

```javascript
couchr.get (url, /*optional*/params, function (err, res, req) { ... })
couchr.post(url, /*optional*/data,   function (err, res, req) { ... })
couchr.put (url, /*optional*/data,   function (err, res, req) { ... })
couchr.del (url, /*optional*/data,   function (err, res, req) { ... })
couchr.head(url, function (err, res, req) { ... })

couchr.copy(from, to, function (err, res, req) { ... }) 

var feed = couchr.changes(db_url);
feed.on('change', function (change_object) { ...  });
feed.on('error', function (err) { ...  });
feed.pause();
feed.resume();
```

### Installation

    npm install couchr-browser
