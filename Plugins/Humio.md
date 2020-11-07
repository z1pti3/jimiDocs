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

**Example Uses**

* SIEM type events to use in combination with jimi's correlation engine
* System performance monitoring ( CPU, Memory, Disk ), creating alerts when thresholds are met and even having different thresholds depending on the host
* Asset driven automation, drive automated software deployment or configuration management when an asset is seen online
* Security posture checking as devices connect to a VPN Humio can tell jimi who can then check the status of that asset
* Scheduled reports

## Actions

### humioSearch

**Properties:**

| Name | Description |
--- | ---

### humioIngest

**Properties:**

| Name | Description |
--- | ---
