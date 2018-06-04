---
title: 'How to: Add Pages to Navigation'
TOCTitle: 'How to: Add Pages to Navigation'
ms:assetid: 803c6864-8de3-463e-afe0-f41f39b09905
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc600786(v=AX.60)
ms:contentKeyID: 35245454
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Add Pages to Navigation 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To be accessed in Enterprise Portal, pages must be part of the navigation. Use the following procedures to add a page to the navigation for Enterprise Portal.

## Creating a URL Web Menu Item

A URL Web Menu Item in the AOT contains the URL that points to a page in Enterprise Portal.

### To create a URL Web Menu Item

1.  In the AOT, expand the **Web** node, and then expand the **Web Menu Items** node.

2.  Right-click the **URLs** node and then click **New URL**.

3.  Edit the properties for the new URL.

4.  Specify the Name for the URL. Use a name that specifies the page that the URL will point to.

5.  Specify a label for the page.

6.  Specify the URL, with the following form:
    
    *Module*/Enterprise%20Portal/*PageName*.aspx
    
    Replace *Module* with the name of the module that contains the page and *PageName* with the name of the page to access. For example, the following URL points to the WorkOrderAddEdit page that is part of the Facility module:
    
    Facility/Enterprise%20Portal/WorkOrderAddEdit.aspx
    
    You can also use the browse button to open a dialog box that lets you select the page. Navigate to the module site and document library that contains the page. Select the page and then click OK.

7.  Save the new URL Web Menu Item.

## Using the URL Web Menu Item

The URL Web Menu Item is used by a web menu, submenu, or menu item to specify the page to display when the item is clicked by the user.

### To use a URL Web Menu Item

1.  In the AOT, expand the **Web** node, and then expand the **Web Menus** node.

2.  Create a web menu, submenu, or menu item.

3.  Edit the properties for the new item.

4.  Specify Url as the MenuItemType.

5.  Use the drop-down list for the MenuItemName to locate the URL Web Menu Item that you created.

6.  Save the new Web menu, submenu, or menu item.

## See also

[How to: Create Pages](how-to-create-pages.md)

