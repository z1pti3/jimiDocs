---
sort: 1
---


# Architecture

jimi is split into two separate components jimi_core and jimi_web. Each component can be deployed separately however all components require access to the mongo database and jimi_web must have API communication access to all instants of jimi_core.


## Future Changes

* Replacement web client from Jquery components to react
* Planned for release 3.0 will provide options to remove database exposure for the jimi_web component so that three tier architecture principles can be adhered to during the deployment options that split components across multiple computer nodes. 