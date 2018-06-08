---
title: Best Practices for Methods
TOCTitle: Methods
ms:assetid: 5b583705-9cb9-4b67-a047-e32a2a8a85f8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa641216(v=AX.60)
ms:contentKeyID: 35244378
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Methods 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Methods should:

  - Be logical.

  - Do a specific task.

  - Have no side effects.

  - Be well structured, especially when it comes to good places for overriding and for overlayering.

Make your methods small and logical. If you have a method that does more than one 'thing'; then consider splitting it up in two (or more) methods. It will then be easier to override or overlayer exactly the functionality that needs to be specialized or customized.

Do not have any unused variables in your methods. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

For more detail about best practices for methods, see:

  - [Best Practices for Method Modifiers](best-practices-for-method-modifiers.md)

  - [Best Practices for Local Functions](best-practices-for-local-functions.md)

  - [Best Practices for Table Methods](best-practices-for-table-methods.md)

  - [Naming Conventions: Methods](naming-conventions-methods.md)

  - [Best Practices for Parameters](best-practices-for-parameters.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

