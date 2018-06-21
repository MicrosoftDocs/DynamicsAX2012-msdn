---
title: ReleaseUpdateTransformDB50_Bank.rCashTransPreUpgradeProcess_RU Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Bank.rCashTransPreUpgradeProcess_RU Upgrade Script
ms:assetid: a0d02aa8-9711-f6b5-11d7-83d8f4d3a18b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736712(v=AX.60)
ms:contentKeyID: 49710144
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Bank.rCashTransPreUpgradeProcess\_RU Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Bank</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>rCashTransPreUpgradeProcess_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Update ReportingCurrencyAmount, LedgerDimension, DefaultDimension, OffsetLedgerDimension, OffsetDefaultDimension, OffsetLedgerDimensionNum and OffsetLedgerDimensionNum fields in &lt;c&gt;RCashTrans&lt;/c&gt; table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>Bank</p></td>
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
<td><p>RCashTrans</p></td>
</tr>
<tr class="even">
<td><p>Shadow_RCashTrans</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

