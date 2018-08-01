---
title: AxGroup
TOCTitle: AxGroup
ms:assetid: c7b4bb97-f314-4ddf-8845-d986429bf986
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc619613(v=AX.60)
ms:contentKeyID: 28119493
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# AxGroup [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AxGroup component acts as a container for fields in a form. The AxGroup component is frequently placed within an [AxSection](axsection.md) component or an [AxColumn](axcolumn.md) component.

Use the **Bound Field Designer** to select the fields displayed in the group. The designer is accessed through the **Fields** collection property for the AxGroup component.

## Properties

The AxGroup component has the following properties:

### Accessiblity

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
<td><p>The keyboard shortcut used by the control.</p></td>
</tr>
<tr class="even">
<td><p>AutoGenerateCaption</p></td>
<td><p>Specifies whether the caption for the group will be displayed.</p></td>
</tr>
<tr class="odd">
<td><p>Caption</p></td>
<td><p>The caption text for the group.</p></td>
</tr>
<tr class="even">
<td><p>CaptionAlign</p></td>
<td><p>Specifies the alignment for the group caption.</p></td>
</tr>
<tr class="odd">
<td><p>TabIndex</p></td>
<td><p>Specifies the tab order of the control.</p></td>
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
<td><p>BorderColor</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>BorderStyle</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>BorderWidth</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>CssClass</p></td>
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
<td><p>Enabled</p></td>
<td><p>Specifies whether the group is enabled.</p></td>
</tr>
<tr class="even">
<td><p>EnableTheming</p></td>
<td><p>Indicates whether the control can be themed.</p></td>
</tr>
<tr class="odd">
<td><p>EnableViewState</p></td>
<td><p>Indicates whether the control automatically saves its state for use in round-trips.</p></td>
</tr>
<tr class="even">
<td><p>SkinID</p></td>
<td><p>The SkinId of the control skin that provides the skin of the control.</p></td>
</tr>
<tr class="odd">
<td><p>ToolTip</p></td>
<td><p>The tooltip displayed when the mouse is over the control.</p></td>
</tr>
<tr class="even">
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
<td><p>FormID</p></td>
<td><p>Specifies the AxForm component that the group is part of.</p></td>
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
<td><p>Specifies the padding for the group.</p></td>
</tr>
<tr class="even">
<td><p>CellSpacing</p></td>
<td><p>Specifies the spacing between groups.</p></td>
</tr>
<tr class="odd">
<td><p>DataCellCssClass</p></td>
<td><p>Specifies the additional CSS class for data cells in the AxGroup.</p></td>
</tr>
<tr class="even">
<td><p>Height</p></td>
<td><p>Specifies the height of the control.</p></td>
</tr>
<tr class="odd">
<td><p>HorizontalAlign</p></td>
<td><p>Specifies the horizontal alignment of the group.</p></td>
</tr>
<tr class="even">
<td><p>LabelCellCssClass</p></td>
<td><p>Specifies the additional CSS class for label cells in the AxGroup.</p></td>
</tr>
<tr class="odd">
<td><p>Width</p></td>
<td><p>Specifies the width of the group.</p></td>
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
<td><p>DataBoundControl</p></td>
<td><p>The form control that the fields in the group will be using to access data.</p></td>
</tr>
<tr class="odd">
<td><p>DataControlFieldCollection</p></td>
<td><p>The collection of bound fields for the group. Use the <strong>Fields</strong> property to select the fields for the group.</p></td>
</tr>
<tr class="even">
<td><p>Fields</p></td>
<td><p>The collection of fields shown in the group. Use the <strong>Bound Field Designer</strong> accessed through this property to specify the fields in the group.</p></td>
</tr>
</tbody>
</table>


### Styles

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
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>EditRowStyle</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>EmptyDataRowStyle</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>FieldHeaderStyle</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>InsertRowStyle</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>RowStyle</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
</tbody>
</table>


## Events

The AxGroup component has the events listed in the following table.

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
<td><p>DataBinding</p></td>
<td><p>Occurs when the server control binds to a data source.</p></td>
</tr>
<tr class="even">
<td><p>Disposed</p></td>
<td><p>Occurs when a server control is released from memory, which is the last stage of the server control lifecycle when an ASP.NET page is requested.</p></td>
</tr>
<tr class="odd">
<td><p>Init</p></td>
<td><p>Occurs when the server control is initialized, which is the first step in its lifecycle.</p></td>
</tr>
<tr class="even">
<td><p>Load</p></td>
<td><p>Occurs when the server control is loaded into the System.Web.UI.Page object.</p></td>
</tr>
<tr class="odd">
<td><p>PreRender</p></td>
<td><p>Occurs after the System.Web.UI.Control object is loaded by prior to rendering.</p></td>
</tr>
<tr class="even">
<td><p>Unload</p></td>
<td><p>Occurs when the server control is unloaded from memory.</p></td>
</tr>
</tbody>
</table>

