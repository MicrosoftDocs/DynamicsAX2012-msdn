---
title: ReleaseUpdateDB60_Cust.updateCreditCardTypeSetup Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCreditCardTypeSetup Upgrade Script
ms:assetid: dc18c802-b644-66e7-60b5-3818631e7ab3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737206(v=AX.60)
ms:contentKeyID: 49711649
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCreditCardTypeSetup Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateCreditCardTypeSetup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the &lt;c&gt;CreditCardTypeName&lt;/c&gt; field of the &lt;c&gt;CreditCardTypeSetup&lt;/c&gt; table.</p></td>
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
<td><p>CreditCardTypeSetup</p></td>
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
<th><p>From Table: CreditCardTypeSetup</p></th>
<th><p>To Table: CreditCardTypeSetup</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_CardType</p></td>
<td><p>CreditCardTypeName</p></td>
</tr>
</tbody>
</table>


## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CreditCardTypeSetup</p></td>
<td><p>CreditCardTypeName</p></td>
<td><p>CreditCardTypeName</p></td>
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
<td><p>CreditCardTypeSetup</p></td>
<td><p>DEL_CardType</p></td>
</tr>
</tbody>
</table>

  


