---
title: 'How to: Enable Hot Swapping of Assemblies'
TOCTitle: 'How to: Enable Hot Swapping of Assemblies'
ms:assetid: 9571ef49-4978-4cb8-b0f8-67343f414a06
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889279(v=AX.60)
ms:contentKeyID: 35272171
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# How to: Enable Hot Swapping of Assemblies 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The hot swapping option enables you to deploy assemblies to the server without the inconvenience of restarting the Application Object Server (AOS). Hot swapping of assemblies is for use only in development scenarios.

Hot swapping is supported by having the AOS create more than one application domain. An application domain is an instance of the .NET Framework class named System.AppDomain.

The default configuration for the AOS is to have its hot swapping option turned off. When hot swapping is off, the AOS contains only one application domain. The AOS assigns all client connections to its single application domain.

However, if hot swapping was turned on before the AOS was restarted, a new application domain is created for each client connection. Each application domain loads the latest version of the assemblies. This means two application domains might contain different versions of the same assembly.

The following diagram illustrates the application domains in the AOS, when hot swapping is on.

![One AppDomain in AOS per client connection.](images/Gg889279.HotSwapAssembliesGm(AX.60).png "One AppDomain in AOS per client connection.")

The scenario illustrated by the preceding diagram is as follows:

1.  Hot swapping is turned on, and then the AOS is restarted.

2.  Client 1 connects to the AOS, so AppDomain 1 is created. This new application domain remains dedicated to client 1.  
    Later when client 1 eventually disconnects, AppDomain 1 will be discarded.

3.  When AppDomain 1 is created, the latest version of a given assembly DLL is v1.0, so that version is loaded into AppDomain 1.  
    The DLL is already known to Microsoft Dynamics AX because the Microsoft Visual Studio project that created the DLL is listed under **AOT** \> **Visual Studio Projects**.

4.  A developer uses Visual Studio to modify and recompile the DLL.  
    This causes a new version, v1.1, of the DLL to be deployed to the AOS server\\bin\\VSAssemblies\\ directory.

5.  Client 2 connects to the AOS, so AppDomain 2 is created. This new application domain remains dedicated to client 2.

6.  Version v1.1 of the DLL is loaded into AppDomain 2.

7.  Client 3 connects to the AOS, so AppDomain 3 is created. Version v1.1 of the DLL is loaded into AppDomain 3.

### To Enable Hot Swapping of Assemblies

1.  Open the Microsoft Dynamics AX server configuration utility by clicking **Start** \> **Administrative Tools** \> **Microsoft Dynamics AX 2012 Server Configuration**.  
    To change the server configuration, you must run the utility with administrative privileges.

2.  On the **Application Object Server** tab, select **Allow hot swapping of assemblies when the server is running**.

3.  Click **OK**. You will see a prompt that asks whether you want to restart the AOS service. The change will only take effect after you restart the AOS.

### To Turn Off Hot Swapping

After you have completed your code change and have compiled the assembly DLL for the last time, we recommend that you turn off hot swapping.

To turn off hot swapping, you clear the **Allow hot swapping of assemblies when the server is running** check box, and then restart the AOS. This ensures that all connections use the same version of the DLL.

## See also

[Deploying Managed Code](deploying-managed-code.md)

[How to: Configure Deployment of Managed Code Assemblies](how-to-configure-deployment-of-managed-code-assemblies.md)

[Deployment Overview of .NET Assemblies for Interop](deployment-overview-of-net-assemblies-for-interop.md)

