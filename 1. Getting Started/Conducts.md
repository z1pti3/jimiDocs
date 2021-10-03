---
sort: 2
---

# Conducts

Conducts within jimi are a logical workspace for you to build one or more jimiFlows.

jimi Conducts are:

* Multi-user
* Auto refreshing and saving

## New

1. Navigate to the Conducts page
2. Click the "+" to open up a "Create new conduct" menu
3. Enter a name for the conduct, and optionally a description
![image](https://user-images.githubusercontent.com/14958920/125165168-b815b200-e18d-11eb-92e0-fc49700ade02.png)
4. Click the create button
5. You should now find your conduct listed on the page
![image](https://user-images.githubusercontent.com/14958920/125165202-e09dac00-e18d-11eb-8484-4a1e7b8c61b3.png)

## Open

1. Open "Conducts Editor"
2. Select by name the conduct you wish to edit

## Create Objects

Within an open Conduct:

1. Press "+" in the top right of the open tab next to ```Debug```, ```Export```, ```Codify``` and ```Import```
![image](https://user-images.githubusercontent.com/14958920/125165241-1347a480-e18e-11eb-9a65-c9fb12c7fb61.png)
3. Select within the empty dropdown box the object type
4. Press "Create"

The object will appear in the middle of the Conduct workspace, as shown in the example below
![image](https://user-images.githubusercontent.com/14958920/125165284-45f19d00-e18e-11eb-9447-be1878f94ad8.png)

## Import Existing Objects

Only objects that have a scope of 1,2 or 3 will appear in the existing objects box, if you object does not appear then check the object editor and ensure one of these values is defined.

Within an open Conduct:

1. Press "+" in the top right of the open tab next to ```Debug```, ```Export```, ```Codify``` and ```Import```
2. Press "Existing"
3. Double click on any object you wish to import
![image](https://user-images.githubusercontent.com/14958920/125170528-5104f700-e1a7-11eb-9deb-260785e632ba.png)

The object will appear in the middle of the Conduct workspace 

*NOTE*
Imported objects are just reused objects. If you change it, it will be changed everywhere it is used!

### Scope Values

Scope values do not affect object permissions. - If you dont have access to an object you wont be able to read it or use it.

| Value | Purpose |
--- | ---
0 | Cant be seen in existing objects
1 | Can be seen by the object creator within exiting objects
2 | Can be seen by the objects creators groups within exiting objects
3 | Can be seen by everyone within exiting objects

## Editing Objects

1. Right click on the object you wish to edit. Alternatively, double click on the object you wish to edit
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
You can also delete objects by selecting them and pressing the delete key on your keyboard

| Action | Hotkey |
--- | ---
Delete | del

## Link Objects

Links are how you build jimiFlows, they allow you to build a flow chart like diagram that is used to control execution

1. Select the object you want to go from
2. While holding the "c" key select the object you want to go to

![image](https://media1.giphy.com/media/DEtX0pRNkxMvBXs0tt/giphy.gif?cid=790b7611e6904791d5147cfb891ea79f9723b02df73f7d9c&rid=giphy.gif&ct=g)

## Editing Link Logic

Link logic allows you to have fine grain control over what objects are executed under what conduction's.

1. Double click on a link

Supported link logic includes:

| Value | Description | Colour in Flow
--- | --- | ---
True | From object returned as success | Green
False | From object returned as failure | Red
exitCode | From object exit code matches the defined integer value e.g 0 | Yellow
If Logic | Logical conduction is met following jimi Logic definition e.g. if 1 == 1 | Pink
\* | Wildcard, will always continue | Blue

## Deleting Links

1. Select the link you wish to delete
2. Press "del" on your keyboard

| Action | Hotkey |
--- | ---
Delete | del

