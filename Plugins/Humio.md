---
sort: 1
---

# Humio

Unlock the power of your data with the Humio plugin for jimi

By using Humio and jimi together you can achieve functionality similar to that of IBM resilience or Splunk Phantom

## Download

[Download](https://github.com/z1pti3/jimiPlugin-humio)

## Install

```
wget https://github.com/z1pti3/jimiPlugin-humio/archive/master.zip
unzip master.zip
mv jimiPlugin-humio-master plugin/humio
rm master.zip
```

## settings.json ( Optional )

To avoid having to set the Humio API settings in every jimi object you can configure it globally within the settings.json file

```
humio : {
  "host": "<host>",
  "port": <port>,
  "apiToken": "<apiToken>",
  "secure" : <true/false>, - Optional
  "ca" : "<CAPATH>", - Optional
  "requestTimeout": <TimeoutValue> - Optional
}
```

## Triggers

### humio

jimi will use this trigger to follow Humio for a list of events, each event is then passed down the jimiFlow from action to action

**Properties:**

| Name | Description |
--- | ---
humioOverriseSettings | When enabled the settings.json file is ignored and "humioTimeout,humioAPIToken,humioPort,humioHost" are used to connect to your humio instance 
humioTimeout | Request timeout in seconds, the amount of time to wait for the Humio web server to respond
humioAPIToken | A user search API token obtained from your users settings in Humio
humioPort | TCP port number to connect to the Humio instance
humioHost | Host DNS or IP address to connect to the Humio instance
onlyNew | When enabled jimi will only return new events since the last API poll, @timestamp must be within the events returned by Humio
searchLive | Setup and use a live Humio job, this is recommended if jimi is going to be requesting the data frequently from Humio
searchEnd | Optional end time for the search e.g. 1h
searchStart | How far back to search e.g. 2h
searchRepository | Which repository within Humio is use for the search
searchQuery | Your Humio search query

**Returns:**

A list of events that are passed one at a time along the attached jimiFlows

**Example Uses**

* SIEM type events to use in combination with jimi's correlation engine
* System performance monitoring ( CPU, Memory, Disk ), creating alerts when thresholds are met and even having different thresholds depending on the host
* Asset driven automation, drive automated software deployment or configuration management when an asset is seen online
* Security posture checking as devices connect to a VPN Humio can tell jimi who can then check the status of that asset
* Scheduled reports

## Actions

### humioSearch

Same as humio trigger but is an action version

**Properties:**

| Name | Description |
--- | ---
humioOverriseSettings | When enabled the settings.json file is ignored and "humioTimeout,humioAPIToken,humioPort,humioHost" are used to connect to your humio instance 
humioTimeout | Request timeout in seconds, the amount of time to wait for the Humio web server to respond
humioAPIToken | A user search API token obtained from your users settings in Humio
humioPort | TCP port number to connect to the Humio instance
humioHost | Host DNS or IP address to connect to the Humio instance
onlyNew | When enabled jimi will only return new events since the last API poll, @timestamp must be within the events returned by Humio
searchLive | Setup and use a live Humio job, this is recommended if jimi is going to be requesting the data frequently from Humio
searchEnd | Optional end time for the search e.g. 1h
searchStart | How far back to search e.g. 2h
searchRepository | Which repository within Humio is use for the search
searchQuery | Your Humio search query

**Returns:**

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Failed to poll Humio job | False | -1 | None
Success | True | 0 | "humio" : { "searchQuery", "searchRepository" }


### humioIngest

Enables events to be sent by jimi to Humio, this action requires settings.json to be defined

**Properties:**

| Name | Description |
--- | ---
custom_time | When enabled time_field is used to extract the time to send to Humio alongside the event 
time_field | Field name within the dictionary to use as a source of time
field | When defined is used to build a custom event. e.g. [{"time":"00:00:01","type":"abc"}], the field can only contain 1 dictionary event and supports jimi string replacement %% syntax. If blank the event defaults to the data dictionary
flatten_field | A field within data that is compressed to the top of data e.g. event
humio_ingest_token | Humio ingest API token
humio_repo |  Humio repo to send the data

**Returns:**

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Failed to send data list | False | 1 | None
Failed to send data dict | False | 2 | None
Success | True | 0 | None

