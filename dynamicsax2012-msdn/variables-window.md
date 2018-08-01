---
title: Variables Window
TOCTitle: Variables Window
ms:assetid: fdb4be70-99d2-48ba-a200-c8aa4d1fe68e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa569672(v=AX.60)
ms:contentKeyID: 35239337
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Variables Window [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In the **Variables** window in the Microsoft Dynamics AX debugger, you can observe the values of the variables changing as you traverse through the code. The **Variables** window displays the values of the variables that are within the current scope. When the value of a variable has changed between stops, it is highlighted in a different color in the variables window to make it easy to identify the changes.

You can also modify the value of a variable in the **Variables** window. If a single line in the **Variables** window holds a compound object, you can click the plus sign (+) to expand it.


> [!NOTE]
> <P>Microsoft Dynamics AX must be in break mode for you to modify variable values. Also, the maximum tooltip length for these values is 1,024 characters. Anything longer than this is truncated.</P>



## Locals View

The **Locals** view displays the variables that are part of the current scope.

## Globals View

The **Globals** view displays the following classes:

  - Infolog

  - Application

  - ClassFactory

  - VersionControl

The variables in these classes are global variables and are always instantiated. These global classes are derived from kernel classes. Any classes that you create in the Application Object Tree (AOT) do not appear in this view, but are shown in the Variables window and Locals view.

## This View

The **This** view displays the variables that apply to the current object. These variables can also be accessed in the **Locals** view because they are always a subset of the current scope. However, the **This** view provides quicker access to these values.

## See also

[Microsoft Dynamics AX Debugger](microsoft-dynamics-ax-debugger.md)

[Debugger Windows](debugger-windows.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

