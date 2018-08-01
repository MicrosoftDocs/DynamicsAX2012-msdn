---
title: ReleaseUpdateTransformDB40_Invent.InventSettlementDeltaPreUpgradeProcess
TOCTitle: ReleaseUpdateTransformDB40_Invent.InventSettlementDeltaPreUpgradeProcess
ms:assetid: 08f3ce56-473b-dddc-41fd-17c2386f3917
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684797(v=AX.60)
ms:contentKeyID: 49706492
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Invent.InventSettlementDeltaPreUpgradeProcess 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Invent</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>InventSettlementDeltaPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates &lt;c&gt;Dimension&lt;/c&gt;, &lt;c&gt;OperationsAccount&lt;/c&gt;, &lt;c&gt;BalanceSheetAccount&lt;/c&gt; fields of &lt;c&gt;InventSettlement&lt;/c&gt; table to the &lt;c&gt;defaultDimension&lt;/c&gt;, &lt;c&gt;OperationsLedgerDimension&lt;/c&gt;, &lt;c&gt;BalanceSheetLedgerDimension&lt;/c&gt; field of &lt;c&gt;Shadow_InventSettlement&lt;/c&gt; table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Pre-processing60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>4.01</p></td>
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
<td><p>Inventory management</p></td>
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
<td><p>InventSettlement</p></td>
</tr>
</tbody>
</table>

  


