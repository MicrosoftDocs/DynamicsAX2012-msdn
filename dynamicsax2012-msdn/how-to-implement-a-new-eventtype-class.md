---
title: 'How to: Implement a New EventType Class'
TOCTitle: 'How to: Implement a New EventType Class'
ms:assetid: 52b5134a-eafc-494f-963e-38e88e173859
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa639867(v=AX.60)
ms:contentKeyID: 35244321
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Implement a New EventType Class 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To create a new event type, you must create a new class that inherits either from the top level [EventType Class](https://msdn.microsoft.com/en-us/library/gg745137\(v=ax.60\)) or from one of its subclasses, and then override certain methods as appropriate. The first two sections below describe the key members and methods of the top level EventType class. The last section provides an example of implementing a custom event type class.

## Key Members of the EventType Class

  - The original value holds the old value; for example, the value of a table field.

  - The current value holds the new value; for example, the value of a table field.

  - xValue is the event parameter.

  - The TypeTrigger base enum determines what causes the event to occur. The TypeTrigger could be, for example, a change of data, insertion of data, deletion of data, or a date value being due.

Not all of these members are necessarily used by each event type.

For example, the **has increased** event (implemented in the EventTypeCUDIncreased class) does not use the xValue member variable because it monitors all changes to a table field whenever the field value is increased. Therefore, in the isMatchingRule method of the EventTypeCUDIncreased class, only the original value member variable is compared with the CurrentValue member. If the original value is less than the current value, there is a match.

Original value, current value, and xValue are of any type; therefore, events are supported for all potential data types.

## Key Methods of the EventType Class

  - The description method must be implemented because it provides the label for the **Event** option in the **Create alert rule** form.

  - The IsMatchingRule method contains the logic that determines when a rule matches your custom event type.

  - The isValidEventType method determines which data types the event applies to; for example, due date events apply only to date types. You must know this in order to determine which event types to offer in the **Event** option in the **Create alert rule** form.

  - The isRequiringX method determines whether your custom event type requires a parameter. For example, the **is set to:** event requires an xValue as its parameter. If a method returns true, the text box in which the user enters this parameter is enabled on the **Create alert rule** form. The Alerts framework ensures that the text box for the event parameter corresponds to the data type. For example, if the user sets up a rule for a string type field, a StringEdit control is displayed automatically on the **Create alert rule** form where the event parameter can be entered.

  - The isFieldRelated method determines whether your custom event type relates to a field.

## Create a New EventType Class

Microsoft Dynamics AX users might want to monitor unusually large increases to numeric fields made by transactions in the system. Based on business knowledge, users can quantify what an unusually large increase is for a certain field.

In other words, if the new value of a numeric field has been increased by X by a transaction, an alert is generated.

X is the parameter of the new custom event type.

1.  Create a new class called EventTypeCUDIncreasedAtLeastBy inheriting from EventTypeCUDIncreased by using the following code.
    
        class EventTypeCUDIncreasedAtLeastBy extends EventTypeCUDIncreased
        {
        }

2.  Override the following methods by using the following code.
    
        public EventTypeDescription description()
        {
            return "has increased at least by:"; //hardcoded for demo purpose only
                                            //you must use a label here
        }
        
        public boolean isMatchingRule()
        {
            return (currentValue - originalValue ) >= xValue;
        }
        
        public boolean isRequeringX()
        {
            return true;
        }

You do not need to override the isValidEventType method because your custom event type is valid for exactly the same data types as the EventTypeCUDIncreased event type, from which it inherits.

The same applies for the isFieldRelated method because this method is overridden in the EventTypeCUD class, which is a parent of your custom EventTypeCUDIncreasedAtLeastBy class.

However, you must override the isRequiringX method. The immediate parent of your custom event type class, EventTypeCUDIncreased, does not require an X parameter because it is used for monitoring any increases to numeric fields.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

