---
title: Proxy Classes for .NET Interop to X++
TOCTitle: Proxy Classes for .NET Interop to X++
ms:assetid: a1f6adc2-6dd6-447f-b1fc-a5dee3116e6f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg879799(v=AX.60)
ms:contentKeyID: 35248310
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Proxy Classes for .NET Interop to X++ 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A proxy class is a .NET Framework class that provides access to one X++ item type of Microsoft Dynamics AX. You can build proxies for the following X++ item types:

  - Classes – both application and system classes.

  - Tables – both application and system tables.

  - Enums – both base and system enums.


> [!WARNING]
> <P>You cannot build a proxy for an X++ interface. If you try, a proxy is generated for a .NET Framework class which at best approximates the interface. This improper translation into a class causes some common scenarios to fail, and it might create problems in future releases.</P>



You can generate the proxy C\# or Visual Basic source code by using the Application Explorer in Microsoft Visual Studio. For more information, see [Walkthrough: Adding an X++ Object to a Visual Studio Project](walkthrough-adding-an-x-object-to-a-visual-studio-project.md).

Proxies are usually a better alternative to [.NET Business Connector](net-business-connector-overview.md). .NET Business Connector requires your C\# code to use a late-bound programming model. Proxies require an early-bound programming model. The early-bound model enables the code editor to provide IntelliSense. The early-bound model also enables the compiler to catch misspellings and other errors before the code is run.

## In This Section

The following topics are in this section:

[C\# Proxy Source Code for X++ Classes](csharp-proxy-source-code-for-x-classes.md)

[C\# Proxy Source Code for X++ Tables](csharp-proxy-source-code-for-x-tables.md)

[Scenarios for Constructing Proxy Objects](scenarios-for-constructing-proxy-objects.md)

[Proxies and Exception Mapping](proxies-and-exception-mapping.md)

## See also

[Integration with X++ Objects from Visual Studio](integration-with-x-objects-from-visual-studio.md)

[Integration with Microsoft Dynamics AX](integration-with-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

