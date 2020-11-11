---
sort: 1
---

# Conducts

Conducts within jimi are a logical workspace for you to build one or more jimiFlows.

jimi Conducts are:

* Multi-user
* Auto refreshing and saving

## New

1. Open "Administration -> Object Editor"
2. Click edit on "conduct"
3. Click "Create Object" in the upper left of the open tab
4. Complete at a minimum the "name" field and ensure "enabled" is set to true
5. On your keyboard press Control + S to the save the page - it will refresh and a banner will appear in green

## Open

1. Open "Conducts Editor"
2. Select by name the conduct you wish to edit

## Create Objects

Within an open Conduct:

1. Press "+" in the top right of the open tab next to "Export, Codify, Import"
2. Select within the empty dropdown box the object type
3. Press "Create"

The object will appear in the middle of the Conduct workspace 

## Import Existing Objects

Only objects that have a scope of 1,2 or 3 will appear in the existing objects box, if you object does not appear then check the object editor and ensure one of these values is defined.

Within an open Conduct:

1. Press "+" in the top right of the open tab next to "Export, Codify, Import"
2. Press "Existing"
3. Double click on any object you wish to import

The object will appear in the middle of the Conduct workspace 

*NOTE*

Imported objects are just reused objects if you change it, it will be changed everywhere it is used!

### Scope Values

Scope values do not affect object permissions. - If you dont have access to an object you wont be able to read it or use it.

| Value | Purpose |
--- | ---
0 | Cant be seen in existing objects
1 | Can be seen by the object creator within exiting objects
2 | Can be seen by the objects creators groups within exiting objects
3 | Can be seen by everyone within exiting objects

## Editing Objects

1. Right click on the object you wish to edit
2. Click "Edit"

*NOTE*
Within the object editor panel it is possible to use the following hotkeys:

| Action | Hotkey |
--- | ---
Save | Control + s
Exit | esc

## Deleting Objects

1. Right click on the object you wish to delete
2. Click "Delete"
3. Confirm the deletion on the prompt

*NOTE*
You can delete objects by selecting them and pressing del

| Action | Hotkey |
--- | ---
Delete | del

## Link Objects

Links are how you build jimiFlows, they allow you to build a flow chart like diagram that is used to control execution

1. Select the from object
2. While holding the "c" key select the to object

## Editing Link Logic

Link logic allows you to have fine grain control over what objects are executed under what conduction's.

1. Double click on a link

Supported link logic includes:

| Value | Description |
--- | ---
True | From object returned successfully
False | From object returned failure 
exitCode e.g. 0 | From object exit code matches the defined integer value e.g 0
If Logic | Logical conduction is met following jimi Logic definition e.g. if 1 == 1

## Deleting Links

1. Select the link you wish to delete
2. Press "del" on your keyboard

| Action | Hotkey |
--- | ---
Delete | del

