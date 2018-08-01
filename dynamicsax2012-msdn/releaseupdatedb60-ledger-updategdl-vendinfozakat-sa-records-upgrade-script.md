---
title: ReleaseUpdateDB60_Ledger.updateGDL_VendInfoZakat_SA_Records Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_VendInfoZakat_SA_Records Upgrade Script
ms:assetid: 244e6fc4-dcfd-7b64-4e16-e7984855a792
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684988(v=AX.60)
ms:contentKeyID: 49707190
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_VendInfoZakat\_SA\_Records Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateGDL_VendInfoZakat_SA_Records</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records in the VendInfoZakat_SA table with the values of the corresponding records from the VendTable table.</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>VendInfoZakat_SA</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the FileNumber, ServiceType, RegistrationNum, and IsSubcontractor fields in the VendInfoZakat\_SA table with the DEL\_FileNum\_SA, DEL\_ServiceType\_SA, DEL\_OrganizationNum\_SA, and DEL\_SubContractor\_SA fields in the VendTable table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

