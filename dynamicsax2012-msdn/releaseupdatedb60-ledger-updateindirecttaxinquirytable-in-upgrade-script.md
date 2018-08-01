---
title: ReleaseUpdateDB60_Ledger.updateIndirectTaxInquiryTable_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateIndirectTaxInquiryTable_IN Upgrade Script
ms:assetid: 16abfd59-764e-06dc-9da1-df996c7e34ec
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718561(v=AX.60)
ms:contentKeyID: 49706847
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateIndirectTaxInquiryTable\_IN Upgrade Script 


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
<td><p>updateIndirectTaxInquiryTable_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the value for the FieldName field in the IndirectTaxInquiryTable_IN table.</p></td>
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
<td><p>IndirectTaxInquiryTable_IN</p></td>
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
<th><p>From Table: IndirectTaxInquiryTable_IN</p></th>
<th><p>To Table: IndirectTaxInquiryTable_IN</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_FieldId</p></td>
<td><p>FieldName</p></td>
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
<td><p>IndirectTaxInquiryTable_IN</p></td>
<td><p>FieldName</p></td>
<td><p>String</p></td>
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
<td><p>IndirectTaxInquiryTable_IN</p></td>
<td><p>DEL_FieldId</p></td>
</tr>
</tbody>
</table>

  


