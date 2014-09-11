# couchr-browser

Lightweight request library for CouchDB. Provides a browser-compatible
module, with better CouchDB error reporting and a simpler API than making XHR
requests directly in the browser or using jQuery.ajax.

This package is designed to be suitable for use with webpack or browserify,
and makes use of the events module (for the changes feed). You can pass in any
jQuery.ajax compatible API to initialize the module (allowing you to use your
favourite library for this). I suggest taking a look at
[reqwest](https://github.com/ded/reqwest) if you don't need full jQuery.

Comes in around 5.9kb minified (2.2kb gzipped)


### Examples

```javascript
var couchr = require('couchr-browser')(jQuery.ajax);

couchr.get('http://hostname:port/dbname/docid', function (err, doc) {
    ...
});
```

### Methods

```javascript
var couchr = require('couchr-browser')(jQuery.ajax);
var couchr = require('couchr-browser')(reqwest.compat);

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
