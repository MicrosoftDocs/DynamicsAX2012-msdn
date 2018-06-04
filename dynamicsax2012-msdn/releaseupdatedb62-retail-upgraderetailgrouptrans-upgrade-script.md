---
title: ReleaseUpdateDB62_Retail.upgradeRetailGroupTrans Upgrade Script
TOCTitle: ReleaseUpdateDB62_Retail.upgradeRetailGroupTrans Upgrade Script
ms:assetid: 2409b415-22c1-01d7-5e39-16a9cc3ffd37
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn702703(v=AX.60)
ms:contentKeyID: 65236159
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_Retail.upgradeRetailGroupTrans Upgrade Script 


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB62_Retail</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>upgradeRetailGroupTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates retail dimension groups in the Product information management module.</p></td>
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
<td><p>Retail</p></td>
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
<td><p>RETAILSIZEGROUPTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILSTYLEGROUPTRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCOLORGROUPTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILSIZEGROUPTRANSTRANSLATION</p></td>
</tr>
<tr class="odd">
<td><p>RETAILSTYLEGROUPTRANSTRANSLATION</p></td>
</tr>
<tr class="even">
<td><p>RETAILCOLORGROUPTRANSTRANSLATION</p></td>
</tr>
</tbody>
</table>


## Remarks

The names of product master dimension values are moved to RetailXxxxGroupTransTranslation to enable translation.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: RetailSizeGroupTrans</p></th>
<th><p>To Table: RetailSizeGroupTransTranslation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Name</p></td>
<td><p>Name</p></td>
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
<th><p>From Table: RetailStyleGroupTrans</p></th>
<th><p>To Table: RetailStyleGroupTransTranslation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Name</p></td>
<td><p>Name</p></td>
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
<th><p>From Table: RetailColorGroupTrans</p></th>
<th><p>To Table: RetailColorGroupTransTranslation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Name</p></td>
<td><p>Name</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

