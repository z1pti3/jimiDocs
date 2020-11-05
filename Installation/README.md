---
sort: 1
---

# Installation

Installing jimi is simple and we offer step by step instructions for both manual and docker deployment options. 


Reconmended: Docker


## Cluster Support


Creating a jimi cluster is as simple as install jimi twice and adjusting the settings.json file for each node.


1. Install jimi
2. Ensure all plugins and data files are copied and are the same
3. Update settings.json so that the systemID is unique

Change the below 0 -> 1

'''
    "system" : {
        "systemID" : 0,
        "accessAddress" : "127.0.0.1",
        "accessPort" : 5000
    },
'''


'''
    "system" : {
        "systemID" : 1,
        "accessAddress" : "127.0.0.1",
        "accessPort" : 5000
    },
'''


4. Ensure that all jimiWeb instances can talk to the exposed API of jimiCore (jimiCore does not need to talk to other jimiCore deployments)
