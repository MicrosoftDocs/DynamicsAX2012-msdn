---
title: Partner Hooks Design Pattern
TOCTitle: Partner Hooks
ms:assetid: 1d8b3be3-aafe-491c-aa97-376854d41ff8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa557129(v=AX.60)
ms:contentKeyID: 35241473
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Partner Hooks Design Pattern 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Partner hooks are places in the standard application where extra functionality can be added to the existing code without causing subsequent upgrade issues.

## Situation

Some places in the application are very likely to be changed for each new version or service pack. Moreover, it is common for them to be modified by partners and/or customers. By providing a hook, partners can add their own code in a location that doesn't affect changes that are made to the standard application. For example, a partner should add code to Info.startupPost, instead of Info.startup, so their code does not affect any updates to Info.startup in a new version of Microsoft Dynamics AX.

Do not use this pattern instead of the [Strategy pattern](strategy-class-design-pattern.md). It provides the same benefits in a more streamlined manner. Use partner hooks only for sensitive places in the standard application where partner code can hinder initialization of vital areas.

## Solution

To help make the upgrade more cost-efficient, create a hook method that remains unused by the standard application. Partners and customers can make changes with less focus on possible impact to upgrades.

## Known Uses

Partner hooks are provided in the following methods:

  - Company.selectParametersPost (partner hook for Company.selectParameters)

  - Info.startupPost (partner hook for Info.startup)

  - Application.startupPost (partner hook for Application.startup)

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

