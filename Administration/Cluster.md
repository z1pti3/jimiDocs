---
sort: 2
---

# Cluster

Creating a jimi cluster is as simple as install jimi twice and adjusting the settings.json file for each node.


1. Install jimi
2. Ensure all plugins and data files are copied and are the same
3. Update settings.json so that the systemID is unique

Change the below 0 -> 1

```
    "system" : {
        "systemID" : 0,
        "accessAddress" : "127.0.0.1",
        "accessPort" : 5000
    },
```


```
    "system" : {
        "systemID" : 1,
        "accessAddress" : "127.0.0.1",
        "accessPort" : 5000
    },
```


Ensure that all jimi instances can talk to the API interfaces by default 5000 for jimi_core and 4443 for jimi_web
