---
title: Event Method Sequences when a Record is Deleted
TOCTitle: Event Method Sequences when a Record is Deleted
ms:assetid: d1e051d0-aa16-41f7-9f42-393702f21bf9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa871725(v=AX.60)
ms:contentKeyID: 35251854
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Event Method Sequences when a Record is Deleted [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An event method sequence is executed when a record is deleted from a grid control. The grid control is on a form.

## Grid Scenario

This scenario has a form that contains a grid control, which is bound to a data source. The data source is associated with a table. The form is open and the grid is populated. Focus is on the first line of the grid.

The user presses ALT+F9 to delete the record, and then clicks **Yes** to confirm. The following event methods are executed in response to that event.

1.  validateDelete on the table.

2.  delete on the table.

3.  aosValidateDelete on the table.

4.  leaveRecord on the data source.

## See also

[Event Method Sequences in Form Scenarios](event-method-sequences-in-form-scenarios.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

