---
title: Framework Changes
TOCTitle: Framework Changes
ms:assetid: 427a957a-2ea4-46c4-932c-1aeace20f420
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272124(v=AX.60)
ms:contentKeyID: 36542033
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Framework Changes [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Some of the frameworks that are used by Enterprise Portal for Microsoft Dynamics AX 2009 are no longer available or have changed significantly for Microsoft Dynamics AX 2012.

## X++ Web Framework

In earlier versions of Enterprise Portal, the X++ Web Framework provided Web Forms, Web Controls, and Weblets. These were the primary method to implement functionality in Enterprise Portal. The X++ Web Framework is no longer available in Enterprise Portal for Microsoft Dynamics AX 2012.

Enterprise Portal for Microsoft Dynamics AX 2012 uses a framework based on ASP.NET. User Controls created by using this framework are the primary method for adding functionality to Enterprise Portal. Visual Studio is used to develop or customize User Controls.

If you have created Web Forms for an earlier version of Enterprise Portal, you can convert them to use the new ASP.NET-based framework. You will have to do this in Enterprise Portal for Microsoft Dynamics AX 2009 because it contains both the ASP.NET framework and the X++ web framework. A Web Form Converter class is available for Microsoft Dynamics AX 2009 that can take an existing Web form and convert it into components that can be used with the new Enterprise Portal framework. Refer to the Microsoft Dynamics AX 2009 documentation for more information about how to use the Web Form Converter class.


> [!TIP]
> <P>The changes that were made in the recent versions of Enterprise Portal are significant. If you have an X++ web framework application, you should consider re-creating it in Enterprise Portal for Microsoft Dynamics AX 2012. This may be easier than converting the application.</P>



## X++ Report Framework

The X++ Report Framework can no longer be used to create reports for Enterprise Portal. Instead, you must use SQL Server Reporting Services (SSRS) to create reports. These SSRS reports can be displayed in Enterprise Portal. See [Reports in Enterprise Portal Overview](reports-in-enterprise-portal-overview.md) for information about reporting in Enterprise Portal.

## Number Sequence Framework

The Number Sequence framework has changed significantly for Microsoft Dynamics AX 2012. If you have used the Number Sequence framework to generate your own number sequences for your Enterprise Portal application, you will have to update your number sequence implementation. See [Number Sequence Framework](number-sequence-framework.md) for information about how to implement number sequences.

## Security

The Security framework has changed significantly for Microsoft Dynamics AX 2012. You will have to configure security for your Enterprise Portal application after you have completed converting it to work with Enterprise Portal for Microsoft Dynamics AX 2012. See [Security in Enterprise Portal](security-in-enterprise-portal.md) for detailed information about how to implement security.

