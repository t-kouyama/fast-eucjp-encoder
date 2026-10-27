# fast-eucjp-encoder

Fast EUC-JP(CP51932) encoder - About 2.6x to 7x faster than iconv-lite

## Installation

```bash
npm install fast-eucjp-encoder
```

## Usage

Browser
```html
<script src="https://cdn.jsdelivr.net/npm/fast-eucjp-encoder"></script>
```

ES Modules
```javascript
import eucjp from 'fast-eucjp-encoder';
```

CommonJS
```javascript
const eucjp = require('fast-eucjp-encoder');
```

Encode string to EUC-JP byte array
```javascript
const bytes = eucjp('Hello 世界');
console.log(bytes); // Uint8Array(10) [72, 101, 108, 108, 111, 32, 192, 164, 179, 166]
```

## Benchmark

Comparison with iconv-lite 0.7.3 (operations per second, Japanese text, Node.js 24)

| chars | fast-eucjp-encoder | iconv-lite | faster |
|------:|-------------------:|-----------:|-------:|
|    30 |          5,906,591 |    767,683 |  7.69x |
|   300 |            564,185 |    216,349 |  2.61x |
|  3000 |             83,207 |     26,356 |  3.16x |

About 2.6x to 7.7x faster than iconv-lite.

## Decoder?

```javascript
const text = new TextDecoder('euc-jp').decode(bytes);
console.log(text); // "Hello 世界"
```

## License

MIT
