---
title: ReleaseUpdateTransformDB40_Vend.purchBookVATOprPreUpgradeProcess_RU Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Vend.purchBookVATOprPreUpgradeProcess_RU Upgrade Script
ms:assetid: 04556872-f153-ff84-d629-aa2e982aafa3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684691(v=AX.60)
ms:contentKeyID: 49706390
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Vend.purchBookVATOprPreUpgradeProcess\_RU Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>purchBookVATOprPreUpgradeProcess_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Update LedgerDimension, DefaultDimensio and OffsetLedgerDimension fields in &lt;c&gt;PurchBookVATProcessLogTransOper_RU&lt;/c&gt; table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>Accounts payable</p></td>
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
<td><p>PurchBookVATProcessLogTransOper_RU</p></td>
</tr>
<tr class="even">
<td><p>Shadow_PurchBookVATProcessLogTransOpr_RU</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

