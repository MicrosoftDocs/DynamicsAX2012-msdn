---
title: Troubleshooting a Workspace
TOCTitle: Troubleshooting a Workspace
ms:assetid: 2575235f-69da-4258-b554-375f63b3afdb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg844298(v=AX.60)
ms:contentKeyID: 35241674
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Troubleshooting a Workspace [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes common problems that can occur when you work with Development and Application Workspaces in Microsoft Dynamics AX.

## General

By default, the Microsoft Dynamics AX client opens in the Application Workspace. For application development, you should open a new Development Workspace. For more information, see [How to: Open a Development Workspace](how-to-open-a-development-workspace.md).


> [!NOTE]
> <P>To open a Development Workspace, a developer license code is required, and the installation checklist must be completed. No more than eight workspaces per client can be opened at the same time.</P>



## Troubleshooting in the Development Workspace

### ![Gg844298.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844298.collapse_all(en-us,AX.60).gif")Insufficient rights to start a Development Workspace error

To use the -development switch to start Microsoft Dynamics AX in the Development Workspace, you must have a developer license code installed. For more information, see [Provide license information](https://msdn.microsoft.com/en-us/library/aa496447\(v=ax.60\)).

### ![Gg844298.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844298.collapse_all(en-us,AX.60).gif")The Command menu is not available

The Command menu is only available if an Application Object Tree (AOT) window is open. Press CTRL+D to open the AOT.

### ![Gg844298.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844298.collapse_all(en-us,AX.60).gif")The Workspace menu items are not available

You must have a developer license code to open a Development Workspace. For more information, see [Provide license information](https://msdn.microsoft.com/en-us/library/aa496447\(v=ax.60\)). No more than eight workspaces can be opened in the same client session.

### ![Gg844298.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844298.collapse_all(en-us,AX.60).gif")The Application Workspace icon is not available

You must have a developer license code to open a Development Workspace. For more information, see [Provide license information](https://msdn.microsoft.com/en-us/library/aa496447\(v=ax.60\)). No more than eight workspaces can be opened in the same client session.

### ![Gg844298.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844298.collapse_all(en-us,AX.60).gif")CTRL+W does not open an Application Workspace

No more than a total of eight workspaces can be opened in the same client session.

### ![Gg844298.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844298.collapse_all(en-us,AX.60).gif")The Workspace toolbar is not available

To enable or disable the workspace toolbar, on the **Tools** menu, click **Customize**, and then select or clear **Workspace**.

## Troubleshooting in the Application Workspace

### ![Gg844298.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844298.collapse_all(en-us,AX.60).gif")The Development Workspace icon is not available

There is no toolbar for workspace icons in the Application Workspace. To open a Development Workspace from the Application Workspace, press CTRL+SHIFT+W. You must have a developer license code to open a Development Workspace. For more information, see [Provide license information](https://msdn.microsoft.com/en-us/library/aa496447\(v=ax.60\)). No more than eight workspaces can be opened in the same client session.

### ![Gg844298.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844298.collapse_all(en-us,AX.60).gif")The Workspace menu items are not available

You must have a developer license code to open a Development Workspace. For more information, see [Provide license information](https://msdn.microsoft.com/en-us/library/aa496447\(v=ax.60\)). No more than eight workspaces can be opened in the same client session.

### ![Gg844298.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844298.collapse_all(en-us,AX.60).gif")CTRL+SHIFT+W does not open a Development Workspace

No more than eight workspaces can be opened in the same client session. You must have a developer license code to open a Development Workspace. For more information, see [Provide license information](https://msdn.microsoft.com/en-us/library/aa496447\(v=ax.60\)).

## See also

[Workspaces](workspaces.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

