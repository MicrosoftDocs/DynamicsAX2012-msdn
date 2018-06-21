---
title: ReleaseUpdateDB60_Cust.updateCreditCardCust Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCreditCardCust Upgrade Script
ms:assetid: 99f9cab8-9308-2249-651e-f48202434782
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686281(v=AX.60)
ms:contentKeyID: 49709984
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCreditCardCust Upgrade Script [AX 2012]


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
<td><p>updateCreditCardCust</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;CreditCardCust&lt;/c&gt; table from the existing &lt;c&gt;CreditCardCustNumber&lt;/c&gt; records.</p></td>
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
<td><p>CreditCardCust</p></td>
</tr>
</tbody>
</table>


## Remarks

The \<c\>CardNumber\</c\> field is set to the last few digits of the \<CreditCardNumber\</c\> field for security purposes. It is 4 or 5 digits depending upon the \<c\>DEL\_CardType\</c\> field value. The \<c\>CardToken\</c\> field is a calculated field based on information from the \<c\>DEL\_CardType\</c\>, \<c\>Name\</c\>, \<c\>CreditCardNumber\</c\> and \<c\>ExpiryDate\</c\> fields.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_CreditCardCustNumber</p></th>
<th><p>To Table: CreditCardCust</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CreditCardNumber</p></td>
<td><p>CardNumber</p></td>
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
<th><p>From Table: CreditCardCust</p></th>
<th><p>To Table: CreditCardCust</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_CardType</p></td>
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
<td><p>DEL_CreditCardCustNumber</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>CreditCardCust</p></td>
<td><p>DEL_CardType</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

