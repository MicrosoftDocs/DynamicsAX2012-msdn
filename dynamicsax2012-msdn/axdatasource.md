---
title: AxDataSource
TOCTitle: AxDataSource
ms:assetid: b5fe28bc-a34c-4535-8a2f-c481a32c8b10
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc636502(v=AX.60)
ms:contentKeyID: 28119475
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# AxDataSource [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An AxDataSource component provides access to a data set in the AOT. The other components of the User Control will use the AxDataSource when retrieving or saving data in the data set.

## Properties

The AxDataSource component has the following properties:

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
<td><p>DataSetName</p></td>
<td><p>The data set the control is bound to.</p></td>
</tr>
<tr class="even">
<td><p>EnableViewState</p></td>
<td><p>Indicates whether the control automatically saves its state for use in round-trips.</p></td>
</tr>
<tr class="odd">
<td><p>Expressions</p></td>
<td><p>The expressions that are bound to properties of the control.</p></td>
</tr>
<tr class="even">
<td><p>ID</p></td>
<td><p>The programmatic name of the control.</p></td>
</tr>
<tr class="odd">
<td><p>PersistState</p></td>
<td><p>When set to true, enables the control to persist state information for the dataset. Information persisted includes the following:</p>
<ul>
<li><p>Dataset metadata</p></li>
<li><p>Calculated field values</p></li>
<li><p>Ax queries that are initially generated using the data source metadata</p></li>
<li><p>Temporary tables</p></li>
<li><p>Cursor position (active record) within each table</p></li>
<li><p>Uncommitted record buffer for the active record</p></li>
</ul>
<p>The default value is true.</p></td>
</tr>
<tr class="even">
<td><p>ProviderView</p></td>
<td><p>The view in the data set that is being used for the current context.</p></td>
</tr>
<tr class="odd">
<td><p>Role</p></td>
<td><p>Sets the context behavior for the data source. It can be one of the following values:</p>
<ul>
<li><p><strong>None</strong> - No context behavior</p></li>
<li><p><strong>Provider</strong> - Data source provides context to other web parts</p></li>
<li><p><strong>Consumer</strong> - Data source receives context from other web parts</p></li>
<li><p><strong>ProviderConsumer</strong> - Data source provides context to other web parts and receives context from other web parts.</p></li>
</ul>
<p>A User Control can have multiple AxDataSource components. A maximum of one AxDataSource component for the User Control can act as a context provider. Multiple AxDataSource components can act as context consumers.</p></td>
</tr>
<tr class="even">
<td><p>SuppressDeleteConfirmationDialog</p></td>
<td><p>When set to true, the dialog to confirm delete operations will not be displayed.</p></td>
</tr>
</tbody>
</table>


## Events

The AxDataSource component has the events listed in the following table.

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
<td><p>CreatingDataSetRun</p></td>
<td><p>Occurs when a data set is created or unpacked.</p></td>
</tr>
<tr class="even">
<td><p>DataBinding</p></td>
<td><p>Occurs when the server control binds to a data source.</p></td>
</tr>
<tr class="odd">
<td><p>DataSetDetached</p></td>
<td><p>Occurs when the data set is detached from the control.</p></td>
</tr>
<tr class="even">
<td><p>DataSetReady</p></td>
<td><p>Occurs after the RunningDataSetRun event, when the data set has been initialized and is ready for access.</p></td>
</tr>
<tr class="odd">
<td><p>InitializedDataSetRun</p></td>
<td><p>Occurs when the data set is initialized, after the CreatingDataSetRun event.</p></td>
</tr>
<tr class="even">
<td><p>RunningDataSetRun</p></td>
<td><p>Occurs after the InitializedDataSetRun event.</p></td>
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
<td><p>PreRender</p></td>
<td><p>Occurs after the System.Web.UI.Control object is loaded by prior to rendering.</p></td>
</tr>
<tr class="odd">
<td><p>Unload</p></td>
<td><p>Occurs when the server control is unloaded from memory.</p></td>
</tr>
</tbody>
</table>


## See also

[Data Access Overview](data-access-overview.md)

