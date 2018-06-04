---
title: 'How to: Configure a Table for Search'
TOCTitle: 'How to: Configure a Table for Search'
ms:assetid: a45af31c-6ab3-4c4d-bb0c-fb61eb94211c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb190090(v=AX.60)
ms:contentKeyID: 35245585
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Configure a Table for Search 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Data in tables that you create in Microsoft Dynamics AX can be searchable. To make data available for search, the table must meet certain criteria.

## Setting Up a Table for Search

### To set up a table for search

1.  In the AOT, expand the **Data Dictionary** node and then expand the **Tables** node.

2.  Locate the table that you want to be searchable. Right-click the node and then click **Properties**.

3.  Set the **ModifiedDateTime** property to **Yes**. This causes the UTC (Universal Coordinated Time) value of the last time each record was modified to be saved in the table. This is required for search.

4.  Verify the **TableGroup** property. If it is any of the following, the table will not be available for search:
    
      - **Transaction**
    
      - **TransactionHeader**
    
      - **TransactionLine**
    
      - **WorksheetHeader**
    
      - **WorksheetLine**

5.  Save any changes in the AOT.

Next, you must create a query that will be used to search the table. See [How to: Create a Query for Search](how-to-create-a-query-for-search.md) for more information.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

