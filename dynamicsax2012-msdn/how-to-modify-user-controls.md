---
title: 'How to: Modify User Controls'
TOCTitle: 'How to: Modify User Controls'
ms:assetid: b77519fd-a4bb-4283-a76a-ec066a471658
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc574069(v=AX.60)
ms:contentKeyID: 28119479
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Modify User Controls [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can modify existing User Controls that are used on Enterprise Portal pages. User Controls are modified in an EP Web Application project in Visual Studio. For more information about how to create an EP Web Application project, see [How to: Create an EP Web Application Project](how-to-create-an-ep-web-application-project.md).

## Finding the User Control to Modify

You must find the name of the specific User Control in Enterprise Portal before you can modify it.

### To find the User Control to modify

1.  In Enterprise Portal, navigate to the page that contains the User Control web part that you want to modify.

2.  In the ribbon, display the **Page** tab.

3.  Click the **Edit Page** command.

4.  In the menu for the web part, click **Edit Web Part**. The properties and settings for the web part will be displayed.

5.  Examine the **Managed content item** property. Its value corresponds to an item in the **Web** \> **Web Content** \> **Managed** node of the AOT. The **Object** property for the managed content item identifies the User Control that you want to modify.
    

    > [!TIP]
    > <P>In most cases, the name of the User Control that you want to modify will be the same as the name that you see for the Managed content item property of the web part.</P>



## Modifying a User Control

After you know the User Control that you want to modify, you can edit it in Visual Studio.

### To modify a User Control

1.  Start Visual Studio. If User Account Control (UAC) is active, be sure you start Visual Studio with administrative privileges.

2.  Open the EP Web Application project that you want to use to modify the User Control. For information about how to create a project, see [How to: Create an EP Web Application Project](how-to-create-an-ep-web-application-project.md).

3.  In the **View** menu, click **Application Explorer**.

4.  In the **Application Explorer**, expand the **Web** \> **Web Files** \> **Web Controls** node.

5.  Locate the User Control that you want to modify in the **Web Controls** node.

6.  Right-click the control and then click **Add to project** to add the User Control to the EP Web Application project.
    

    > [!NOTE]
    > <P>If the User Control has explicit dependencies on other User Controls, those User Controls will also be added to the EP Web Application project.</P>



7.  Use the techniques described in [Designing User Controls](designing-user-controls.md) to modify the User Control.

