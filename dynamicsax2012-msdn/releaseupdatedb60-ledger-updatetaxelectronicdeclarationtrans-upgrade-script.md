---
title: ReleaseUpdateDB60_Ledger.updateTaxElectronicDeclarationTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateTaxElectronicDeclarationTrans Upgrade Script
ms:assetid: 7a590315-2c79-a315-4e40-6793aa7a9dc8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719412(v=AX.60)
ms:contentKeyID: 49709203
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateTaxElectronicDeclarationTrans Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateTaxElectronicDeclarationTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the time and date information for the TaxElectronicDeclarationTrans table.</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>TaxElectronicDeclarationTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

The transDate and transTime fields in the TaxElectronicDeclarationTrans table have been deleted and the createdDateTime field now stores these values.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

