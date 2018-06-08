---
title: ReleaseUpdateDB60_Vend.updateCustomsVendBOESubTrans_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateCustomsVendBOESubTrans_IN Upgrade Script
ms:assetid: 7a6264a9-06b1-a0b6-d79b-eebd09a6f5c6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719414(v=AX.60)
ms:contentKeyID: 49709205
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateCustomsVendBOESubTrans\_IN Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>updateCustomsVendBOESubTrans_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the CustomsVendBOESubTrans_IN table. The record IDs of the CustomsBillOfEntryNumberTable_IN and CustomsImportInvoiceNumberTable_IN tables are now stored in place of the CustomsBillOfEntryNumber_IN and CustomsImporterInvoiceNumber_IN field values.</p></td>
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
<td><p>CustomsVendBOESubTrans_IN</p></td>
</tr>
<tr class="even">
<td><p>CustomsBillOfEntryNumberTable_IN</p></td>
</tr>
<tr class="odd">
<td><p>CustomsImportInvoiceNumberTable_IN</p></td>
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
<td><p>CustomsVendBOESubTrans_IN</p></td>
<td><p>del_BillOfEntryNumber</p></td>
</tr>
<tr class="even">
<td><p>CustomsVendBOESubTrans_IN</p></td>
<td><p>del_ImporterInvoiceNumber</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

