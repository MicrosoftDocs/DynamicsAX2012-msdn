---
title: AxMultiColumn
TOCTitle: AxMultiColumn
ms:assetid: 88dc1f3d-1a4b-43ba-ae71-03a084bfb17d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg862147(v=AX.60)
ms:contentKeyID: 35245480
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# AxMultiColumn 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AxMultiColumn component acts as a container for columns displayed on a page. The AxMultiColumn component can be positioned on its own on a page. It is also frequently put inside an [AxSection](axsection.md) component to provide multiple columns for the section. The AxMultiColumn component can contain only [AxColumn](axcolumn.md) components.

## Properties

The AxMultiColumn component has the following properties:

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
<td><p>TabIndex</p></td>
<td><p>The tab order of the control.</p></td>
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
<td><p>Specifies the cascading style sheet class name associated with the AxMultiColumn component. Typically, this is set to dynMultiColumn so the cascading style sheet for Enterprise Portal can format the component.</p></td>
</tr>
<tr class="even">
<td><p>Font</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>ForeColor</p></td>
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
<td><p>Specifies whether the multicolumn control is enabled.</p></td>
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
<td><p>SkinID</p></td>
<td><p>The SkinId of the control skin that provides the skin of the control.</p></td>
</tr>
<tr class="odd">
<td><p>ToolTip</p></td>
<td><p>Not used for Enterprise Portal.</p></td>
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
<td><p>Height</p></td>
<td><p>The height of the control.</p></td>
</tr>
<tr class="even">
<td><p>Width</p></td>
<td><p>The width of the control.</p></td>
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
</tbody>
</table>


## Events

The AxMultiColumn component has the events listed in the following table.

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
<td><p>Occurs when a server control is released from memory, which is the last stage of the server control life cycle when an ASP.NET page is requested.</p></td>
</tr>
<tr class="odd">
<td><p>Init</p></td>
<td><p>Occurs when the server control is initialized, which is the first step in its life cycle.</p></td>
</tr>
<tr class="even">
<td><p>Load</p></td>
<td><p>Occurs when the server control is loaded into the System.Web.UI.Page object.</p></td>
</tr>
<tr class="odd">
<td><p>PreRender</p></td>
<td><p>Occurs after the System.Web.UI.Control object is loaded but prior to rendering.</p></td>
</tr>
<tr class="even">
<td><p>Unload</p></td>
<td><p>Occurs when the server control is unloaded from memory.</p></td>
</tr>
</tbody>
</table>

