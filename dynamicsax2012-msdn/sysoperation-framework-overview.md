---
title: SysOperation Framework Overview
TOCTitle: SysOperation Framework Overview
ms:assetid: 7d9ec4fa-82f5-41e6-9378-65d6bd8cbd46
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg862488(v=AX.60)
ms:contentKeyID: 35246106
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# SysOperation Framework Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You use the SysOperation framework (formerly known as the Business Operation framework, or BOF) when you extend Microsoft Dynamics AX by adding new functionality that may require batch processing. The SysOperation framework replaces the [RunBase Framework](runbase-framework.md) and provides infrastructure for creating user interaction dialog boxes and integration with the batch server for batch processing. For a comparison of the SysOperation and RunBase frameworks and to view sample code that illustrates interactive and batch execution, see the white paper [Introduction to the SysOperation Framework](http://go.microsoft.com/fwlink/?linkid=246316).

## Using the SysOperation Framework

The SysOperation framework supports the following kinds of development scenarios:

  - Developing a new module that provides implementation-specific inventory closing functionality.

  - Creating a user interface for entering report parameters for Microsoft SQL Server Reporting Services.

  - Extending Microsoft Dynamics AX to support a complex addition to the sales tax calculation.

You can use the SysOperation framework to enhance processing performance by explicitly specifying when and how operations are executed. For example, you can run operations that are triggered by user interaction, or schedule them to run via the batch server.

In another example, the FormLetter framework is used to post documents for sales or purchase orders. This framework has been refactored to provide better support for customizations, extensibility, and performance by using the SysOperation framework. For more information, see the white paper [Using the Refactored Formletter Framework](http://go.microsoft.com/fwlink/?linkid=218315).

## SysOperation Framework Features

The SysOperation framework implements support for the following features:

  - Queries.

  - Pack and unpack for parameter serialization.

  - Routing tasks to the .NET Common Language Runtime (CLR) environment.

  - Building operations that scale to multiple processors by using batch processing.

  - Prompting the user for input only on the client tier.

  - Using batch processing to control when and where to run operations that require increased processing time and resources.

The SysOperation framework enables you to develop functionality that can be run by using batch processing. For information about other development patterns and programming models available with Microsoft Dynamics AX 2012, see the white paper [Selecting the Best Development Technology for Your Application Development Scenario](http://go.microsoft.com/fwlink/?linkid=213138).

## See also

[Designing a Microsoft Dynamics AX Application](designing-a-microsoft-dynamics-ax-application.md)

[Batch processing overview](https://msdn.microsoft.com/en-us/library/gg243235\(v=ax.60\))

[Batch Processing Classes](batch-processing-classes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

