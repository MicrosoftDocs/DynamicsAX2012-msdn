---
title: ReleaseUpdateTransformDB40_FimDimGroup.inventJournalTransPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_FimDimGroup.inventJournalTransPreUpgradeProcess Upgrade Script
ms:assetid: a81863e1-450e-13c5-f372-3196ac1ab381
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686383(v=AX.60)
ms:contentKeyID: 49710340
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_FimDimGroup.inventJournalTransPreUpgradeProcess Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_FimDimGroup</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>inventJournalTransPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the &lt;c&gt;ServiceTariff_Id_PL&lt;/c&gt; field in the &lt;c&gt;SalesLine&lt;/c&gt; table.</p></td>
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
<td><p>InventJournalTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

The field service tariff id field is deleted from the \<c\>InventJournalTrans\</c\> table in 6.2. A reference to the \<c\>InventJournalTrans\</c\> record and corresponding \<c\>ServiceTariffNumber\_PL\</c\> is added in the new table \<c\>TaxServiceTariff\</c\>.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: InventJournalTrans</p></th>
<th><p>To Table: TaxServiceTariff</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>ParentRecId</p></td>
</tr>
<tr class="even">
<td><p>TableId</p></td>
<td><p>ParentTableId</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table:</p></th>
<th><p>To Table:</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>InventJournalTrans</p></td>
<td><p>ServiceTariffId_PL</p></td>
</tr>
</tbody>
</table>

  


