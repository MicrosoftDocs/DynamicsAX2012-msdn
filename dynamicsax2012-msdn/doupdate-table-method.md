---
title: doUpdate Table Method
TOCTitle: doUpdate Table Method
ms:assetid: 6270526c-faf0-4356-bc76-d77fdddd35a6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa633234(v=AX.60)
ms:contentKeyID: 35244572
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# doUpdate Table Method 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The doUpdate method updates the current record with the contents of the buffer. This method also updates the appropriate system fields.

The doUpdate method should be used when the [update](update-table-method.md) method on the table is to be bypassed.

## Syntax

void doUpdate()

## Example

   ```X++
   static void Job1(Args _args)
    {
        CustTable custTable;
        ttsBegin;
        select forUpdate custTable
        where custTable.CreditMax == 3000;
        if (custTable)
        {
           custTable.CreditMax += 1000;
           custTable.doUpdate();
        }
    
        ttsCommit;
    
    }
    ttsCommit;
   ```

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

