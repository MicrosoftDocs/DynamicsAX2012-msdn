---
title: Best Practice for Destructors (finalize)
TOCTitle: Destructors
ms:assetid: 145d4182-7fbc-47bb-96c1-f747380bf3be
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa598206(v=AX.60)
ms:contentKeyID: 35240602
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practice for Destructors (finalize) [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The X++ language has no destructor method. A destructor method is one that is called by the system when there are no more references to an object and the system starts to destroy the object.

The Object class has a finalize method, but finalize is empty and the Microsoft Dynamics AX system never calls it. You can override the finalize method if you want a method to contain code that might otherwise belong in a destructor method. However, finalize is not called unless your code calls it explicitly.

## See also

[Best Practices for Class Declarations](best-practices-for-class-declarations.md)

[Best Practices for Constructors](best-practices-for-constructors.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

