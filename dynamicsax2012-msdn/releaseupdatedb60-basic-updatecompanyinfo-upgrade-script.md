---
title: ReleaseUpdateDB60_Basic.updateCompanyInfo Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateCompanyInfo Upgrade Script
ms:assetid: 4a3f4e04-7307-e9d9-5cdd-561ce54f4766
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685371(v=AX.60)
ms:contentKeyID: 49708070
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateCompanyInfo Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCompanyInfo</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This routine ensures that the CompanyInfo table has records corresponding to every record in the DataArea field.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>CompanyInfo</p></td>
</tr>
</tbody>
</table>


## Remarks

For every record in the data area table - this routine checks to see if a record with the same value for the DataArea field exists in the CompanyInfo table. If it doesn't this routine adds it.

  


