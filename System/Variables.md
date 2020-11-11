---
sort: 1
---

# Variables

jimi has the ability to define jimiFlow scoped variables that can then be referenced throughout the rest of the jimiFlow.

Variables set during a jimiFlow are persistent only during the execution of a single event within a single jimiFlow.

## Set

To set a variable you must currently define it within an objects varDefinitions property field.

varDefinitions are defined within this property field as json the key being the name of the variable being define and a value key within a dictionary value e.g.

`{ "VAR_NAME" : { "value" : "VAR_VALUE" } }`

On the above example you would replace VAR_NAME and VAR_VALUE with your variable name and variable value. 

Values within variables in jimi can be:

* str
* int
* bool
* list
* dict

### Examples

Set a variable called "int1" to the value of 1: 

`{ "int1" : { "value" : 1 } }`


Set a variable called "list1" to the value of [0,1]: 

`{ "list1" : { "value" : [0,1] } }`


Set a variable called "dict1" to the value of { "a" : 1, "b" : 2 }: 

`{ "dict1" : { "value" : { "a" : 1, "b" : 2 } } }`

Dictionary values can also be expanded on future objects e.g.

On the first action we set "dict1" to { "a" : 1 }

`{ "dict1" : { "value" : { "a" : 1 } } }`

Currently "dict1" has a value of { "a" : 1 }

If on another object occurrence in the jimiFlow after the first we set "dict1" to { "b" : 2 }

`{ "dict1" : { "value" : { "b" : 2 } } }`

Now "dict1" has a value of { "a" : 1, "b" : 2 } as  { "b" : 2 } was appended to the existing value of "dict1"

## Get

jimi permits values to be used in any location that jimi string replacement syntax is permitted.

To access variables you could use %%data[var][VAR_NAME]%% within a field that supports jimi string replacement syntax

### Examples

If "init1" was set as above then we would access it as follows:

`%%data[var][init1]%%`

