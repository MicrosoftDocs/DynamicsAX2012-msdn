---
title: Best Practices for Table Collections
TOCTitle: Table Collections
ms:assetid: d72426db-4c29-4f8f-93d9-b7245c66a301
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa874118(v=AX.60)
ms:contentKeyID: 35252062
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Table Collections [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Several standard table collections have been created in the standard application. Go to **AOT** \> **Data Dictionary** \> **Table Collections** to see the list of table collections.

These table collections must be updated by any solution that changes or adds new tables to the application. By using these collections, the most common shared data or virtual company situations can be set up at the installation.

Add tables to the Global collection if the data is not company-specific. Examples are State and Unit.

There must not be a foreign key in a table in a virtual company, where the key is in the (non-virtual) company. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

To get the most use of the standard table collections, it might be necessary to adjust the data model. For example, you might have to split data that would all be in one table if all data was stored under one company.

## See also

[Data Dictionary Best Practices](data-dictionary-best-practices.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

