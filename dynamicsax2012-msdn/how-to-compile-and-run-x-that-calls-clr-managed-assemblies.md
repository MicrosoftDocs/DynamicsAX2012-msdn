---
title: 'How to: Compile and Run X++ that Calls CLR Managed Assemblies'
TOCTitle: 'How to: Compile and Run X++ that Calls CLR Managed Assemblies'
ms:assetid: 3424a5ab-0efb-48d2-8b47-0f1dcf11815e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc586538(v=AX.60)
ms:contentKeyID: 35241999
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Compile and Run X++ that Calls CLR Managed Assemblies [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you write X++ code that calls into an assembly that is managed by the common language runtime (CLR) of the .NET Framework, you must make sure that the X++ compiler can find the assembly.

## How CLR Managed Assemblies are Found by the X++ Compiler

If your X++ code calls the .NET Framework class System.String, the X++ compiler finds the managed assembly because of two system configurations:

  - In the Application Object Tree (AOT), there is a reference under the **References** node to the assembly that contains the class.

  - The assembly is in the Global Assembly Cache.

The installation of Microsoft Dynamics AX includes references to some of the commonly needed .NET Framework assemblies.

### ![Cc586538.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc586538.collapse_all(en-us,AX.60).gif")Referencing Your Assemblies

If your X++ code calls into a CLR managed assembly that you wrote, you must follow these steps.

### To compile on the client

1.  Copy your assembly into the client\\bin\\ directory under your Microsoft Dynamics AX installation directory.
    

    > [!NOTE]
    > <P>Your full path might resemble C:\Program Files\Microsoft Dynamics AX\version\client\bin\.</P>



2.  In the AOT, right-click **References**, and then click **Add Reference**.

3.  Click the **Browse** button.

4.  In the **Select file** dialog box, select your assembly file. Click **Open**.

## Running on a Tier that Has Your Assembly

Your X++ code might be unable to run on the Application Object Server (AOS) tier, even though your X++ code compiles successfully on the client. A copy of each assembly that is needed by your X++ code must exist on the AOS computer for your X++ code to run on the AOS tier.

To run your X++ code on the AOS tier, you must copy your assembly to the server\\...\\bin\\ subdirectory on the AOS computer. This is located under the Microsoft Dynamics AX installation directory.

It is not required to provide any reference to the assembly because the X++ code is already compiled.

## See also

[.NET Interop from X++](net-interop-from-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

