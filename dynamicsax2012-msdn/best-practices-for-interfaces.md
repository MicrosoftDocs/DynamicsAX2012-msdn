---
title: Best Practices for Interfaces
TOCTitle: Interfaces
ms:assetid: 7265a568-794c-454e-a153-a391bae58c18
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa655103(v=AX.60)
ms:contentKeyID: 35245887
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Interfaces [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic provides information on the best practices for interfaces. Details are provided on interface names and interfaces that are provided by the Microsoft Dynamics AX development environment.

## Interface Naming

The names of interfaces should follow the general naming guideline for [classes](best-practices-for-classes.md).

It is a best practice to infix an interface name with the letter I to indicate that the type is an interface. The letter I should be infixed right after the prefix.

The following list provides examples of recommended interface names:

  - SysIComponent (descriptive noun)

  - CustITransactionProvider (noun phrase)

  - CustIInvoicePersistable (adjective)

## SysPackable

Classes that implement SysPackable must not pack the element IDs, such as Class, Field, or Table ID. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

Classes that implement SysPackable must pack the same contents across versions (the same variables and the same types of variables). Another option is to change the version number of the container. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

The following code example changes the version number of the container.

\#define.CurrentVersion(2)


> [!NOTE]
> <P>Use a number other than 1.</P>



## SysUnitTestable

Classes that implement SysUnitTestable must have a name postfixed with 'UnitTest'. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

## See also

[Interfaces Overview](interfaces-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

