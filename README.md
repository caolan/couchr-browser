# couchr-browser

Simple stand-alone request library for CouchDB. Provides a browser-compatible
module, with better CouchDB error reporting and a simpler API than making XHR
requests directly in the browser or using jQuery.ajax.

This package is designed to be suitable for use with webpack or browserify,
and makes use of the 'events' and 'component-ajax' modules.

Comes in around 11kb minified (4.2kb gzipped)


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


### Building stand-alone version

    npm run build
