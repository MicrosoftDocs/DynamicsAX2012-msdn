---
title: ReleaseUpdateDB60_Vend.createNewAgreementLineQuantityCommitment Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.createNewAgreementLineQuantityCommitment Upgrade Script
ms:assetid: 28952282-6867-7dca-b9ad-047e65a7a79b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735878(v=AX.60)
ms:contentKeyID: 49707296
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.createNewAgreementLineQuantityCommitment Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Vend</p></td>
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

This method is called from the updateBOs2PurchAgreements method.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

