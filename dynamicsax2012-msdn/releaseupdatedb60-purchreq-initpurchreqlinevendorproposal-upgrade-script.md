---
title: ReleaseUpdateDB60_PurchReq.initPurchReqLineVendorProposal Upgrade Script
TOCTitle: ReleaseUpdateDB60_PurchReq.initPurchReqLineVendorProposal Upgrade Script
ms:assetid: 20ab0219-5254-bab2-04f0-7343bfe729b5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684900(v=AX.60)
ms:contentKeyID: 49707102
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_PurchReq.initPurchReqLineVendorProposal Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_PurchReq</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>initPurchReqLineVendorProposal</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the proposed vendors. Copies the contents of the note that represents the proposed vendor into the PurchReqLineVendorProposal.Notes field. Copies an Upgrade string into both the Name and Contact Information fields. Deletes the attached note from the DocuRef table.</p></td>
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
<td><p>SRM</p></td>
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
<td><p>PurchReqLineVendorProposal</p></td>
</tr>
<tr class="even">
<td><p>DocuRef</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DocuRef</p></th>
<th><p>To Table: PurchReqLineVendorProposal</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Notes</p></td>
<td><p>Notes</p></td>
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
<td><p>PurchReqLineVendorProposal</p></td>
<td><p>Notes</p></td>
<td><p>PurchReqProposedVendor</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

