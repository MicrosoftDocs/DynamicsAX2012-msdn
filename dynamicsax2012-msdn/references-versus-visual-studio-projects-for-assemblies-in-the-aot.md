---
title: References versus Visual Studio Projects for Assemblies in the AOT
TOCTitle: References versus Visual Studio Projects for Assemblies in the AOT
ms:assetid: df80650d-d873-476a-9ece-495a12d65745
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh538486(v=AX.60)
ms:contentKeyID: 39508919
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# References versus Visual Studio Projects for Assemblies in the AOT [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes the developer scenarios that involve .NET Framework assemblies. You can find information about .NET Framework assemblies in the following locations in the application object tree (AOT) of Microsoft Dynamics AX:

  - **AOT** \> **References**

  - **AOT** \> **Visual Studio Projects**

The Application Object Server (AOS) treats the items in these two AOT locations differently from each other.

## AOT \> References

The information in the **AOT** \> **References** nodes tells Microsoft Dynamics AX the names of assemblies that it must attempt to load when they are needed to support compile or run operations. The system looks for the assemblies first in the global assembly cache (GAC). If the assembly is not found there, the system next looks under the server\\bin\\ or client\\bin\\ directory.

This scenario starts with the existence of a .NET Framework assembly .dll file. For this scenario it is irrelevant how the .dll became available. The following list shows the sequence of events in this scenario:

1.  You manually copy the .dll file into your client\\bin\\ directory.  
    This step is unnecessary if the assembly is already in the GAC on your local computer.

2.  In the AOT, right-click the **References** node, and then click **Add reference**. The **Add reference** form is displayed.

3.  If the assembly is not in the list, click **Browse** to open the **Select file** form.

4.  Navigate to the client\\bin\\ directory and select your .dll file. Then click the **Open** button. The **Select file** form closes.

5.  Back in the **Add reference** form, the .dll file that you selected is listed in the bottom grid. Select your .dll file.

6.  Click **OK**. The form closes.  
    You can see your new entry under **AOT** \> **References**.

### ![Hh538486.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538486.collapse_all(en-us,AX.60).gif")No Ongoing Deployments

In the preceding **References** scenario, when you add a reference to the AOT, the AOS copies the assembly .dll file from your local computer to the server\\bin\\ directory on the hard drive of the AOS computer. The transfer of the assembly occurs only this one time. It occurs only in the direction from the client to the server.

Later, when another client tries to compile X++ code that depends on the referenced assembly, the compilation will fail unless the assembly already exists on the client. X++ code that runs on the client would also fail unless the assembly already exists on the client.

## AOT \> Visual Studio Projects

The AOS and Microsoft Visual Studio work together to automate the deployment of an assembly and its corresponding project into the metadata stores of the AOS. After the AOS has this metadata, the AOS can distribute the assembly to clients as needed.

The following list shows the sequence of events when you use Visual Studio to write C\# code and compile a DLL assembly file:

1.  In Visual Studio you compile your DLL.

2.  You right-click your project node, and then click **Add YourProjectName to AOT**.  
    This causes your Visual Studio client to pass to the AOS textual and binary parameters which represent your .csproj and .dll files and other files. This adds your project under **AOT** \> **Visual Studio Projects**.

3.  Each successive compilation causes Visual Studio to again call the AOS to pass the latest files to the AOS.

### ![Hh538486.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538486.collapse_all(en-us,AX.60).gif")Ongoing Deployments

In the preceding **Visual Studio Projects** scenario, you do not need to manually copy any assembly files to any location. The system handles all the file management. The AOS contains your assembly in the database that the AOS manages for storing metadata.

Later, when the .dll file is needed for a process that runs on the AOS, the AOS copies the .dll file from the database and stores the .dll file under the server\\bin\\VSAssemblies\\ directory on its local hard drive. (The exact directory path might vary slightly between installations.)


> [!NOTE]
> <P>In production environments, the AOS has the security authority to write under its local server\bin\ directory, whereas clients on other computers typically do not.</P>



If a client needs the .dll file in order to compile or run X++ code that references classes that are in the .dll file, the client calls the AOS for a copy of the .dll file.

## See also

[Deployment Overview of .NET Assemblies for Interop](deployment-overview-of-net-assemblies-for-interop.md)

[.NET Framework Classes for Microsoft Dynamics AX](https://msdn.microsoft.com/en-us/library/gg990362\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

