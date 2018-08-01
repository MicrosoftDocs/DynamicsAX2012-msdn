---
title: Creating Rules for Alerts
TOCTitle: Creating Rules for Alerts
ms:assetid: 24cd925f-e9e1-4ef9-a3dd-372ecb0da624
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa634822(v=AX.60)
ms:contentKeyID: 35241628
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Creating Rules for Alerts [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you create a rule, all the information about the rule is collected in the EventCreateRule form. If you want to modify the rule later, you must do so in the EventRule form.


> [!NOTE]
> <P>Any item in the Application Object Tree (AOT) that starts with the word Event belongs to the Alerts functionality.</P>



When you subscribe to a type of event, your subscription is recorded in the EventRule table. The EventRule table contains information about your subscription, such as the type of event you want to monitor, the field or record in which you want to monitor the event, and the specific way that you want to be alerted when an event occurs (by an alert pop-up message or e-mail message).

When you create a new rule in the **Create alert rule** form, you can select the type of event to be monitored in the **Event** field of this form.

Each event is represented by an EventType class that contains the definition and the parameters of the event. When you create a rule, a new instance of an EventType object is created, and then recorded in the EventRuleData table. For more information about how event processing uses these objects to match rules against events, see [Event Detection and Processing for Alerts](event-detection-and-processing-for-alerts.md).

Actions are also represented by classes. A class representing an action must inherit from the [EventAction Class](https://msdn.microsoft.com/en-us/library/gg758245\(v=ax.60\)), and it must implement the execute method. For each event rule, the Alerts module creates a list of action class IDs that must be instantiated. The individual execute method that is associated with each respective class ID is called whenever a rule matches an event. The list of actions is customizable. For more information, see [How to: Add Custom Actions for Alerts](how-to-add-custom-actions-for-alerts.md).

The following objects are related to rule creation:

  - EventRule, EventRuleData, EventRuleField, EventRuleRel, and EventRuleRelData tables

  - EventCreateRule and EventRuleFormHandler classes

  - EventCreateRule and EventRule forms

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

