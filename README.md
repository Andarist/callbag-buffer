# callbag-buffer

Callbag operator which buffers source values until separator stream emits.

## Example

```js
import buffer from 'callbag-buffer'
import forEach from 'callbag-for-each'
import fromEvent from 'callbag-from-event'
import map from 'callbag-map'
import pipe from 'callbag-pipe'

const btn = document.getElementById('#release')

pipe(
  fromEvent(document, 'click'),
  map(() => Math.floor(Math.random() * 100))
  buffer(fromEvent(btn, 'click')),
  forEach(values => {
  	console.log(values) // [86, 93, 57, 64] ...
  })
)
```
