---
title: AxContentPanel
TOCTitle: AxContentPanel
ms:assetid: fbf1f2d2-888c-4c52-a700-55e19a7aa3d4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc642797(v=AX.60)
ms:contentKeyID: 28119532
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# AxContentPanel [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AxContentPanel is used to display a User Control within another User Control. To do this, add the AxContentPanel to the User Control you are creating. Specify the **Managed Web Content Item** property to indicate the User Control you want to display.

## Properties

The AxContentPanel component has the following properties:

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
<td><p>ChildrenAsTriggers</p></td>
<td><p>Indicates whether postbacks coming from the child controls in the panel will cause the panel to refresh.</p></td>
</tr>
<tr class="even">
<td><p>EnableViewState</p></td>
<td><p>Indicates whether the control automatically saves its state for use in round-trips.</p></td>
</tr>
<tr class="odd">
<td><p>Triggers</p></td>
<td><p>A collection of triggers that can cause the panel to be updated.</p></td>
</tr>
<tr class="even">
<td><p>UpdateMode</p></td>
<td><p>Indicates whether the panel will refresh on every asynchronous postback or only as a result of a specific action, such as a call to Update.</p></td>
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
<td><p>RenderMode</p></td>
<td><p>Indicates whether the panel should render as a block tag (&lt;div&gt;) or an inline tag (&lt;span&gt;).</p></td>
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
<td><p>Managed Web Content Item</p></td>
<td><p>Specifies the User Control to be displayed in the content panel.</p></td>
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

The AxContentPanel component has the events listed in the following table.

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
<td><p>EnsuringConsumerContext</p></td>
<td><p>Occurs before the control is rendered. This event can be used to verify that the context has been passed before the control is rendered.</p></td>
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
<td><p>PreRender</p></td>
<td><p>Occurs after the System.Web.UI.Control object is loaded but prior to rendering.</p></td>
</tr>
<tr class="odd">
<td><p>Unload</p></td>
<td><p>Occurs when the server control is unloaded from memory.</p></td>
</tr>
</tbody>
</table>

