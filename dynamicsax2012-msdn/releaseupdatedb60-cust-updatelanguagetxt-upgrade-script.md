---
title: ReleaseUpdateDB60_Cust.updateLanguageTxt Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateLanguageTxt Upgrade Script
ms:assetid: ee2067da-7e82-3bc1-31d7-0b54ea0c62d2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719961(v=AX.60)
ms:contentKeyID: 49712033
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateLanguageTxt Upgrade Script 


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
<td><p>updateLanguageTxt</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts or updates records into the LanguageTxt table from the existing LanguageTxt, CustInterestFee and CustInterestVersion records.</p></td>
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
<td><p>LanguageTxt</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CustInterestVersion</p></th>
<th><p>To Table: LanguageTxt</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TableId</p></td>
<td><p>TxtTableId</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>TxtRecId</p></td>
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
<th><p>From Table: CustInterestFee</p></th>
<th><p>To Table: LanguageTxt</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TableId</p></td>
<td><p>TxtTableId</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>TxtRecId</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustInterestFee</p></td>
<td><p>DEL_InterestCode</p></td>
</tr>
<tr class="even">
<td><p>CustInterestFee</p></td>
<td><p>DEL_FeeType</p></td>
</tr>
</tbody>
</table>

  


