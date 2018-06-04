---
title: Event Method Sequences in Form Scenarios
TOCTitle: Event Method Sequences in Form Scenarios
ms:assetid: 72656527-c37d-4975-8f6a-fb13eabedf4e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa655101(v=AX.60)
ms:contentKeyID: 35245873
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Event Method Sequences in Form Scenarios 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

User actions on a form are input through mouse pointers and keyboards. These actions cause events that are recognized by Microsoft Dynamics AX. The recognized events include the following:

  - [Opening a form](event-method-sequences-when-a-form-is-opened.md)

  - [Closing a form](event-method-sequences-when-a-form-is-closed.md)

  - [Leaving a control](event-method-sequences-when-the-value-of-a-control-changes.md)

  - [Leaving a record](event-method-sequences-when-focus-is-removed-from-a-record.md)

  - [Deleting a record](event-method-sequences-when-a-record-is-deleted.md)

  - [Creating a record](event-method-sequences-when-a-record-is-created.md)

The system reacts to each event by executing several event methods. The user is often unaware that these methods are being executed.

## Customize the Responses to User Events

Use the Application Object Tree (AOT) to override the event methods and customize the response to form events.

1.  Expand the **Forms** node to see its **Methods** subnode.

2.  Expand the **Methods** node to see a subnode for each method that is currently overridden.

3.  Right-click the **Methods** node, and then select **Override Method** to see a list of methods that have not yet been overridden.

4.  Expand other nodes under **Forms** to see additional **Methods** nodes.

## Use Sequence Information to Determine the Correct Method to Override

Information about the sequence of event method execution is useful when you are determining the correct method to override. For example, you could write code to log the inserts that the user causes when they enter data into a grid control. This code could be placed in various event methods. You could override the insert event method on an underlying table. By knowing the aosValidateInsert method is executed immediately after the insert method, you might instead choose to log the aosValidateInsert method. Overriding aosValidateInsert might provide log information that has the results of security checks.

## See also

[Event Method Sequences when the Value of a Control Changes](event-method-sequences-when-the-value-of-a-control-changes.md)

[Event Method Sequences when a Form is Closed](event-method-sequences-when-a-form-is-closed.md)

[Event Method Sequences when a Form is Opened](event-method-sequences-when-a-form-is-opened.md)

[Event Method Sequences when a Record is Created](event-method-sequences-when-a-record-is-created.md)

[Event Method Sequences when a Record is Deleted](event-method-sequences-when-a-record-is-deleted.md)

[Event Method Sequences when Focus is Removed from a Record](event-method-sequences-when-focus-is-removed-from-a-record.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

