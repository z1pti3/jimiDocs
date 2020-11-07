---
sort: 1
---

# Variables

Every object within a jimiFlow permits variable setting after it has run. 

![Screenshot](https://github.com/z1pti3/jimi/blob/v1.1/examples/screenshots/screenshot4.png)

The following example will set a variable called ip to the current value of the dictionary data[event][ip] set by the trigger starting the jimiflow

`{"ip":{"value":"%%data[event][ip]%%"}}`

Variables support str, int, float, list, dict but must follow the standard setting format `{ "<VARName>" : { "value" : <VARVALUE> }`

Set variables are only persistent for a given flow and can be accessed within `data[var][<VARName>]`