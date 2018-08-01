---
title: Keep Business and User Interface Logic Separate
TOCTitle: Keep Business and User Interface Logic Separate
ms:assetid: b26cbb64-22f9-45af-a02e-b67d69cbf1c9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa857073(v=AX.60)
ms:contentKeyID: 35249751
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Keep Business and User Interface Logic Separate [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

It is very important to have a clear interface between the presentation logic (user interface) and the business logic. Do not mix these two types of logic.

Business logic must be implemented in classes and on tables.

Never design your business logic so that it has direct references to controls on forms or reports. The design of the business logic must enable any relevant form or report to use it.

Remember that the business logic in Microsoft Dynamics AX can be used though COM from other applications. For example, an X++ script can access the business logic that creates a sales quotation. This underscores the importance of not letting the business logic be dependent on a specific Microsoft Dynamics AX form or report.

## See also

[Where to Place the Code](where-to-place-the-code.md)

[Designing a Microsoft Dynamics AX Application](designing-a-microsoft-dynamics-ax-application.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

