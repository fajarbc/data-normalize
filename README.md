# Data Normalize

## Description
A modified version for [andreamangano/normalize-data](https://github.com/andreamangano/normalize-data).

Library to normalize data structure changes, include Map object.

## Usage 
- CJS
  ```javascript
  const { normalize } = require("data-normalize")
  ```
- ESM
  ```javascript
  import { normalize } from "data-normalize";
  ```


```javascript
import { normalize } from "data-normalize";

const originObjectMap = {
    name: new Map([
        ["first", "Fajar"],
        ["last", "BC"],
    ]),

};

function transformToFullname(name) {
return `${name.get("first")} ${name.get("last")}`;
}

console.log(normalize(originObjectMap, [["fullname", "name", transformToFullname]], true))
/**
 * Output
 * { fullname: 'Fajar BC' }
 */
console.log(normalize(originObjectMap, [["name", "name.first"]]))
/**
 * Output
 * { name: 'Fajar' }
 */
```