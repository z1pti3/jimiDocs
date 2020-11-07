---
sort: 1
---

# First Flow


Login to jimi

Navigate to "Administration" -> "Object Editor"

Click "conduct"

Click "Create Object"

Set a name and change enabled from "false" to "true"

Press "control+s" to save the page

Refresh jimi within your browser

Navigate to "Conducts Editor" -> ""

Press the "+" within the top right

Select "trigger" press "Create"

Double click on the object that was added to your page

Set a name

Set a schedule for running the trigger this can be in the following example formats: 1-5s, 60s, cron ( for the example use 10s )

Click log and enabled

Press Save

Press the "+" within the top right

Select "action" press "Create"

Drag the object away from the trigger

Double click the object and set a name, and enable log then press "control+s"

Select the trigger, hold down the c key and then click the action a link should be formed

Wait 60 seconds so that the jimi_core system detects the change

Navigate to "Audit"

If all has gone well you should see your trigger running and the action being called. Your now ready to build a real flow with real objects. - Remember to download and install the plugins you require in order to enable the actions and triggers you want to use.