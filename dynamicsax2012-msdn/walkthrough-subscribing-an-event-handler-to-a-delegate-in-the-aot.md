---
title: 'Walkthrough: Subscribing an Event Handler to a Delegate in the AOT'
TOCTitle: 'Walkthrough: Subscribing an Event Handler to a Delegate in the AOT'
ms:assetid: dc988de2-74ed-467c-91d1-7279a8684fb6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg864387(v=AX.60)
ms:contentKeyID: 35252080
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Subscribing an Event Handler to a Delegate in the AOT 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX you can use the AOT to make a method be an event handler for a delegate.

The tasks in this topic are as follows:

  - Add a delegate to a class

  - Add an event handler to a class

  - Add a public method that calls the delegate

  - Run a job that calls the public method

## Prerequisites

To complete the tasks in this walkthrough you need to understand the following topics:

  - [How to: Create Tables](how-to-create-tables.md)

  - [Event Handler Nodes in the AOT](event-handler-nodes-in-the-aot.md)

## Add a Delegate to a Class

In the AOT, you can add a delegate to a class. Do as follows:

1.  In the AOT, create a class named **TestDelegateClass**.

2.  Right-click the **TestDelegateClass** node and then click **New** \> **Delegate**.

3.  Right-click the delegate node, and then click **Edit**. This starts the X++ **Editor** window.

4.  In the **Editor** window, name the delegate reportColorDelegate.

5.  In the **Editor** window, make the delegate input one parameter of type str.

6.  Save the delegate.

## Add an Event Handler to a Class

You can add a method to a class, and then you can subscribe the method to a delegate. Do as follows:

1.  Right-click the **TestDelegateClass** node and then click **New** \> **Method**.

2.  Right-click the method node, and then click **Edit**.

3.  In the **Editor** window, name the method reportColorEH.

4.  In the **Editor** window, make the modifiers be static public.

5.  Make the input parameters be the same as for the earlier delegate.

Here is an example of what the X++ code should look like.
```X++  
    static public void reportColorEH(str _color)
    {
        info(strFmt("%1 is the color value in the event handler.",_color));
    }
```
## Subscribe the Method to the Delegate as an Event Handler

You can subscribe the **reportColorEH** method to the **reportColorDelegate** delegate as an event handler. Do as follows:

1.  Highlight the node for the **reportColorEH** method.

2.  Use the mouse to drop the **reportColorEH** node onto the **reportColorDelegate** delegate node.

## Add a public Method that Calls the Delegate

You can add a public method that calls the delegate. The X++ code in the method must look similar to the following code example.
```X++  
    public void callTheDelegate()
    {
        this.reportColorDelegate("red");
    }
```
## Run a Job that Calls the public Method

You can write and run a job that calls the public method that calls the delegate. Do as follows:

1.  In the AOT, right-click the node **AOT** \> **Jobs**, and then click **New job**.

2.  In the code **Editor** window, enter X++ code that is similar to the following.
    ```X++  
        static void Job1(Args _args)
        {
            TestDelegateClass myTestDelegateClass = new TestDelegateClass();
            myTestDelegateClass.callTheDelegate();
        }
    ```
3.  Compile the job by pressing the F1 key while focus is in the **Editor** window.

4.  Run the job by pressing the F5 key.

The output to the **Infolog** window looks like the following:

red is the color value in the event handler.

## See also

[Event Handler Nodes in the AOT](event-handler-nodes-in-the-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

