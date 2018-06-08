---
title: Event Method Sequences when the Value of a Control Changes
TOCTitle: Event Method Sequences when the Value of a Control Changes
ms:assetid: 7f9aceb2-61a9-4c73-9bc4-40590b5d708a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa642643(v=AX.60)
ms:contentKeyID: 35246132
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Event Method Sequences when the Value of a Control Changes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Event methods are executed when the value of a control changes. The exact sequence of event methods varies for different controls.

## Check Box Scenario

The example scenario uses a simple form that has a check box control. The check box is bound to a field in a data source.

A check box is a control that has a value property. In contrast, a grid control contains fields that each display a value, but the grid itself does not have a value property.

### ![Aa642643.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa642643.collapse_all(en-us,AX.60).gif")Click to Change the Value in a Check Box

The following sequence of event methods is executed when the check box is either selected or cleared by a user.

1.  validate on the check box.

2.  modified on the check box.

3.  validateField on the table.

### ![Aa642643.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa642643.collapse_all(en-us,AX.60).gif")Remove Focus from a Check Box

The following event method is the only one executed when focus is removed from the check box:

  - leave on the check box.

## See also

[Event Method Sequences in Form Scenarios](event-method-sequences-in-form-scenarios.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

