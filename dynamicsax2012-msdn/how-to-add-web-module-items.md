---
title: 'How to: Add Web Module Items'
TOCTitle: 'How to: Add Web Module Items'
ms:assetid: b127fb43-2dff-4cbd-9ef7-049cff68ccc5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc635940(v=AX.60)
ms:contentKeyID: 35245648
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Add Web Module Items 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Web Module items are created in the AOT, and then deployed to the server that is running Enterprise Portal.

## Adding a Submodule

### To create a submodule

1.  In the AOT, expand the **Web** node, and then expand the **Web Modules** node.

2.  Expand the **Home** node. This node represents the main site for Enterprise Portal. The submodules under this node represent module sites for Enterprise Portal.

3.  Right-click the node for the module or submodule to which you want to add the new submodule.

4.  Specify the properties for the new submodule, including the **Name** and **Label**.

5.  Specify the **MenuItemName** property, which indicates which Web Menu Item URL will be displayed for the submodule. Typically, this is the site home page for the submodule. If this page has not yet been created, you can set this property after the page has been created and the URL item for the page has been defined.

6.  Specify the **QuickLaunch** property, which indicates the Web Menu resource that will be displayed in the QuickLaunch area for all pages in the subsite that have the QuickLaunch web part. Refer to [How to: Create a QuickLaunch](how-to-create-a-quicklaunch.md) for more information about how to do this.

7.  Save the changes in the AOT.

8.  Right-click the new submodule and click Deploy. This will create the subsite and menu item for the Enterprise Portal installation.

## Adding a Menu Item

### To create a menu item

1.  In the AOT, expand the **Web** node, and then expand the **Web Modules** node.

2.  Expand the **Home** node. This node represents the main site for Enterprise Portal. The submodules under this node represent module sites for Enterprise Portal.

3.  Right-click the node for the module or submodule to which you want to add the new menu item.

4.  Specify the **MenuItemName** property, which indicates which Web Menu Item URL will be used for navigation of the submodule menu item.

5.  Save the changes in the AOT.

