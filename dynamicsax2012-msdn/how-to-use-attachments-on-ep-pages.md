---
title: 'How to: Use Attachments on EP Pages'
TOCTitle: 'How to: Use Attachments on EP Pages'
ms:assetid: a588a3d2-1989-442d-bdbb-d704de77a32e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh812510(v=AX.60)
ms:contentKeyID: 44090296
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Use Attachments on EP Pages 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX has built-in support that lets users attach documents to customers, vendors, and other objects in the system. These attachments can be accessed from list pages and forms in the Microsoft Dynamics AX client. They can also be accessed from list pages and entity overview pages in Enterprise Portal. If you have created new list pages or entity overview pages, consider enabling them to support attachments. For more information about attachments, see [Attachments](https://msdn.microsoft.com/en-us/library/hh271546\(v=ax.60\)).

## Adding an Attachments Button to a List Page for Enterprise Portal

Two separate buttons are used when you add the **Attachments** button to a list page. The first button is used when the list page is displayed in the Microsoft Dynamics AX client. The second button is used when the list page is displayed in Enterprise Portal. The following procedure describes how to create the **Attachments** button for a list page in Enterprise Portal.

### To add an Attachments button to a list page

1.  Create the web menu item that will be used for attachments. In the AOT, expand the **Web** \> **Web Menu Items** \> **URLs** node. Right-click the **URLs** node and then click **New URL**.

2.  Right-click the new web menu item and then click **Properties**.

3.  Set the following properties for the new URL web menu item:
    
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
    <td><p>Name</p></td>
    <td><p>Supply a name that indicates what type of object attachments are being added to.</p></td>
    </tr>
    <tr class="even">
    <td><p>Label</p></td>
    <td><p>Attachments</p></td>
    </tr>
    <tr class="odd">
    <td><p>HelpText</p></td>
    <td><p>View documents associated with the selected <em>object</em>. (Replace <em>object</em> with the name of the type of object that you are enabling attachments for.)</p></td>
    </tr>
    <tr class="even">
    <td><p>URL</p></td>
    <td><p>Enterprise%20Portal/EPDocuList.aspx</p></td>
    </tr>
    <tr class="odd">
    <td><p>NormalImage</p></td>
    <td><p>10442</p></td>
    </tr>
    <tr class="even">
    <td><p>ImageLocation</p></td>
    <td><p>EmbeddedResource</p></td>
    </tr>
    <tr class="odd">
    <td><p>PageDefinition</p></td>
    <td><p>EPDocuList</p></td>
    </tr>
    <tr class="even">
    <td><p>WindowMode</p></td>
    <td><p>NewModal</p></td>
    </tr>
    </tbody>
    </table>


4.  Save the changes for the new web menu item.

5.  Create a menu item that will be used for the **Attachments** button. In the AOT, expand the **Menu Items** \> **Display** node. Right-click the **Display** node and then click **New Menu Item**.

6.  Right-click the new menu item and then click **Properties**.

7.  Set the following properties for the new menu item:
    
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
    <td><p>Name</p></td>
    <td><p>Supply a name that indicates what type of object attachments are being added to.</p></td>
    </tr>
    <tr class="even">
    <td><p>Label</p></td>
    <td><p>Documents</p></td>
    </tr>
    <tr class="odd">
    <td><p>HelpText</p></td>
    <td><p>View or attach documents to the selected activity.</p></td>
    </tr>
    <tr class="even">
    <td><p>Object</p></td>
    <td><p>Select the form object for the main form of that type. For example, the FCMRooms form is the main form for the room object. Therefore that is the form that is selected.</p></td>
    </tr>
    <tr class="odd">
    <td><p>WebMenuItemName</p></td>
    <td><p>Select the web menu item that you created earlier in this procedure.</p></td>
    </tr>
    </tbody>
    </table>


8.  Save the changes for the new menu item.

9.  In the AOT, expand the **Forms** node and locate the form that defines the list page to which you are adding the **Attachments** button.

10. Expand the **Designs** \> **Design** \> **ActionPane** \> **ActionPaneTab** node for the form.

11. Typically, the **ActionPaneTab** for a list page has a ButtonGroup that is named **AttachmentsGroup**. Right-click this group and then click **New Control** \> **MenuItemButton**.

12. Right-click the new menu item button and then click **Properties**.

13. Set the following properties for the new menu item button:
    
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
    <td><p>Name</p></td>
    <td><p>EPDocumentsMenuItem</p></td>
    </tr>
    <tr class="even">
    <td><p>HelpText</p></td>
    <td><p>View or attach documents to the selected record.</p></td>
    </tr>
    <tr class="odd">
    <td><p>DisplayTarget</p></td>
    <td><p>EP</p></td>
    </tr>
    <tr class="even">
    <td><p>Text</p></td>
    <td><p>Attachments</p></td>
    </tr>
    <tr class="odd">
    <td><p>NormalImage</p></td>
    <td><p>10442</p></td>
    </tr>
    <tr class="even">
    <td><p>ImageLocation</p></td>
    <td><p>EmbeddedResource</p></td>
    </tr>
    <tr class="odd">
    <td><p>ShowShortcut</p></td>
    <td><p>No</p></td>
    </tr>
    <tr class="even">
    <td><p>Big</p></td>
    <td><p>Yes</p></td>
    </tr>
    <tr class="odd">
    <td><p>Primary</p></td>
    <td><p>Yes</p></td>
    </tr>
    <tr class="even">
    <td><p>BackStyle</p></td>
    <td><p>Transparent</p></td>
    </tr>
    <tr class="odd">
    <td><p>DataSource</p></td>
    <td><p>Select the main data source for the list page.</p></td>
    </tr>
    <tr class="even">
    <td><p>MenuItemName</p></td>
    <td><p>Select the menu item that you created earlier in this procedure.</p></td>
    </tr>
    </tbody>
    </table>


14. Save the changes for the form.

## Adding an Attachments Button to an Entity Overview Page for Enterprise Portal

Entity overview pages in Enterprise Portal typically have an action pane that lets the user perform actions for the entity. To add an **Attachments** button to an entity overview page, you just add a web menu item to the web menu that defines the content that is used for the action pane.

### To add an Attachments button to an entity overview page

1.  In the AOT, expand the **Web** \> **Web Menus** node.

2.  Locate the web menu that defines the items in the action pane for the page.

3.  If it does not already exist, add a submenu that is named **Attachments**.

4.  Right-click the **Attachments** submenu and then click **New** \> **Menu item**.

5.  Right-click the new menu item and then click **Properties**.

6.  Set the **MenuItemName** property to **EPDocuListFromInfo**.

7.  Save the changes for the web menu. When you view the entity overview page, the action pane will display the **Attachments** button.

## See also

[Entity Overview Page Reference](entity-overview-page-reference.md)

[List Page Reference](list-page-reference.md)

[How to: Create Web Menu Items](how-to-create-web-menu-items.md)

