---
title: 'How to: Schedule Cross-references Without a Batch'
TOCTitle: 'How to: Schedule Cross-references Without a Batch'
ms:assetid: 1553ba83-c907-49ce-a1c7-e1974e93d75c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc566587(v=AX.60)
ms:contentKeyID: 35240610
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Schedule Cross-references Without a Batch 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX can gather and report cross-reference information. For example, this information can tell you which methods use a given table. A full refresh of the cross-reference information takes several hours. The refresh must run on the client, not on the Application Object Server (AOS). Therefore it is often desirable to schedule the cross-reference refresh to start after your normal working hours.

There are different ways you can run a refresh of the cross-reference information, some of which are automatic and unattended. The options include the following:

  - Use the client menu to start a cross-reference refresh immediately.

  - Use the Microsoft Windows operating system to schedule a run of Ax32.exe at designated times.

  - Use the client to refresh the cross reference information by calling the xRefUpdate.updateAll method in a job.

You cannot run a cross-reference refresh by using the Microsoft Dynamics AX batch system.

## Use the Client Menu for an Immediate Run

You can run a cross-reference refresh immediately by using the client menu. It might take several hours to complete. It might be hard to use your computer during this time.

  - In the client menu, click **Tools**, click **Development Tools**, click **Cross-reference**, **Periodic**, and then click **Update**.

## Schedule Ax32.exe through Windows

You can run Ax32.exe through the command line on the client computer. You must supply the appropriate parameter to generate a complete refresh of the cross-reference information.

    "C:\Program Files\Microsoft Dynamics AX\60\Client\Bin\Ax32.exe"  -startupcmd=CompileAll_+

The full path of Ax32.exe varies among installations. The previous example is the default installation path, but your path might be different. For example, the directory name shown as 60\\ varies by product version.

Windows provides the **Task Scheduler** utility. You can use the **Task Scheduler** utility to run the Ax32.exe command line for you. You can setup the task scheduler to run the task at specified times or intervals For instance, you can have the task run every day at 1 a.m., or have it run only on particular dates, and so on.


> [!NOTE]
> <P>In the <STRONG>Task Scheduler</STRONG>, select the option that indicates that the task should begin only if you are logged on. This gives the process the necessary security credentials.</P>



### ![Cc566587.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc566587.collapse_all(en-us,AX.60).gif")Finding the Task Scheduler on Windows

The procedure on how to find the Windows Task Scheduler depends on the version of Windows.

### To find the task scheduler on Windows 7

1.  In Windows 7, click the **Start** menu button.

2.  Click **Control Panel**.

3.  Click **System and Security**.

4.  Double-click **Administrative Tools**.

5.  Double-click **Task Scheduler**.

### To find the task scheduler on Windows Vista

1.  In Windows Vista, click the **Start** menu button.

2.  Click **Control Panel**.

3.  Double-click **Administrative Tools**.

4.  Double-click **Task Scheduler**.

### To find the task scheduler on Windows XP

1.  In Windows XP, click the **Start** menu button.

2.  Click **Control Panel**.

3.  Double-click **Scheduled Tasks**.

\-or-

1.  Click the **Start** menu button.

2.  Click **All Programs**.

3.  Click **Accessories**.

4.  Click **System Tools**.

5.  Click **Scheduled Tasks**.

### ![Cc566587.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc566587.collapse_all(en-us,AX.60).gif")The AT.exe Command Line Alternative

As an alternative to the graphical user interface of the **Task Scheduler**, you can use the AT.exe command line utility to interact with the **Task Scheduler** service. For more information, run AT.exe /? for the utility documentation.

## See also

[Cross-reference Tool](cross-reference-tool.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

