---
sort: 1
---

# Plugins

Out of the box jimi is nothing more than a few building blocks. jimi uses plugins to come alive providing vast flexibility through a flexible structured plugin system.

View Plugins: [Plugins](https://github.com/topics/jimiplugin)

## Installing Plugins

Download the plugin and extract it into the plugin folder, after doing this you will need to restart jimi.

If you are running jimi in a cluster then make sure you install the plugin to all jimi instances.

### Example

From within the jimi root directory or the directory containing the jimi plugin folder

```
wget https://github.com/z1pti3/jimiPlugin-humio/archive/master.zip
unzip master.zip
mv jimiPlugin-humio-master plugin/humio
rm master.zip
```

The folder name of the plugin MUST match the plugin name - this can be found by looking at the .py file within the plugin in the example above it would be humio.py

You may find that some plugins required additional python modules. If this is the case you will need to install them on your jimi instance/s

`pip install -r requirements.txt`


## Recommended Plugins

Bring jimi alive by installing our recommended plugins

| Name | Description |
--- | ---
Humio | API integration with Humio event log management, this enables searching and ingest giving jimi the ability to make your data come alive by taking automated actions based on event data
Remote | Ansible style automation using SSH and WINRM to take control of remote systems
Occurrence | Alarm functionality granting jimi the ability to carry out actions upon state i.e. raise, update and clear
Event | SIEM correlation engine
api | HTTP/S calls to custom APIs
playbook | Version controlled management ideal for configuration management whereby a config can be deployed once based on a given version number and redeployed when changes are made to the flow
subflow | Reuse jimiFlows, just like function calls in a programming language 
script | Direct access to run python code within a jimiFlow
email | Enables jimi to construct and send email messages via an SMTP relay

