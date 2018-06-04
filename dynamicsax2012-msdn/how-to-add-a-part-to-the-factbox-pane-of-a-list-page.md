---
title: 'How to: Add a Part to the FactBox pane of a List Page'
TOCTitle: 'How to: Add a Part to the FactBox pane of a List Page'
ms:assetid: 4ef339d3-8fb4-4f1f-a7cf-e3d25cb7df8d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg845334(v=AX.60)
ms:contentKeyID: 35243491
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Part to the FactBox pane of a List Page 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A FactBox is a part (info part, form part, or cue group) from the AOT that appears in the FactBox pane of a list page. A part is a type of control that you use to retrieve and display a collection of data related to the list page. In addition, you can use some parts to create FactBoxes that display data specific to the highlighted record on the list page. Before you add a FactBox to a list page, you must have first defined the part for it in the **Parts** node of the AOT. For more information about parts, see [Parts](parts.md).

The FactBox pane is an optional element of a list page. If the **Parts** node of the list page form does not include any parts, the FactBox pane does not appear. To make a FactBox appear in the FactBox pane of a list page, you must add a part to the **Parts** node of the list page form. To best use the FactBox pane, you should have at least two FactBoxes. As a result, you should always add at least two parts to a list page form.

### To add a part to the FactBox pane

1.  In the AOT, expand **Forms**, locate the form for the list page, and then expand the node for the list page.

2.  Open a second AOT window. Expand **Parts**, and then expand **Info Parts**, **Form Parts**, or **Cue Groups**. Click the part node that you want to appear in the FactBox pane.

3.  Open a third AOT window. Expand **Menu Items** and expand **Display**. Drag the part you identified in the previous step to the **Display** node. A menu items is created for the specified part.

4.  Drag the menu item you created in the previous step to the **Parts** node of the list page form. The part is added to the form.

5.  Expand the **Parts** node of the list page form, right-click the part that you just added, and then click **Properties**. Specify values for the following properties.
    
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
    <td><p>Use the default value.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MenuItemName</strong></p></td>
    <td><p>Use the default value.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>DisplayTarget</strong></p></td>
    <td><p><strong>Auto</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>PartLocation</strong></p></td>
    <td><p><strong>Auto</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>DataSource</strong></p></td>
    <td><p>Use the default value.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DataSourceRelation</strong></p></td>
    <td><p>Specify the table relationship to use to join the form data source to the part data source.</p></td>
    </tr>
    </tbody>
    </table>


6.  Right-click the form, and then click **Save**.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

