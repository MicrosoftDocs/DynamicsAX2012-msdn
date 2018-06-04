---
title: Hot-swapping of .NET Assemblies in the AOS
TOCTitle: Hot-swapping of .NET Assemblies in the AOS
ms:assetid: e39c1cc2-4eb7-493c-b909-c58f2a3fdfeb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh538487(v=AX.60)
ms:contentKeyID: 39508920
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Hot-swapping of .NET Assemblies in the AOS 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In your development environment, you can use the hot-swap feature of the Application Object Server (AOS) to use updated assembly DLL files without having to repeatedly stop and restart the AOS. Restarting the AOS terminates the connections from other developer clients, which can be an inconvenience.


> [!NOTE]
> <P>The hot-swap feature applies only to assemblies that are used by X++ code that runs on the AOS, not for assemblies that are used on the client only.</P>



The following sections explain the importance of application domains in the hot-swap feature. An application domain is an instance of the .NET Framework class named System.AppDomain.

## Visual Studio Scenarios

The primary use for the hot-swap feature is in the following standard development cycle with Microsoft Visual Studio. This involves the **AOT** \> **Visual Studio Projects** area, which is analogous to the **Visual Studio Projects** area of the **Application Explorer** window for Microsoft Dynamics AX in Visual Studio. The scenario begins with the following steps:

1.  In Visual Studio, write the C\# code for an assembly DLL that you will call from X++ code.

2.  Compile the DLL. Add more code, and compile again.

3.  Add the Visual Studio project to the **Application Explorer** window.  
    Do this by right-clicking the project in the **Solution Explorer** window of Visual Studio, and then clicking **Add YourProjectName to AOT**.
    
    This action causes Visual Studio to send various project files to the AOS, including the assembly DLL file. The AOS saves the contents of these files in its metadata stores.

4.  Start a new Microsoft Dynamics AX AX32.exe client.  
    In some cases where the project creates an .exe file instead of a .dll file, an alternative is to press the F5 key in Visual Studio to initiate a run. This also creates a client connection to the AOS.

5.  In your AX32.exe client, run X++ code to test the new assembly DLL. Find a bug that requires a fix.

6.  In Visual Studio, modify the C\# code, and then compile the assembly again.  
    Each compile action sends the updated binary DLL file contents to the AOS to replace the older version in the metadata stores.

7.  Run X++ code to test the modified assembly.

A problem is encountered in the last step of the preceding list. The AOS has already loaded the earlier version of the assembly. You can activate the hot-swap feature to make the AOS load the updated version of the assembly for each new connection.

The following sections describe the scenarios for the two possible states of the hot- swap configuration option.

### ![Hh538487.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538487.collapse_all(en-us,AX.60).gif")Scenario with Hot-Swapping Off

The hot-swap configuration value is set to off when Microsoft Dynamics AX is installed. Under this default, one application domain is created when the AOS starts. No additional domains will be created. All .NET Framework assemblies that are loaded into the AOS share the single domain. Also, the single domain is shared by all client connections.

To test the updated assembly, you must restart the AOS. Then connect an AX32.exe client to the AOS, and run the tests. Having to restart the AOS after every compilation is inconvenient. The inconvenience is increased if other developers are sharing the same AOS, because their connections are broken with each restart. Their connections can be from an AX32.exe client, and from Visual Studio.

It is not necessary to stop and restart the AOS when you need the AOS to load a new assembly that it has not loaded before.

### ![Hh538487.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538487.collapse_all(en-us,AX.60).gif")Scenario with Hot-Swapping On

When the hot-swap configuration value is on, each new client connection to the AOS is assigned to a new application domain that is dedicated to that connection. Each connection has its own application domain. The creation of new application domains does not affect other connections.

Each new application domain is populated with the versions of assembly DLLs that are available to the AOS when the DLLs are loaded into the new domain. In any given application domain, no updates can be made to any assembly DLL that is already loaded into the domain.

In Visual Studio, after you modify your C\# code and again compile the assembly DLL, you only need to start a new AX32.exe client to gain access to the updated assembly for testing.

![One AppDomain in AOS per client connection.](images/Gg889279.HotSwapAssembliesGm(AX.60).png "One AppDomain in AOS per client connection.")

**Hot-swapping on: Each client connection gets its own AppDomain in the AOS.**

## How to Turn On Hot-Swapping

You can activate the hot swapping feature of the AOS by following these steps:

1.  Open the Microsoft Dynamics AX server configuration utility by clicking **Start** \> **Administrative Tools** \> **Microsoft Dynamics AX 2012 Server Configuration**.  
    To change the server configuration, you must run the utility with administrative privileges.

2.  On the **Application Object Server** tab, select **Allow hot swapping of assemblies when the server is running**.

3.  Click **OK**. You will see a prompt that asks whether you want to restart the AOS service. The change takes effect only after you restart the AOS.


> [!WARNING]
> <P>You should not use the hot-swap feature in your production environment. The AOS might consume a lot of memory due to an accumulation of application domains. Many assemblies would be loaded multiple times, which would waste memory resources.</P>



## See also

[Deploying Managed Code](deploying-managed-code.md)

[Deployment Overview of .NET Assemblies for Interop](deployment-overview-of-net-assemblies-for-interop.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

