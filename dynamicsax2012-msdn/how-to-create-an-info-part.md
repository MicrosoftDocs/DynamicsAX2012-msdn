---
title: 'How to: Create an Info Part'
TOCTitle: 'How to: Create an Info Part'
ms:assetid: 0fbcdb98-c074-482b-b272-7195837a9c48
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg843678(v=AX.60)
ms:contentKeyID: 35240495
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create an Info Part [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following steps describe how to create an info part that appears in the FactBox pane of a form. These steps use the default permissions to help secure access to the tables and server methods. For more information about how to set permissions for an info part, see [Security Permissions Properties for an Info Part](security-permissions-properties-for-an-info-part.md).

### To Create the Info Part

1.  In the AOT, click **Parts**, right-click **Info Parts**, and then click **New Info Part**. A part is added to the **Info Parts** node.

2.  Click the new info part. In the property sheet, click the **Name** property and specify a name that uniquely identifies the info part.

3.  Click **Query** and then select the query to use to obtain the data fields for the part.

4.  Click **Caption**, and then select the label. This label will appear in the title bar of the FactBox.

### To Add Groups and Fields

1.  Click **Layout**. In the property sheet, click **ShowMore** and then click **Yes**. This property adds **More** as a link at the bottom of the FactBox.

2.  Click **ShowMoreDataSource** and select a data source. The **FormRef** property of the main table of the selected data source specifies the form that opens when you click the **More** link in the FactBox.

3.  To organize the data fields that appear in the FactBox, add one or more groups to the info part. To add a group, right-click **Layout**, and then click **New Group**.

4.  For each group in the **Layout** node, click the group and supply values for the following properties.
    
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
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies the group.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Caption</strong></p></td>
    <td><p>Select a label that describes the group.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ShowCaption</strong></p></td>
    <td><p>If you want the label in the <strong>Caption</strong> property to appear in the FactBox, click <strong>Yes</strong>.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Repeating</strong></p></td>
    <td><p>If you want the data fields in the group to appear as a data grid, click <strong>Yes</strong>. If you click <strong>No</strong>, the FactBox shows the data fields as a list of name and value pairs.</p></td>
    </tr>
    </tbody>
    </table>


5.  Each group in the info part must have one or more data fields. To add a field, right-click the group, and then click **New Field**. For each field you add to a group, click the field, and then supply values for the following properties.
    
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
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies the field.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Label</strong></p></td>
    <td><p>Select the label you want to appear with the data field. If you leave the <strong>Label</strong> property empty, the FactBox uses the field label from the data source.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>DataSource</strong></p></td>
    <td><p>Click the query data source that contains the data field or data method to use to get the data value that appears in the FactBox.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DataField</strong></p></td>
    <td><p>Select the name of the field that has the value that you want to appear in the FactBox. If you specify a field, you cannot use the <strong>DataMethod</strong> property.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>DataMethod</strong></p></td>
    <td><p>Select the name of the method that provides the value that you want to appear in the FactBox. If you specify a method, you cannot use the <strong>DataField</strong> property.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Style</strong></p></td>
    <td><p>Select the text style to use when the field appears in the FactBox.</p></td>
    </tr>
    </tbody>
    </table>


### To Add an Action

1.  Right-click **Actions**, and then click **New Action**.

2.  Click the action, click the **Name** property, and then enter a name that uniquely identifies the action.

3.  Click the **MenuItemType** and select the type of menu item associated with the action you want to perform. For example, click **Display** to select from the menu items listed in the **Menu Items** \> **Display** node of the AOT.

4.  Click **MenuItemName** and then click the menu item that you want to use.

5.  Right-click the info part and then click **Save**.

## See also

[How to: Create a Part for a Preview Pane](how-to-create-a-part-for-a-preview-pane.md)

[Info Parts](info-parts.md)

[Parts](parts.md)

[FactBox Panes](factbox-panes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

