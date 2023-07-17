---
title: ReleaseUpdateDB60_Ledger.updateMainAccountSeparateBalance Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateMainAccountSeparateBalance Upgrade Script
ms:assetid: 3b770551-df47-fb53-f5a7-5c693e240468
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685282(v=AX.60)
ms:contentKeyID: 49707734
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateMainAccountSeparateBalance Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateMainAccountSeparateBalance</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>The method populates the MainAccountSeparateBalance table from the LedgerTable table so the country/region specific value is stored in a separate table.</p></td>
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
<td><p>MainAccountSeparateBalance</p></td>
</tr>
</tbody>
</table>


## Remarks

The LedgerTable table populates the MainAccount table. The MainAccount table does not store country/region specific fields.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerTable</p></th>
<th><p>To Table: MainAccountSeparateBalance</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DetBalance_PL</p></td>
<td><p>IsSeparateBalanceMainAccount</p></td>
</tr>
</tbody>
</table>

  


