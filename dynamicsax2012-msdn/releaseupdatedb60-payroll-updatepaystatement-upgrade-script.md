---
title: ReleaseUpdateDB60_Payroll.updatePayStatement Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayStatement Upgrade Script
ms:assetid: 6e96d1e0-a9d2-3ad9-e5ab-dc15dcb8be94
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685749(v=AX.60)
ms:contentKeyID: 49708950
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayStatement Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Payroll</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePayStatement</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the PayrollPayStatement table from the PrlEmployeePayElementsTransPosted table.</p></td>
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
<td><p>Payroll</p></td>
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
<td><p>PayrollPayStatement</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will create records in the PayrollPayStatement table from the PrlEmployeePayElementsTransPosted table records that are posted and paid. Create required document numbers based on the number sequence.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

