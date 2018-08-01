---
title: 'How to: Configure Deployment of Managed Code Assemblies'
TOCTitle: 'How to: Configure Deployment of Managed Code Assemblies'
ms:assetid: 632c5038-deb3-4a25-a617-bd0d94eaf9e0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889216(v=AX.60)
ms:contentKeyID: 35272110
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# How to: Configure Deployment of Managed Code Assemblies [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

After you write code in Microsoft Visual Studio and add the project to the model store, you can configure the deployment of the project output to various locations. You can do this by setting project properties. This topic explains how to deploy project output such as an assembly (DLL). For more information, see [Deploying Managed Code](deploying-managed-code.md).

## Prerequisites

To complete this scenario you will need:

  - Microsoft Dynamics AX with Visual Studio Tools installed

  - Visual Studio 2010

### Deploy an Assembly

1.  Open Visual Studio and create a new project such as a C\# Class Library project.

2.  Compile the project by pressing Shift+F6.

3.  Add the project to the model store by using Application Explorer. For more information, see [How to: Add a Visual Studio Project to the AOT](how-to-add-a-visual-studio-project-to-the-aot.md).

4.  After you add the project to the model store, set the project deployment properties based on where you want to deploy the assembly. For more information, see [Deploying Managed Code](deploying-managed-code.md). The deployment properties are as follows:
    
      - Deploy to Server
    
      - Deploy to Client
    
      - Deploy to EP
    
    In this case, set the **Deploy to Server** and **Deploy to Client** properties to Yes.
    

    > [!TIP]
    > <P>To deploy an assembly to the server when you are developing, you must enable hot swapping of assemblies. For more information, see <A href="how-to-enable-hot-swapping-of-assemblies.md">How to: Enable Hot Swapping of Assemblies</A>. Hot swapping is only necessary for assemblies that are deployed to the server.</P>



5.  In Solution Explorer, right-click the project and then click **Deploy**. The assembly is then deployed to both the server and the client. Clients that are currently connected will not use the updated assembly until they reconnect and make a call to managed code.

## See also

[Deploying Managed Code](deploying-managed-code.md)

[How to: Enable Hot Swapping of Assemblies](how-to-enable-hot-swapping-of-assemblies.md)

