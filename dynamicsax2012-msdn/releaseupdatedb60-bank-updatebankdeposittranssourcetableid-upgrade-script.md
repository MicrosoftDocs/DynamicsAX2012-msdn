---
title: ReleaseUpdateDB60_Bank.updateBankDepositTransSourceTableId Upgrade Script
TOCTitle: ReleaseUpdateDB60_Bank.updateBankDepositTransSourceTableId Upgrade Script
ms:assetid: e2e34ab7-2f74-5cc5-0248-b50012b13f71
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737337(v=AX.60)
ms:contentKeyID: 49711778
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Bank.updateBankDepositTransSourceTableId Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Bank</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateBankDepositTransSourceTableId</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the source table ID in the BankAccountTrans field when the source is from the BankDepositDocument table.</p></td>
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
<td><p>Bank</p></td>
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
<td><p>BANKACCOUNTTRANS</p></td>
</tr>
<tr class="even">
<td><p>DEL_SQLDICTIONARY</p></td>
</tr>
<tr class="odd">
<td><p>SQLDICTIONARY</p></td>
</tr>
</tbody>
</table>


## Remarks

The source table ID from source upgrade side is not consistent with tagret side. This method will update it to the valid ID in target side.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

