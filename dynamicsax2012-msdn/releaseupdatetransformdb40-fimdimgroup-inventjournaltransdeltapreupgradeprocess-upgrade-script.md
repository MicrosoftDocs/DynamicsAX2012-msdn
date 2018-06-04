---
title: ReleaseUpdateTransformDB40_FimDimGroup.inventJournalTransDeltaPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_FimDimGroup.inventJournalTransDeltaPreUpgradeProcess Upgrade Script
ms:assetid: 38b5bb60-44a0-d82b-4dc3-170c1813dda2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685215(v=AX.60)
ms:contentKeyID: 49707669
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_FimDimGroup.inventJournalTransDeltaPreUpgradeProcess Upgrade Script 


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
<td><p>inventJournalTransDeltaPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the &lt;c&gt;ServiceTariff_Id_PL&lt;/c&gt; field in the &lt;c&gt;InventJournalTrans&lt;/c&gt; table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
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

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

