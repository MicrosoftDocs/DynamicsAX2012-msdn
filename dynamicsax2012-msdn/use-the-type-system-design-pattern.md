---
title: Use the Type System Design Pattern
TOCTitle: Use the Type System
ms:assetid: eeba68db-f0e7-4edd-99e7-8f1eff9edf8d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa885168(v=AX.60)
ms:contentKeyID: 35253274
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Use the Type System Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

X++ is a type-strong language. It is a best practice to fully exploit the Microsoft Dynamics AX Type system.

## Situation

Implement code that is type-safe rather than type-unsafe.

## Solution

Always code in a strongly typed manner—define, declare, and use specific types. Do not use general types. Create and use specialized types for any special situation.

Use types that are as specialized as possible. This helps identify problems at compile time, leaving as few problems as possible to be found at run time.

Always use the root types Object, Common, and str with great care as follows:

  - Used members – have no compile-time checking

  - str – has no compile-time or run-time checks of length-compatibility

  - str – avoid using in any business-specific situation

Take care when you work with unstructured types, such as anytype, container, and struct. Use unstructured types only if there is no better alternative.

Do not write or call lots of code to validate data where the type system or other supporting systems already guarantee that everything is functioning correctly. This affects run-time resources and wastes development time.

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

