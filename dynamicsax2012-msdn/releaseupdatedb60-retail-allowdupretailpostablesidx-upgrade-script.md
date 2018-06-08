---
title: ReleaseUpdateDB60_Retail.allowDupRetailPosTablesIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Retail.allowDupRetailPosTablesIdx Upgrade Script
ms:assetid: c3d875f9-cf6c-d94a-7e67-7b81990818a0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686853(v=AX.60)
ms:contentKeyID: 49711050
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.allowDupRetailPosTablesIdx Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Retail</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowDupRetailPosTablesIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the LayoutId index in the RetailFormLayout table to allow duplicate records. Updates the profileIdx index in the RetailFunctionalityProfile table to allow duplicate records. Updates the profileIdx index in the RetailHardwareProfile table to allow duplicate records. Updates the PictureIdIdx index in the RetailImages table to allow duplicate records. Updates the keyboardIdx index in the RetailKeyboardMappingTable table to allow duplicate records. Updates the keyboardASCIIValueIdx index in the RetailKeyboardMappingTrans table to allow duplicate records. Updates the profileMapFromIdx index in the RetailKeyMapping table to allow duplicate records. Updates the OperationIdIdx index in the RetailOperations table to allow duplicate records. Updates the Primary index in the RetailReceiptMasks table.</p></td>
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
<td><p>RETAILFORMLAYOUT</p></td>
</tr>
<tr class="even">
<td><p>RETAILFUNCTIONALITYPROFILE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILHARDWAREPROFILE</p></td>
</tr>
<tr class="even">
<td><p>RETAILIMAGES</p></td>
</tr>
<tr class="odd">
<td><p>RETAILKEYBOARDMAPPINGTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILKEYBOARDMAPPINGTRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILKEYMAPPING</p></td>
</tr>
<tr class="even">
<td><p>RETAILOPERATIONS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILRECEIPTMASKS</p></td>
</tr>
<tr class="even">
<td><p>RETAILRECEIPTPROFILE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILRECEIPTPROFILELINE</p></td>
</tr>
<tr class="even">
<td><p>RETAILTILLLAYOUT</p></td>
</tr>
<tr class="odd">
<td><p>RETAILVISUALPROFILE</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

