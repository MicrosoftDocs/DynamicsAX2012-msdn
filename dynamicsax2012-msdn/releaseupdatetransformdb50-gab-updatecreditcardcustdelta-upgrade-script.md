---
title: ReleaseUpdateTransformDB50_GAB.updateCreditCardCustDelta Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_GAB.updateCreditCardCustDelta Upgrade Script
ms:assetid: 81a9cc0a-c215-a751-ac74-3f1baa1cd671
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685930(v=AX.60)
ms:contentKeyID: 49709383
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_GAB.updateCreditCardCustDelta Upgrade Script [AX 2012]


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
<td><p>updateCreditCardCustDelta</p></td>
</tr>
<tr class="odd">
<td><p></p>
<p><strong>Description</strong></p></td>
<td><p>Transform the Address field into the Location field in the CreditCardCust table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 2009</p></td>
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

The update is required in order to transform the address data in the Location field in the CreditCardCust table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: Address</p></th>
<th><p>To Table: CreditCardCust</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AddrTableId</p></td>
<td><p>Location</p></td>
</tr>
<tr class="even">
<td><p>AddrRecId</p></td>
<td><p>Location</p></td>
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
<td><p>CreditCardCust</p></td>
<td><p>Location</p></td>
<td><p>LogisticsLocationRecId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

