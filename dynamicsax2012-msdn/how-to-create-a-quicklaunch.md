---
title: 'How to: Create a QuickLaunch'
TOCTitle: 'How to: Create a QuickLaunch'
ms:assetid: 11976181-4bc8-4b6c-8e24-4320d45efcc8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc582912(v=AX.60)
ms:contentKeyID: 35244912
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Create a QuickLaunch [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A QuickLaunch is the set of menu items that will be displayed in the leftmost navigation for the pages in a module site. The items can be defined once, and then are automatically referenced by all the pages that use the [QuickLaunch Web Part](quicklaunch-web-part.md).

## Creating a QuickLaunch

### To create a QuickLaunch

1.  Create the Web Menu Items that will be used for the QuickLaunch. For more information, see [How to: Create Web Menu Items](how-to-create-web-menu-items.md).

2.  Create the Web Menu that will be used for the QuickLaunch. For more information, see [How to: Create Web Menus](how-to-create-web-menus.md).

3.  Add the Submenus and Menu items to the Web Menu being used for the QuickLaunch.

4.  In the AOT, locate the submodule in the **Web Modules** node for which you are creating a QuickLaunch. Set the **QuickLaunch** property for this submodule to the Web Menu that you created for the QuickLaunch.

5.  Add a QuickLaunch web part to the page that you want to have display the QuickLaunch. For more information, see [How to: Add Web Parts](how-to-add-web-parts.md).

