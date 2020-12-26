---
sort: 5
---

# Logic

All action objects within jimiflows support logic that is evaluated before an action is executed.

![Screenshot](https://github.com/z1pti3/jimi/blob/v1.1/examples/screenshots/screenshot5.png)

The following example checks if the event dictionary set by the trigger has an ip key and it is equal to 127.0.0.1

`if data[event][ip] == "127.0.0.1"`

Logic supports standard python symbols !=, >, <, ==, (, ), and, or

Logic can reference any part of the data dictionary passed along the jimiflow

Jimi functions can also be used e.g. `if lower(data[event][ip]) == "127.0.0.1"`

Jimi preforms automatic type casting on variables before he attempts to use them e.g. "1" as a string will be converted automatically to an int

## Match ( Regex )

jimi can carry out regex checks on strings as follows:

if "192.168.0.1" match "^[0-9]{1,3}\.0-9]{1,3}\.0-9]{1,3}\.0-9]{1,3}$"

if "192.168.0.1" not match "^[0-9]{1,3}\.0-9]{1,3}\.0-9]{1,3}\.0-9]{1,3}$"
