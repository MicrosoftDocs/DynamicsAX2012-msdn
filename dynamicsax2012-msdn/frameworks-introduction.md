---
title: Frameworks Introduction
TOCTitle: Frameworks Introduction
ms:assetid: 89ff07bd-4fbc-4395-b72c-883e0f7455c6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa659223(v=AX.60)
ms:contentKeyID: 35246313
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Frameworks Introduction 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic provides descriptions of some of the frameworks, subsystems, and features in Microsoft Dynamics AX. Frameworks are collections of design patterns, interfaces, and code that provide support to you as a developer.

## Address System

Addresses are uniformly handled by the Address subsystem. For information, see [Global address book overview](https://msdn.microsoft.com/en-us/library/gg231541\(v=ax.60\)).

## BatchJournal Framework

The BatchJournal Framework enables you to run a group of tasks that have been created by using the RunBase framework. (There are individual tts transaction controls for each task.)

## Consistency Check Framework—Check and Fix

The Consistency Check Framework helps validate the consistency of the data in the production database and helps fix the inconsistencies that it finds.

The framework consists of classes with names ending in "ConsistencyCheck." For example, InventConsistencyCheck.

## Dimension

Use the [Dimension](https://msdn.microsoft.com/en-us/library/hh272858\(v=ax.60\)) subsystem to work with financial dimensions. Use the InventDim subsystem to work with inventory dimensions.

## Document Management System

The document management system is automatically available everywhere in Microsoft Dynamics AX. Text notes and documents of any type and size can be attached to any record in Microsoft Dynamics AX.

Note fields should not be placed on your own tables. The document management system's text notes are used for that.

**Note**   If documents attached to a record are stored on a file share rather than in the database in Microsoft Dynamics AX, you must ensure that the correct access levels have been set.

## Infolog

Information and messages to the user are placed in the Infolog. It also contains contextual information and supporting Help and actions.

## Number Sequence

Create a number sequence for a new module by using the [Number Sequence Framework](number-sequence-framework.md).

## OLAP

Microsoft Dynamics AX provides a model driven approach for developing Business Intelligence (BI) applications that use the SQL Server Business Intelligence Development Studio (BIDS) development environment. Microsoft SQL Server Analysis Services provides OLAP functionality.

## Operation progress

Inform the user that a process will take some time by using the [How to: Create Progress Indicators](how-to-create-progress-indicators.md) (SysOperationProgress).

## ReleaseUpdate

Use the ReleaseUpdate framework to update the data in the customer database.

## Reporting Framework

SQL Server Reporting Services is the primary reporting platform for Microsoft Dynamics AX. The default, out-of-the-box reports that are provided with Microsoft Dynamics AX run on the Reporting Services platform. The new report development environment takes advantage of extended SQL Server tools and components. The report development environment is fully integrated into Microsoft Visual Studio. For more information, see [Reporting in Microsoft Dynamics AX](https://msdn.microsoft.com/en-us/library/ee873263\(v=ax.60\)).

## RunBase

Use the [RunBase Framework](runbase-framework.md) to execute tasks that cannot be executed in batch.

The framework provides you with dialogs, users last values, query dialogs, and progress bars. It also provides a unified user and programmer experience.

It is best practice to make it possible to execute the jobs in Batch.

### ![Aa659223.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa659223.collapse_all(en-us,AX.60).gif")RunbaseBatch

Use RunBaseBatch to execute tasks and reports in batches. This enables the user to work with the next task in Microsoft Dynamics AX instead of waiting for another task to finish.

All tasks that cannot be executed in batch should be implemented with the RunBase Framework.

### ![Aa659223.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa659223.collapse_all(en-us,AX.60).gif")RunbaseReportStd

Use the RunBaseReportStd framework to implement all reports.

### ![Aa659223.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa659223.collapse_all(en-us,AX.60).gif")RunBaseMultiParm

The RunbaseMultiParm framework does the following:

  - Enables you to run one or many updates in one job

  - Provides a job history

  - Provides more straightforward parameter handling

The frameworks use parameter tables that are specifically designed for a particular task. For example, ProdParmBOMCalc, which is used with the ProdMultiBOMCalc class.

Instead of packing many parameters, only a parmId is packed. It identifies one or many records in the parameter table.

The parameters needed are created as fields in the parameter table. The dialog is a form in the AOT, showing a grid by using the parameter table instead of a traditional dialog form.

For each parameter record, the actual RunbaseMultiParm class runs a specific UpdateBase class. There will typically be an UpdateBase class for each RunbaseMultiParm class.

## SysOperation Framework

Use the [SysOperation framework](sysoperation-framework-overview.md) (formerly known as the Business Operation framework, or BOF) to extend Microsoft Dynamics AX by adding new functionality that may require batch processing. The SysOperation framework replaces the [RunBase Framework](runbase-framework.md). For a comparison of the SysOperation and RunBase frameworks and to view sample code that illustrates interactive and batch execution, see the white paper [Introduction to the SysOperation Framework](http://go.microsoft.com/fwlink/?linkid=246316).

The SysOperation framework enables the following features when you extend Microsoft Dynamics AX:

  - Menu-driven execution or batch execution of services.

  - Execution in in synchronous or asynchronous mode.

  - Automatically creates a customizable UI based on the data contract.

  - Encapsulates code to operate on the appropriate tier (prompting on the client tier, and business logic on the server tier).

## TransactionLog Subsystem

The TransactionLog subsystem is used to offload the transaction details, such as CreatedDate and CreatedBy, from the transaction tables and place them in a central transaction header table. All transactions across the application share a common entry in the transaction header table, and they are related to it.

## Web Applications (WebApp)

Create applications for the Web by using the Web Application Framework for Microsoft Dynamics AX. For more information, see [Enterprise Portal for Microsoft Dynamics AX](enterprise-portal-for-microsoft-dynamics-ax.md).

## Wizard

Create wizards by using the Wizard Wizard, and the Wizard framework.

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

[Microsoft Dynamics AX Class Design Patterns](microsoft-dynamics-ax-class-design-patterns.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

