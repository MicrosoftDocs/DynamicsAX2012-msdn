---
title: 'How to: Use a Predefined Proxy for a Web Application Project'
TOCTitle: 'How to: Use a Predefined Proxy for a Web Application Project'
ms:assetid: 5f6c35f4-65d7-4d68-8351-258dbebb36f3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg846077(v=AX.60)
ms:contentKeyID: 35245348
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Use a Predefined Proxy for a Web Application Project 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

It is common for EP Web Application projects to access some of the required Microsoft Dynamics AX resources through a proxy. Resources like X++ classes, methods, and enumerations are typically accessed in this manner. A separate Visual Studio project is used to define the proxy.

Enterprise Portal has several predefined proxies that are used when you are creating code for User Controls. The **EPApplicationProxies** project is the most frequently-used proxy project. It contains definitions for several enums, classes, and tables that are used in code for User Controls.


> [!IMPORTANT]
> <P>Most EP Web Application projects for User Controls must have a reference to the <STRONG>EPApplicationProxies</STRONG> project, or they will not build correctly.</P>



To use one of the predefined proxies, you must create a reference to the proxy project.

## Adding a Reference to a Predefined Proxy Project

### To add a reference to a predefined proxy project

1.  Start Visual Studio.

2.  Open the EP Web Application project you created.

3.  In the **Project** menu, choose **Add EP Proxy Project**. A dialog box will be displayed that lists all of the proxy projects that have been added to the AOT.

4.  Select the proxy project that you want to use for your User Control, such as **EPApplicationProxies**, and then click **OK**. The proxy project will be added to the solution, and a reference to the proxy project will be created.

## See also

[Proxies](proxies.md)

