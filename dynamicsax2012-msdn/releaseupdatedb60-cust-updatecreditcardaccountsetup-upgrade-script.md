---
title: ReleaseUpdateDB60_Cust.updateCreditCardAccountSetup Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCreditCardAccountSetup Upgrade Script
ms:assetid: 586b90fc-112b-e4b2-1c13-641c00857364
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736255(v=AX.60)
ms:contentKeyID: 49708430
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCreditCardAccountSetup Upgrade Script 


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
<td><p>updateCreditCardAccountSetup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;CreditCardAccountSetup&lt;/c&gt; table from the existing &lt;c&gt;CreditCardMicrosoftSetup&lt;/c&gt; records.</p></td>
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
<td><p>CreditCardAccountSetup</p></td>
</tr>
</tbody>
</table>


## Remarks

The \<c\>ConnectorProperties\</c\> field is calculated from information provided by the user.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_CreditCardMicrosoftSetup</p></th>
<th><p>To Table: CreditCardAccountSetup</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AddressVerification</p></td>
<td><p>AddressVerification</p></td>
</tr>
<tr class="even">
<td><p>AddressVerificationLevel</p></td>
<td><p>AddressVerificationLevel</p></td>
</tr>
<tr class="odd">
<td><p>AddressVerificationVoidUnknown</p></td>
<td><p>AddressVerificationVoidUnknown</p></td>
</tr>
<tr class="even">
<td><p>CardVerificationCheck</p></td>
<td><p>CardVerificationCheck</p></td>
</tr>
<tr class="odd">
<td><p>CardVerificationCheckAllowBlank</p></td>
<td><p>CardVerificationCheckAllowBlank</p></td>
</tr>
<tr class="even">
<td><p>Name</p></td>
<td><p>ConnectorName</p></td>
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
<th><p>From Table: CreditCardProcessors</p></th>
<th><p>To Table: CreditCardAccountSetup</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>CreditCardProcessors</p></td>
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
<td><p>CreditCardAccountSetup</p></td>
<td><p></p></td>
<td><p></p></td>
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
<td><p>DEL_CreditCardMicrosoftSetup</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

