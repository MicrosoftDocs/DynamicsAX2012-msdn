---
title: X++ Scenarios that are Not Supported in CIL
TOCTitle: X++ Scenarios that are Not Supported in CIL
ms:assetid: fed9b42b-4ca6-4c27-a427-716c898ae487
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh397320(v=AX.60)
ms:contentKeyID: 36929811
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Scenarios that are Not Supported in CIL 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A small number of X++ items or scenarios are not always supported in the Microsoft .NET Framework common intermediate language (CIL), and should be avoided.

## X++ Functions that are Not Supported in CIL

X++ language functions that run strings of dynamically written X++ code are not supported when compiled to CIL. The following [X++ functions](x-function-categories-and-their-functions.md) are not supported when compiled to CIL:

  - evalbuf

  - runbuf

## Scenario that is Not Supported by Incremental CIL Generation

You must run a full CIL generation to remove items from the CIL, after you remove them from the Application Object Tree (AOT). The following list gives the details of the scenario:

  - Run a full CIL generation in your Microsoft Dynamics AX system.
    

    > [!WARNING]
    > <P>When running a full CIL generation, make sure that the operation finishes before opening any additional Microsoft Dynamics AX clients to ensure a successful completion.</P>



  - Use the Application Object Tree (AOT) to remove a method from a class or table.  
    The system removes the method from the p-code that X++ is compiled to.

  - Run an incremental CIL generation.
    

    > [!WARNING]
    > <P>The incremental CIL generation does not remove the method from the CIL. Instead, use a full CIL generation to remove the method from the CIL.</P>



## Compile Outcome When a Class has One Bad Method

When a C\# class for the .NET Framework is compiled to CIL, a C\# syntax error in any method causes the entire compile to fail. In contrast, in X++ a method on a class can run normally even after another method on the same class has been failed by the X++ compiler. The X++ compiler still generates valid p-code for methods that contain no errors.

In Microsoft Dynamics AX, when a full compile of X++ p-code to CIL is performed, the entire compile fails if valid p-code is unavailable for any method on any class.


> [!IMPORTANT]
> <P>Until your system has a successful full CIL compile, your system cannot run services, SSRS reports, or batch jobs.</P>




> [!TIP]
> <P>The <EM>Cumulative Update 2 for Microsoft Dynamics AX 2012</EM> includes a change that affects the X++ compiler. When the updated X++ compiler encounters invalid X++ source code, it writes valid p-code that throws an exception at run time. This enables the subsequent compile to CIL to succeed.</P>
> <P>The cumulative update can be downloaded from the Customer Source website. The X++ compiler update hotfix is associated with KB2617478, which is part of KB2606916.</P>



## See also

[X++ Compiled to .NET CIL](x-compiled-to-net-cil.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

