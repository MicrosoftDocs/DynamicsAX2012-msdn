---
title: 'How to: Add a List Page to the Navigation Pane'
TOCTitle: 'How to: Add a List Page to the Navigation Pane'
ms:assetid: 0364f72c-3ac5-4fb8-b7fe-7e0db7d9d9a4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc518832(v=AX.60)
ms:contentKeyID: 35240233
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a List Page to the Navigation Pane [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To view a primary or secondary list page for a Microsoft Dynamics AX module, you use the Navigation Pane or the area page for that module. To add a list page to the Navigation Pane and to the area page, you add a list page menu item to the menu in the Application Object Tree (AOT). The following procedures explain how to create a list page menu item and add that menu item to the menu.

### To create a list page menu item

1.  In the AOT, expand the **Menu Items** node, right-click **Display**, and then click **New Menu Item**. A new menu item is added to the **Display** node in the AOT.

2.  Right-click the new menu item, and then click **Properties**. The **Properties** window opens. Set values for the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Label</strong></p></td>
    <td><p>Specify the text that appears in the Navigation Pane.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies this menu item.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Object</strong></p></td>
    <td><p>Click the name of the list page form.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ObjectType</strong></p></td>
    <td><p><strong>Form</strong></p></td>
    </tr>
    </tbody>
    </table>


3.  In the AOT, right-click the new menu item, and then click **Save**.

### To add the list page menu item to the menu

1.  In the AOT, expand the **Menus** node, right-click the menu where you want the new list page to appear, point to **New**, and then click **Menu item**. A new menu item is added to the specified menu in the AOT.
    
    For example, assume that you want to add a list page to the Customers section of the Navigation Pane for Accounts Receivable. In the AOT, expand **Menus**, expand **AccountsReceivable**, expand **Common**, right-click **Customers**, click **New**, and then click **Menu item**.

2.  Click the new menu item and then use ALT+UP ARROW or ALT+DOWN ARROW to specify the location of the new menu item in the menu.

3.  View the menu item properties in the **Properties** window. To add the list page menu item, set values for the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>IsDisplayedInContentArea</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MenuItemName</strong></p></td>
    <td><p>Click the name of the menu item that you created for the list page.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>MenuItemType</strong></p></td>
    <td><p><strong>Display</strong></p></td>
    </tr>
    </tbody>
    </table>
    

    > [!NOTE]
    > <P>When you specify the <STRONG>MenuItemName</STRONG> property, the <STRONG>Name</STRONG> property of the menu is automatically updated to use the value of the <STRONG>Label</STRONG> property from the menu item.</P>



4.  Right-click the menu, and then click **Save**.

To view the list page in the Navigation Pane, you have to restart the Microsoft Dynamics AX client. The list page appears in Navigation Pane and the area page of the specified module.

## See also

[How to: Add a List Page to an Area Page](how-to-add-a-list-page-to-an-area-page.md)

[List Page Overview](list-page-overview.md)

[Menus and Menu Items](menus-and-menu-items.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

