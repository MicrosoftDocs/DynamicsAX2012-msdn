---
title: 'How to: Add a List Page to an Area Page'
TOCTitle: 'How to: Add a List Page to an Area Page'
ms:assetid: a9e02765-a581-4f65-92e4-adeb7e506a64
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc572916(v=AX.60)
ms:contentKeyID: 35249517
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a List Page to an Area Page 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To make a new list page or content page available in the Microsoft Dynamics AX client, you have to add a menu item for that list page or content page to the **Places** group of an area page. The area page **Places** group lists all the primary list pages, secondary list pages, and content pages associated with a Microsoft Dynamics AX module.


> [!NOTE]
> <P>If you follow the steps in <A href="how-to-add-a-list-page-to-the-navigation-pane.md">How to: Add a List Page to the Navigation Pane</A> to add a list page or content page to a menu, the list page or content page will also be added to the area page.</P>



The following procedures describe how to add a list page to an area page.

### To create a menu item

1.  In the AOT, expand the **Menu Items** node, right-click **Display**, and then click **New Menu Item**. A new menu item is added to the **Display** node in the AOT.

2.  Right-click the new menu item, and then click **Properties**. The properties window opens. To create a menu item for a list page, set values for the following properties.
    
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
    <td><p>Specify the text that the area page displays in the <strong>Places</strong> group.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies this menu item.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Object</strong></p></td>
    <td><p>Click the name of the list page that you want to add to the area page.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ObjectType</strong></p></td>
    <td><p><strong>Form</strong></p></td>
    </tr>
    </tbody>
    </table>


3.  In the AOT, right-click the new menu item, and then click **Save**.

The menu item specifies the list page to open. The next step is to add this menu item to a menu.

### To add the menu item to the menu

1.  In the AOT, expand the **Menus** node, right-click the menu where you want to add a link to a list page, point to **New**, and then click **Menu item**. A new menu item is added to the specified menu in the AOT. For example, right-click **Cust** to add a list page menu item to the area page of the **Accounts receivable** module.

2.  Click the new menu item and then use ALT+UP ARROW or ALT+DOWN ARROW to specify the location of the new menu item in the menu.

3.  View the menu item properties in the properties window. To add the list page menu item, set values for the following properties.
    
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
    <td><p><strong>Yes</strong></p>
    > [!note]  
    > <P>Setting this property to <strong>Yes</strong> causes the area page to display the list page link in the <strong>Places</strong> group.</P>
    </td>
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
    > <P>When you specify the <STRONG>MenuItemName</STRONG> property, the <STRONG>Name</STRONG> property is automatically updated to use the value of the <STRONG>Label</STRONG> property from the specified menu item.</P>



4.  Close the properties window.

5.  In the AOT, right-click the menu, and then click **Save**. For example, right-click **Cust**, and then click **Save**.

To view the list page link, restart the Microsoft Dynamics AX client. In the Navigation Pane, click the module where you added the list page. The area page displays in the client content pane. View the list of links in the **Places** group. The group now includes a link to the list page specified by the menu item.

## See also

[Area Page Overview](area-page-overview.md)

[Menus and Menu Items](menus-and-menu-items.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

