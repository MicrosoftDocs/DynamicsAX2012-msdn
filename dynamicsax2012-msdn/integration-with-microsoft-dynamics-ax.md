---
title: Integration with Microsoft Dynamics AX
TOCTitle: Integration
ms:assetid: de60dbce-d080-41e9-93a4-40a260927e6b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa877498(v=AX.60)
ms:contentKeyID: 35252086
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Integration with Microsoft Dynamics AX 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

There can be benefits to integrating your Microsoft Dynamics AX application with other technologies. One benefit is you can use other technologies to develop parts of your overall Microsoft Dynamics AX application. For example, you can write some of your functions in C\# instead of in X++, and then integrate your Microsoft .NET Framework assembly into Microsoft Dynamics AX.

Another benefit from integration is the ability to coordinate your Microsoft Dynamics AX application with external applications. The external applications can be inside or outside the boundary of your enterprise. The functionalities of the two applications can interact, and data can be exchanged.

You can integrate your Microsoft Dynamics AX application by using the following technologies:

  - Services and Application Integration Framework (AIF) – Exposes business logic to other internal or external systems. Microsoft Dynamics AX supports integration with the Application Integration Framework (AIF) components using the services programming model. Microsoft Dynamics AX can expose its functionality through services that are based on Windows Communication Foundation (WCF). Microsoft Dynamics AX code and external applications can consume Microsoft Dynamics AX services. AIF supports the processing of inbound and outbound messages. This processing includes message transforms and value lookups. Together, services and AIF provide the programming model, tools, and infrastructure support for XML-based integration with external applications and data.

  - .NET Business Connector – Enables external applications to access Microsoft Dynamics AX data and invoke business logic.

  - .NET Framework – Enables X++ code to call methods in assemblies that are managed by the common language runtime (CLR). Also provides proxy classes generated as C\# or Visual Basic source code for X++ classes in Microsoft Dynamics AX. Your C\# code can call the proxies and use them much as an X++ class would call other X++ classes directly. You generate the proxy classes by using Microsoft Visual Studio.


> [!TIP]
> <P>To apply advanced criteria to your search for Help about Microsoft Dynamics AX, use the <A href="http://go.microsoft.com/fwlink/?linkid=247587&amp;xver=ax060">WebSearchAx</A> tool.</P>



## Services and AIF

To support a range of options for customization and programmability, Microsoft Dynamics AX provides the following types of services:

  - Custom services are services that you create to expose X++ logic through a service interface. You can use the business logic with inbound or outbound transfers.

  - Document services represent data and business logic within Microsoft Dynamics AX. You can use or customize standard Axd document services that are included with Microsoft Dynamics AX. If none of the standard document services meet your needs, you can create a new document service by using the [AIF Document Service Wizard](https://msdn.microsoft.com/en-us/library/aa856656\(v=ax.60\)).

  - System services cannot be customized. The Query Service, Metadata Service, and User Session Service are WCF services included with Microsoft Dynamics AX. System services provide the following:
    
      - Access to data that is returned in AOT queries.
    
      - Metadata for AOT objects such as tables and extended data types (EDTs).
    
      - Data about the calling user, such as default language and default company.

For more information about integration with services and AIF, see [Services and Application Integration Framework (AIF)](https://msdn.microsoft.com/en-us/library/gg731810\(v=ax.60\)).

## .NET Business Connector

The Microsoft Dynamics AX .NET Business Connector enables external applications to access Microsoft Dynamics AX data and invoke business logic.

The .NET Business Connector provides interoperability with the .NET Framework. Use these components for integration with external applications that are written in managed code and which are built with the .NET Framework. The .NET Business Connector requires the installation of the Windows Server SDK. For more information about .NET Business Connector, see [.NET Business Connector Overview](net-business-connector-overview.md).

## .NET Interop

The Microsoft Dynamics AX system can interoperate with the .NET Framework in either direction. For more information, see the following topics:

  - [Proxy Classes for .NET Interop to X++](proxy-classes-for-net-interop-to-x.md)

  - [Code Example: LINQ to AX from C\#](code-example-linq-to-ax-from-csharp.md)

  - [.NET Interop from X++](net-interop-from-x.md)

## See also

[Developing with Services and AIF](https://msdn.microsoft.com/en-us/library/hh509053\(v=ax.60\))

[CLRObject Class](https://msdn.microsoft.com/en-us/library/gg803404\(v=ax.60\))

[CLRInterop Class](https://msdn.microsoft.com/en-us/library/gg803050\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

