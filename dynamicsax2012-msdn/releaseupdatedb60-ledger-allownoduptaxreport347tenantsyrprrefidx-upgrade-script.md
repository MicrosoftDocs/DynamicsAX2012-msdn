---
title: ReleaseUpdateDB60_Ledger.allowNoDupTaxReport347TenantsYrPrRefIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupTaxReport347TenantsYrPrRefIdx Upgrade Script
ms:assetid: 697260cd-2cc5-3de9-1e30-0b68ebe6d5fb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685631(v=AX.60)
ms:contentKeyID: 49708833
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupTaxReport347TenantsYrPrRefIdx Upgrade Script [AX 2012]


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
<td><p>allowNoDupTaxReport347TenantsYrPrRefIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the YrPropRefIdx index in the TaxReport347Tenants table not to allow for duplicate records.</p></td>
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

The name of this method is truncated from allowNoDupTaxReport347TenantsYrPropRefIdx to allowNoDupTaxReport347TenantsYrPrRefIdx. After updating the TaxReport347Table surrogate key field with the value of the RecId field of the TaxReport347Table table, the YrPropRefIdx index is reset not to allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

