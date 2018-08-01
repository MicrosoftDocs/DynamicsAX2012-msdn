---
title: RunBase Class Design Pattern
TOCTitle: RunBase
ms:assetid: 0d6ef345-7c32-480a-ba65-3188c9ec6a42
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa584460(v=AX.60)
ms:contentKeyID: 35240433
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# RunBase Class Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The [RunBase framework](runbase-framework.md)is used to create a job or an Action class. An Action class is a program that runs processes. For example, accepting parameters from the user and then updating records in the database.

The RunBase framework provides the functions needed in such a job, and provides a consistent interface.

## Candidates

Most classes that use a main method are candidates for using the RunBase framework.

## See also

[Microsoft Dynamics AX Class Design Patterns](microsoft-dynamics-ax-class-design-patterns.md)

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

