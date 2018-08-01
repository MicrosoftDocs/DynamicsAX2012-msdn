---
title: ReleaseUpdateDB62_Vend.updateTax1099FieldsUpdate Upgrade Script
TOCTitle: ReleaseUpdateDB62_Vend.updateTax1099FieldsUpdate Upgrade Script
ms:assetid: 10ff3dde-4fa2-7018-71d1-c32d1dc03619
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn975036(v=AX.60)
ms:contentKeyID: 65236150
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_Vend.updateTax1099FieldsUpdate Upgrade Script 


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB62_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateTax1099FieldsUpdate</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates OID box values from old to new fields for 2013.</p></td>
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
<td><p>Accounts payable</p></td>
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
<td><p>Tax1099Fields</p></td>
</tr>
</tbody>
</table>


## Remarks

This is a minor version upgrade script. The upgrade script modifies the Tax1099Box field. The values 'OID-06', 'OID-07' and 'OID-10' are changed to 'OID-08', 'OID-09' and 'OID-12' respectively.

  


