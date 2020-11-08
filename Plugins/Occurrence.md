---
sort: 2
---

# Occurrence

Occurrence can be used to get jimi to take actions based on state. This enables you to have alarm like functionality when something is first notice, updated and/or cleared.

## Download

[Download](https://github.com/z1pti3/jimiPlugin-occurrence)

## Install

```
wget https://github.com/z1pti3/jimiPlugin-occurrence/archive/master.zip
unzip master.zip
mv jimiPlugin-occurrence-master plugin/occurrence
rm master.zip
```

## Actions

### occurrence

Alarm and state functionality for a jimiFlow

**Properties:**

| Name | Description |
--- | ---
dbSlowUpdate | When enabled an occurrence is only updated when half of its lullTime has passed. If lullTime is set to 300 the occurrence would only get update when 150 seconds have past
lullTime | The amount of time in seconds that an occurrence is considered in alarm state. Each time occurrence see the same state it will extend the lullTime
lullTimeExpiredCount | The number of times the raising trigger must be checked after lullTime has expired before the occurrence is cleared i.e. no longer in alarm state
occurrenceMatchString | A string that is used to understand what is a unique match. occurenceMatchString supports jimi string replacement syntax e.g. %%data[event][host]%%-%%data[event][metric]%%-CPU  

**Returns:**

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
New occurrence raised | True | 201 | None
Existing occurrence updates | True | 302 | None
Occurrence cleared | True | 205 | None
Error updating occurrence - no ID | True | 500 | None
