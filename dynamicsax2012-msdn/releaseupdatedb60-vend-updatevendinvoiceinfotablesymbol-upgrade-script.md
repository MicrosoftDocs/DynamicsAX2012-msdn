---
title: ReleaseUpdateDB60_Vend.updateVendInvoiceInfoTableSymbol Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendInvoiceInfoTableSymbol Upgrade Script
ms:assetid: 605d7b3a-6ace-def0-01b4-4ee0e3f25a92
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719049(v=AX.60)
ms:contentKeyID: 49708589
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendInvoiceInfoTableSymbol Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateVendInvoiceInfoTableSymbol</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method updates the bank constant symbol information for the VendInvoiceInfoTable table.</p></td>
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
<td><p>Accounts payable</p></td>
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
<td><p>BankConstantSymbol</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceInfoTable</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceInfoTableSymbol</p></td>
</tr>
</tbody>
</table>


## Remarks

The bank constant symbol information used to be stored as a textual string in the old fields in AX4 and AX5. The new data model is a field that now holds a surrogate foreign key reference to the new BankConstantSymbol table through an extension table, namely the VendInvoiceInfoTableSymbol table.

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
<td><p>BankConstantSymbol</p></td>
<td><p>ConstantSymbol</p></td>
<td><p>CzConstantSymbol</p></td>
</tr>
<tr class="even">
<td><p>BankConstantSymbol</p></td>
<td><p>Name</p></td>
<td><p>Name</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceInfoTableSymbol</p></td>
<td><p>BankConstantSymbol</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceInfoTableSymbol</p></td>
<td><p>CustInvoiceTable</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceInfoTableSymbol</p></td>
<td><p>SpecificSymbol</p></td>
<td><p>SpecificSymbol</p></td>
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
<th><p>Old Table Name: VendInvoiceInfoTable</p></th>
<th><p>New Table Name: VendInvoiceInfoTableSymbol</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>ConstantSymbol_CZ</p></td>
<td><p>BankConstantSymbol (SFK)</p></td>
</tr>
<tr class="odd">
<td><p>SpecificSymbol_CZ</p></td>
<td><p>SpecificSymbol</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

