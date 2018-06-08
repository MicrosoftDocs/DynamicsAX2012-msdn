---
title: ReleaseUpdateDB60_Vend.createPurchAgreementHeaderFromBO Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.createPurchAgreementHeaderFromBO Upgrade Script
ms:assetid: 99edd191-d80c-445b-b0bb-0db03e01dc30
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686279(v=AX.60)
ms:contentKeyID: 49709982
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.createPurchAgreementHeaderFromBO Upgrade Script 


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
<td><p>createPurchAgreementHeaderFromBO</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates instances of AgreementHeader, SalesAgreementHeader, AgreementHeaderDefault, and SalesAgreementHeaderDefault entities for the provided blanket order.</p></td>
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
<td><p>AgreementHeader</p></td>
</tr>
<tr class="even">
<td><p>PurchAgreementHeader</p></td>
</tr>
<tr class="odd">
<td><p>AgreementHeaderDefault</p></td>
</tr>
<tr class="even">
<td><p>PurchAgreementHeaderDefault</p></td>
</tr>
</tbody>
</table>


## Remarks

This method is called from the updateBOs2PurchAgreements method.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

