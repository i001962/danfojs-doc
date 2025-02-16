---
description: round off floating values in series
---

# Series.round

> danfo.Series.round(dp, options)     \[[source](https://github.com/opensource9ja/danfojs/blob/master/danfojs/src/core/series.js#L404)]

| Parameters | Type   | Description                                                                                    | Default                               |
| ---------- | ------ | ---------------------------------------------------------------------------------------------- | ------------------------------------- |
| dp         | int    | decimal place to round off to                                                                  |                                       |
| options    | Object | inplace: Boolean indicating whether to perform the operation inplace or not. Defaults to false | <p>{</p><p>inplace: false</p><p>}</p> |

**Returns: **Series

**Example**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data1 = [30.21091, 40.190901, 3.564, 5.0212]
let sf1 = new dfd.Series(data1)

sf1.round(2).print()
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ 0 │ 30.21                ║
╟───┼──────────────────────╢
║ 1 │ 40.19                ║
╟───┼──────────────────────╢
║ 2 │ 3.56                 ║
╟───┼──────────────────────╢
║ 3 │ 5.02                 ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

