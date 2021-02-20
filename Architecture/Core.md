---
sort: 2
---

# Core

jimi_core is the brains and is responsible for running all automation flows. jimi_core only requires communication to the mongo database and can be deployed into a cluster for high availability and ob distribution.

Each jimi_core instance runs with its own cache and distribution only enables the system to spread the running of jimiFlows, it does not enable a single running flow to the balanced across all instances. Options exist to group jimiFlows so that they always exist and run on the same jimi_core instance.


flowData - Persistent for a given flow within an event

eventData - Persistent for a given event

persistentData - Persistent for a given trigger

