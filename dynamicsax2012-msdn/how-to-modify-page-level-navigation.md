---
title: 'How to: Modify Page-level Navigation'
TOCTitle: 'How to: Modify Page-level Navigation'
ms:assetid: c68df105-62c5-4df1-ae8f-0d065c6dfa08
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc637671(v=AX.60)
ms:contentKeyID: 35246135
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Modify Page-level Navigation 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To add or modify page-level navigation for a page, you need to determine the Web Menu resource that is being used to define the navigation.

## Modifying page-level navigation

### To modify page-level navigation

1.  In Enterprise Portal, open the page that contains the page-level navigation that you want to modify.

2.  Choose **Edit Page** from the **Site Actions** menu.

3.  Locate the web part being used for the page-level navigation. Choose **Edit Web Part** from the **Edit** menu for the web part.

4.  In the Microsoft Dynamics AX properties for the web part, look for the **Web Menu** property. If this property is listed, the value of this property indicates the Web Menu resource in the AOT that you must edit.

5.  If the **Web Menu** property does not exist, the menu items in the page-level navigation are defined by the QuickLaunch specified for the module site. In the AOT, expand the **Web** node, and then expand the **Web Modules** node. Display the properties for the submodule that contains the page that you are viewing. The value of the **QuickLaunch** property indicates the Web Menu resource in the AOT that you must edit.

6.  In the AOT, locate the **Web Menu** resource in the **Web** node, and then expand the **Web Menus** node.

7.  Make the required changes to the Web Menu, such as adding a new item.

8.  Save the changes in the AOT.

