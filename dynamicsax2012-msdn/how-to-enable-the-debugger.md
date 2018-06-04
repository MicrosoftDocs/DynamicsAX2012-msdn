---
title: 'How to: Enable the Debugger'
TOCTitle: 'How to: Enable the Debugger'
ms:assetid: 71f3d0ff-145a-46d4-afb8-93c8f8fd4882
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa569665(v=AX.60)
ms:contentKeyID: 35239297
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Enable the Debugger 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic shows you how to enable the debugger according to where the code is being executed: on the Microsoft Dynamics AX client, the Application Object Server (AOS), or Microsoft Dynamics AX Business Connector.

To run the Microsoft Dynamics AX Debugger, you must be a member of the **Microsoft Dynamics AX Debugging Users** group on the machine on which you are debugging. After you are added to this group, you must log off and log back on.


> [!NOTE]
> <P>On some operating systems it is necessary to run the debugger with administrator privileges. The operating systems on which this is necessary include Microsoft Windows 7 SP1, and Microsoft Windows Server 2008 R2 SP1.</P>



## To enable the debugger on the Microsoft Dynamics AX client

Enabling the debugger on the client allows you to debug code that runs on the client. You must first enable the debugger on the client before you enable it on either the Application Object Server (AOS) or Business Connector.

1.  On the **Tools** menu, click **Options** \> **Development**.

2.  Set the **Debug mode** field to **When Breakpoint**.


> [!NOTE]
> <P>The debugger can be related to only one instance of Microsoft Dynamics AX at a time. When you simultaneously debug code on two different clients on the same computer, two instances of the debugger are started.</P>



## To enable the debugger on the AOS

To debug code that is run on the AOS, you must enable this feature of the debugger.

1.  Enable the debugger on the client as shown in the first set of steps.

2.  On the computer that hosts the AOS, open the Microsoft Dynamics AX server configuration utility, which is a stand-alone utility that manages server configurations:
    
    1.  Click **Control Panel**, click **Administrative Tools**, and then double-click **Microsoft Dynamics AX 2012 Server Configuration**.

3.  On the **Application Object Server** tab, select the check box labeled **Enable breakpoints to debug X++ code running on this server**.


> [!NOTE]
> <P>If the controls on the <STRONG>Application Object Server</STRONG> tab are disabled, you may have to create a new server configuration. To create a new configuration, run the Microsoft Dynamics AX server configuration utility as an administrator, and then click <STRONG>Manage</STRONG> &gt; <STRONG>Create configuration</STRONG>, enter a configuration name, such as <STRONG>AOS Debugging</STRONG>, and then click <STRONG>OK</STRONG>.</P>



## To enable the debugger on Business Connector

To debug code that is run by Business Connector or to debug Business Connector code on the client, you must enable those features of the debugger.

1.  Enable the debugger on the client, as shown in the first procedure.

2.  Open the Microsoft Dynamics AX configuration utility. This is a stand-alone utility that manages client configurations:
    
    1.  Click **Control Panel**, click **Administrative Tools**, and then double-click **Microsoft Dynamics AX 2012 Configuration**.

3.  On the **Developer** tab, select the check boxes in the **Settings** area, to enable the functionality you want.
    
      - To enable breakpoints for user code, select **Enable user breakpoints to debug code in the Business Connector**.
    
      - To enable global breakpoints in the Business Connector or client, select **Enable global breakpoints to debug code running in the Business Connector or client**.


> [!NOTE]
> <P>If the controls on the <STRONG>Developer</STRONG> tab are disabled, you may have to create a new configuration. To create a new configuration, run the Microsoft Dynamics AX configuration utility as an administrator, and then click <STRONG>Manage</STRONG> &gt; <STRONG>Create configuration</STRONG>, enter a configuration name, such as <STRONG>BC Debugging</STRONG>, and then click <STRONG>OK</STRONG>.</P>



## See also

[Microsoft Dynamics AX Debugger](microsoft-dynamics-ax-debugger.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

