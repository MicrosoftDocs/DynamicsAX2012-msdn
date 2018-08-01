---
title: ReleaseUpdateDB60_Ledger.updateLedgerTableMandatoryPaymRef_IS Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerTableMandatoryPaymRef_IS Upgrade Script
ms:assetid: c4f549b8-8d4b-f54d-be49-7e098ec6eaa0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686872(v=AX.60)
ms:contentKeyID: 49711069
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerTableMandatoryPaymRef\_IS Upgrade Script 


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
<td><p>updateLedgerTableMandatoryPaymRef_IS</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the LedgerTable.MandatoryPaymReference field.</p></td>
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
<td><p>MainAccount</p></td>
</tr>
</tbody>
</table>


## Remarks

This script is required while you are upgrading from Microsoft Dynamics AX 4.0

with GLS\_IS layer installed, because the pre-processing upgrade script for the source environment only handles fields from SYS layer.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_LedgerTable</p></th>
<th><p>To Table: MainAccount</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>MandatoryPaymReference</p></td>
<td><p>MandatoryPaymentReference</p></td>
</tr>
</tbody>
</table>

  


