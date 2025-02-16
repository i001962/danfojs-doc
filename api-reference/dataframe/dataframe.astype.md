---
description: Cast column of a DataFrame to a specified dtype.
---

# DataFrame.astype

danfo.DataFrame.**astype**(options) \[[source](https://github.com/opensource9ja/danfojs/blob/cf5c7ae3a009458e61eedd18d9c9b5b6b10d5276/danfojs/src/core/frame.js#L125)]

| Parameters | Type   | Description                                                                                                                                                                                                                                                                                                | Default            |
| ---------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------ |
| options    | Object | <p>{</p><p><strong>column</strong>:  Array, label/column name of column to cast</p><p><strong>dtype</strong>: dtype to cast to. One of [string, float32, int32, boolean]</p><p><strong>inplace</strong>: Boolean indicating whether to perform the operation inplace or not. Defaults to false</p><p>}</p> | { inplace: false } |

**Returns:**

**       **return** DataFrame**

## **Examples**

### **Cast a float dtype column to int**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20.1, 30, 47.3, -20] ,
             "B": [34, -4, 5, 6],
             "C": [20.1, -20.23, 30.3, 40.11],
             "D": ["a", "b", "c", "c"] }

let df = new dfd.DataFrame(data)
df.print()
df.ctypes.print()

let df_new = df.astype({column: "A", dtype: "int32"})
df_new.print()

df.ctypes.print()
```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
//before casting
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ -20.1             │ 34                │ 20.1              │ a                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ -4                │ -20.23            │ b                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 47.3              │ 5                 │ 30.3              │ c                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ -20               │ 6                 │ 40.11             │ c                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ A │ float32              ║
╟───┼──────────────────────╢
║ B │ int32                ║
╟───┼──────────────────────╢
║ C │ float32              ║
╟───┼──────────────────────╢
║ D │ string               ║
╚═══╧══════════════════════╝


 //after casting

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ -20               │ 34                │ 20.1              │ a                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ -4                │ -20.23            │ b                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 47                │ 5                 │ 30.3              │ c                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ -20               │ 6                 │ 40.11             │ c                 ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ A │ int32                ║
╟───┼──────────────────────╢
║ B │ int32                ║
╟───┼──────────────────────╢
║ C │ float32              ║
╟───┼──────────────────────╢
║ D │ string               ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}

### **Casting a string column of numbers to int**

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20.1, 30, 47.3, -20] ,
             "B": [34, -4, 5, 6],
             "C": [20.1, -20.23, 30.3, 40.11],
             "D": ["20", "13", "45", "90"] }

let df = new dfd.DataFrame(data)
let df_new = df.astype({column: "D", dtype: "int32"})
df_new.print()

df_new.ctypes.print()


```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```
╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ -20.1             │ 34                │ 20.1              │ 20                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ -4                │ -20.23            │ 13                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 47.3              │ 5                 │ 30.3              │ 45                ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ -20               │ 6                 │ 40.11             │ 90                ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ A │ float32              ║
╟───┼──────────────────────╢
║ B │ int32                ║
╟───┼──────────────────────╢
║ C │ float32              ║
╟───┼──────────────────────╢
║ D │ int32                ║
╚═══╧══════════════════════╝

```
{% endtab %}
{% endtabs %}

**Note: **Casting a string column of alphabets/words to numeric form will return NaNs as values

{% tabs %}
{% tab title="Node" %}
```javascript
const dfd = require("danfojs-node")

let data = { "A": [-20.1, 30, 47.3, -20] ,
             "B": [34, -4, 5, 6],
             "C": [20.1, -20.23, 30.3, 40.11],
             "D": ["a", "b", "c", "c"] }

let df = new dfd.DataFrame(data)
let df_new = df.astype({column: "D", dtype: "int32"})
df_new.print()

df_new.ctypes.print()


```
{% endtab %}

{% tab title="Browser" %}
```
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Output" %}
```

╔═══╤═══════════════════╤═══════════════════╤═══════════════════╤═══════════════════╗
║   │ A                 │ B                 │ C                 │ D                 ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 0 │ -20.1             │ 34                │ 20.1              │ NaN               ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 1 │ 30                │ -4                │ -20.23            │ NaN               ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 2 │ 47.3              │ 5                 │ 30.3              │ NaN               ║
╟───┼───────────────────┼───────────────────┼───────────────────┼───────────────────╢
║ 3 │ -20               │ 6                 │ 40.11             │ NaN               ║
╚═══╧═══════════════════╧═══════════════════╧═══════════════════╧═══════════════════╝

╔═══╤══════════════════════╗
║   │ 0                    ║
╟───┼──────────────────────╢
║ A │ float32              ║
╟───┼──────────────────────╢
║ B │ int32                ║
╟───┼──────────────────────╢
║ C │ float32              ║
╟───┼──────────────────────╢
║ D │ int32                ║
╚═══╧══════════════════════╝
```
{% endtab %}
{% endtabs %}
