﻿---
title: ReleaseUpdateDB60_Proj.updateCreditInvoicingTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateCreditInvoicingTable Upgrade Script
ms:assetid: 7c4749d1-705b-649e-cae5-14b7603a5fd9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719461(v=AX.60)
ms:contentKeyID: 49709251
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateCreditInvoicingTable Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Proj</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCreditInvoicingTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the CustVendCreditInvoicingTable table to reflect changes in supporting multiple transaction sales amount.</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>CustVendCreditInvoicingTable</p></td>
</tr>
</tbody>
</table>


## Remarks

A project transaction can now support multiple sales amount. For example, a project transaction can be billed to multiple customers. To support multiple sales amounts, another level of tables were created, such as the ProjInvoiceEmplDetail table, which is related to the existing ProjInvoiceEmpl table. The RefTableId and RefRecId fields of the CustVendCreditInvoicingTable table will then be updated to reference the new tables.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

