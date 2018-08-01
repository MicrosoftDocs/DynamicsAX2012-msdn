---
title: ReleaseUpdateTransformDB50_GAB.updateBankCodaAccountStatementLines Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_GAB.updateBankCodaAccountStatementLines Upgrade Script
ms:assetid: b63fbf66-b6d5-0de0-3cd5-7314f8966e16
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737026(v=AX.60)
ms:contentKeyID: 49710708
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_GAB.updateBankCodaAccountStatementLines Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_GAB</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateBankCodaAccountStatementLines</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This script is used for updating the address related data in the BankCodaAccountStatementLines table with the new Global Address Book data model.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p>
<p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>CRM</p></td>
</tr>
<tr class="even">
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
<td><p>BankCodaAccountStatementLines</p></td>
</tr>
<tr class="even">
<td><p>LogisticsPostalAddress</p></td>
</tr>
</tbody>
</table>


## Remarks

The script creates new LogisticsPostalAddress records and assigns the appropriate references to the BankCodaAccountStatementLines table.

  


