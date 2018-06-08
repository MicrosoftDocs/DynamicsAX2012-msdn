---
title: ReleaseUpdateDB60_Payroll.updatePrlPayrollParameters Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePrlPayrollParameters Upgrade Script
ms:assetid: 0477775a-54e8-f39a-bb04-06a41433a68c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684697(v=AX.60)
ms:contentKeyID: 49706385
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePrlPayrollParameters Upgrade Script 


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
<td><p>updatePrlPayrollParameters</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the vendor account number in the PRLPayrollParameters table.</p></td>
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
<td><p>PRLPayrollParameters</p></td>
</tr>
<tr class="even">
<td><p>PrlPostingSetupDetails</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the vendor account number in the PRLPayrollParameters table from the PrlPostingSetupDetails table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PrlPostingSetupDetails</p></th>
<th><p>To Table: PRLPayrollParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_AccountNum</p></td>
<td><p>VendAccountNum</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

