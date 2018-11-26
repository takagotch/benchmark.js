### benchmarkjs
---
https://github.com/bestiejs/benchmark.js

```
<script src="lodash.js"></script>
<script src="platform.js"></script>
<script src="benchmark.js"></script>
```

```js
require({
  'paths': {
    'benchmark': 'path/to/benchmark',
    'lodash': 'path/to/lodash',
    'platform': 'path/to/platform'
  }
},
['benchmark'], function(Benchmark) {/*...*/});

var Benchmark = require('benchmark');

var suite = new Benchmark.Suite;
suite.add('RegExp#test', function(){
  /o/.test('Hello World');
})
.add('String#indexOf', function(){
  'Hello World!'.indexOf('o') > -1;
})
.on('cycle', function(event){
  console.log(String(event.target));
})
.on('complete', function(){
  console.log('Fastest is ' + this.filter('fastest').map('name'));
})
.run({ 'async': true });

```

```
npm i --save benchmark
npm i --save microtime
```


