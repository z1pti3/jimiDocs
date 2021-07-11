---
sort: 1
---

# First Flow

_We've also released a video of this tutorial! Check it out at https://youtu.be/g-Eo6qMQGoE_

### Creating your first conduct
Login to jimi

If this is a brand new instance of jimi, you might see a status page similar to the below
![image](https://user-images.githubusercontent.com/14958920/125165125-843a8c80-e18d-11eb-8c97-7a13590ddd0f.png)

Navigate to the Conducts page

Click the "+" to open up a "Create new conduct" menu

Enter a name for the conduct, and optionally a description
![image](https://user-images.githubusercontent.com/14958920/125165168-b815b200-e18d-11eb-92e0-fc49700ade02.png)

Click the create button

You should now find your conduct listed on the page
![image](https://user-images.githubusercontent.com/14958920/125165202-e09dac00-e18d-11eb-8484-4a1e7b8c61b3.png)

### Creating your first objects
To navigate to the conduct, click on the name of the conduct

This will bring up a blank looking page

Press the "+" within the top right. This will show the "Create New Object" box
![image](https://user-images.githubusercontent.com/14958920/125165241-1347a480-e18e-11eb-9a65-c9fb12c7fb61.png)

Search for "trigger" in the search box, and once selected press "Create"

This will place a grey box on your screen. This is your first object within jimi!
![image](https://user-images.githubusercontent.com/14958920/125165284-45f19d00-e18e-11eb-9447-be1878f94ad8.png)

Double click on the object that was added to your page. This will bring up a the object properties windows, where you can customise your trigger
![image](https://user-images.githubusercontent.com/14958920/125165368-80f3d080-e18e-11eb-9706-bd00954dd143.png)

Set a name, this will be visible within the GUI

Set a schedule for running the trigger. This can be in the following example formats: 1-5s, 60s, cron ( for the example use 10s )

Tick enabled. Without this, the trigger won't ever be scheduled or run

Press Save, or hit CTRL-S

You will notice the box changes colour to black. This means it is now enabled. You will also see three numbers above the name. The first number represents the system the trigger is scheduled to run on. The second number (after the decimal) represents which CPU core on the system is being used. The third number represents a clusterSet the trigger is within. If a trigger is within a clusterSet greater than 0, jimi will attempt to make all triggers with the same number run on the same system.
![image](https://user-images.githubusercontent.com/14958920/125165553-5d7d5580-e18f-11eb-940f-712b5a3cfaa9.png)

You may notice the trigger flashes green every 10s. This is how you can visually see on the conduct when the trigger is currently running
![image](https://user-images.githubusercontent.com/14958920/125165635-b5b45780-e18f-11eb-9581-ed78460801b7.png)

Press the "+" within the top right to open the "Create New Object" box again

This time, select "action" and press "Create"

You will notice that the action does not appear as a grey box, but a black box. This is because by default actions are not disabled, as they won't do anything without first being triggered within a flow or via the debugger.

Drag the object away from the trigger

Double click the object and set a name, then save the object

###Creating a flow

In order for the objects to be able to work in a flow, they must first be connected. 

To do this, select the trigger, hold down the "c" key and then click the action. A link should be formed
![image](https://user-images.githubusercontent.com/14958920/125165715-1774c180-e190-11eb-8cf8-9b3b55d28112.png)

This link is coloured green, which represents "True". This is explained further in https://z1pti3.github.io/jimiDocs/System/Conducts.html#link-objects 

You have now created your first flow! It might not do anything yet, but you have already learned the basic steps in order to create flows within jimi.

### Viewing your flow in action
In order to see what your flow is doing, the easiest way is to view the flow in debug mode. To do this, click the debug icon in the top right (near the "+" used for adding objects). This will open a new tab, which will look similar to the below
![image](https://user-images.githubusercontent.com/14958920/125166029-94ed0180-e191-11eb-86ea-1c2f5b514e22.png)

You can now manually run the flow by clicking on the trigger, right clicking and selecting run
![image](https://user-images.githubusercontent.com/14958920/125166049-a9c99500-e191-11eb-838a-ef7f11a76046.png)

This should bring up a black box with the name of your trigger in the executed-flows window in the top left. By clicking on this you will see action appears when the box is expanded

![image](https://user-images.githubusercontent.com/14958920/125166081-cf569e80-e191-11eb-9839-50fb010e2121.png)

You will also notice that after clicking on the box you can see some output in the data-in box in the bottom left. This shows that the trigger generated an event with the value of ```{"tick": true}```. This is because the default trigger object generates this value so that the flow has some data to start with. Other plugins that create their own triggers will contain other data within here.
![image](https://user-images.githubusercontent.com/14958920/125166135-18a6ee00-e192-11eb-8a2e-b1db51ba36ed.png)

If you now click on the next box ("My First Action" in this example), you will find more data populated within the data-in box, as well as the data-out box.
![image](https://user-images.githubusercontent.com/14958920/125166158-3c6a3400-e192-11eb-91da-7253383c754d.png)

Although there is a lot of information in here that is past the point of this tutorial, the main bit to focus on is that within ```flowData```. You will notice that the tick value is there, under ```event```, being passed in from the trigger. You will also see ```action``` is added to to the flow, with any output from our action added into the flow in data-out. As this action doesn't do anything there isn't much here to see, but hopefully you can start to understand how the flow passes data between one object and the next.

### Conclusion
Congratulations, you have succesfully built your first flow within jimi! You have also begun to see how different objects such as triggers and actions work, and how they can be viewed within the debugger.

Remember to download and install the plugins you require in order to enable the actions and triggers you want to use.
