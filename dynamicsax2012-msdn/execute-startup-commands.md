---
title: Execute Startup Commands
TOCTitle: Execute Startup Commands
ms:assetid: 2cfa2ccc-45b6-4ba9-8d25-c0e06eaafbe6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa569641(v=AX.60)
ms:contentKeyID: 35241875
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Execute Startup Commands 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Use the SysStartupCmd class framework to execute commands at startup.

When Microsoft Dynamics AX starts, calls are made to the \*startup methods on the application-substituted kernel classes Application (Application.startup) and Info (Info.startup).


> [!WARNING]
> <P>The *startup methods are used for vital system and version-specific calls, and you must never directly modify these methods. Instead, use the SysStartupCmd framework. Serious consequences may follow if the SYS layer versions of the startup methods are not called.</P>



When Microsoft Dynamics AX is started, calls are executed in the sequence shown in the following code.
```X++  
    appl.startup() // The SysStartupCmd class is instantiated here.
    sysStartupCmd.applInit()
    super()
    sysStartupCmd.applRun()
    
    info.startup()
    sysStartupCmd.infoInit()
    super()
    sysStartupCmd.infoRun()
```
## Commands Available when Microsoft Dynamics AX Starts

The commands that are available when Microsoft Dynamics AX starts are listed in the SysStartupCmd.construct method (available in the **Classes** node in the Application Object Tree (AOT)). The commands include the following:

  - AutoRun

  - AOTImport

  - Synchronize

## Execute a New Command when Microsoft Dynamics AX Starts

1.  Create a class that extends the SysStartupCmd class to perform your specific task.
    
    For example, in the standard application, the SysStartupCmdBuildNoSet class is used to set the build number. Use a similar approach for your task.

2.  Modify the construct method on the SysStartupCmd class so that your class is called.
    
    Following is an example.
    ```X++  
        switch (s)
        {
            // Code lines are left out here. 
            case 'autorun':
                sysStartupCmd = new SysStartupCmdAutoRun(s,parm);
                break;
            // Code lines are left out here.
        }
    ```
3.  Add parameters (if necessary) to commands that are executed on startup to the **Command to run at application startup** field on the **General** tab in the Microsoft Dynamics AX Configuration Utility.
    
    Instead of giving the command from the Microsoft Dynamics AX Configuration Utility, you might choose to use the command-line parameter **-startupcmd=** MyCommand.

## See also

[Substitute Application Classes for System Classes](substitute-application-classes-for-system-classes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

