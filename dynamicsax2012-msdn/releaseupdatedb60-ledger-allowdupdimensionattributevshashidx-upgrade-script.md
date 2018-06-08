---
title: ReleaseUpdateDB60_Ledger.allowDupDimensionAttributeVSHashIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupDimensionAttributeVSHashIdx Upgrade Script
ms:assetid: a48e87f0-ac4a-8348-c096-4c0d52bbb6b9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736786(v=AX.60)
ms:contentKeyID: 49710217
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupDimensionAttributeVSHashIdx Upgrade Script 


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
<td><p>allowDupDimensionAttributeVSHashIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the HashIdx index in the DimensionAttributeValueSet table to allow for duplicate records.</p></td>
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
<td><p>DimensionAttributeValueSet</p></td>
</tr>
</tbody>
</table>


## Remarks

Initially this field contains no value. So the index is set to allow for duplicates before the field is updated with the value of the hash fields in the DimensionAttributeValueSet value.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

