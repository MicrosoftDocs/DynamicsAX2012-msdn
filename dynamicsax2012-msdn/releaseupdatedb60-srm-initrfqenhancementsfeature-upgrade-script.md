---
title: ReleaseUpdateDB60_Srm.initRFQEnhancementsFeature Upgrade Script
TOCTitle: ReleaseUpdateDB60_Srm.initRFQEnhancementsFeature Upgrade Script
ms:assetid: 9190510e-50a3-a2ad-67a2-9c7285ea78ee
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736589(v=AX.60)
ms:contentKeyID: 49709779
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Srm.initRFQEnhancementsFeature Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Srm</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>initRFQEnhancementsFeature</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Introduces and initializes new fields to the RFQ tables to uptake the new Blanket Order framework and procurement categories.</p></td>
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
<td><p>SRM</p></td>
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
<td><p>PurchRFQCaseLine</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQCaseTable</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQLine</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQTable</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQReplyLine</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQReplyTable</p></td>
</tr>
<tr class="odd">
<td><p>VendRFQJour</p></td>
</tr>
<tr class="even">
<td><p>VendRFQTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

The new script adds a small number of fields to the RFQ tables and initializes them appropriately. These data upgrades are needed by the RFQ Enhancements feature in M2. The resulting data upgrade class is now attribute-based. The details of the upgrades will be published in the corresponding design document.

## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PurchRFQCaseTable</p></td>
<td><p>ResponsibleEmployeeId</p></td>
<td><p>ResponsibleEmplId</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQCaseTable</p></td>
<td><p>ValidityDateStart</p></td>
<td><p>ValidFromDate</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQCaseTable</p></td>
<td><p>ValidityDateEnd</p></td>
<td><p>ValidToDate</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQTable</p></td>
<td><p>ResponsibleEmployeeId</p></td>
<td><p>ResponsibleEmplId</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQTable</p></td>
<td><p>ValidityDateStart</p></td>
<td><p>ValidFromDate</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQTable</p></td>
<td><p>ValidityDateEnd</p></td>
<td><p>ValidToDate</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQTable</p></td>
<td><p>BlanketId</p></td>
<td><p>PurchBlanketOrderId</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQReplyTable</p></td>
<td><p>ValidityDateStart</p></td>
<td><p>ValidFromDate</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQReplyTable</p></td>
<td><p>ValidityDateEnd</p></td>
<td><p>ValidToDate</p></td>
</tr>
<tr class="even">
<td><p>VendRFQJour</p></td>
<td><p>ResponsibleEmployeeId</p></td>
<td><p>ResponsibleEmplId</p></td>
</tr>
<tr class="odd">
<td><p>VendRFQJour</p></td>
<td><p>ValidityDateStart</p></td>
<td><p>ValidFromDate</p></td>
</tr>
<tr class="even">
<td><p>VendRFQJour</p></td>
<td><p>ValidityDateEnd</p></td>
<td><p>ValidToDate</p></td>
</tr>
<tr class="odd">
<td><p>VendRFQJour</p></td>
<td><p>BlanketId</p></td>
<td><p>PurchBlanketOrderId</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQCaseLine</p></td>
<td><p>CategoryId</p></td>
<td><p>PurchCategory</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQLine</p></td>
<td><p>CategoryId</p></td>
<td><p>PurchCategory</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQLine</p></td>
<td><p>BlanketId</p></td>
<td><p>PurchBlanketOrderId</p></td>
</tr>
<tr class="odd">
<td><p>VendRFQTrans</p></td>
<td><p>CategoryId</p></td>
<td><p>PurchCategory</p></td>
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
<td><p>PurchRFQTable</p></td>
<td><p>VendPriceGroupId</p></td>
</tr>
<tr class="even">
<td><p>VendRFQJour</p></td>
<td><p>RFQDocNum</p></td>
</tr>
<tr class="odd">
<td><p>VendRFQJour</p></td>
<td><p>VendPriceGroupId</p></td>
</tr>
</tbody>
</table>

  


