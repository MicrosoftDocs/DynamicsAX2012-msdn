---
title: ReleaseUpdateTransformDB50_Basic.updatePartyElectronicAddrPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Basic.updatePartyElectronicAddrPreProcessing Upgrade Script
ms:assetid: 76c97c19-9107-0ebb-a54b-bd8173ad4e6f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719343(v=AX.60)
ms:contentKeyID: 49709134
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Basic.updatePartyElectronicAddrPreProcessing Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePartyElectronicAddrPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data in the DirPartyECommunicationRelationship table into the new logistics address model for Microsoft Dynamics AX 2012.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
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
<td><p>DirPartyECommunicationRelationship</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to update the DirPartyECommunicationRelationship table. The electronic address associated to the party will be upgraded into the new logistics address model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DirECommunicationAddress</p></th>
<th><p>To Table: LogisticsElectronicDirPartyECommunicatio</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Phone</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>PhoneLocal</p></td>
<td><p>LocatorExtension</p></td>
</tr>
<tr class="odd">
<td><p>TeleFax</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>Telex</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="odd">
<td><p>URL</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>CellularPhone</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="odd">
<td><p>Email</p></td>
<td><p>Locator</p></td>
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
<td><p>LogisticsElectronicAddress</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DirPartyLocation</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>LogisticsLocation</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirECommunicationAddress</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>DirPartyECommunicationRelationship</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

