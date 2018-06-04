---
title: Event Method Sequences when a Record is Created
TOCTitle: Event Method Sequences when a Record is Created
ms:assetid: 2e042a8a-8cdc-4121-b35b-992f27547a4e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa592877(v=AX.60)
ms:contentKeyID: 35241948
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Event Method Sequences when a Record is Created 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Event methods are executed when a form is used to create a new record. The details can vary, depending on the type of controls present on the form.

## Grid Scenario

In this scenario, a form contains one grid control. A data source is bound to the grid control. The data source is associated with two fields from a table.

A user opens the form, and then the grid is populated with data. The first line in the grid has focus.

### ![Aa592877.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa592877.collapse_all(en-us,AX.60).gif")A User Creates a Record

A user enters a new record by using a grid control on a form. They begin by pressing the shortcut keys CTRL+N. This creates a new, empty line in the grid and gives focus to the new line. The following list shows the sequence of event method executions that occurs when the user continues with the steps needed to create a record in the database.

1.  leaveRecord on the data source.
    
    The user enters data into the first empty cell, and then presses TAB.

2.  validateField on the table.

3.  modifiedField on the table.
    
    The user now enters data into the second empty cell. They click a grid line that is already populated to take focus from the new line.

4.  validateField on the table.

5.  modifiedField on the table.

6.  validateWrite on the table.

7.  insert on the table.

8.  aosValidateInsert on the table.

9.  leaveRecord on the data source.

10. leave on the data source.

11. leaveRecord on the data source.

## See also

[Event Method Sequences in Form Scenarios](event-method-sequences-in-form-scenarios.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

