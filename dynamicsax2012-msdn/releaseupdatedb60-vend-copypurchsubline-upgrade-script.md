---
title: ReleaseUpdateDB60_Vend.copyPurchSubLine Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.copyPurchSubLine Upgrade Script
ms:assetid: 6accd12c-51f8-d6c8-cc5c-12823d4ad665
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685680(v=AX.60)
ms:contentKeyID: 49708881
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.copyPurchSubLine Upgrade Script 


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
<td><p>copyPurchSubLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies data from the PurchParmSubLine table, which is related to a non-duplicate PurchParmLine table, to the VendInvoiceInfoSubLine table.</p></td>
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
<td><p>PurchParmLine</p></td>
</tr>
<tr class="even">
<td><p>PurchParmSubLine</p></td>
</tr>
<tr class="odd">
<td><p>PurchParmTable</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceInfoLine</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceInfoSubLine</p></td>
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
<th><p>From Table: PurchParmSubLine</p></th>
<th><p>To Table: VendInvoiceInfoSubLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ParmId</p></td>
<td><p>ParmId</p></td>
</tr>
<tr class="even">
<td><p>InventNow</p></td>
<td><p>InventNow</p></td>
</tr>
<tr class="odd">
<td><p>ReceiveNow</p></td>
<td><p>ReceiveNow</p></td>
</tr>
<tr class="even">
<td><p>JournalRefRecId</p></td>
<td><p>JournalRefRecId</p></td>
</tr>
<tr class="odd">
<td><p>JournalRefTableId</p></td>
<td><p>JournalRefTableId</p></td>
</tr>
<tr class="even">
<td><p>LineRefRecId</p></td>
<td><p>LineRefRecId</p></td>
</tr>
<tr class="odd">
<td><p>DocumentId</p></td>
<td><p>DocumentId</p></td>
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
<th><p>From Table: VendInvoiceInfoLine</p></th>
<th><p>To Table: VendInvoiceInfoSubLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>LineRefRecId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

