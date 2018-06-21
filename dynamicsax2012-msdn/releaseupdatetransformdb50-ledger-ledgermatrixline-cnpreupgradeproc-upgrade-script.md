---
title: ReleaseUpdateTransformDB50_Ledger.ledgerMatrixLine_CNPreUpgradeProc Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Ledger.ledgerMatrixLine_CNPreUpgradeProc Upgrade Script
ms:assetid: 3d22f154-7f9d-a602-a112-13e10bee4ccc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685317(v=AX.60)
ms:contentKeyID: 49707769
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Ledger.ledgerMatrixLine\_CNPreUpgradeProc Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>ledgerMatrixLine_CNPreUpgradeProc</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the &lt;c&gt;MainAccountId&lt;/c&gt; field from the &lt;c&gt;MainAccount&lt;/c&gt; table to the &lt;c&gt;MainAccountNum&lt;/c&gt; field in the &lt;c&gt;LedgerMatrixLine_CN&lt;/c&gt; table.</p></td>
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
<td><p>Shadow_LedgerMatrixLine_CN</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

