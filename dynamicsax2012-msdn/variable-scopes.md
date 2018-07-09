---
title: Variable Scopes
TOCTitle: Variable Scopes
ms:assetid: 389bf564-4f95-4bb4-9589-323e1149179a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa624361(v=AX.60)
ms:contentKeyID: 35242855
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Variable Scopes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A scope defines the area in which an item can be accessed:

  - Instance variables, declared in class declarations, can be accessed from any methods in the class, and from methods that extend the class.

  - Local variables can be accessed only in the block in which they were defined. All variables created by users have local scope.

## Example
 ```X++
    class ANewClass
    {
        int a;
        
        void aNewMethod()
        {
            int b;
        }
    }
 ```
A variable, a, is declared in the class and a variable, b, is declared in the aNewMethod method.

As the method is declared in the class block, it can access all variables defined in the class. The aNewMethod method has access to variable a.

Variable b is declared in the aNewMethod method block, so that it can be accessed only from within this block.

## See also

[Scope of Variables in Methods](scope-of-variables-in-methods.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

