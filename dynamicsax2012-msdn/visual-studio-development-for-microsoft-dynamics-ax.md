---
title: Visual Studio Development for Microsoft Dynamics AX
TOCTitle: Visual Studio Development for Microsoft Dynamics AX
ms:assetid: 3b2cfb0f-4211-42ca-a514-55af7ff11dcd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889157(v=AX.60)
ms:contentKeyID: 35272052
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# Visual Studio Development for Microsoft Dynamics AX 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft Dynamics AX development environment (MorphX) and the Visual Studio development environment are integrated through Visual Studio Tools for Microsoft Dynamics AX (Visual Studio Tools). Visual Studio Tools is a collection of tools and functionality that enable managed code development for Microsoft Dynamics AX.

Visual Studio Tools gives developers a rapid application development (RAD) experience and supports managed code within MorphX and the Visual Studio integrated development environment (IDE). The tools and functionality can be categorized as follows:

  - Managed code integration functionality

  - Managed code tools in both MorphX and Visual Studio

Close integration between MorphX and Visual Studio means that developers can take advantage of the benefits of each development tool and work in the environment that best suits their development scenario. For more information, see [Selecting the Best Development Technology for Your Application Development Scenario](http://go.microsoft.com/fwlink/?linkid=213138).


> [!NOTE]
> <P>Managed code is code that is executed by the common language runtime (CLR) environment instead of directly by the operating system. Managed code applications gain common language runtime services such as automatic garbage collection, runtime type checking and security support, and so on. In this context, it refers to .NET managed code.</P>



## Managed Code Integration Functionality

Managed code integration refers to a set of capabilities that enable integration between X++ objects and managed code. This integration is provided by the following developer features:

  - Managed code business logic

  - Proxies

  - Event handlers

### Managed Code Business Logic

You can write business logic in C\# or Visual Basic and manage this code in Microsoft Dynamics AX just as you would with X++ classes.

  - You can save C\# or Visual Basic class library projects to the model store.

  - You can customize these managed code projects using the various layers.

  - Managed code projects are updated when you build in Visual Studio and automatically deployed if they are configured to do so. Any modifications to the managed project are live and persisted to the Microsoft Dynamics AX model store. For more information, see [Model store architecture](https://msdn.microsoft.com/en-us/library/dd362019\(v=ax.60\)).

### Proxies

This feature lets you add an X++ object to your project in Visual Studio so that it can be accessed by managed code. You can add the following X++ object types to a project: classes, tables and enums.

When you add an X++ object to a project by using the Application Explorer, a proxy for that class is created internally by the system. After the proxy is created, that type is available as a strong type and features such as IntelliSense are available. For more information, see [Integration with X++ Objects from Visual Studio](integration-with-x-objects-from-visual-studio.md) and [Walkthrough: Adding an X++ Object to a Visual Studio Project](walkthrough-adding-an-x-object-to-a-visual-studio-project.md). For more information about proxies, see [Proxy Classes for .NET Interop to X++](proxy-classes-for-net-interop-to-x.md)

If you change an X++ object after you add it to a project, the proxy is automatically updated.

### Event Handlers

You can create an event handler in managed code or X++. The event handler subscribes to an event (method) in X++. Event handlers can handle events raised only by a class in the **Classes** node in the Application Object Tree (AOT). For more information about event handlers in the AOT, see [Event Handler Nodes in the AOT](event-handler-nodes-in-the-aot.md). For more information about managed code event handlers, see [Integration with X++ Objects from Visual Studio](integration-with-x-objects-from-visual-studio.md) and [Walkthrough: Creating an Event Handler in Visual Studio](walkthrough-creating-an-event-handler-in-visual-studio.md).

### Deployment from Visual Studio

The deployment functionality enables you to make assemblies (DLLs) that you create in Visual Studio available in Microsoft Dynamics AX. After you specify whether the assembly should be deployed to the client, server, or Enterprise Portal, the system deploys the assembly to the appropriate locations. For more information, see [Deploying Managed Code](deploying-managed-code.md).

## Managed Code Tools

In addition to the managed code integration functionality, there are tools in both MorphX and Visual Studio that support managed code development. These tools include the following:

  - Application Explorer in Visual Studio

  - AOT support for Visual Studio projects

  - Cross-reference tool support for managed code in MorphX

  - Code upgrade tools support for managed code in MorphX

### Application Explorer in Visual Studio

Application Explorer is a tool in Visual Studio that provides a view into the Microsoft Dynamics AX model store. You can use Application Explorer to:

  - View the properties of elements in the AOT

  - View code for elements in the AOT

  - Add AOT elements to a Visual Studio Project

  - Open a Visual Studio project for edit

  - Remove a project from the model store

### Visual Studio Projects in the AOT

When you create a project in Visual Studio, you can add it to the model store by using Application Explorer. After you add a project to the model store, the project appears in the AOT below the **Visual Studio Projects** node. As you add files to your project, those changes are reflected in the AOT. After you add a project to the model store, the managed code in that project can be accessed in Microsoft Dynamics AX.


> [!IMPORTANT]
> <P>You must add a managed code project to the model store before you can access it from Microsoft Dynamics AX. This is necessary if you want X++ elements and managed code elements to interact, for example, if you create a managed code event handler.</P>



### Cross-Reference Tool

The [Cross-reference Tool](cross-reference-tool.md) in Microsoft Dynamics AX lets you see the relationships between objects. By using the Cross-reference tool, you can see which other objects the current object uses or which other objects use the current object. The Cross-reference tool fully supports Visual Studio projects in the AOT (under the Visual Studio Projects node). This means you can identify whether an AOT element such as an X++ class or a managed code class is used by a managed code project.

### Code Upgrade

The code upgrade tools enable developers to detect and resolve conflicts between two versions of Microsoft Dynamics AX. The layered architecture of Microsoft Dynamics AX enables third-parties such as VARs to customize the code base and add functionality. When an updated version of Microsoft Dynamics AX such as a service pack is released, conflicts can occur when the service pack contains changes to elements that were also changed by the VAR. The code upgrade tools are used to find and resolve these conflicts. The code upgrade tools include the following:

  - Detect code upgrade conflicts tool - Compares the elements in the current layer and the underlying layer. If any differing elements are found, the tool creates an upgrade project and moves the conflicting element in the current layer to that project. You then use the Compare tool to analyze the conflicts and decide which element should be included in the current layer.
    
    The Detect code upgrade conflicts tool supports managed code that has been added to the model store by using Application Explorer. This means you use the same process to upgrade code, whether that code originates from MorphX or Visual Studio.

  - Compare tool - Compares two elements in the AOT or two elements in an upgrade project created by the Detect code upgrade conflicts tool. The Compare tool supports managed code so that you can compare two managed code files in the AOT.

## See also

[Visual Studio Integration](visual-studio-integration.md)

[Installing Visual Studio Tools](installing-visual-studio-tools.md)

