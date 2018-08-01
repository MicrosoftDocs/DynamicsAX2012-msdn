---
title: ReleaseUpdateDB60_Cust.createNewAgreementLineQuantityCommitment Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.createNewAgreementLineQuantityCommitment Upgrade Script
ms:assetid: 7cb4235d-da6f-6a06-ec9d-874e5ace91ee
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719469(v=AX.60)
ms:contentKeyID: 49709259
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.createNewAgreementLineQuantityCommitment Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>createNewAgreementLineQuantityCommitment</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates new AgreementLineQuantityCommitment, AgreementLine, and AgreementLineDefault entities for the old BO line.</p></td>
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
<td><p>Accounts receivable</p></td>
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
<td><p>AgreementLineQuantityCommitment</p></td>
</tr>
<tr class="even">
<td><p>AgreementLine</p></td>
</tr>
<tr class="odd">
<td><p>AgreementLineDefault</p></td>
</tr>
</tbody>
</table>


## Remarks

Called from the updateBOs2SalesAgreements method.

  


