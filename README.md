# node-polyfills
(dev) set node polyfill by specific version or specific ECMA.

## example
set all polyfills for node 8.4 and ECMAScript 2017

```javascript
require('node-polyfills')({node: '8.4', ecma: '2017'});
```

### node : string | number
define node version, default is the lasted (8.4) node version when the packeage was published in `npm`. 

### ecma : string | number
define ECMAScript version, default is the lasted (2018)

## why?
example the dev environmet whas set node version in 8.2, but the production environmet will run node in version 7.8.
in most cases its not a problem. but if you had one code like that:
```javascript
const fs = require('fs')
const util = require('util')

const {promisify} = util
// the promisify function is present only in versio 8+
// when you run this code in that production environmet will be the error: 'undefined is not a function'
fs.writeFileAsync = promisify(fs.writeFile)
```
