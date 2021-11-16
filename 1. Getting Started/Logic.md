---
sort: 6
---

# Logic

jimi logic makes your flows come alive by allowing you to make decisions based on the data returned from objects. All action objects within jimiflows support logic that is evaluated before an action is executed. Within jimi we apply logic can be applied in a number of ways:

* Actions
* Links
* Variables

Logic supports standard python symbols !=, >, <, ==, (, ), and, or

Within actions we use the logicString field:

![image](https://user-images.githubusercontent.com/66521110/142067434-c792966f-a30a-431a-a1fd-a80566a9f84d.png)

Action logic is tested before a given action is executed.

Links from within the Link Logic field on the link editor that can be accessed by double clicking on the line between objects:

![image](https://user-images.githubusercontent.com/66521110/142067484-28db2428-49b1-4ea5-a3a0-3e81ddd95354.png)

Link logic is tested before a link is used.

Lastly variable logic is done during the definition of varDefintions from within the object editor:

![image](https://user-images.githubusercontent.com/66521110/142067510-03d3a6db-2526-47bf-93c2-6555b768e6c1.png)

Variable logic is tested before a variable is defined.

To define logic we will always used the if statement and within jimi if statements loosely follow the same format as standard python if statements. i.e. setting “if  1 == 1” within any of the fields mentioned will always evaluate to true but highlights how if statements are defined.  

![image](https://user-images.githubusercontent.com/66521110/142067536-e90820f3-2eac-4ab4-9e58-703b915dd03d.png)

You will notice in the above screenshot how each field should look for the if statement if 1 == 1. varDefintions is the most complicated and supports two formats:

**Standard:

Single if statement and the value will only be deployed if the logic is true.

{ “varName” : { “value” : “var_value”, “if” : “if 1 == 1 ” } }

**Multiple:

Evaluate if logic in order and the first match is used to define the value. You can also put in a value at the end within the if key to define a fall-back value if none of the logic returns true. 

{ “varName” : [{ “value” : “var_value”, “if” : “if 1 == 1 ” },{ “value” : “var_value”, “if” : “if 1 == 1 ” }] }

Logic within jimi supports groups, regex, in and functions some examples are provided:

**Groups

if (1 == 1 or 2 == 2) and 1 == 2

**Regex:

if “test” match “[a-z]*”

if “test” not match “[0-9]*”

**In:

if “test” in “this is a test”

if “test” not in “this is a test”

**Functions:

if lower(“TEST”) == “test”

The most important part of logic has been left for last and is related to how you access data within the executed flow. jimi passes json data into and out of each object which can be accessed using:

data

eventData

conductData

persistentData

Each of these objects are json objects that are accessed just like within python i.e. data[var][varName]

The structure of each of these objects is:

{  “var” : {}, “plugin” : {} }

data has two extra very important keys:

event –  Which is event and the event object contains all of the data first passed into a jimi flow

action – Which is the action data returned from the last action that was executed within a jimi flow

**Examples:

if data[event][server] == “serverName”

if lower(data[event][server]) == “servername”

if data[var][varName] in data[action][data]

