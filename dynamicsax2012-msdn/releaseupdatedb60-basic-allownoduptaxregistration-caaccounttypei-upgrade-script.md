---
title: ReleaseUpdateDB60_Basic.allowNoDupTaxRegistration_CAAccountTypeI Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowNoDupTaxRegistration_CAAccountTypeI Upgrade Script
ms:assetid: d490858f-4cef-877f-d0ee-3d912f4f40c0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687001(v=AX.60)
ms:contentKeyID: 49711449
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowNoDupTaxRegistration\_CAAccountTypeI Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupTaxRegistration_CAAccountTypeI</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the AccountTypeIdx index in the TaxRegistration_CA table not to allow duplicate records.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>TaxRegistration_CA</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the CompanyInfo surrogate key field with the value of the RecId field of the CompanyInfo table, the AccountTypeIdx index is reset not to allow duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

