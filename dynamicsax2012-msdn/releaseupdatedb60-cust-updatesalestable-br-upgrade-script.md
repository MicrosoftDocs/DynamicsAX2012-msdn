---
title: ReleaseUpdateDB60_Cust.updateSalesTable_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateSalesTable_BR Upgrade Script
ms:assetid: c41cfb59-11fe-e856-033a-32bf344c67f1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686861(v=AX.60)
ms:contentKeyID: 49711058
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateSalesTable\_BR Upgrade Script 


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
<td><p>updateSalesTable_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the SalesTable_BR table records from the SalesTable table records.</p></td>
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
<td><p>SalesTable</p></td>
</tr>
<tr class="even">
<td><p>SalesTable_BR</p></td>
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
<th><p>From Table: SalesTable</p></th>
<th><p>To Table: SalesTable_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Authority_BR</p></td>
<td><p>Authority_BR</p></td>
</tr>
<tr class="even">
<td><p>CFPSId_BR</p></td>
<td><p>CFPSId_BR</p></td>
</tr>
<tr class="odd">
<td><p>CustFinalUser_BR</p></td>
<td><p>CustFinalUser_BR</p></td>
</tr>
<tr class="even">
<td><p>InvoiceRefRecId</p></td>
<td><p>InvoiceRefRecId</p></td>
</tr>
<tr class="odd">
<td><p>RefProcessNo</p></td>
<td><p>RefProcessNo</p></td>
</tr>
<tr class="even">
<td><p>ServiceCodeOnDlvAddress</p></td>
<td><p>ServiceCodeOnDlvAddress</p></td>
</tr>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>SalesTable</p></td>
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
<td><p>SalesTable_BR</p></td>
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
<td><p>SalesTable</p></td>
<td><p>Authority_BR</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>CFPSId_BR</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
<td><p>CustFinalUser_BR</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>InvoiceRefRecId</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
<td><p>RefProcessNo</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>ServiceCodeOnDlvAddress</p></td>
</tr>
</tbody>
</table>

  


