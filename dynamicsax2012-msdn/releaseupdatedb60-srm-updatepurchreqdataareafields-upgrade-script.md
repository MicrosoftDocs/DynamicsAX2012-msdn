---
title: ReleaseUpdateDB60_Srm.updatePurchReqDataAreaFields Upgrade Script
TOCTitle: ReleaseUpdateDB60_Srm.updatePurchReqDataAreaFields Upgrade Script
ms:assetid: a9c4a43c-302a-a092-8a76-bb89ef445945
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686438(v=AX.60)
ms:contentKeyID: 49710394
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Srm.updatePurchReqDataAreaFields Upgrade Script 


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
<td><p>updatePurchReqDataAreaFields</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Initializes the values of the DataArea field.</p></td>
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
<td><p>PurchReqTable</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
</tr>
</tbody>
</table>


## Remarks

The SaveDataPerCompany property of the PurchReqTable table and the PurchReqLine table has been set to "No" in this release. Various DataArea fields such as the AssetGroupDataArea field have been introduced to create a composite relation with organization specific tables. This method initializes values of these fields.

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
<td><p>PurchReqTable</p></td>
<td><p>ProjIdDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>AssetGroupDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqLine</p></td>
<td><p>InventDimIdDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>InventLocationIdDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqLine</p></td>
<td><p>ProductGroupIdDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>ItemIdDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqLine</p></td>
<td><p>ProjCategoryDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>ProjTransIdDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqLine</p></td>
<td><p>ProjLinePropertyDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>ProjIdDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqLine</p></td>
<td><p>ProjTaxGroupIdDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>ProjTaxItemGroupIdDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqLine</p></td>
<td><p>PurchRFQCaseIdDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>PurchIdDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqLine</p></td>
<td><p>ActivityNumberDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>TaxGroupDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqLine</p></td>
<td><p>VendAccountDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>TaxItemGroupDataArea</p></td>
<td><p>DataAreaId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

