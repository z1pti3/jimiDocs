---
sort: 1
---

# Functions

In addition to action logic functions can be used anywhere that supports jimi's string replacement %% synatax

Example:
```
%%upper(data[event])%%
```

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

## Network

### cidr

Is a given IP within a given cidr

`cidr(<address>, <addressRange>)`

### reverseDNS

Get DNS from a give IP:

`reverseDNS(<IPv4Address>)`

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
