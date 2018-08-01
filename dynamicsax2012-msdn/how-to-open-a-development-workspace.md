---
title: 'How to: Open a Development Workspace'
TOCTitle: 'How to: Open a Development Workspace'
ms:assetid: 7363e6c5-afa2-4a70-90de-e1dc5359c5cd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg846350(v=AX.60)
ms:contentKeyID: 35245905
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Open a Development Workspace [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX 2012, by default, the client opens in an Application Workspace. As a developer, you may prefer to open the Microsoft Dynamics AX client directly into a Development Workspace.


> [!NOTE]
> <P>To open a Development Workspace, a developer license key is required, and the installation checklist must be completed. No more than eight workspaces per client can be opened at the same time.</P>



This topic describes:

  - How to open a Development Workspace from the Application Workspace.

  - Three methods to directly start the client in a Development Workspace.

  - A code example to open a Development Workspace using X++.

### To open a Development Workspace from the Application Workspace

  - Click **Windows** \> **New Development Workspace**. A Development Workspace opens in a new window.
    

    > [!TIP]
    > <P>You can also press CTRL+Shift+W to open a Development Workspace.</P>



### To open a Development Workspace by configuration

1.  Click **Start** \> **All Programs** \> **Administrative Tools** \> **Microsoft Dynamics AX 2012 Configuration**. The **Microsoft Dynamics AX Configuration Utility** window opens.

2.  On the **General** tab, click **Manage**, and then click **Create configuration**.

3.  On the **Create Configuration** form, enter a name for the configuration in the **Configuration name** field, and then click **OK**. The **Create Configuration** form closes and you return to the **Microsoft Dynamics AX Configuration Utility** window.

4.  On the **General** tab, in the **Command to run at application startup** field, enter -development, and then click **OK** to save the new configuration. The settings will apply the next time you open the Microsoft Dynamics AX client.

### To open a Development Workspace using the command line

1.  On the taskbar, click **Start**, and then click **Run**.

2.  In the **Open** field, enter cmd, and then click **OK**.

3.  At the command prompt, type the following: "C:\\Program Files\\Microsoft Dynamics AX\\60\\Client\\Bin\\Ax32.exe" -development

### To create a shortcut to open a Development Workspace

1.  In Windows Explorer, right-click the Ax32.exe file in your Microsoft Dynamics AX 2012 client installation, and then click **Create Shortcut**. By default, this file is located in the C:\\Program Files\\Microsoft Dynamics AX\\60\\Client\\Bin directory. A new shortcut named **Shortcut to Ax32.exe** is created.

2.  Right-click **Shortcut to Ax32.exe**, and then click **Properties**. The **Shortcut to Ax32.exe Properties** window opens.

3.  On the **Shortcut** tab, in the **Target** field, enter -development after the path to the Ax32.exe file. The **Target** field should resemble "C:\\Program Files\\Microsoft Dynamics AX\\60\\Client\\Bin\\Ax32.exe" -development.

4.  Click **OK** to save the shortcut. You can move and rename the shortcut as needed.

## Example

You can also open a Development Workspace directly from X++ code. For example, you can add a customized button in the Application Workspace to open a Development Workspace. The following X++ code can be used to open a Development Workspace.

```X++
  static void OpenDevWorkspace(Args _args)
    {
        int hWorkspace;
        hWorkspace = infolog.createDevelopmentWorkspaceWindow();
    }
```

## See also

[About the Development Workspace](about-the-development-workspace.md)

[About the Application Workspace](about-the-application-workspace.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

