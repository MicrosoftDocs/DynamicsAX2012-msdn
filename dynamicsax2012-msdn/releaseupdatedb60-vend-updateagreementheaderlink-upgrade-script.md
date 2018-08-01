---
title: ReleaseUpdateDB60_Vend.updateAgreementHeaderLink Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateAgreementHeaderLink Upgrade Script
ms:assetid: e06bb3f3-af55-696e-4cd9-d38413ee76c3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737270(v=AX.60)
ms:contentKeyID: 49711712
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateAgreementHeaderLink Upgrade Script [AX 2012]


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
<td><p>updateAgreementHeaderLink</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades intercompany links for blanket order headers and blanket order lines to agreement headers and agreement lines.</p></td>
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
<tr class="even">
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
<td><p>AgreementReference</p></td>
</tr>
<tr class="even">
<td><p>AgreementLineReference</p></td>
</tr>
<tr class="odd">
<td><p>DEL_BlanketOrderHeaderUpgrade</p></td>
</tr>
<tr class="even">
<td><p>DEL_PurchBlanketOrderLineUpgrade</p></td>
</tr>
<tr class="odd">
<td><p>DEL_SalesBlanketOrderLineUpgrade</p></td>
</tr>
<tr class="even">
<td><p>SalesAgreementHeader</p></td>
</tr>
<tr class="odd">
<td><p>PurchAgreementHeader</p></td>
</tr>
<tr class="even">
<td><p>AgreementLineQuantityCommitment</p></td>
</tr>
</tbody>
</table>


## Remarks

Upgrade job.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PurchAgreementHeader</p></th>
<th><p>To Table: AgreementReference</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>SourceAgreement</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>DerivedAgreement</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: SalesAgreementHeader</p></th>
<th><p>To Table: AgreementReference</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>SourceAgreement</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>DerivedAgreement</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: AgreementLineQuantityCommitment</p></th>
<th><p>To Table: AgreementLineReference</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>SourceAgreementLine</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>DerivedAgreementLine</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

