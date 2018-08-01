---
title: ReleaseUpdateDB60_Ledger.updateServiceTaxInquiryTable_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateServiceTaxInquiryTable_IN Upgrade Script
ms:assetid: b402f87f-081e-6290-ec5a-8fed099fd90e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736948(v=AX.60)
ms:contentKeyID: 49710632
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateServiceTaxInquiryTable\_IN Upgrade Script 


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
<td><p>updateServiceTaxInquiryTable_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ServiceTaxInquiryTable_IN table. The record ID of the TaxRegistrationNumberTable_IN table is stored in place of the STCNumber value. Also the FieldId field is replaced by the new FieldName field.</p></td>
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
<td><p>Ledger</p></td>
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
<td><p>ServiceTaxInquiryTable_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxRegistrationNumberTable_IN</p></td>
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
<th><p>From Table: TaxRegistrationNumberTable_IN</p></th>
<th><p>To Table: ServiceTaxInquiryTable_IN</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>STCTaxRegistrationNumberTable</p></td>
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
<td><p>ServiceTaxInquiryTable_IN</p></td>
<td><p>STCTaxRegistrationNumberTable</p></td>
<td><p>RefRecId</p></td>
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
<td><p>ServiceTaxInquiryTable_IN</p></td>
<td><p>DEL_STCNumber</p></td>
</tr>
</tbody>
</table>

  


