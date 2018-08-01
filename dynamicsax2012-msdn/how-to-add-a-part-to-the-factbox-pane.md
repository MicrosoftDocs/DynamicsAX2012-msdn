---
title: 'How to: Add a Part to the FactBox Pane'
TOCTitle: 'How to: Add a Part to the FactBox Pane'
ms:assetid: e67412cc-0768-45de-8655-e304934f86cf
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg848021(v=AX.60)
ms:contentKeyID: 35253219
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Part to the FactBox Pane [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To add a FactBox to a form, you must add a part to the FactBox pane of that form. A part is a specialized type of control that shows a collection of data. You can add an info part, form part, or cue group to the FactBox pane of a form. For more information about parts, see [Parts](parts.md). The following steps describe how to add a part to the FactBox pane of a form.

### To add a Part to the FactBox pane

1.  In the AOT, expand **Forms**, and then expand the form where you want to add the part.
    

    > [!WARNING]
    > <P>Verify that the form includes a FactBox pane. Expand <STRONG>Designs</STRONG>, right-click <STRONG>Design</STRONG>, and then click <STRONG>Properties</STRONG>. View the <STRONG>Style</STRONG> property. If the property value is <STRONG>ListPage</STRONG>, <STRONG>DetailsFormMaster</STRONG>, or <STRONG>DetailsFormTransaction</STRONG>, the form includes a FactBox pane. If you add a part to a form that does not have a FactBox pane, the FactBox will not be shown.</P>



2.  Press Ctrl + D to open a second AOT window, expand **Parts**, and then expand **Info Parts**, **Form Parts**, or **Cue Groups**. Click the part you want to appear on the form.

3.  Press Ctrl + D to open a third AOT window, expand **Menu Items** and then expand **Display**. Drag the part you identified in the previous step to the **Display** node. A menu item is created for the specified part.

4.  Drag the menu item you created in the previous step to the **Parts** node of the form. A part reference is added to **Parts** node of the form. Click the part reference and view or update the value of the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property name</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specifies the name of the part reference. If you drag the menu item to the form, the name will be the same as the name of the menu item.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DataSource</strong></p></td>
    <td><p>Specifies the form data source you want to link to the part. If you drag the menu item to the form, the data source is automatically populated.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>IsLinked</strong></p></td>
    <td><p>Specifies whether the part data source is linked to the form data source. The default value is <strong>Auto</strong>.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>IsVisible</strong></p></td>
    <td><p>Specifies whether the part is visible in the FactBox pane. The default value is <strong>Yes</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>MenuItemName</strong></p></td>
    <td><p>Specifies the menu item that is used to indicate which part is to be displayed. You do not specify the part directly. Instead, you use a menu item to indicate the type and specific instance of part to display.</p></td>
    </tr>
    </tbody>
    </table>


5.  View **Properties**, click the **DataSourceRelation** property, and then click the table relation that you want to use. The **DataSourceRelation** specifies the join between the form data source and the part data source. You set this property to have the data that appears in the FactBox update every time that you change the record in the form.

6.  Click the **PartLocation** property and specify where you want the part to appear. Click **Auto** to have the part appear as a FactBox in the FactBox pane of the form.
    

    > [!TIP]
    > <P>You can also use a part to populate the preview pane of a list page. The <STRONG>PartLocation</STRONG> property lets you add an info part to the preview pane. For more information about the preview pane, see <A href="how-to-add-a-preview-pane-to-a-list-page.md">How to: Add a Preview Pane to a List Page</A>.</P>



7.  Save the form.

## See also

[FactBox Panes](factbox-panes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

