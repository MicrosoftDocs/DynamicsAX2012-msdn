---
title: AxHierarchicalGridView
TOCTitle: AxHierarchicalGridView
ms:assetid: 76ea487f-bf91-407d-9862-1e536d3c4ef1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg862064(v=AX.60)
ms:contentKeyID: 35245390
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# AxHierarchicalGridView [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AxHierarchicalGridView component displays data in a grid with a hierarchy. The grid supports drag-and-drop actions.


> [!TIP]
> <P>Monitor the amount of data that is being displayed in the AxHierarchicalGridView. The performance can become reduced when a large amount of data is displayed in the control.</P>



## Properties

The AxHierarchicalGridView component has the following properties:

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
<td><p>AllowDragAndDrop</p></td>
<td><p>Specifies whether drag-and-drop actions are allowed for the control.</p></td>
</tr>
<tr class="odd">
<td><p>AllowEdit</p></td>
<td><p>When set to true, the data in the selected line can be edited.</p></td>
</tr>
<tr class="even">
<td><p>AllowIndentation</p></td>
<td><p>Specifies whether rows can be indented in the control.</p></td>
</tr>
<tr class="odd">
<td><p>AllowInsert</p></td>
<td><p>When set to true, allows a new row to be inserted into the grid.</p></td>
</tr>
<tr class="even">
<td><p>AllowSelection</p></td>
<td><p>When set to true, allows a row to be selected in the grid.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSorting</p></td>
<td><p>When set to true, allows the items in the grid be sorted by clicking on the column headers.</p></td>
</tr>
<tr class="even">
<td><p>AutoGenerateColumns</p></td>
<td><p>When set to true, columns will be automatically added to the grid for each column in the data set linked to the grid.</p></td>
</tr>
<tr class="odd">
<td><p>AutoGenerateDeleteButton</p></td>
<td><p>When set to true, a Delete link will appear at the beginning of each row in the grid.</p></td>
</tr>
<tr class="even">
<td><p>AutoGenerateEditButton</p></td>
<td><p>When set to true, an Edit link will appear at the beginning of each row in the grid.</p></td>
</tr>
<tr class="odd">
<td><p>AutoGenerateSelectButton</p></td>
<td><p>When set to true, a Select link will appear at the beginning of each row in the grid.</p></td>
</tr>
<tr class="even">
<td><p>ContextMenuName</p></td>
<td><p>The name of the Web Menu in the AOT that contains the menu items to be displayed for the context menu.</p></td>
</tr>
<tr class="odd">
<td><p>Enabled</p></td>
<td><p>Specifies whether the grid is enabled.</p></td>
</tr>
<tr class="even">
<td><p>EnableModelValidation</p></td>
<td><p>Specifies whether page validation will be performed after validation is done in the model.</p></td>
</tr>
<tr class="odd">
<td><p>EnableSortingAndPagingCallbacks</p></td>
<td><p>Indicates whether the client script for sorting and paging should be rendered to browser clients that can support callbacks.</p></td>
</tr>
<tr class="even">
<td><p>EnableTheming</p></td>
<td><p>Indicates whether the control can be themed.</p></td>
</tr>
<tr class="odd">
<td><p>EnableViewState</p></td>
<td><p>Specifies whether the control automatically saves its state for use in round-trips.</p></td>
</tr>
<tr class="even">
<td><p>Filter</p></td>
<td><p>Not currently used.</p></td>
</tr>
<tr class="odd">
<td><p>FixedGridHeight</p></td>
<td><p>When set to true, specifies that the grid should show a fixed number of rows that is equal to the page size.</p></td>
</tr>
<tr class="even">
<td><p>HierarchyExpandAtLevelOnFirstLoad</p></td>
<td><p>Specifies the level of hierarchy to expand up to when the control first loads data.</p></td>
</tr>
<tr class="odd">
<td><p>MinimumGridHeight</p></td>
<td><p>Specifies the minimum number of rows to display in the control.</p></td>
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
<td><p>ShowOnlyGridFieldsInFilter</p></td>
<td><p>When set to true, the filter will list only the fields that are currently displayed as grid columns.</p></td>
</tr>
<tr class="even">
<td><p>SkinID</p></td>
<td><p>The SkinId of the control skin that provides the skin of the control.</p></td>
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
<td><p>ExpandEditableRow</p></td>
<td><p>Specifies whether to expand the editable row when it is displayed.</p></td>
</tr>
<tr class="even">
<td><p>ExpansionColumnIndexesHidden</p></td>
<td><p>A comma-separated list of integers representing which columns to hide from the expansion row. The value 1 indicates the first column.</p></td>
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
<td><p>Specifies whether an expansion is available for each row in the control. When set to true, the expansion is available.</p></td>
</tr>
</tbody>
</table>


### Hierarchy

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
<td><p>HierarchyIdFieldName</p></td>
<td><p>The name of the field that uniquely identifies a row.</p></td>
</tr>
<tr class="even">
<td><p>HierarchyIndentationWidth</p></td>
<td><p>Specifies the amount to indent child rows.</p></td>
</tr>
<tr class="odd">
<td><p>HierarchyParentIdFieldName</p></td>
<td><p>The name of the field that identifies the parent of a row.</p></td>
</tr>
<tr class="even">
<td><p>HierarchyTitleField</p></td>
<td><p>The name of the field whose column will be used to render indentation and expand/collapse buttons.</p></td>
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
<td><p>DraggedRowCssClass</p></td>
<td><p>The style applied to rows being dragged.</p></td>
</tr>
<tr class="odd">
<td><p>EditRowStyle</p></td>
<td><p>The style applied to rows in edit mode.</p></td>
</tr>
<tr class="even">
<td><p>EmptyDataRowStyle</p></td>
<td><p>The style applied to the row that contains the EmptyDataTemplate.</p></td>
</tr>
<tr class="odd">
<td><p>EmptyRowCssClass</p></td>
<td><p>Specifies the cascading style sheet class name to use for formatting an empty row.</p></td>
</tr>
<tr class="even">
<td><p>FooterStyle</p></td>
<td><p>The style applied to the footer.</p></td>
</tr>
<tr class="odd">
<td><p>HeaderStyle</p></td>
<td><p>The style applied to the header.</p></td>
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

The AxHierarchicalGridView component has the events listed in the following table.

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
<td><p>Occurs after a new row is created</p></td>
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
<td><p>PageIndexChanged</p></td>
<td><p>Occurs when the page index of the control has changed.</p></td>
</tr>
<tr class="odd">
<td><p>PageIndexChanging</p></td>
<td><p>Occurs just before the page index of the control has changed.</p></td>
</tr>
<tr class="even">
<td><p>PreRender</p></td>
<td><p>Occurs after the System.Web.UI.Control object is loaded but prior to rendering.</p></td>
</tr>
<tr class="odd">
<td><p>RowCancelingEdit</p></td>
<td><p>Occurs when a Cancel event is generated within the control.</p></td>
</tr>
<tr class="even">
<td><p>RowCollapsed</p></td>
<td><p>Occurs after a hierarchy row is collapsed.</p></td>
</tr>
<tr class="odd">
<td><p>RowCollapsing</p></td>
<td><p>Occurs just before a hierarchy row is collapsed.</p></td>
</tr>
<tr class="even">
<td><p>RowCommand</p></td>
<td><p>Occurs when an event is generated within the control.</p></td>
</tr>
<tr class="odd">
<td><p>RowCreated</p></td>
<td><p>Occurs when a row is created in the control.</p></td>
</tr>
<tr class="even">
<td><p>RowDataBound</p></td>
<td><p>Occurs after a row has been data-bound.</p></td>
</tr>
<tr class="odd">
<td><p>RowDeleted</p></td>
<td><p>Occurs after a Delete command is executed on the data source.</p></td>
</tr>
<tr class="even">
<td><p>RowDeleting</p></td>
<td><p>Occurs before a Delete command is executed on the data source.</p></td>
</tr>
<tr class="odd">
<td><p>RowDropped</p></td>
<td><p>Occurs when the user dropped the row and changes have been made.</p></td>
</tr>
<tr class="even">
<td><p>RowDropping</p></td>
<td><p>Occurs after the user has dropped the row, but changes have not yet been made.</p></td>
</tr>
<tr class="odd">
<td><p>RowEditing</p></td>
<td><p>Occurs when an Edit event is generated within the control.</p></td>
</tr>
<tr class="even">
<td><p>RowExpanded</p></td>
<td><p>Occurs after a hierarchy row is expanded.</p></td>
</tr>
<tr class="odd">
<td><p>RowExpanding</p></td>
<td><p>Occurs just before a hierarchy row is expanded.</p></td>
</tr>
<tr class="even">
<td><p>RowIndented</p></td>
<td><p>Occurs after a hierarchy row is indented.</p></td>
</tr>
<tr class="odd">
<td><p>RowIndenting</p></td>
<td><p>Occurs just before a hierarchy row is indented.</p></td>
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
<td><p>RowOutdented</p></td>
<td><p>Occurs after a hierarchy row is outdented.</p></td>
</tr>
<tr class="odd">
<td><p>RowOutdenting</p></td>
<td><p>Occurs just before a hierarchy row is outdented.</p></td>
</tr>
<tr class="even">
<td><p>RowUpdated</p></td>
<td><p>Occurs after an Update command is executed on the data source.</p></td>
</tr>
<tr class="odd">
<td><p>RowUpdating</p></td>
<td><p>Occurs just before an Update command is executed on the data source.</p></td>
</tr>
<tr class="even">
<td><p>SelectedIndexChanged</p></td>
<td><p>Occurs when a new row is selected in the control, but after the selection is complete.</p></td>
</tr>
<tr class="odd">
<td><p>SelectedIndexChanging</p></td>
<td><p>Occurs when a new row is selected in the control, but just before the selection occurs.</p></td>
</tr>
<tr class="even">
<td><p>Sorted</p></td>
<td><p>Occurs when a column is sorted in the control, but after the sort is complete.</p></td>
</tr>
<tr class="odd">
<td><p>Sorting</p></td>
<td><p>Occurs when a column is sorted in the control, but before the sort occurs.</p></td>
</tr>
<tr class="even">
<td><p>Unload</p></td>
<td><p>Occurs when the server control is unloaded from memory.</p></td>
</tr>
</tbody>
</table>

