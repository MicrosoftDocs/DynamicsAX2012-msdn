---
title: Registering New Event Types
TOCTitle: Registering New Event Types
ms:assetid: e341fc4f-7c65-4fdc-b4b3-4eaf28ad112c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa879879(v=AX.60)
ms:contentKeyID: 35253130
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Registering New Event Types 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When your custom event type class is implemented, you must register it with the Alerts framework. The Alerts framework enables the Alerts functionality, which is a notification system that helps users track critical events in Microsoft Dynamics AX. To register your custom event type class, you need to list it in the EventType::eventTypeClassIdsHook static method of EventType class. The method is formatted as follows.

    protected static container eventTypeClassIdsHook()
    {
        return [classNum(myEventTypeClass1), classNum(myEventTypeClass2), ... ];
    }

## Register a New Event Type

If you implement only the EventTypeCUDIncreasedAtLeastBy event type class, the method is formatted as follows.

    protected static container eventTypeClassIdsHook()
    {
        return [classNum(EventTypeCUDIncreasedAtLeastBy)]; 
    }

When you have done this, your custom event type will appear in the list of events offered for numerical fields in the **EventCreateRule** form. The following figure shows the **EventCreateRule** form with the option **has increased above:** appearing for selection in the **Event** field.

![EventCreateRule form with a custom event type](images/Aa879879.CreateAlertRuleEvent(en-us,AX.60).gif "EventCreateRule form with a custom event type")

**The EventCreateRule form with a custom event type**

The option **has increased above:**, which now appears in the list, is the label returned by the Description method of your custom event type class.

After you select the **has increased above:** event, enter the appropriate value in the text box next to the **Event** field. The following figure shows the **EventCreateRule** form with a value that qualifies the **has increased above:** option.

![EventCreateRule form: value to qualify event type](images/Aa879879.CreateAlertRuleEventInserted(en-us,AX.60).gif "EventCreateRule form: value to qualify event type")

**The EventCreateRule form with a custom event type and a value that qualifies the event type**

For many forms, when you right-click on the form, you see the option to **Create alert rule...**. Clicking the option starts the **Create alert rule** form.

## See also

[Create alert rule (form)](https://msdn.microsoft.com/en-us/library/bb220776\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

