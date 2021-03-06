---
title: Option from_line
navtitle: from_line
description: Option "from_line" handles records starting from a requested line number.
keywords: ['csv', 'parse', 'options', 'columns']
sort: 4
---

# Option `from_line`

The `from_line` handles records starting from a requested line number with the first line being `1`.

* Type: `number`
* Optional
* Default: `1`
* Since: 4.0.0

## Simple example with inferred column names

This [example](https://github.com/adaltas/node-csv-parse/blob/master/samples/option.from_line.js) skip the first lines and return records after the second line. The first records is used to determine column names:

```js
const parse = require('csv-parse')
const assert = require('assert')

parse(`
x,x
a,b
1,2
`.trim(), {
  columns: true,
  from_line: 2
}, function(err, records){
  assert.deepEqual(
    records, [{
      a: '1',
      b: '2'
    }]
  )
})
```
