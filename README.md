![](https://echorial.com/Images/carpeg.png)

![https://www.echorial.com](https://img.shields.io/badge/carbon-v1.0-blue.svg?label=carbon&colorB=2e3d6b&style=flat-square)
![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/Echorial/carpeg.svg?style=flat-square)
![GitHub last commit](https://img.shields.io/github/last-commit/Echorial/carpeg.svg?style=flat-square)
![license](https://img.shields.io/github/license/Echorial/carpeg.svg?style=flat-square)

A simple parser generator inspired by [Peg.js](https://girhub.com/pegjs/pegjs)

# Tutorial

## Installation
```
$ npm install carpeg-cli
```

## Basic parser
``` js
// myParser.cpeg
import WhiteSpace;
import String;

map|start = "~" _ items: Item*|"|" _ "~" {items: {$items}};

map|Item = _ value: ([0-9] / String)
{map|
	export = $value;
};

```

## Generating
```
$ carpeg generate myParser.cpeg myParser.js --target javascript
```

## Parser usage
``` js
const myParser = require("myParser.js");
myParser.parse("~ 1|3|4|'Hello' ~") // Array(1, 3, 4, "hello")
```

---

## Platform support
![https://www.echorial.com](https://img.shields.io/badge/php-full-green.svg?style=flat-square)
![https://www.echorial.com](https://img.shields.io/badge/javascript-full-green.svg?style=flat-square)