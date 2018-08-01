---
title: X++ Functions
TOCTitle: X++ Functions
ms:assetid: 48248522-df84-415a-b6b1-ae7897b58c95
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa595142(v=AX.60)
ms:contentKeyID: 35243085
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Functions [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, the X++ language provides more than 100 system functions that are not part of any class. The two types of functions are as follows:

  - Run time – functions that are executed during run time.

  - Compile time – functions that are executed during compile time.

## Run Time Functions

Run time functions used for data type conversions, mathematical operations, and so on. Some common run time functions are as follows:

  - str2Int – creates an int value from a str value.

  - abs – creates a positive real value from a real value that is either positive or negative.

  - conFind – retrieves the location of an element in a container.

For more information, see the reference topics that are listed under [Functions](https://msdn.microsoft.com/en-us/library/aa856741\(v=ax.60\)).

### ![Aa595142.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa595142.collapse_all(en-us,AX.60).gif")Call Run Time Functions from .NET

The logic of the X++ run time functions is also implemented in the following .NET assembly:

Microsoft.Dynamics.AX.Xpp.Support.DLL

Inside the previous assembly, the X++ run time functions are implemented as static methods of the following class:

Microsoft.Dynamics.AX.Xpp.PredefinedFunctions

## Compile Time Functions

Compile time functions are executed early in the compile of X++ code. Most of these functions retrieve metadata about items that are in the Application Object Tree (AOT). Some common compile time functions are as follows:

  - classNum – retrieves the ID of a class.

  - classStr – verifies during compile time that a class by that name exists. This is better than discovering the error later during run time.

  - evalBuf – evaluates the input string of X++ code, and then returns the results as a string.

  - literalStr – retrieves a label ID when given the string representation of a label, such as the string "@SYS12345". For example, myLabel.exists(literalStr("@SYS12345"));.

 


> [!NOTE]
> <P>Compile time functions are sometimes called intrinsic functions.</P>




> [!NOTE]
> <P>X++ compile time functions cannot be called from a .NET program.</P>



For more information, see [Intrinsic Functions](intrinsic-functions.md).

## See also

[X++ Function Categories and their Functions](x-function-categories-and-their-functions.md)

[Functions](https://msdn.microsoft.com/en-us/library/aa856741\(v=ax.60\))

[Intrinsic Functions](intrinsic-functions.md)

[Functions and Macros](functions-and-macros.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

