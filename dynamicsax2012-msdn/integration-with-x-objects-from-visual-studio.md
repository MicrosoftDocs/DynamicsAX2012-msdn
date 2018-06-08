---
title: Integration with X++ Objects  from Visual Studio
TOCTitle: Integration with X++ Objects  from Visual Studio
ms:assetid: 3ce3d09e-6f79-4737-b5cf-14247e493139
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889166(v=AX.60)
ms:contentKeyID: 35272059
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# Integration with X++ Objects from Visual Studio 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The two features in Microsoft Dynamics AX that support managed code and X++ interop are proxies and event handlers.

## Proxies

Proxies enable you to add an AOT element to your project in Visual Studio so that element can be accessed by managed code. When you add an AOT element to a project by using Application Explorer, a proxy for that element is created internally by the system.

The AOT elements that you can add to a managed code project are as follows:

  - Classes

  - Tables

  - Enums

After you add the AOT element to your managed code project, all the methods and properties are available through IntelliSense. For more information, see [Walkthrough: Adding an X++ Object to a Visual Studio Project](walkthrough-adding-an-x-object-to-a-visual-studio-project.md).

A typical scenario for adding an X++ object to managed code is when you identify managed code functionality that you want to call from X++. This functionality may already be located in managed code or the development scenario may require that it run in managed code.

For example, you might want to have your Microsoft Dynamics AX installation updated with customer data from an external system. In this case, you create an X++ job that is scheduled to run periodically and calls a managed code class method. This method could then check for the external data and then call the appropriate CustTable methods to update the customer data (see the following diagram). Because the managed code that you write runs in the Microsoft Dynamics AX process, that code will typically be in a class library project.

The following diagram provides a high-level view of the integration of X++ and managed code. The initial call from X++ to managed code can originate from either an X++ .NET interop call or from an event handler.

![Proxies Managed Code Flow](images/Gg889166.ProxiesManagedCodeFlow(AX.60).gif "Proxies Managed Code Flow")

**X++ and managed code integration**

## Event Handlers

In the AOT, you can associate a class method with an event handler. An event handler is code that runs before the associated method runs or after the associated method has finished running. The event handler itself is also a class method, and it can be written in either X++ or managed code.

For example, you may have an X++ class method called MyClass.myMethod, and you have managed code that you want to run after the MyClass.myMethod method has finished running. In this case, you would create an event handler class and method in managed code, such as MyEventHandlerClass.PostmyMethod. This event handler contains the code that will execute after the MyClass.myMethod method is called.

When you add an event handler in Visual Studio, the system automatically creates a method that begins with either “Pre” (for event handlers that run before the method runs) or “Post” (for event handlers that run after the method completes). An event handler subscription is also automatically added to the MyClass.myMethod method. In addition, the properties of that subscription are set to point to the managed code class method. After the MyClass.myMethod method has finished running, then the MyEventHandlerClass.PostmyMethod event handler code executes. Event handlers can only be associated with a class in the AOT **Classes** node. For more information about event handlers, see [Event Handler Nodes in the AOT](event-handler-nodes-in-the-aot.md).

The following diagram illustrates how a managed code post-event handler is called. You can create the managed code class method and configure the event handler in the AOT to call that class method all from Visual Studio. For more information, see [Walkthrough: Creating an Event Handler in Visual Studio](walkthrough-creating-an-event-handler-in-visual-studio.md).

![Managed Code Event Handler Flow](images/Gg889166.ManagedCodeEventHandlerFlow(AX.60).gif "Managed Code Event Handler Flow")

**Managed code post-event handler flow**

## See also

[Walkthrough: Adding an X++ Object to a Visual Studio Project](walkthrough-adding-an-x-object-to-a-visual-studio-project.md)

[Walkthrough: Creating an Event Handler in Visual Studio](walkthrough-creating-an-event-handler-in-visual-studio.md)

[Proxy Classes for .NET Interop to X++](proxy-classes-for-net-interop-to-x.md)

[.NET Interop from X++](net-interop-from-x.md)

