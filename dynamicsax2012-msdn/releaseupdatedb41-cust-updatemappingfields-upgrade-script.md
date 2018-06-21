---
title: ReleaseUpdateDB41_Cust.updateMappingFields Upgrade Script
TOCTitle: ReleaseUpdateDB41_Cust.updateMappingFields Upgrade Script
ms:assetid: b8dc8f1f-8574-b7a5-e14c-d0b947d8ba6f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737084(v=AX.60)
ms:contentKeyID: 49710766
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Cust.updateMappingFields Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateMappingFields</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Adds the mapping for customer related fields and tables.</p></td>
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
<td><p>CustInvoiceJour</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTable</p></td>
</tr>
<tr class="odd">
<td><p>CustTable</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
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
<td><p>CustInvoiceJour</p></td>
<td><p>InvDistrict</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceJour</p></td>
<td><p>SuframaDiscount</p></td>
</tr>
<tr class="odd">
<td><p>CustTable</p></td>
<td><p>TributarySubstitutionRegistry</p></td>
</tr>
</tbody>
</table>


## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name: CustInvoiceTable</p></th>
<th><p>New Table Name: CustinvoiceTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>ServiceCodeOnDlvAddress</p></td>
<td><p>ServiceCodeOnDlvAddress_BR</p></td>
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
<th><p>Old Table Name: SalesTable</p></th>
<th><p>New Table Name: SalesTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>ServiceCodeOnDlvAddress</p></td>
<td><p>ServiceCodeOnDlvAddress_BR</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

