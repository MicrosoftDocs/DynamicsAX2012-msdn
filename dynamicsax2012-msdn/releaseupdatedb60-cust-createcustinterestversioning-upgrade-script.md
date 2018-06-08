---
title: ReleaseUpdateDB60_Cust.createCustInterestVersioning Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.createCustInterestVersioning Upgrade Script
ms:assetid: dfbcb7e4-09d0-b064-7333-ee8f7f8746d0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737258(v=AX.60)
ms:contentKeyID: 49711701
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.createCustInterestVersioning Upgrade Script 


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
<td><p>createCustInterestVersioning</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the CustInterestVersion and CustInterestVersionDetail tables from the CustInterest and CustInterestRate tables.</p></td>
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
<td><p>CustInterestVersion</p></td>
</tr>
<tr class="even">
<td><p>custInterestVersionDetail</p></td>
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
<th><p>From Table: CustInterest</p></th>
<th><p>To Table: CustInterestVersion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>CustInterest</p></td>
</tr>
<tr class="even">
<td><p>DEL_GraceDays</p></td>
<td><p>GraceDays</p></td>
</tr>
<tr class="odd">
<td><p>DEL_InterestCodeFromDate</p></td>
<td><p>ValidFrom</p></td>
</tr>
<tr class="even">
<td><p>DEL_InterestCodeToDate</p></td>
<td><p>ValidTo</p></td>
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
<th><p>From Table: CustInterest</p></th>
<th><p>To Table: CustInterestVersionDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_InvoicePer</p></td>
<td><p>InterestInterval</p></td>
</tr>
<tr class="even">
<td><p>DEL_InvoiceCalculate</p></td>
<td><p>InterestCalculate</p></td>
</tr>
<tr class="odd">
<td><p>DEL_DebitInterestByRange</p></td>
<td><p>InterestByRange</p></td>
</tr>
<tr class="even">
<td><p>DEL_DebitInterestCalcType</p></td>
<td><p>InterestCalcType</p></td>
</tr>
<tr class="odd">
<td><p>DEL_DebitInterestPercent</p></td>
<td><p>InterestPercent</p></td>
</tr>
<tr class="even">
<td><p>DEL_PaymentPer</p></td>
<td><p>InterestInterval</p></td>
</tr>
<tr class="odd">
<td><p>DEL_PaymentCalculate</p></td>
<td><p>InterestCalculate</p></td>
</tr>
<tr class="even">
<td><p>DEL_CreditInterestByRange</p></td>
<td><p>InterestByRange</p></td>
</tr>
<tr class="odd">
<td><p>DEL_CreditInterestCalcType</p></td>
<td><p>InterestCalcType</p></td>
</tr>
<tr class="even">
<td><p>DEL_CreditInterestPercent</p></td>
<td><p>InterestPercent</p></td>
</tr>
<tr class="odd">
<td><p>DEL_AccountDebit</p></td>
<td><p>LedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>DEL_AccountCredit</p></td>
<td><p>LedgerDimension</p></td>
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
<th><p>From Table: CustInterestVersion</p></th>
<th><p>To Table: CustInterestVersionDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>CustInterestVersion</p></td>
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
<td><p>CustInterestVersion</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>CustInterestVersionDetail</p></td>
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
<td><p>DEL_CustInterestRate</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>CustInterest</p></td>
<td><p>DEL_GraceDays</p></td>
</tr>
<tr class="odd">
<td><p>CustInterest</p></td>
<td><p>DEL_InvoicePer</p></td>
</tr>
<tr class="even">
<td><p>CustInterest</p></td>
<td><p>DEL_InvoiceCalculate</p></td>
</tr>
<tr class="odd">
<td><p>CustInterest</p></td>
<td><p>DEL_DebitInterestByRange</p></td>
</tr>
<tr class="even">
<td><p>CustInterest</p></td>
<td><p>DEL_DebitInterestCalcType</p></td>
</tr>
<tr class="odd">
<td><p>CustInterest</p></td>
<td><p>DEL_DebitInterestPercent</p></td>
</tr>
<tr class="even">
<td><p>CustInterest</p></td>
<td><p>DEL_PaymentPer</p></td>
</tr>
<tr class="odd">
<td><p>CustInterest</p></td>
<td><p>DEL_PaymentCalculate</p></td>
</tr>
<tr class="even">
<td><p>CustInterest</p></td>
<td><p>DEL_CreditInterestByRange</p></td>
</tr>
<tr class="odd">
<td><p>CustInterest</p></td>
<td><p>DEL_CreditInterestCalcType</p></td>
</tr>
<tr class="even">
<td><p>CustInterest</p></td>
<td><p>DEL_CreditInterestPercent</p></td>
</tr>
<tr class="odd">
<td><p>CustInterest</p></td>
<td><p>DEL_AccountDebit</p></td>
</tr>
<tr class="even">
<td><p>CustInterest</p></td>
<td><p>DEL_AccountCredit</p></td>
</tr>
<tr class="odd">
<td><p>CustInterest</p></td>
<td><p>DEL_InterestCodeFromDate</p></td>
</tr>
<tr class="even">
<td><p>CustInterest</p></td>
<td><p>DEL_InterestCodeToDate</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

