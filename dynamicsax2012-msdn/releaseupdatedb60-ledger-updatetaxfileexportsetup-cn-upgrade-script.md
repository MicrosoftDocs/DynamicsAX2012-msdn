---
title: ReleaseUpdateDB60_Ledger.updateTaxFileExportSetup_CN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateTaxFileExportSetup_CN Upgrade Script
ms:assetid: cc0ec9e1-ab66-adbd-aaae-dfc5360632d3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719685(v=AX.60)
ms:contentKeyID: 49711251
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateTaxFileExportSetup\_CN Upgrade Script [AX 2012]


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
<td><p>updateTaxFileExportSetup_CN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies records from the DEL_TaxSetupField_CN table to the TaxFileExportSetup_CN, and updates the TaxProfileTable_CN field in the TaxDataMappingTable_CN and TaxDataRulesTable_CN tables.</p></td>
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
<td><p>Ledger</p></td>
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
<td><p>TaxFileExportSetup_CN</p></td>
</tr>
<tr class="even">
<td><p>TaxDataMappingTable_CN</p></td>
</tr>
<tr class="odd">
<td><p>TaxDataRulesTable_CN</p></td>
</tr>
<tr class="even">
<td><p>DEL_TaxSetupField_CN</p></td>
</tr>
<tr class="odd">
<td><p>TaxProfileTable_CN</p></td>
</tr>
<tr class="even">
<td><p>TaxSetupTable_CN</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

