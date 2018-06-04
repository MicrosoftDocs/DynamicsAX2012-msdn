---
title: ReleaseUpdateDB60_Vend.updateBOs2PurchAgreements Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateBOs2PurchAgreements Upgrade Script
ms:assetid: 8fd8bfef-53f6-ea74-6b49-ceda21d63e56
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736552(v=AX.60)
ms:contentKeyID: 49709741
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateBOs2PurchAgreements Upgrade Script 


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
<td><p>updateBOs2PurchAgreements</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the old version of blanket orders to Microsoft Dynamics AX 2012 purchase agreements.</p></td>
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
<td><p>AgreementClassification</p></td>
</tr>
<tr class="even">
<td><p>AgreementHeader</p></td>
</tr>
<tr class="odd">
<td><p>AgreementHeaderDefault</p></td>
</tr>
<tr class="even">
<td><p>AgreementLine</p></td>
</tr>
<tr class="odd">
<td><p>AgreementLineDefault</p></td>
</tr>
<tr class="even">
<td><p>AgreementLineQuantityCommitment</p></td>
</tr>
<tr class="odd">
<td><p>AgreementLineReleasedLine</p></td>
</tr>
<tr class="even">
<td><p>AgreementReleaseHeaderMatch</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
</tr>
<tr class="even">
<td><p>DEL_PurchBlanketOrderUpgrade</p></td>
</tr>
<tr class="odd">
<td><p>HcmWorker</p></td>
</tr>
<tr class="even">
<td><p>PurchAgreementHeader</p></td>
</tr>
<tr class="odd">
<td><p>PurchAgreementHeaderDefault</p></td>
</tr>
<tr class="even">
<td><p>PurchLine</p></td>
</tr>
<tr class="odd">
<td><p>PurchTable</p></td>
</tr>
<tr class="even">
<td><p>PurchTableLinks</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceTrans</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

