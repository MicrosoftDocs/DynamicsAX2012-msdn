---
title: 'How to: Add a Preview Pane to a List Page'
TOCTitle: 'How to: Add a Preview Pane to a List Page'
ms:assetid: bee262ac-2765-4ea3-8c7f-6cb53b73e082
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc574825(v=AX.60)
ms:contentKeyID: 35250065
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Preview Pane to a List Page 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A preview pane is the part of a list page that shows additional information about the highlighted record in the list. A preview pane is optional and is located under the list page grid. Before you add a preview pane to a list page, you must have first created an info part that includes the data fields you want to appear in the preview pane on the list page. For information about how to create the info part, see [How to: Create a Part for a Preview Pane](how-to-create-a-part-for-a-preview-pane.md).

### To add a preview pane

1.  In the AOT, expand **Forms**, locate the form for the list page, and then expand the node for the list page.

2.  Open a second AOT window. Expand **Parts**, expand **Info Parts**, and then click the info part that you want to use for the preview pane.

3.  Open a third AOT window. Expand **Menu Items** and expand **Display**. Drag the info part you identified in the previous step to the **Display** node in the AOT. A menu item is created for the info part.

4.  Drag the menu item that you created in the previous step to the **Parts** node of the list page form.

5.  Expand the **Parts** node of the list page form, right-click the part that you added, and then click **Properties**. Specify values for the following properties.
    
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
    <td><p><strong>PreviewPane</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>DataSource</strong></p></td>
    <td><p>Use the default value.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DataSourceRelation</strong></p></td>
    <td><p><strong>SelfLink</strong></p></td>
    </tr>
    </tbody>
    </table>


6.  Right-click the form for the list page, and then click **Save**.

## See also

[List Page Overview](list-page-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

