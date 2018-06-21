---
title: Info Parts
TOCTitle: Info Parts
ms:assetid: d3175867-59df-49cf-9a7c-2e4bcd378593
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg881316(v=AX.60)
ms:contentKeyID: 35251961
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Info Parts [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An info part is a type of part that you use to add a collection of fields and values to the FactBox pane of a form, or the preview pane of a list page. An info part that appears in the FactBox pane of a form is called a FactBox. You can use an info part in both the client and Enterprise Portal (EP).

## Metadata

To appear in both the client and EP, the info part uses metadata that the client and EP can interpret and show as a FactBox or preview pane. You use the properties of the info part to supply values for the metadata model. Typically, you use an info part to show a collection of data fields from a query. The use of metadata does limit the flexibility you have to customize the appearance of an info part. You use an info part to create the following types of FactBoxes:

  - A collection of data field names and values.

  - A small data grid that shows a list of records.

Info parts are located in the **Parts** node of the AOT. To create an info part, you add a part to the **Info Parts** node and then populate the properties of the info part. For example, you use the **Name** property to uniquely identify the info part. You use the **Caption** property to specify the label that appears in the title bar of the FactBox. However, an info part that appears in the preview pane should leave the **Caption** property blank. For more information about how to create an info part, see [How to: Create an Info Part](how-to-create-an-info-part.md).

## Data Source

You use the **Query** property of the info part to specify the query that will be used to retrieve the data that appears in the FactBox or preview pane. The query should include data sources that you use to add the data fields that appear in the FactBox pane or preview pane. The query can have more than one data source, and each group in an info part can use a different data source.

To update the data in the info part every time a different record is displayed in the form, you must have a dynamic link between the form data source and the info part query. A dynamic link creates a relationship between the data source of the form and the query that is the data source of the info part. To use a dynamic link for the form and info part, you create a relationship between the main form data source table and the query data source table. Typically, the form data source table includes a table relation that specifies the relationship to the table that is the data source for the info part. If the table relation exists, the info part uses the dynamic link and does not require any additional configuration. For more information about dynamic links, see [How to: Link Two Forms by Using Dynamic Links](how-to-link-two-forms-by-using-dynamic-links.md).

When you add an info part to the FactBox pane of a form, the dynamic link between the form data source and the part data source is created. If a dynamic link between the form data source and the part data source does not exist, the data in the info part does not update when you display a different record in the form.

## Layout

You use the objects and properties of the **Layout** node to specify the appearance of the info part. You use the **Layout** node to add groups and fields to the info part. You use the **ShowMore** and **ShowMoreDataSource** properties to have a hyperlink labeled **More** appear at the bottom of a FactBox.


> [!WARNING]
> <P>You should set <STRONG>ShowMore</STRONG> to <STRONG>Yes</STRONG> only if <STRONG>ShowMoreDataSource</STRONG> specifies a data source. If <STRONG>ShowMoreDataSource</STRONG> is empty and you set <STRONG>ShowMore</STRONG> to <STRONG>Yes</STRONG>, the <STRONG>More</STRONG> link appears at the bottom of the FactBox but is inactive.</P>



### ![Gg881316.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg881316.collapse_all(en-us,AX.60).gif")Groups

A group is an object that contains one or more fields. All the fields that appear in an info part must be a member of a group. When you add a group, you should consider the values for the following properties.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Caption</strong></p></td>
<td><p>Select the label that appears at the top of the group in the info part. If you do not want a group label, you can leave the property blank.</p></td>
</tr>
<tr class="even">
<td><p><strong>ShowCaption</strong></p></td>
<td><p>Specify whether the caption appears in the info part. The default value is <strong>No</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Repeating</strong></p></td>
<td><p>Specify whether the data fields appear as a list in a data grid. The default value is <strong>No</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DataSource</strong></p></td>
<td><p>Select the data source from the query that includes the data fields that appear in the group. If you do not want to specify a data source for the group, you can leave the property empty.</p></td>
</tr>
</tbody>
</table>



> [!WARNING]
> <P>The <STRONG>ShowWhenPartSize</STRONG> property of a <STRONG>Group</STRONG> is not used and should not be set. Any value specified for this property is ignored.</P>



### ![Gg881316.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg881316.collapse_all(en-us,AX.60).gif")Fields

A field is an object that shows a data value in an info part. When you add a field, you should consider the values for the following properties.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DataSource</strong></p></td>
<td><p>Select the data source from the query that includes the data field you want to add to the group.</p></td>
</tr>
<tr class="even">
<td><p><strong>DataField</strong></p></td>
<td><p>Specify the data field that has the value that you want to appear in the info part. If you specify a data field, you cannot use a data method.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DataMethod</strong></p></td>
<td><p>Specify the method that returns the value that you want to appear in the info part. If you specify a method, you cannot use a data field.</p></td>
</tr>
<tr class="even">
<td><p><strong>Label</strong></p></td>
<td><p>Select the label that appears with the data value. If you leave this property blank, the info part uses the label from the data source.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Style</strong></p></td>
<td><p>Specify the text style to use with the field. The default is <strong>Auto</strong>. You should use <strong>TitleField</strong> when the data value is used as the title for a preview pane.</p></td>
</tr>
</tbody>
</table>


## Actions

You use the **Actions** node of an info part to add a link that opens a related form. You initiate an action when you click a link that appears in the info part. Actions are optional, and many info parts do not include an action. An info part can have more than one action link.

To add an action to an info part, you use the properties of the **Action** object to specify a menu item that opens a form. You must supply values for the following Action object properties.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>MenuItemType</strong></p></td>
<td><p>Select the type of menu item. For example, click <strong>Display</strong> to see the list of <strong>Display</strong> menu items in the <strong>MenuItemName</strong> property.</p></td>
</tr>
<tr class="even">
<td><p><strong>MenuItemName</strong></p></td>
<td><p>Select the menu item you use to open the related form. The info part uses the label from the menu item to create the link text that appears in the FactBox or preview pane.</p></td>
</tr>
</tbody>
</table>


## Permissions

An info part includes a set of security permissions that you use to configure security. For more information about how to help secure an info part, see [Security Permissions Properties for an Info Part](security-permissions-properties-for-an-info-part.md).

## See also

[How to: Create an Info Part](how-to-create-an-info-part.md)

[How to: Create a Part for a Preview Pane](how-to-create-a-part-for-a-preview-pane.md)

[FactBox Panes](factbox-panes.md)

[Parts](parts.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

