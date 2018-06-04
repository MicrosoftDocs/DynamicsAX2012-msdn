---
title: 'How to: Create Web Menus'
TOCTitle: 'How to: Create Web Menus'
ms:assetid: 3caaeb68-1e0f-4f1f-be0f-9fb668cde966
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa625572(v=AX.60)
ms:contentKeyID: 35245237
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Create Web Menus 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can create a web menu that uses web menu items to link to other web pages or perform actions. You use web parts to add web menus to web part pages. For more information, see [How to: Add Page-level Navigation](how-to-add-page-level-navigation.md).

A web menu can also refer to another web menu. This is useful if the same set of web menu items will be used in multiple web menus.

## Creating a Web Menu

### To create a web menu

1.  In the AOT, expand the **Web** node.

2.  Right-click **Web Menus** and then click **New Web Menu**.

3.  Right-click the new web menu that you created in step 2, and then do one of the following:
    
      - To create a new menu item, click **New** \> **Menu Item**.
    
      - To create a new submenu, click **New** \> **Submenu**.

4.  Right-click the menu item and then click **Properties**.

5.  In the property sheet, do the following:
    
    1.  Go to the **MenuItemType** property. In the right column, select **URL** or **Action** from the drop-down menu, according to the type of menu item that you want to add. For more information, see [How to: Create Web Menu Items](how-to-create-web-menu-items.md).
    
    2.  Go to the **MenuItemName** property. In the right column, select the menu item that you want from the drop-down list.
    
    3.  Go to the **Parameters** property. If you want to pass parameter values on the URL for the page being accessed, set this property. See [Passing Parameters to Pages](passing-parameters-to-pages.md) for more information.
    
    4.  Go to the **ShowParentModule** property. The default for this property is Yes. This means that the QuickLaunch area will be updated with the navigation for the web module where the target page is located. Sometimes you will access a page that is located in a different web module. If you do not want the QuickLaunch navigation to be updated when the page is accessed, set this property to No. The page will be displayed, but the QuickLaunch navigation will not be changed.

6.  Save the changes in the AOT.

## Adding a Reference to an Existing Web Menu

### To add a reference an existing web menu

1.  In the AOT, expand the **Web** node, and then expand the **Web Menus** node.

2.  Right-click the web menu or the submenu to which you want to add the menu reference, and then click **Menu Reference**. The list of existing web menus is displayed.

3.  Drag an existing web menu from the **Select: Web Menus** dialog box to the web menu or submenu.

4.  Save the changes in the AOT.

