---
title: 'Best Practices: List Pages'
TOCTitle: 'Best Practices: List Pages'
ms:assetid: ced65d17-2c3d-49bf-85b1-86775f30b083
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc638392(v=AX.60)
ms:contentKeyID: 35251738
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices: List Pages 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX conducts a best practices check of new or modified list pages. The best practice checks seek to establish a common look and behavior for all list pages. For more information about best practice checks, see [Best Practices for Microsoft Dynamics AX Development](best-practices-for-microsoft-dynamics-ax-development.md).

## Best Practice Checks

The following table lists the best practices error messages for list pages.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Message</p></th>
<th><p>Message type</p></th>
<th><p>How to fix the error or warning</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>List Pages must have a name that ends with &quot;ListPage&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Append <strong>ListPage</strong> to the value of the form <strong>Name</strong> property.</p></td>
</tr>
<tr class="even">
<td><p>List Pages must have their TopMargin property set to &quot;Auto&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>TopMargin</strong> property in the form <strong>Design</strong> node to <strong>Auto</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>List Pages must have their BottomMargin property set to &quot;Auto&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>BottomMargin</strong> property in the form <strong>Design</strong> node to <strong>Auto</strong>.</p></td>
</tr>
<tr class="even">
<td><p>List Pages must have their LeftMargin property set to &quot;Auto&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>LeftMargin</strong> property in the form <strong>Design</strong> node to <strong>Auto</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>List Pages must have their RightMargin property set to &quot;Auto&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>RightMargin</strong> property in the form <strong>Design</strong> node to <strong>Auto</strong>.</p></td>
</tr>
<tr class="even">
<td><p>List Page datasources must have their AllowEdit property set to &quot;No&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>AllowEdit</strong> property in the list page data source to <strong>No</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>List Page datasources must have their AllowCreate property set to &quot;No&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>AllowCreate</strong> property in the list page data source to <strong>No</strong>.</p></td>
</tr>
<tr class="even">
<td><p>List Page datasources must have their StartPosition property set to &quot;First&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>StartPosition</strong> property in the list page data source to <strong>First</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>A List Page must have a single Action Pane.</p></td>
<td><p>Warning</p></td>
<td><p>If the list page does not include an <strong>ActionPane</strong>, add an <strong>ActionPane</strong> control to the <strong>Design</strong> node of that list page.</p>
<p>If the list page includes more than one <strong>ActionPane</strong>, remove all except one <strong>ActionPane</strong> control from the <strong>Design</strong> node of that list page.</p></td>
</tr>
<tr class="even">
<td><p>An Action Pane should not be present on a form that isn't a List Page or Content Page.</p></td>
<td><p>Warning</p></td>
<td><p>Remove the <strong>ActionPane</strong> control from the <strong>Design</strong> node of the form. Or, set the <strong>WindowType</strong> property in the <strong>Design</strong> node of the form to <strong>ListPage</strong> or <strong>ContentPage</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>A List Page must have a grid.</p></td>
<td><p>Warning</p></td>
<td><p>Add a <strong>Grid</strong> control to the <strong>Design</strong> node of the list page.</p></td>
</tr>
<tr class="even">
<td><p>List Page grids must have their AllowEdit property set to &quot;No&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>AllowEdit</strong> property of the <strong>Grid</strong> control to <strong>No</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>List Page grids must have their Width property set to &quot;Column width&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>Width</strong> property of the <strong>Grid</strong> control to <strong>Column width</strong>.</p></td>
</tr>
<tr class="even">
<td><p>List Page grids must have their Height property set to &quot;Column height&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>Height</strong> property of the <strong>Grid</strong> control to <strong>Column height</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>List Page grids must have their ShowRowLabels property set to &quot;Yes&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>ShowRowLabels</strong> property of the <strong>Grid</strong> control to <strong>Yes</strong>.</p></td>
</tr>
<tr class="even">
<td><p>List Page grids must have their Datasource property set to a valid datasource.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>DataSource</strong> property of the <strong>Grid</strong> control to the name of a data source for that list page.</p></td>
</tr>
<tr class="odd">
<td><p>List Page grids must have their DefaultAction property set to a button on the form. The DefaultAction property should normally point to a button that performs the &quot;Open&quot; action.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>DefaultAction</strong> property of the <strong>Grid</strong> control. Specify the name of an action pane button.</p></td>
</tr>
<tr class="even">
<td><p>List Page Action Panes must have their Width property set to &quot;Column width&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>Width</strong> property of the <strong>ActionPane</strong> control to <strong>Column width</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>A document handling button on an Action Pane should use the label @SYS114630 for its Text property.</p></td>
<td><p>Warning</p></td>
<td><p>Use the specified <strong>Label ID</strong> value for the <strong>Text</strong> property of a document handling button.</p></td>
</tr>
<tr class="even">
<td><p>A document handling button on an Action Pane should have its Name property set to &quot;Attachments&quot;.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>Name</strong> property of the document handling button to <strong>Attachments</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>All buttons on an Action Pane should have their ShowShortcut properties set to &quot;No&quot; to suppress the addition of extra characters for mnemonic usage.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>ShowShortcut</strong> property of the action pane button control to <strong>No</strong>.</p></td>
</tr>
<tr class="even">
<td><p>List Page controls must not have any vertical spacing between them.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>VerticalSpacing</strong> property of the control to <strong>Auto</strong> or <strong>0</strong>. Use <strong>Auto</strong> whenever possible.</p></td>
</tr>
<tr class="odd">
<td><p>List Pages must have their TitleDatasource property set.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>TitleDataSource</strong> property in the form <strong>Design</strong> node to the name of a list page data source.</p></td>
</tr>
<tr class="even">
<td><p>List Page Action Panes must have their VerticalSpacing property set to zero.</p></td>
<td><p>Warning</p></td>
<td><p>Set the value of the <strong>VerticalSpacing</strong> property of the <strong>ActionPane</strong> control to <strong>Auto</strong> or <strong>0</strong>. Use <strong>Auto</strong> whenever possible.</p></td>
</tr>
</tbody>
</table>


## See also

[List Page Overview](list-page-overview.md)

[How to: Create a List Page Form](how-to-create-a-list-page-form.md)

[How to: Add a Data Source to a Primary List Page](how-to-add-a-data-source-to-a-primary-list-page.md)

[How to: Add Fields to the List Page Grid](how-to-add-fields-to-the-list-page-grid.md)

[Walkthrough: Creating a List Page and Adding an Action Pane](walkthrough-creating-a-list-page-and-adding-an-action-pane.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

