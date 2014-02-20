*This repository is a mirror of the [component](http://component.io) module [part/async-series](http://github.com/part/async-series). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/part-async-series`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# Async Series

## Installation

node.js:

```bash
npm install part-async-series
```

browser:

```bash
component install part/async-series
```

## Example

```js
var series = require('part-async-series');

var calls = [];

var a = function(context, next){
  setTimeout(function(){
    calls.push('a.' + context);
    next();
  }, 1);
}
var b = function(context, next){
  setTimeout(function(){
    calls.push('b.' + context);
    next();
  }, 1);
}

series([a, b], 'ctx', function(){
  assert('a.ctx' === calls[0]);
  assert('b.ctx' === calls[1]);
  done();
});
```

## Licence

MIT