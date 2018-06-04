---
title: 'How to: Create Menus and Menu Items'
TOCTitle: 'How to: Create Menus and Menu Items'
ms:assetid: 5277205c-edb9-498e-b927-406237806217
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa639737(v=AX.60)
ms:contentKeyID: 35244319
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create Menus and Menu Items 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can create menu items to provide access to forms, reports, classes, jobs, and queries. You can also create menus. All these procedures are performed in the Application Object Tree (AOT).

To help you manage changes to AOT objects such as menu items, a version control system is available. For more information, see [Version Control System](version-control-system.md).

You can implement existing menu items based on a set of conditions using the [MenuFunction](https://msdn.microsoft.com/en-us/library/gg912148\(v=ax.60\)) class and X++. You add the code to a table method, and then call the method from a form or a report.

## Create a Menu and a Menu Item

1.  In the AOT, click **Menu Items**.

2.  Do one of the following:
    
      - To create a display menu item, drag a form from the **Forms** node to the **Display** node.
    
      - To create an output menu item, drag a report from the **Reports** node to the **Output** node.
    
      - To create an action menu item, drag a job, a class, or a query from the **Jobs**, **Classes**, or **Queries** node to the **Action** node.

3.  Right-click **Menus**, and then click **New Menu**.

4.  Add the menu item you created in step 2 to the new menu by doing the following:
    
    1.  Right-click the new menu, and then click **New** \> **Menu Item**.
    
    2.  Right-click the menu item, and then click **Properties**.
    
    3.  In the property sheet, do the following:
    
    <!-- end list -->
    
      - Click **MenuItemType**. In the right column, select **Display**, **Output**, or **Action** from the drop-down menu, according to the type of menu item that you created in step 2.
    
      - Click **MenuItemName**. In the right column, select the menu item from the drop-down menu. The available menu items are determined by the **MenuItemType** property setting.

5.  Modify menu properties as needed. Right-click the menu that you created in step 3, and then click **Properties**.

6.  Right-click the menu, and then click **Save**.

## See also

[How to: Access a Class from a Menu](how-to-access-a-class-from-a-menu.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

