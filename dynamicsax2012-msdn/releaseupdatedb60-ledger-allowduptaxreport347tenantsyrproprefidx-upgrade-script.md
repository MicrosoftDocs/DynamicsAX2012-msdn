---
title: ReleaseUpdateDB60_Ledger.allowDupTaxReport347TenantsYrPropRefIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxReport347TenantsYrPropRefIdx Upgrade Script
ms:assetid: 0bcf0b0e-0930-b9e4-faf6-3fd87c6ba0bd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735659(v=AX.60)
ms:contentKeyID: 49706570
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxReport347TenantsYrPropRefIdx Upgrade Script 


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
<td><p>allowDupTaxReport347TenantsYrPropRefIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the YrPropRefIdx index in the TaxReport347Tenants table to allow for duplicate records.</p></td>
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
<td><p>TaxReport347Tenants</p></td>
</tr>
</tbody>
</table>


## Remarks

The Year field is replaced with the new TaxReport347Table surrogate key field in the unique YrPropRefIdx index. Initially, this field contains no value. Therefore, the index is set to allow for duplicate values before the field is updated with the value of the RecId field of the TaxReport347Table table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

