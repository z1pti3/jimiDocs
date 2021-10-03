---
sort: 5
---

# Functions

In addition to action logic, functions can be used anywhere that supports jimi's string replacement ```%%``` syntax

Example:
```
%%upper(data[event])%%
```
## Array

### index

Select a defined index of a given array:

`index(<array>,<index>)`

### append

Append a given value to the array

`append(<array>,<value>)`

### remove

Append a given value to the array

`remove(<array>,<index>)`

## Conversion

### strToInt

Convert a string into an integer:

`strToInt(<string>)` 

### strToFloat

Convert a string into an float:

`strToFloat(<string>)`

### strToBool

Convert a string into an boolean:

`strToBool(<string>)`

### intToStr

Convert a integer into a string:

`intToStr(<int>)`

### lower

Lowercase a string:

`lower(<string>)`

### upper

Uppercase a string:

`upper(<string>)`

### toJson

Convert a string to python dictionary:

`toJson(<string>)`

### fromJson

Convert a python dictionary into a string:

`fromJson(<dict>)`

### jsontoHtml

Convert JSON into a HTML format:

`jsontoHtml(<dict>,<wrap=False>)`

## Date and Time

### now

Get the current time as epoch:

`now(<milliseconds=False>)`

### day

Get the current day:

`day()`

### year

Get the current year:

`year()`

### month

Get the current month:

`month()`

### dt

Get the current dateTime by format

`dt(<format="%d-%m-%Y">)`

### dateBetween

Check if date is between given dates:

`dateBetween(<startDateStr>, <endDateStr>, <dateStr=None>)`

### timeBetween

Check if time is between given time:

`timeBetween(<startDateStr>, <endDateStr>, <dateStr=None>)`

## Maths

### sum

Sum the provided values

`sum(*args)`

### length

Get the length of a given variable:

`length(<var>)`

### roundNum

Return the given value as a rounded int:

`roundNum(<var>)`

### ceil

Return the given value as a rounded (up) int:

`ceil(<var>)`

### floor

Return the given value as a rounded (down) int:

`floor(<var>)`

### increment

Return the given value, incremented by another given value:

`increment(<var>,<by>)`

### decrement

Return the given value, decremented by another given value:

`decrement(<var>,<by>)`

## Network

### cidr

Is a given IP within a given cidr

`cidr(<address>, <addressRange>)`

### reverseDNS

Get DNS from a give IP:

`reverseDNS(<IPv4Address>)`

## Security

### encryptString

Encrypt a string with a given password:

`encryptString(<plaintext>, <secureString>)`

### decryptString

Decrypt a string with a given password:

`encryptString(<encryptedString>, <secureString>)`

## String

### contains

Is a string within a string:

`contains(<string>, <contents>)`

### split

Split a string but a substring:

`split(<string>, <spliton>, <position>)`

### strCount

Count the number of occurrences of a given substring within the given string:

`strCount(<string>, <searchString>)`

### join

Make a string by joining a list:

`join(<stringList>, <by=None>)`

### concat

Make a string by joining multiple inputs together:

`concat(<*args>)`

### strLower

Returned a string that has been converted to lowercase:

`strLower(<string>)`

### replace

Replace a value within a string based on a pattern and return the replaced string:

`replace(<string>, <match>, <replacement>)`

### strip

Strip leading and trailing whitespace, or by the character(s) provided:

`strip(<string>, <stripOn="">)`

### startsWith

Return a boolean representing if the string starts with the provided value:

`startsWith(<string>, <startswithString>)`

### endsWith

Return a boolean representing if the string ends with the provided value:

`endsWith(<string>, <endswithString>)`

