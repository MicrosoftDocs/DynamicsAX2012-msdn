---
title: Event Method Sequences when Focus is Removed from a Record
TOCTitle: Event Method Sequences when Focus is Removed from a Record
ms:assetid: 492bedff-b53a-4624-865f-832b419dfc45
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa628445(v=AX.60)
ms:contentKeyID: 35243146
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Event Method Sequences when Focus is Removed from a Record [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An event method sequence is executed when focus is removed from a record. The sequence includes the leaveRecord method. Form controls that simultaneously display multiple records have the leaveRecord event method.

## Grid Scenario

This scenario has a form that contains a grid control, which is bound to a data source. The form is open, and the grid is populated with data. Focus is on the first line of the grid.

### ![Aa628445.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa628445.collapse_all(en-us,AX.60).gif")Move Focus from one Record to Another

Without changing any data, the user clicks a different grid line to move focus to that line. The following event method sequence is executed when data in the first line is unchanged.

1.  leave on the data source.

2.  leaveRecord on the data source.

A longer event method sequence occurs when grid line data changes before focus is moved from that grid line.

1.  modifiedField on the table.

2.  update on the table.

3.  aosValidateUpdate on the table.

4.  leaveRecord on the data source.

5.  leave on the data source.

6.  leaveRecord on the data source.

## See also

[Event Method Sequences in Form Scenarios](event-method-sequences-in-form-scenarios.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

