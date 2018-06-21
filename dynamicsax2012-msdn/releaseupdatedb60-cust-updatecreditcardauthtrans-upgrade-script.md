---
title: ReleaseUpdateDB60_Cust.UpdateCreditCardAuthTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.UpdateCreditCardAuthTrans Upgrade Script
ms:assetid: b49375f2-155d-209e-1792-a2290db51af2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736977(v=AX.60)
ms:contentKeyID: 49710662
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.UpdateCreditCardAuthTrans Upgrade Script [AX 2012]


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
<td><p>UpdateCreditCardAuthTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the &lt;c&gt;CardToken&lt;/c&gt; field of the &lt;c&gt;CreditCardAuthTrans&lt;/c&gt; table with the value from the &lt;c&gt;CardToken&lt;/c&gt; field of the related &lt;c&gt;CreditCardCust&lt;/c&gt; table.</p></td>
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
<td><p>CreditCardAuthTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

The \<c\>CardTokenResult\</c\> field is calculated using the values from the \<c\>ApprovalType\</c\> \<c\>DEL\_AuthorizeNetTransId\</c\> and \<c\>DEL\_SecureCardData\</c\> fields.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CreditCardCust</p></th>
<th><p>To Table: CreditCardAuthTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CardNumber</p></td>
<td><p>CreditCardNumber</p></td>
</tr>
<tr class="even">
<td><p>CreditCardTypeName</p></td>
<td><p>CreditCardTypeName</p></td>
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
<th><p>To Table: CreditCardAuthTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>CreditCardProcessors</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

