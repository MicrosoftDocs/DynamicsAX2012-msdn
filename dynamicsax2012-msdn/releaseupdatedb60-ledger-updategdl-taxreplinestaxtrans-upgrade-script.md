---
title: ReleaseUpdateDB60_Ledger.updateGDL_TaxRepLinesTaxTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_TaxRepLinesTaxTrans Upgrade Script
ms:assetid: 39ebd7a5-af45-c4ab-f4aa-cdfc7a9263a5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685248(v=AX.60)
ms:contentKeyID: 49707700
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_TaxRepLinesTaxTrans Upgrade Script 


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
<td><p>updateGDL_TaxRepLinesTaxTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the TaxReportLinesTaxTrans table that was introduced to establish a many-to-many relationship between the TaxReportLines table and the TaxTrans table.</p></td>
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
<td><p>TaxReportLines</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
</tr>
<tr class="odd">
<td><p>TaxReportLinesTaxTrans_ES</p></td>
</tr>
</tbody>
</table>


## Remarks

The TaxReportLinesTaxTrans table can be populated by using the existing one-to-many relationship between the TaxReportLines and TaxTrans table.

  


