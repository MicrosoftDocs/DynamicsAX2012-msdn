---
title: Data and Engine Class Design Pattern
TOCTitle: Data and Engine Class Design Pattern
ms:assetid: 88f5ffb5-17d8-4aff-a6d8-ae37e9787d8e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa658986(v=AX.60)
ms:contentKeyID: 35246290
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Data and Engine Class Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Use this pattern for the following situations:

  - When data can be manipulated by programs and data can be different from situation to situation.

  - When manipulation can be different from situation to situation.

## Class hierarchies

One class hierarchy defines the different data structures, and another class hierarchy defines the different manipulations. As a user of the class hierarchies, you always use and call methods on the superclasses.

The objects are the data (hierarchies). The methods on the objects are implemented by using the manipulation hierarchies.


> [!NOTE]
> <P>Be sure to separate data and functions correctly.</P>



The following illustrates an example of the data and engine class design pattern.

![Example of a Data + Engine Pattern](images/Aa658986.ClassModelWrkCtr(en-us,AX.60).gif "Example of a Data + Engine Pattern")

## See also

[Microsoft Dynamics AX Class Design Patterns](microsoft-dynamics-ax-class-design-patterns.md)

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

