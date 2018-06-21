---
title: Macros Best Practices
TOCTitle: Macros
ms:assetid: f5858de7-034f-4c60-8c2c-176295f0af39
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa889325(v=AX.60)
ms:contentKeyID: 35253554
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Macros Best Practices [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Macro names should start with an uppercase letter.

## Constant Values

For constant values that are used in multiple places in your code, you should use \#define to define a macro that has the constant value. If you must change the value later, you have to change only the one macro definition. You would not have to find and edit every location where the value is used.

If the constant applies beyond the range of one class and the classes that extend from it, the macro definition must be in a macro library. Macro libraries are stored in the Application Object Tree (AOT) under the **Macros** node.

## X++ Statement Substitution

The \#localmacro directive is the best choice when you want to substitute part or all of an X++ statement into several locations in your code. For example, a recurring part of an SQL where clause can be reused as a macro.

## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

