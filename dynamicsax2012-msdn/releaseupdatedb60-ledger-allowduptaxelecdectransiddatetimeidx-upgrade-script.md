---
title: ReleaseUpdateDB60_Ledger.allowDupTaxElecDecTransIdDateTimeIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxElecDecTransIdDateTimeIdx Upgrade Script
ms:assetid: 4b3d3398-3fbe-9468-c59f-22af5d761d8b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685389(v=AX.60)
ms:contentKeyID: 49708096
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxElecDecTransIdDateTimeIdx Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowDupTaxElecDecTransIdDateTimeIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the IdDateTimeIdx index in the table TaxElectronicDeclarationTrans table to allow for duplicate records.</p></td>
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
<td><p>TaxElectronicDeclarationTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

The createdDateTime field is added to the unique IdDateTimeIdx index. Initially, this field contains no value. Therefore, the index is set to allow for duplicate values before the field is updated with a proper value for the createdDateTime field.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

