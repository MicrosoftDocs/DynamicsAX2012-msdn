---
title: ReleaseUpdateTransformDB40_Basic.updateParty_DocuRef Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Basic.updateParty_DocuRef Upgrade Script
ms:assetid: 3bea3f44-233a-b5a0-6115-438e381c8b08
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685297(v=AX.60)
ms:contentKeyID: 49707756
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Basic.updateParty\_DocuRef Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateParty_DocuRef</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the DocuRef table into the DirPartyTable table and the new logistics address model for Microsoft Dynamics AX 2012.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>CRM</p></td>
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
<td><p>DocuRef</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to update the DocuRef table. The party will be kept as a reference to the DirPartyTable record. The addresses associated to the party will be upgrade into the new logistics address model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DocuRef</p></th>
<th><p>To Table: DirPartyTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CompetitorId</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>CompetitorId</p></td>
<td><p>NameAlias</p></td>
</tr>
</tbody>
</table>


## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DocuRef</p></td>
<td><p>Party</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DirPartyTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>DirOrganization</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DirOrganizationName</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


