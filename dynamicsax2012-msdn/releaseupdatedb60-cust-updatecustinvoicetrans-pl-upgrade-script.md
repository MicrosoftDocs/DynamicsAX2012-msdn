---
title: ReleaseUpdateDB60_Cust.updateCustInvoiceTrans_PL Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCustInvoiceTrans_PL Upgrade Script
ms:assetid: ead2effc-df8d-630e-eea8-e5a03f724821
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719903(v=AX.60)
ms:contentKeyID: 49711975
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCustInvoiceTrans\_PL Upgrade Script [AX 2012]


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
<td><p>updateCustInvoiceTrans_PL</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates the DEL_CorrectionDesc_PL field of the CustInvoiceTrans table to the ReasonRefRecId field.</p></td>
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
<td><p>CustInvoiceTrans</p></td>
</tr>
<tr class="even">
<td><p>ReasonTableRef</p></td>
</tr>
</tbody>
</table>


## Remarks

The CustInvoiceTrans table used to hold the textual string in the old fields in AX5. The new data model is a field that now holds a surrogate foreign key reference to the ReasonTableRef table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CustInvoiceTrans</p></th>
<th><p>To Table: ReasonTableRef</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_CorrectionDesc_PL</p></td>
<td><p>ReasonComment</p></td>
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
<th><p>From Table: ReasonTableRef</p></th>
<th><p>To Table: CustInvoiceTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecID</p></td>
<td><p>ReasonRefRecId</p></td>
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
<td><p>CustInvoiceTrans</p></td>
<td><p>del_CorrectionDesc_PL</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

