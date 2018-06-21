---
title: AxSection
TOCTitle: AxSection
ms:assetid: ff38570c-d241-4cb3-92f1-bace5fae3e43
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc643429(v=AX.60)
ms:contentKeyID: 28119534
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# AxSection [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AxSection component acts as a container for groups of other controls. The AxSection component can be placed in only an AxMultiSection component. AxGroup components are placed inside the AxSection. [AxMultiColumn](axmulticolumn.md) components are also placed inside the AxSection to provide multiple columns for the section.

The AxSection can display summary values (called FastTabs) in the header of the section. You may have to set the FastTabSummary property of each [AxBoundField](axboundfield.md) to have the specific field appear in the summary.

## Properties

The AxSection component has the following properties:

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
<td><p>Not used for Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>Caption</p></td>
<td><p>The caption displayed for the section.</p></td>
</tr>
<tr class="odd">
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
<td><p>Specifies the cascading style sheet class name associated with the AxSection component. Typically, this is set to dynSection so the cascading style sheet for Enterprise Portal can format the component.</p></td>
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
<td><p>Specifies whether the section is enabled.</p></td>
</tr>
<tr class="even">
<td><p>EnableViewState</p></td>
<td><p>Specifies whether the control automatically saves its state for use in round-trips.</p></td>
</tr>
<tr class="odd">
<td><p>Expanded</p></td>
<td><p>Indicates whether the section is expanded or collapsed.</p></td>
</tr>
<tr class="even">
<td><p>PostBackOnCollapseExpand</p></td>
<td><p>When set to true, a postback occurs when the section is expanded or collapsed.</p></td>
</tr>
<tr class="odd">
<td><p>ShowBorder</p></td>
<td><p>Indicates whether the section displays a border.</p></td>
</tr>
<tr class="even">
<td><p>ShowHeader</p></td>
<td><p>Indicates whether the section displays a header.</p></td>
</tr>
<tr class="odd">
<td><p>ToolTip</p></td>
<td><p>Specifies the tooltip displayed when the mouse is over the control.</p></td>
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
<td><p>NumberOfSummaryFields</p></td>
<td><p>Specifies the maximum number of fields to show on the summary header for the section. If the value is 0, no fields are shown on the summary header.</p></td>
</tr>
<tr class="even">
<td><p>SummaryFieldGroupName</p></td>
<td><p>Specifies the field group that contains the fields to be displayed on the summary header for the section.</p></td>
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

The AxSection component has the events listed in the following table.

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
<td><p>Activate</p></td>
<td><p>Occurs when the section becomes active.</p></td>
</tr>
<tr class="even">
<td><p>DataBinding</p></td>
<td><p>Occurs when the server control binds to a data source.</p></td>
</tr>
<tr class="odd">
<td><p>Deactivate</p></td>
<td><p>Occurs when the section is no longer the active section.</p></td>
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
<td><p>RenderingSummaryField</p></td>
<td><p>Occurs for each field being rendered for the summary header after they were selected.</p></td>
</tr>
<tr class="odd">
<td><p>SectionCollapsed</p></td>
<td><p>Occurs after the section has been collapsed.</p></td>
</tr>
<tr class="even">
<td><p>SectionCollapsing</p></td>
<td><p>Occurs after the collapse button has been clicked, but before the section has been collapsed.</p></td>
</tr>
<tr class="odd">
<td><p>SectionExpanded</p></td>
<td><p>Occurs after the section has been expanded.</p></td>
</tr>
<tr class="even">
<td><p>SectionExpanding</p></td>
<td><p>Occurs after the expand button has been clicked, but before the section has been expanded.</p></td>
</tr>
<tr class="odd">
<td><p>Unload</p></td>
<td><p>Occurs when the server control is unloaded from memory.</p></td>
</tr>
</tbody>
</table>

