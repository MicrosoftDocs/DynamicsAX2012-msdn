---
title: ReleaseUpdateDB60_Cust.updateCreditCardProcessors Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCreditCardProcessors Upgrade Script
ms:assetid: e9a6abe2-2e2b-7a19-fdf0-016fb754fd93
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719848(v=AX.60)
ms:contentKeyID: 49711921
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCreditCardProcessors Upgrade Script [AX 2012]


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
<td><p>updateCreditCardProcessors</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records in the CreditCardTypeSetup table and CreditCardTypeCurrency table from the existing CreditCardProcessors records. Deletes the authorize net credit card processor record from the CreditCardProcessors table.</p></td>
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
<td><p>CreditCardProcessors</p></td>
</tr>
<tr class="even">
<td><p>CreditCardTypeSetup</p></td>
</tr>
<tr class="odd">
<td><p>CreditCardTypeCurrency</p></td>
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
<th><p>From Table: CreditCardProcessors</p></th>
<th><p>To Table: CreditCardTypeSetup</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PaymentJournal_AmericanExpress</p></td>
<td><p>PaymentJournal</p></td>
</tr>
<tr class="even">
<td><p>PaymentJournal_Discover</p></td>
<td><p>PaymentJournal</p></td>
</tr>
<tr class="odd">
<td><p>PaymentJournal_MasterCard</p></td>
<td><p>PaymentJournal</p></td>
</tr>
<tr class="even">
<td><p>PaymentJournal_Visa</p></td>
<td><p>PaymentJournal</p></td>
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
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>CreditCardTypeCurrency</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

