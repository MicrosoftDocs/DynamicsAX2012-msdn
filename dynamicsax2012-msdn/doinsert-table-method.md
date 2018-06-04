---
title: doInsert Table Method
TOCTitle: doInsert Table Method
ms:assetid: f373b851-18b1-4e2a-9b11-2a135f9ab120
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa887334(v=AX.60)
ms:contentKeyID: 35253436
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# doInsert Table Method 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The doInsert method generates values for the RecId field and other system fields, and then inserts the contents of the buffer into the database. This operation is used when the [insert](insert-table-method.md) method on the table is to be bypassed.

## Example

    ttsBegin;
     
    myTable.name = 'Flemming Pedersen';
    myTable.value = 100;
     
    myTable.doInsert();
     
    ttsCommit;

A new record is inserted with the name Flemming Pedersen in the name field and the value 100 in the value field.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

