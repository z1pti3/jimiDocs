---
sort: 3
---

# Playbook

Playbooks are very useful and powershell objects that can define how often or how many times a jimiFlow is executed for a given occurrence. 

Common use-cases include configuration management, software deployment or one off tasks that need to be completed.

## Download

[Download](https://github.com/z1pti3/jimiPlugin-playbook)

## Install

```
wget https://github.com/z1pti3/jimiPlugin-playbook/archive/master.zip
unzip master.zip
mv jimiPlugin-playbook-master plugin/playbook
rm master.zip
```

## Triggers

### playbookSearch

Searches existing playbook entires and returns as events each playbook occurrence that matches the given parameters. Searching is completed based on playbook name, result and sequence number.

**Properties:**

| Name | Description |
--- | ---
playbookName | Name of the existing playbook
sequence | The sequence number that will be used to find existing playbook entries that are within the given sequence
inComplete | When set to true the trigger will return matches within the given playbook name and sequence that are not yet complete
excludeIncrementSequence | Remove any results that also have a higher sequence that is already marked as completed

**Returns:**

A list of events containing playbooks entries within the defined criteria 


## Actions

### playbookStart

Defines that start of a playbook along with options for how a playbook behaves

**Properties:**

| Name | Description |
--- | ---
playbookName | Name of the playbook, this much match between incremental sequence numbers
sequence | An integer value starting from 0 that can be used to build multi stage playbooks whereby in order playbooks must be completed from sequence 0 onwards. sequence 0 must be used on the first playbook and is the default value
occurrence | String value that will define what each unique entry is. This value supports jimi string replacement syntax
delayBetweenAttempts | Amount of time in seconds that must have past before the same occurrence can be attempted again. Default of 0 will result in a 60 seconds delay between attempts
maxAttempts | The maximum number of attempts
version | A defined version number of the playbook, when a version number is incremented all previous successful plays will be replayed
alwaysRun | When selected version and maxAttempts are ignored

**Returns:**

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
New play started | True | 201 | plugin : { "playbook" : { "match", "name", "occurrence", "sequence" } }
Already completed play replayed | True | 205 | { "playbook" : { "match", "name", "occurrence", "sequence" } }
Delay between attempts not met | False | 300 | { "playbook" : { "match", "name", "occurrence", "sequence" } }
Existing play reattempted | True | 302 | { "playbook" : { "match", "name", "occurrence", "sequence" } }
Nothing to do | False | 304 | { "playbook" : { "match", "name", "occurrence", "sequence" } }
Previous sequence number was attempted but was not successful | False | 403 | None
Sequence attempted to too high as no previous sequence was found | False | 404 | None
Unknown | False | 500 | None


### playbookEnd

Defines that end of a playbook along with the result and any defined resulting data

**Properties:**

| Name | Description |
--- | ---
result | True / False to define if the play was a success or failure
resultData | Dictionary supporting jimi string replacement syntax to preserve any of the jimiFlow data or to set a message or error 

**Returns:**

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Play attempt finished | True | 0 | None
Play complete failure | False | 404 | None
