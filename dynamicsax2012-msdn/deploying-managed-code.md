---
title: Deploying Managed Code
TOCTitle: Deploying Managed Code
ms:assetid: 54955e3b-f484-4337-ba07-488a91fbb577
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889192(v=AX.60)
ms:contentKeyID: 35272084
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# Deploying Managed Code [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Visual Studio Tools lets developers automatically deploy the output of their managed code projects. For example, if you have a class library project, deployment involves copying the assembly to the correct locations.

To enable the deployment features, you must first add your project to the model store in Microsoft Dynamics AX. For more information, see [Adding a Visual Studio Project to the AOT](adding-a-visual-studio-project-to-the-aot.md) and [How to: Add a Visual Studio Project to the AOT](how-to-add-a-visual-studio-project-to-the-aot.md).

This topic describes how the deployment of managed code for Microsoft Dynamics AX works. For more information about how to deploy code, see [How to: Configure Deployment of Managed Code Assemblies](how-to-configure-deployment-of-managed-code-assemblies.md).

The general sequence of events for deploying managed code is as follows:

1.  Build the project and add it to the model store.

2.  Set the deployment properties for the project.

3.  Right-click the project and then click **Deploy**. When the managed code is actually deployed depends on the deployment options that you select.

## Project Properties for Deployment

After you add a project to the Application Object Tree (AOT), project properties are enabled that let you define where the project should be deployed.

  - Deploy to Server

  - Deploy to Client

  - Deploy to EP

The managed code deployment properties are available at the project level. To view these properties in Visual Studio, select the project in Solution and Explorer and then click **View** \> **Properties Window**.


> [!TIP]
> <P>Not all deployment properties are available for all project types. For example, Enterprise Portal Web projects and SSRS projects do not have any deployment properties. The system will automatically deploy the output of those projects to the appropriate locations.</P>



### Deploy to Server

When you add a managed code project to the model store, the project files (including the source code) as well as the output, are stored in the model store. If the **Deploy to Server** property is set to **Yes**, the system deploys the project output (a DLL, for example) by copying it to the server Bin directory. The server Bin directory could be located at C:\\Program Files\\Microsoft Dynamics AX\\60\\Server\\MicrosoftDynamicsAX\\Bin\\VSAssemblies\\. After you deploy the assembly to the server, you must restart the AOS. This is so that the assembly can be loaded by the AOS. If you have hot swapping enabled, you do not have to restart the AOS.

Assemblies are deployed to the server based on how you configure hot swapping. Hot swapping should only be enabled in development scenarios. For more information, see [How to: Enable Hot Swapping of Assemblies](how-to-enable-hot-swapping-of-assemblies.md).

### Deploy to Client

When you add a managed code project to the model store, the project files as well as the output, are stored in the model store. If the **Deploy to Client** property is set to **Yes**, the system deploys the project output (a DLL, for example) by copying it to the client Bin directory. The client Bin directory could be located at C:\\Users\\ \<YourUserName\> \\AppData\\Local\\Microsoft\\Dynamics AX\\VSAssemblies\\.

When you deploy to the client, the assembly is copied to the client the first time it is needed. If you deploy an assembly and you want it to download to a client computer, you must first close the client (if it is open), deploy the assembly, and then start the client again. When the assembly is needed by code running on the client, it is downloaded to the client computer.

An assembly is copied to the client under these circumstances:

  - When a call is made from the client to managed code that is contained in the assembly.

  - When you access IntelliSense (at design time).

  - When you compile code that references the managed code assembly.

### Deploy to Enterprise Portal

If the **Deploy to EP** property is set to **Yes**, the system deploys the compiled project output to the Bin folder for the Enterprise Portal server. Typically, the Bin folder is located here:

C:\\intetpub\\wwwroot\\wss\\VirtualDirectorys\\80\\

If the **Deploy to EP** property is set to **Proxies**, only the .cs files for the project are deployed to the Proxies folder within the App\_Code folder for the Enterprise Portal server. Typically, the App\_Code folder is located here:

C:\\intetpub\\wwwroot\\wss\\VirtualDirectories\\80\\

Deploying only the .cs files is the standard practice for deploying proxies to Enterprise Portal, because it reduces the chance of namespace issues when you use objects from the proxy.

Use the **Deploy** command in Visual Studio to deploy the proxies or compiled assembly for the managed code to the Enterprise Portal server. The AxUpdatePortal utility can also be used to deploy the files.


> [!IMPORTANT]
> <P>When creating a proxy project to use with Enterprise Portal, the default namespace is important. In <STRONG>Solution Explorer</STRONG>, right-click the project and then click <STRONG>Properties</STRONG>. Display the Application properties. Set the <STRONG>Default namespace</STRONG> to: Microsoft.Dynamics.Portal.Application.Proxy and save the changes.</P>



## See also

[Adding a Visual Studio Project to the AOT](adding-a-visual-studio-project-to-the-aot.md)

[How to: Add a Visual Studio Project to the AOT](how-to-add-a-visual-studio-project-to-the-aot.md)

