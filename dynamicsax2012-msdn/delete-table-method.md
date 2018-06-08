---
title: delete Table Method
TOCTitle: delete Table Method
ms:assetid: 21c40f13-9f73-4991-b692-d1d4c1c59d19
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa620338(v=AX.60)
ms:contentKeyID: 35241555
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# delete Table Method 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Deletes the current record from the database.

To use this method, specify which rows are to be deleted by using a where clause. Records are then removed, one at a time, from the specified table.

[delete\_from](delete-from.md) is a record-set–based operator, which simultaneously removes multiple records.

The delete method can be overridden, for example, to add extra validation before records are deleted.

If you override the delete method, the original version of the delete method can be executed instead by calling the doDelete method. It is equivalent to calling super() in the delete method; doDelete executes the base version of the delete method.

## Example

    ttsBegin;
     
    while select forUpdate myTable
        where myTable.AccountNum == '1000'
    {
        myTable.delete();
    }
    ttsCommit;

All records in the MyTable table that satisfy the where clause criterion (any record with an Account number equal to 1000) are deleted from the database. These records are deleted one at a time.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

