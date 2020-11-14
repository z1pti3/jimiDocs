---
sort: 4
---

# Choice

jimi choice enables external input within a jimiFlow whereby you may ask a yes/no question and when answered the flow will continue

## Download

[Download](https://github.com/z1pti3/jimiPlugin-choice)

## Install

```
wget https://github.com/z1pti3/jimiPlugin-choice/archive/master.zip
unzip master.zip
mv jimiPlugin-choice-master plugin/choice
rm master.zip
```

## Actions

### choiceRequest

Ask for human input before proceeding.

**Properties:**

| Name | Description |
--- | ---
message | A yes/no question

**Returns:**

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Choice flow continue after a question was answered | True | 100 | None
Request for answer created | False | 300 | { "data" : { "token", "url" } }

