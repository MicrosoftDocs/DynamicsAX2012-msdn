---
title: update Table Method
TOCTitle: update Table Method
ms:assetid: adb4c661-e354-4ce7-95fa-a3a675900a22
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa854683(v=AX.60)
ms:contentKeyID: 35249727
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# update Table Method [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The update table method updates the current record with the contents of the buffer. It also updates the appropriate system fields.

The where clause is optional. When used, the where clause specifies a condition for update to test while processing each row of the table. Only those rows that test true against the condition are updated with the new values.

[update\_recordset](update-recordset.md) is a record-set based operator—it updates multiple records at once.

To override the behavior of update, use the [doUpdate](doupdate-table-method.md) method.

## Example

```X++
  CustTable custTable;
        ttsBegin;
          select forUpdate custTable
          where custTable.AccountNum == '4000'; 
          custTable.CreditMax = 5000; 
          custTable.update(); 
        ttsCommit;
```

The example selects the table custTable for update. Any records with the AccountNum equal to 4000 are updated (in this case only one). The CreditMax field is changed to 5000.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

