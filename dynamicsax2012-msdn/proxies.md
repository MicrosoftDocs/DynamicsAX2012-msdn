---
title: Proxies
TOCTitle: Proxies
ms:assetid: 266904fa-ee3c-445a-af4c-8007497d46eb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc568275(v=AX.60)
ms:contentKeyID: 28119411
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Proxies [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The code added for User Controls can access X++ code. To do this, you must use a proxy. This makes the X++ code resources available for use in the Visual Studio web application project. Microsoft Dynamics AX contains several proxies that are accessed by User Controls for Enterprise Portal. You can also create your own proxies to access X++ code resources from User Controls.

## Creating a Proxy for Enterprise Portal

Define the classes, methods, and enums as you typically would for X++ code. After the X++ code has been defined, you will create a class library project in Visual Studio. This project is used to create the proxy that allows User Controls in Enterprise Portal to access your X++ code resources. You will add the class library project to the AOT. Then you will use the Application Explorer to add the X++ code resources (classes, tables, and enums) that you want to access to the class library project. Refer to [Proxy Classes for .NET Interop to X++](proxy-classes-for-net-interop-to-x.md) for more information about creating a proxy.


> [!IMPORTANT]
> <P>When creating a proxy project to use with Enterprise Portal, the default namespace is important. In <STRONG>Solution Explorer</STRONG>, right-click the project and then click <STRONG>Properties</STRONG>. Display the Application properties. Set the <STRONG>Default namespace</STRONG> to: Microsoft.Dynamics.Portal.Application.Proxy and save the changes.</P>



After you add the proxy project to the AOT, be sure that you set the **Deploy to EP** property for the project in Visual Studio to **Proxies**. When the proxy project is deployed, this setting causes the proxy to be deployed to the server that is running Enterprise Portal. This setting also indicates that the proxy project is intended for use on Enterprise Portal.

## Creating a Reference to the Proxy Project

To use a proxy from within User Control code, you must create a reference to the proxy project.

### To create a reference to the proxy project

1.  In Visual Studio, open the web application project that you want to add a proxy reference to.

2.  In the **Project** menu, choose **Add EP Proxy Project**. A dialog will be displayed that lists all of the proxy projects that have been added to the AOT.

3.  Select the proxy project that you want to use for your User Control, and then click **OK**. The proxy project will be added to the solution, and a reference to the proxy project will be created.
    

    > [!TIP]
    > <P>If you do not see your proxy project listed, check the property settings for your proxy project. Be sure that you have set the <STRONG>Deploy to EP</STRONG> property to <STRONG>Proxies</STRONG> to indicate that the proxy project is to be used for Enterprise Portal.</P>



4.  In the code for your user control, add a using statement to provide access to the definitions in the proxy. For example, to access the resources in the proxy named FCMProxy, you would use the following statement:
    
    using FCMProxy;

## Using Predefined Proxies for Enterprise Portal

Enterprise Portal has several predefined proxies that are used when creating code for User Controls. The **EPApplicationProxies** project is the most commonly used proxy project. It contains definitions for several enums, classes, and tables that are frequently used in code for User Controls. Most User Controls will contain a reference to the **EPApplicationProxies** project. To use one of the predefined proxies, create a reference to it using the procedure in the previous section.

