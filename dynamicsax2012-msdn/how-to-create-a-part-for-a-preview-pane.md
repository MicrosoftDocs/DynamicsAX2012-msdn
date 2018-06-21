---
title: 'How to: Create a Part for a Preview Pane'
TOCTitle: 'How to: Create a Part for a Preview Pane'
ms:assetid: 1000e098-b446-433f-acf9-4365906c790c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg843693(v=AX.60)
ms:contentKeyID: 35240515
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Part for a Preview Pane [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following steps describe how to create an info part that appears in the preview pane of a list page. The preview pane in this example shows a header and related lines. You can also use groups to create a preview pane that shows data fields in up to three columns. The following steps use the default permissions to help secure access to the tables and server methods. For more information about how to set permissions for an info part, see [Security Permissions Properties for an Info Part](security-permissions-properties-for-an-info-part.md).

### To Create the Info Part

1.  In the AOT, click **Parts**, right-click **Info Parts**, and then click **New Info Part**. A part is added to the **Info Parts** node.

2.  Click the new info part. In the property sheet, click the **Name** property and specify a name that uniquely identifies the info part.
    

    > [!TIP]
    > <P>To easily identify that the info part is being used for a preview pane, add PreviewPane to the end of the name.</P>



3.  Click **Query** and then select the query that includes the data fields that you want to appear in the preview pane. The query you use must include a data source for the header fields and a data source for the lines associated with the header. For example, the query named **ReturnTableListPagePreviewPane** contains data sources for both sales headers and sales lines.

### To Add the Header Group and Fields

1.  To add a group, right-click **Layout**, and then click **New Group**.

2.  Click the group, click the **Name** property, and then specify a name that uniquely identifies the group.

3.  Click **DataSource**, and then select the name of the data source that contains the data fields you want to appear in the preview pane. For example, if you had chosen the **ReturnTableListPagePreviewPane** query, you would choose **SalesTable** because it is the data source that contains the header information.

4.  To specify a title field that appears at the top of the preview pane, right-click the group, and then click **New Field**. Click the new field and supply values for the following properties.
    
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
    <td><p>Enter <strong>Title</strong>.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DataSource</strong></p></td>
    <td><p>Select the query data source that contains header information. Use the same data source that you specified for the group.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>DataField</strong> or <strong>DataMethod</strong></p></td>
    <td><p>Select the field or method from the data source that you want to appear in the title of the preview pane. Use a method if you want the title to include values from more than one field.</p>
    <div class="mtps-table">
    <div class="mtps-row">
    <img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
    </div>
    <div class="mtps-row">
    To use data from more than one field, add a method to the data source table that assembles and returns the information that you want to appear in the title.
    </div>
    </div></td>
    </tr>
    <tr class="even">
    <td><p><strong>Style</strong></p></td>
    <td><p>Click <strong>TitleField</strong>.</p></td>
    </tr>
    </tbody>
    </table>


5.  To add fields to the group, right-click the group, and then click **New Field**. For each field you add to the group, supply values for the following properties.
    
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
    <td><p><strong>DataSource</strong></p></td>
    <td><p>Specify the data source. Use the same data source you specified for the group.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>DataField</strong></p></td>
    <td><p>Select the field you want to appear in the preview pane.</p></td>
    </tr>
    </tbody>
    </table>


### To Add the Lines Group and a Data Grid

1.  Right-click **Layout** and then click **New Group**.

2.  Click the group, click the **Name** property, and then specify a name that uniquely identifies the group.

3.  Click **DataSource**, and then click the name of the data source that contains the line fields. For example, click **SalesLines** from the **ReturnTableListPagePreviewPane** query.

4.  Click **Repeating** and then click **Yes**. If you set **Repeating** to **Yes**, the data fields you add to the group appear as a data grid.

5.  Add the fields that you want to appear as columns in the grid. To add a field, right-click the group, and then click **New Field**. For each field you add to the group, supply values for the following properties.
    
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
    <td><p><strong>DataSource</strong></p></td>
    <td><p>Select the data source that contains the data field. Use the same data source you specified for the group.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>DataField</strong></p></td>
    <td><p>Select the field that you want to appear in the preview pane grid.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DataMethod</strong></p></td>
    <td><p>Specify the method of the data source that supplies the value that appears in the grid.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Label</strong></p></td>
    <td><p>Select a label for the column heading. If you do not specify a label, the column heading uses the column name from the table.</p></td>
    </tr>
    </tbody>
    </table>


6.  Right-click the part and then click **Save**.

## See also

[How to: Create an Info Part](how-to-create-an-info-part.md)

[Info Parts](info-parts.md)

[Parts](parts.md)

[FactBox Panes](factbox-panes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

