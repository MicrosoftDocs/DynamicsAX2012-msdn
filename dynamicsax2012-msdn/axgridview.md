---
title: AxGridView
TOCTitle: AxGridView
ms:assetid: 1f56cc51-425f-4153-bf04-2f989a56d837
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc584514(v=AX.60)
ms:contentKeyID: 28119408
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# AxGridView [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An AxGridView component displays data from an AxDataSource in a grid view for a User Control. The AxGridView component can be used to edit existing records in a table. It can also be used to create new records.

Use the **Bound Field Designer** to select the bound fields displayed in the grid. To access this designer, click **Edit Columns** in the context menu for the AxGridView component. The designer is also accessible through the **Columns** collection property for the AxGridView component.

The user can click the columns in the grid to sort the data. Be aware that columns that display data that was retrieved with a display method are not sortable.

## Properties

The AxGridView component has the following properties:

### Accessibility

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
<td><p>AccessKey</p></td>
<td><p>The keyboard shortcut used by the control. Not used for Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>Caption</p></td>
<td><p>The descriptive caption associated with the control.</p></td>
</tr>
<tr class="odd">
<td><p>CaptionAlign</p></td>
<td><p>The alignment of the associated caption.</p></td>
</tr>
<tr class="even">
<td><p>RowHeaderColumn</p></td>
<td><p>The data source field corresponding to the column that is the row header.</p></td>
</tr>
<tr class="odd">
<td><p>TabIndex</p></td>
<td><p>The tab order of the control.</p></td>
</tr>
<tr class="even">
<td><p>UseAccessibleHeader</p></td>
<td><p>Indicates that the control should use accessible header cells in its containing table control.</p></td>
</tr>
</tbody>
</table>


### Appearance

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
<td><p>BackColor</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>BackImageUrl</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>BorderColor</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>BorderStyle</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>BorderWidth</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>CssClass</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>EmptyDataText</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>Font</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>ForeColor</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>GridLines</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>ShowFooter</p></td>
<td><p>When set to true, the footer containing the paging controls for the grid is displayed.</p></td>
</tr>
<tr class="even">
<td><p>ShowHeader</p></td>
<td><p>When set to true, the header containing the column names is displayed.</p></td>
</tr>
</tbody>
</table>


### Behavior

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
<td><p>AllowDelete</p></td>
<td><p>When set to true, an X will be displayed on the selected line, allowing the record to be deleted.</p></td>
</tr>
<tr class="even">
<td><p>AllowEdit</p></td>
<td><p>When set to true, the data in the selected line can be edited.</p></td>
</tr>
<tr class="odd">
<td><p>AllowGroupCollapse</p></td>
<td><p>When related rows in the grid are grouped, allows the groups to be collapsed.</p></td>
</tr>
<tr class="even">
<td><p>AllowGrouping</p></td>
<td><p>When set to true, related rows in the grid are grouped based on the field specified in the <strong>GroupField</strong> property.</p></td>
</tr>
<tr class="odd">
<td><p>AllowInsert</p></td>
<td><p>When set to true, allows a new row to be inserted into the grid.</p></td>
</tr>
<tr class="even">
<td><p>AllowMarking</p></td>
<td><p>When set to true, a checkbox is displayed next to each row. The user can mark the checkbox to indicate the row is marked.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSelection</p></td>
<td><p>When set to true, allows a row to be selected in the grid.</p></td>
</tr>
<tr class="even">
<td><p>AllowSorting</p></td>
<td><p>When set to true, allows the items in the grid be sorted by clicking on the column headers.</p></td>
</tr>
<tr class="odd">
<td><p>AutoGenerateColumns</p></td>
<td><p>When set to true, columns will be automatically added to the grid for each column in the data set linked to the grid.</p></td>
</tr>
<tr class="even">
<td><p>AutoGenerateDeleteButton</p></td>
<td><p>When set to true, a Delete link will appear at the beginning of each row in the grid.</p></td>
</tr>
<tr class="odd">
<td><p>AutoGenerateEditButton</p></td>
<td><p>When set to true, an Edit link will appear at the beginning of each row in the grid.</p></td>
</tr>
<tr class="even">
<td><p>AutoGenerateSelectButton</p></td>
<td><p>When set to true, a Select link will appear at the beginning of each row in the grid.</p></td>
</tr>
<tr class="odd">
<td><p>ContextMenuName</p></td>
<td><p>The name of the Web Menu in the AOT that contains the menu items to be displayed for the context menu.</p></td>
</tr>
<tr class="even">
<td><p>DefaultCollapsed</p></td>
<td><p>When related rows in the grid are grouped, specifies that the groups are collapsed by default.</p></td>
</tr>
<tr class="odd">
<td><p>DisplayGroupFieldName</p></td>
<td><p>When set to true, the name of the field on which the row groups are based is displayed in the header for the group. The value displayed can be controlled by the <strong>GroupFieldDisplayName</strong> property.</p></td>
</tr>
<tr class="even">
<td><p>Enabled</p></td>
<td><p>Specifies whether the grid is enabled.</p></td>
</tr>
<tr class="odd">
<td><p>EnableModelValidation</p></td>
<td><p>Specifies whether page validation will be performed after validation is done in the model.</p></td>
</tr>
<tr class="even">
<td><p>EnableSortingAndPagingCallbacks</p></td>
<td><p>Indicates whether the client script for sorting and paging should be rendered to browser clients that can support callbacks.</p></td>
</tr>
<tr class="odd">
<td><p>EnableTheming</p></td>
<td><p>Indicates whether the control can be themed.</p></td>
</tr>
<tr class="even">
<td><p>EnableViewState</p></td>
<td><p>Specifies whether the control automatically saves its state for use in round-trips.</p></td>
</tr>
<tr class="odd">
<td><p>Filter</p></td>
<td><p>Not currently used.</p></td>
</tr>
<tr class="even">
<td><p>FixedGridHeight</p></td>
<td><p>When set to true, specifies that the grid should show a fixed number of rows that is equal to the page size.</p></td>
</tr>
<tr class="odd">
<td><p>GroupField</p></td>
<td><p>The field based on which the rows in the grid will be grouped. The bound field chosen must have its <strong>SortExpression</strong> property set for grouping to occur.</p></td>
</tr>
<tr class="even">
<td><p>GroupFieldDisplayName</p></td>
<td><p>The value to display in the group header for each group. If no value is supplied, the name of the field specified in the <strong>GroupField</strong> property will be used.</p></td>
</tr>
<tr class="odd">
<td><p>PostBackOnMarking</p></td>
<td><p>Specifies that a postback occurs each time a row is marked or unmarked.</p></td>
</tr>
<tr class="even">
<td><p>SetCurrentRowOnSelection</p></td>
<td><p>Sets the current row in the data set when the user selects a row in the grid.</p></td>
</tr>
<tr class="odd">
<td><p>ShowContextMenu</p></td>
<td><p>When set to true, a context menu will be displayed when the user right-clicks the selected row in the grid.</p></td>
</tr>
<tr class="even">
<td><p>ShowFilter</p></td>
<td><p>When set to true, the filter control for the grid is displayed.</p></td>
</tr>
<tr class="odd">
<td><p>ShowOnly GridFieldsInFilter</p></td>
<td><p>When set to true, the filter will list only the fields that are currently displayed as grid columns.</p></td>
</tr>
<tr class="even">
<td><p>SkinID</p></td>
<td><p>The SkinId of the control skin that provides the skin of the control</p></td>
</tr>
<tr class="odd">
<td><p>ToolTip</p></td>
<td><p>Not used for Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>UpdateOnPostBack</p></td>
<td><p>Indicates whether the component is updated when a postback occurs.</p></td>
</tr>
<tr class="odd">
<td><p>Visible</p></td>
<td><p>Indicates whether the control is visible and rendered.</p></td>
</tr>
</tbody>
</table>


### Data

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
<td><p>Expressions</p></td>
<td><p>The expressions that are bound to properties of the control.</p></td>
</tr>
<tr class="even">
<td><p>DataKeyNames</p></td>
<td><p>A comma separated list of key fields in the data source.</p></td>
</tr>
<tr class="odd">
<td><p>DataMember</p></td>
<td><p>The table or view from the data set that is being used for the grid.</p></td>
</tr>
<tr class="even">
<td><p>DataSourceID</p></td>
<td><p>Specifies the AxDataSource component that will be used by the grid to access data.</p></td>
</tr>
</tbody>
</table>


### ExpansionRowProperties

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
<td><p>ExpandEditiableRow</p></td>
<td><p>When set to true, the row being edited will be rendered as expanded.</p></td>
</tr>
<tr class="even">
<td><p>ExpansionColumnIndexesHidden</p></td>
<td><p>A comma separated list of integers representing which columns to hide from the expansion row. The value 1 indicates the first column.</p></td>
</tr>
<tr class="odd">
<td><p>ExpansionTooltip</p></td>
<td><p>The tooltip displayed on the Expansion row link.</p></td>
</tr>
<tr class="even">
<td><p>GridColumnIndexesHidden</p></td>
<td><p>A comma-separated list of integers representing which columns to hide from the main grid. The value 1 indicates the first column.</p></td>
</tr>
<tr class="odd">
<td><p>ShowExpansion</p></td>
<td><p>Specifies whether an expansion is available for each row in the grid. When set to true, the expansion row link is displayed for each row in the grid.</p></td>
</tr>
</tbody>
</table>


### Layout

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
<td><p>CellPadding</p></td>
<td><p>The padding within cells.</p></td>
</tr>
<tr class="even">
<td><p>CellSpacing</p></td>
<td><p>The spacing between cells.</p></td>
</tr>
<tr class="odd">
<td><p>Height</p></td>
<td><p>The height of the control.</p></td>
</tr>
<tr class="even">
<td><p>HorizontalAlign</p></td>
<td><p>The horizontal alignment of the control.</p></td>
</tr>
<tr class="odd">
<td><p>Width</p></td>
<td><p>The width of the control.</p></td>
</tr>
</tbody>
</table>


### Microsoft Dynamics AX

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
<td><p>AllowPrompting</p></td>
<td><p>When set to true, a prompt will be shown to collect missing concrete types.</p></td>
</tr>
<tr class="even">
<td><p>BodyHeight</p></td>
<td><p>Specifies the body height of the grid. Set this property when the body should have a fixed height.</p></td>
</tr>
<tr class="odd">
<td><p>ManagedWebContentItem</p></td>
<td><p>Specifies the User Control to display that allows the user to select the record type for the new record they are creating. This occurs only when the new type is part of a table hierarchy. If this property is not specified, the default control to select the new type is displayed.</p></td>
</tr>
</tbody>
</table>


### Misc

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
<td><p>ID</p></td>
<td><p>The programmatic name of the control.</p></td>
</tr>
<tr class="even">
<td><p>Columns</p></td>
<td><p>The set of columns to be shown in the control. The <strong>Bound Field Designer</strong> used to select the columns is accessed through this property.</p></td>
</tr>
<tr class="odd">
<td><p>EditIndex</p></td>
<td><p>The index of the row shown in edit mode.</p></td>
</tr>
<tr class="even">
<td><p>SelectedIndex</p></td>
<td><p>The index of the currently selected row.</p></td>
</tr>
</tbody>
</table>


### Paging

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
<td><p>AllowPaging</p></td>
<td><p>Specifies whether paging functionality is enabled for the grid.</p></td>
</tr>
<tr class="even">
<td><p>PageIndex</p></td>
<td><p>Specifies the index of the current page.</p></td>
</tr>
<tr class="odd">
<td><p>PagerSettings</p></td>
<td><p>Controls the paging UI settings associated with the control.</p></td>
</tr>
<tr class="even">
<td><p>PageSize</p></td>
<td><p>The number of rows from the data source to display per page.</p></td>
</tr>
</tbody>
</table>


### Styles

These style properties are groups that contain multiple properties.

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
<td><p>AlternatingRowStyle</p></td>
<td><p>The style applied to alternating rows.</p></td>
</tr>
<tr class="even">
<td><p>EditRowStyle</p></td>
<td><p>The style applied to rows in edit mode.</p></td>
</tr>
<tr class="odd">
<td><p>EmptyDataRowStyle</p></td>
<td><p>The style applied to the row that contains the EmptyDataTemplate.</p></td>
</tr>
<tr class="even">
<td><p>EmptyRowCssClass</p></td>
<td><p>Specifies the cascading style sheet class name to use for formatting an empty row.</p></td>
</tr>
<tr class="odd">
<td><p>FooterStyle</p></td>
<td><p>The style applied to the footer.</p></td>
</tr>
<tr class="even">
<td><p>HeaderStyle</p></td>
<td><p>The style applied to the header.</p></td>
</tr>
<tr class="odd">
<td><p>MarkedRowCssClass</p></td>
<td><p>Specifies the cascading style sheet class name to use for formatting a marked row.</p></td>
</tr>
<tr class="even">
<td><p>PagerStyle</p></td>
<td><p>Controls the paging UI style for the grid.</p></td>
</tr>
<tr class="odd">
<td><p>RowStyle</p></td>
<td><p>The style applied to rows.</p></td>
</tr>
<tr class="even">
<td><p>SelectedRowStyle</p></td>
<td><p>The style applied to the selected row.</p></td>
</tr>
</tbody>
</table>


## Events

The AxGridView component has the events listed in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Event</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AxRowCreated</p></td>
<td><p>Occurs after a new row is created.</p></td>
</tr>
<tr class="even">
<td><p>AxRowCreating</p></td>
<td><p>Occurs just before a new row is created.</p></td>
</tr>
<tr class="odd">
<td><p>DataBinding</p></td>
<td><p>Occurs when the server control binds to a data source.</p></td>
</tr>
<tr class="even">
<td><p>DataBound</p></td>
<td><p>Occurs after the server control binds to a data source.</p></td>
</tr>
<tr class="odd">
<td><p>Disposed</p></td>
<td><p>Occurs when a server control is released from memory, which is the last stage of the server control lifecycle when an ASP.NET page is requested.</p></td>
</tr>
<tr class="even">
<td><p>Init</p></td>
<td><p>Occurs when the server control is initialized, which is the first step in its lifecycle.</p></td>
</tr>
<tr class="odd">
<td><p>Load</p></td>
<td><p>Occurs when the server control is loaded into the System.Web.UI.Page object.</p></td>
</tr>
<tr class="even">
<td><p>MarkingChanged</p></td>
<td><p>Occurs after the marking has changed for a row.</p></td>
</tr>
<tr class="odd">
<td><p>MarkingChanging</p></td>
<td><p>Occurs just before the marking has changed for a row.</p></td>
</tr>
<tr class="even">
<td><p>PageIndexChanged</p></td>
<td><p>Occurs when one of the pager buttons is clicked, but after the grid view handles the paging operation.</p></td>
</tr>
<tr class="odd">
<td><p>PageIndexChanging</p></td>
<td><p>Occurs when one of the pager buttons is clicked, but before the grid view handles the paging operation.</p></td>
</tr>
<tr class="even">
<td><p>PreRender</p></td>
<td><p>Occurs after the System.Web.UI.Control object is loaded by prior to rendering.</p></td>
</tr>
<tr class="odd">
<td><p>RowCancelingEdit</p></td>
<td><p>Occurs when the Cancel button of a row in edit mode is clicked, but before the row exits edit mode.</p></td>
</tr>
<tr class="even">
<td><p>RowCommand</p></td>
<td><p>Occurs when a button is clicked in the grid view control.</p></td>
</tr>
<tr class="odd">
<td><p>RowCreated</p></td>
<td><p>Occurs when a row is created in a grid view control.</p></td>
</tr>
<tr class="even">
<td><p>RowDataBound</p></td>
<td><p>Occurs when a data row is bound to data in grid view control.</p></td>
</tr>
<tr class="odd">
<td><p>RowDeleted</p></td>
<td><p>Occurs when the Delete button of a row is clicked, but after the grid view control deletes the row.</p></td>
</tr>
<tr class="even">
<td><p>RowDeleting</p></td>
<td><p>Occurs when the Delete button of a row is clicked, but before the grid view control deletes the row.</p></td>
</tr>
<tr class="odd">
<td><p>RowEditing</p></td>
<td><p>Occurs when the Edit button of a row is clicked, but before the grid view control enters edit mode.</p></td>
</tr>
<tr class="even">
<td><p>RowInserted</p></td>
<td><p>Occurs after an Insert command is executed on the data source.</p></td>
</tr>
<tr class="odd">
<td><p>RowInserting</p></td>
<td><p>Occurs just before an Insert command is executed on the data source.</p></td>
</tr>
<tr class="even">
<td><p>RowUpdated</p></td>
<td><p>Occurs when the Update button of a row is clicked, but after the grid view control updates the row.</p></td>
</tr>
<tr class="odd">
<td><p>RowUpdating</p></td>
<td><p>Occurs when the Update button of a row is clicked, but before the grid view control updates the row.</p></td>
</tr>
<tr class="even">
<td><p>SelectedIndexChanged</p></td>
<td><p>Occurs when the Select button of a row is clicked, but after the grid view control handles the selection operation.</p></td>
</tr>
<tr class="odd">
<td><p>SelectedIndexChanging</p></td>
<td><p>Occurs when the Select button of a row is clicked, but before the grid view control handles the selection operation.</p></td>
</tr>
<tr class="even">
<td><p>Sorted</p></td>
<td><p>Occurs when the hyperlink to sort a column is clicked, but after the grid view control handles the sorting operation.</p></td>
</tr>
<tr class="odd">
<td><p>Sorting</p></td>
<td><p>Occurs when the hyperlink to sort a column is clicked, but before the grid view control handles the sorting operation.</p></td>
</tr>
<tr class="even">
<td><p>Unload</p></td>
<td><p>Occurs when the server control is unloaded from memory.</p></td>
</tr>
</tbody>
</table>


## Expansion Row for a Grid

If a grid has a large number of fields to display on a single row, consider using an expansion row. An expansion row allows a grid to display fields for the row in an additional line below the row. To use an expansion row, set the **ShowExpansion** property for the grid to true. Set the **ExpansionColumnIndexesHidden** and **GridColumnIndexesHidden** properties to indicate which fields in the grid will appear in the main row for the grid and which fields will appear in the expansion row.

For example, the following customer list grid contains five fields to display.

![Original grid fields](images/Cc584514.EP_ExpansionMOdeOriginal(AX.60).gif "Original grid fields")

**Grid View with Five Fields**

The positions of the fields in this grid are numbered starting with the value 1. The Customer account field is in position 1, the Name field is in position 2, and so on. In this example, the Telephone field will be moved to the expansion row. The Telephone field is in position 5 in the list. To make the expansion row act as desired, fields 1,2,3,and 4 are hidden in the expansion. Field 5 is hidden in the main list. The properties for the grid are set to the following values:

ExpansionColumnIndexesHidden: 1,2,3,4

GridColumnIndexesHidden: 5

ShowExpansion: True

When these settings are applied, each row in the grid will have an expansion button displayed. This is shown in the following illustration.

![Expansion row collapsed](images/Cc584514.EP_ExpansionModeCollapsed(AX.60).gif "Expansion row collapsed")

**Grid View with Expansion Button**

When the expansion button is clicked, the expansion line containing the Telephone field will be displayed. This is shown in the following illustration.

![Expansion row expanded](images/Cc584514.EP_ExpansionModeExpanded(AX.60).gif "Expansion row expanded")

**Grid View with Expansion Displayed**

## Context Menu for a Grid

An AxGridView component can have a context menu that is displayed when the user right-clicks the selected row in the grid. Set the **ShowContextMenu** property to true for the AxGridView. Set the **ContextMenuName** property for the AxGridView component to the name of the Web Menu from the AOT that contains the menu items that you want to display in the context menu. The following illustration shows the context menu displayed for a grid control.

![Context Menu for a Grid](images/Cc584514.EP_GridContextMenu(AX.60).gif "Context Menu for a Grid")

**Grid View with Context Menu**

## Row Grouping

The rows in an AxGridView component can be grouped based on one of the fields in each row. For example, the customer records displayed in a grid could be grouped based on the customer group number. This is shown in the following illustration.

![Groups in AxGridView](images/Cc584514.EP_GridViewGrouping(AX.60).gif "Groups in AxGridView")

**Grid View with Groups**

To group the rows in an AxGridView, set the **AllowGrouping** property to true. Set the **GroupField** property to the bound field that you want to use to group the rows in the grid. The bound field chosen must have its **SortExpression** property set for grouping to occur. Use the other properties such as **AllowGroupCollapse** and **DisplayGroupFieldName** to control the group behavior.

## Multi-selection

When you set the **AllowMarking** property to true, the user can mark multiple rows in the grid. You may want to know which rows the user has marked. The following example shows how to use the GetMarkedRowsSet method for the data source view to retrieve the set of marked rows. In this example, the name of each marked row is added to a list box.

This example uses the .NET Business Connector to access data. It requires access to the following namespaces:

``` csharp
using Microsoft.Dynamics.AX.Framework.Portal.Data;
using Microsoft.Dynamics.Framework.BusinessConnector.Session;
using Microsoft.Dynamics.Framework.BusinessConnector.Adapter;
```

The following code for a button retrieves the list of marked rows.

``` csharp
protected void Button1_Click(object sender, EventArgs e)
{
    // Create a container.
    IAxaptaContainerAdapter recordIds = this.AxSession.AxaptaAdapter.CreateAxaptaContainer();

    // Get the marked rows.
    IReadOnlySet<DataSetViewRow> rows = this.AxDataSource1.GetDataSourceView("FCMRooms").DataSetView.GetMarkedRowsSet();

    // Create an enumerator to examine each marked row.
    IEnumerator enumRows = rows.GetEnumerator();

    DataSetViewRow row;
    string description;

    // Clear the list box.
    ListBox1.Items.Clear();

    while (enumRows.MoveNext())
    {
        // Get the current row.
        row = (DataSetViewRow)enumRows.Current;

        // Retrieve the name of the room.
        description = row.GetFieldValue("RoomName").ToString();

        // Add the item to the list box.
        ListBox1.Items.Add(description);
    }
}
```

