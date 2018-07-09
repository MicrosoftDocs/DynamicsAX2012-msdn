---
title: doDelete Table Method
TOCTitle: doDelete Table Method
ms:assetid: 47e1c669-ab99-4f21-a653-db4da4eaad75
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa628085(v=AX.60)
ms:contentKeyID: 35243062
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# doDelete Table Method 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Deletes the current record from the database.

Use the doDelete method if the [delete table method](delete-table-method.md) has been overridden, and you want to use the original version of the delete method. The doDelete method executes the base version of the delete method instead of the overridden version—it is equivalent to executing super()in the delete method.

## Example
```X++  
    ttsBegin;
    while select forUpdate myTable
        where myTable.AccountNum >='200';
    {
        myTable.doDelete();
    }
    ttsCommit;
```
The previous code deletes all records in the myTable table that have an account number that is greater than or equal to 200.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

