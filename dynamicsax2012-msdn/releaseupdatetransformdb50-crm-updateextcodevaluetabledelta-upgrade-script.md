---
title: ReleaseUpdateTransformDB50_CRM.updateExtCodeValueTableDelta Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_CRM.updateExtCodeValueTableDelta Upgrade Script
ms:assetid: 9833dc60-6f14-1850-827a-fb92b7eaf3cb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686236(v=AX.60)
ms:contentKeyID: 49709940
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_CRM.updateExtCodeValueTableDelta Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_CRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateExtCodeValueTableDelta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the references in the ExtCodeValueTable table to the logistics address codes.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
</tr>
</tbody>
</table>


## Affected Modules and Tables

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Affected Modules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Accounts receivable</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Affected Tables</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustConfirmJour</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert postal address codes to the new logistics postal address model for Microsoft Dynamics AX 2012. The AddressCountryRegion, AddressState, AddressCounty, and AddressZipCode tables are deleted in Microsoft Dynamics AX 2012. The data from these tables is moved to the LogisticsAddressCountryRegion, LogisticsAddressState, LogisticsAddressCounty, and LogisticsAddressZipCode tables that are newly created respectively. The data in the ExtCodeValueTable table can be updated to refer to the records in the LogisticsAddress tables.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LogisticsAddressCountryRegion</p></th>
<th><p>To Table: Shadow_ExtCodeValueTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TableId</p></td>
<td><p>ExtCodeRelationTableId</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>ExtCodeRelationRecId</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LogisticsAddressState</p></th>
<th><p>To Table: Shadow_ExtCodeValueTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TableId</p></td>
<td><p>ExtCodeRelationTableId</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>ExtCodeRelationRecId</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LogisticsAddressCounty</p></th>
<th><p>To Table: Shadow_ExtCodeValueTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TableId</p></td>
<td><p>ExtCodeRelationTableId</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>ExtCodeRelationRecId</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LogisticsAddressZipCode</p></th>
<th><p>To Table: Shadow_ExtCodeValueTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TableId</p></td>
<td><p>ExtCodeRelationTableId</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>ExtCodeRelationRecId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

