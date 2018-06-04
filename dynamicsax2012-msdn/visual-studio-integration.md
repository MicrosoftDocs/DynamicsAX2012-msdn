---
title: Visual Studio Integration
TOCTitle: Visual Studio Integration
ms:assetid: f7c6e32a-be2c-41ec-98ea-4a1e7ff9b342
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889299(v=AX.60)
ms:contentKeyID: 35272189
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# Visual Studio Integration 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX development can be done in either X++ or in .NET managed code. Each type of development has its own environment, MorphX and Visual Studio respectively. Visual Studio Tools for Microsoft Dynamics AX (Visual Studio Tools) provides a set of tools and functionality that support development in managed code as shown in the following diagram. Visual Studio Tools contains tools and functionality from both the MorphX and Visual Studio development environments. For more information about development in MorphX, see [Microsoft Dynamics AX IDE](microsoft-dynamics-ax-ide.md)

![Visual Studio Tools for Microsoft Dynamics AX](images/Gg889299.VisualStudioToolsForMSDAX(AX.60).gif "Visual Studio Tools for Microsoft Dynamics AX")


> [!TIP]
> <P>To apply advanced criteria to your search for Help about Microsoft Dynamics AX, use the <A href="http://go.microsoft.com/fwlink/?linkid=247587%26xver=ax060">WebSearchAx</A> tool.</P>



## Modeling Tools

Modeling tools and functionality enable you to create reports that are accessed within Microsoft Dynamics AX. For more information, see [Creating Reports Overview](https://msdn.microsoft.com/en-us/library/cc557922\(v=ax.60\)).

### Reporting Tools

SQL Server Reporting Services is the reporting platform for Microsoft Dynamics AX. Reporting Services tools work in the Visual Studio environment and are fully integrated with SQL Server tools and components. Visual Studio Reporting Tools for Microsoft Dynamics AX enables you to create Reporting Services reports that access data in the Microsoft Dynamics AX database. After you have deployed a report to the report server you can access the report in the client. To access a report in the client, you can add a menu item in the Application Object Tree (AOT). To access the report in Enterprise Portal, you can add a report Web part. For more information about reporting tools, see [Developing Reports for Microsoft Dynamics AX in Visual Studio](https://msdn.microsoft.com/en-us/library/cc653472\(v=ax.60\)).

## Managed Code Integration

Microsoft Dynamics AX provides a set of tools and functionality that enable you to create and work with managed code related to Enterprise Portal (EP) development, analytics, or with managed code development in general.

### Enterprise Portal Tools

Visual Studio Tools for Microsoft Dynamics AX contains tools that you use to work with User Controls for Enterprise Portal. The layout of a User Control is designed in Visual Studio. Components from the Visual Studio Toolbox are available for use in the User Control. The code editor in Visual Studio is used to add code to the User Control. After they are completed, User Controls can be debugged in the Visual Studio environment.

### Analytics Tools

SQL Server Business Intelligence Development Studio (BIDS) is Microsoft Visual Studio with additional project types that are specific to SQL Server business intelligence. BIDS provides a variety of designers, tools, and wizards to work with the objects in Analysis Services projects that are generated from perspectives in Microsoft Dynamics AX. You can define or update cube features. For example, you may want to update the goals for the KPIs for an existing cube. You can deploy and process cubes within BIDS. For more information, see [Analytics in Microsoft Dynamics AX](https://msdn.microsoft.com/en-us/library/ee873272\(v=ax.60\)).

### Managed Code Business Logic

You can write business logic in C\# or Visual Basic and manage this code in Microsoft Dynamics AX just as you would with X++ classes.

  - You can save C\# or Visual Basic class library projects to the AOT.

  - You can customize these managed code projects using the various layers.

  - Managed code projects are updated when you compile solutions in Visual Studio and are automatically deployed if required. Any modifications to the managed project are immediately reflected in the AOT and persisted in the model store.

### Proxies

Proxies enable you to add an AOT element such as a class or table to your project in Visual Studio so that it can be accessed by managed code. When you add an X++ class or table to a project by using Application Explorer in Visual Studio, a proxy for that class is created internally by the system. For more information see [Visual Studio Development for Microsoft Dynamics AX](visual-studio-development-for-microsoft-dynamics-ax.md) and [Walkthrough: Adding an X++ Object to a Visual Studio Project](walkthrough-adding-an-x-object-to-a-visual-studio-project.md).

### Event Handlers

You can create event handlers for class methods in the AOT. An event handler can be written in managed code or in X++. Event handlers can only handle events raised by a class in the **Classes** node in the AOT. For more information, see [Visual Studio Development for Microsoft Dynamics AX](visual-studio-development-for-microsoft-dynamics-ax.md) and [Walkthrough: Creating an Event Handler in Visual Studio](walkthrough-creating-an-event-handler-in-visual-studio.md).

### Deployment

You can deploy managed assemblies (DLLs) that you create in Visual Studio to Microsoft Dynamics AX. Managed code assemblies are automatically deployed to the location that you specify: client, server, Reporting Services or EP. For more information, see [Visual Studio Development for Microsoft Dynamics AX](visual-studio-development-for-microsoft-dynamics-ax.md) and [Deploying Managed Code](deploying-managed-code.md).

## Managed Code Tools

Managed code tools are tools available in either MorphX or Visual Studio that enable you to work with managed code. These tools include the following:

  - Application Explorer

  - Version Control System

  - Cross-Reference Tool

  - Code Upgrade Tools

### Application Explorer

Application Explorer is a tool in Visual Studio that provides a view into the AOT in Microsoft Dynamics AX. In Application Explorer, you can view, edit, and delete elements in the AOT whether they are managed code or X++ elements. For more information, see [Visual Studio Development for Microsoft Dynamics AX](visual-studio-development-for-microsoft-dynamics-ax.md) and [Application Explorer](application-explorer.md).

To use Application Explorer in Visual Studio, you must first install the Visual Studio Tools as part of the Microsoft Dynamics AX installation. For more information, see [Installing Visual Studio Tools](installing-visual-studio-tools.md).

### Version Control System

You can integrate a Version Control System (VCS) into the MorphX Integrated Development Environment (IDE). You can use this VCS integration for Microsoft Dynamics AX development in Visual Studio, as well as for development in X++. You can use Microsoft Visual SourceSafe, Team Foundation Server, or MorphX VCS for version control. You can also integrate a third-party VCS. For more information, see [Version Control System](version-control-system.md)

### Cross-Reference Tool

The [Cross-reference Tool](cross-reference-tool.md) in Microsoft Dynamics AX lets you see the relationships between objects. By using the Cross-reference tool, you can see which other objects the current object uses or which other objects use the current object. The Cross-reference tool fully supports Visual Studio projects in the AOT (under the Visual Studio Projects node). For more information, see [Visual Studio Development for Microsoft Dynamics AX](visual-studio-development-for-microsoft-dynamics-ax.md) and [Cross-References and Visual Studio Projects](cross-references-and-visual-studio-projects.md).

### Code Upgrade Tools

The code upgrade tools enable you to detect and resolve conflicts between two versions of Microsoft Dynamics AX. The code upgrade tools that are included with Microsoft Dynamics AX support managed code development, so the same code upgrade process can be used for code whether it originates from MorphX or Visual Studio. For more information, see [Visual Studio Development for Microsoft Dynamics AX](visual-studio-development-for-microsoft-dynamics-ax.md) and [Upgrade Support for Managed Code](upgrade-support-for-managed-code.md).

## See also

[Visual Studio Development for Microsoft Dynamics AX](visual-studio-development-for-microsoft-dynamics-ax.md)

[Installing Visual Studio Tools](installing-visual-studio-tools.md)

[Microsoft Dynamics AX IDE](microsoft-dynamics-ax-ide.md)

