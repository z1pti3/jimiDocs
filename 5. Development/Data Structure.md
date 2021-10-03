---
sort: 1
---

# Data Structure

jimi flows are powered by json data passed between and manipulated by objects within the flow. json data is broken into 4 parent dictionaries:  

flowData - Persistent for a given flow within an event

eventData - Persistent for a given event

conductData - Persistent for a given conduct across multiple triggers executed

persistentData - Persistent for a given executed flow no matter the event, conduct or trigger executed

jimi uses a function within the parent conduct class to define the data template ( "def dataTemplate(...)" )


```
{
    "flowData" : {
        "var" : { },
        "plugin" : { }
    },
    "eventData" : {
        "var" : { },
        "plugin" : { }
    },
    "conductData" : {
        "var" : { },
        "plugin" : { }
    },
    "persistentData" : {
        "var" : { },
        "plugin" : { },
        "system" : {
            "trigger" : None,
            "conduct" : None
        }
    }
}
```

With the exception of "system" within "persistentData" all other defined child dictionaries ( "var", "plugin" ) only support native types ( string, int, float, bool, list, dictionaries ) and cannot be used to store other objects or classes. If you require other types you must create an additional child item within one of the parent dictionaries. You should avoid modifying "system" data within "persistentData" as it is critical for jimi to execution a give flow.