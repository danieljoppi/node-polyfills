# node-polyfills
(dev) set node polyfill by specific version or specific ECMA.

## set all polyfills for node 8.4 and ECMAScript 2017

```javascript
require('node-polyfills')({node: '8.4', ecma: '2017'});
```

### node : string | number
define node version, default is the lasted (8.4) node version when the packeage was published in `npm`. 

### ecma : string | number
define ECMAScript version, default is the lasted (2018)
