node-plist
==========
### Mac OS X Plist parser/builder for Node.js and browsers

Provides facilities for reading and writing Mac OS X Plist (property list) files. These are often used in programming OS X and iOS applications, as well as the iTunes
configuration XML file.

Plist files represent stored programming "object"s. They are very similar
to JSON. A valid Plist file is representable as a native JavaScript Object and vice-versa.


## Tests

`npm test`


## Usage

Parsing a plist from filename

``` javascript
var plist = require('plist');

var obj = plist.parseFileSync('myPlist.plist');
console.log(JSON.stringify(obj));
```

Parsing a plist from string payload

``` javascript
var plist = require('plist');

var obj = plist.parseStringSync('<plist><string>Hello World!</string></plist>');
console.log(obj);  // Hello World!
```

Given an existing JavaScript Object, you can turn it into an XML document that complies with the plist DTD

``` javascript
var plist = require('plist');

console.log(plist.build({'foo' : 'bar'}).toString());
```


### Deprecated methods

These functions work, but may be removed in a future release. version 0.4.x added Sync versions of these functions.

Parsing a plist from filename
``` javascript
var plist = require('plist');

plist.parseFile('myPlist.plist', function(err, obj) {
  if (err) throw err;

  console.log(JSON.stringify(obj));
});
```

Parsing a plist from string payload
``` javascript
var plist = require('plist');

plist.parseString('<plist><string>Hello World!</string></plist>', function(err, obj) {
  if (err) throw err;

  console.log(obj[0]);  // Hello World!
});
```


License
-------

(The MIT License)

Copyright (c) 2010-2014 Nathan Rajlich <nathan@tootallnate.net>

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the "Software"), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.
