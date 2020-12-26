---
sort: 7
---

# FuzzyMatch

Access to VirusTotal APIs from within a jimiFlow

## Download

[Download](https://github.com/z1pti3/jimiPlugin-fuzzymatch)

## Install

```
wget https://github.com/z1pti3/jimiPlugin-fuzzymatch/archive/master.zip
unzip master.zip
mv jimiPlugin-fuzzymatch-master plugin/fuzzymatch
rm master.zip
```

## Actions

### fuzzymatchString

Checks for likeness between two given strings i.e. test and t3st

**Properties:**

| Name | Required | Replacement Syntax | Description |
--- | ---
checkString | True | True | String1
matchString | True | True | String2

**Returns:**

Returns True if the two strings are alike

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Not alike | False | 0 | None
alike | True | 0 | None
Very far apart | False | 21 | None

### fuzzymatchList

Checks a string for likeness to a given list i.e. t3st in [hello, test, none] 

**Properties:**

| Name | Required | Replacement Syntax | Description |
--- | ---
checkString | True | True | String1
matchList | True | True | List of strings

**Returns:**

Returns True if the string is alike to any string in the provided list

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Not alike | False | 0 | None
alike | True | 0 | None
Failure | False | 1 | None

### fuzzymatchLevenshteinDistance

Uses Levenshtein Distance to check two strings 

**Properties:**

| Name | Required | Replacement Syntax | Description |
--- | ---
checkString | True | True | String1
matchString | True | True | String2
matchAboveScore | True | False | Min score for which True is returned when the match score is above

**Returns:**

Returns True if the score is above the matchAboveScore value provided

| Name | Result Bool | Return Code | Other |
--- | --- | --- | ---
Not alike | False | 0 | { "score" : int() }
alike | True | 0 | { "score" : int() }
