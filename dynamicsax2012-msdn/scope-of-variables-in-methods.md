---
title: Scope of Variables in Methods
TOCTitle: Scope of Variables in Methods
ms:assetid: a3bfd628-5f41-452f-a6b5-f20116649294
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa850145(v=AX.60)
ms:contentKeyID: 35248381
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Scope of Variables in Methods 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A scope defines the area in which an item can be accessed. Variables defined in a class are available to the methods within that class. Variables in methods can be accessed only within the current block, as shown in the following figure.

![class variables](images/Aa850145.LangScop(en-us,AX.60).gif "class variables")

The class A contains methods b and c and class variables. All methods in the class can see and use all variables in the class.

The method b has some local variables that can only be accessed from within method b.

Method c has some local variables, a function d, and a function e. Functions d and e can be seen only inside method c. As functions d and e are declared inside method c, they have access to their local variables—the local variables in c and the variables in the class, respectively.

## See also

[Parameters and Scoping](parameters-and-scoping.md)

[Variable Scopes](variable-scopes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

