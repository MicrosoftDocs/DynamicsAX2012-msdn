---
title: ReleaseUpdateDB60_Cust.updateFiscalPrinterWorkerSetup_PL Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateFiscalPrinterWorkerSetup_PL Upgrade Script
ms:assetid: 43c33663-d6c2-ab73-1f57-b68eedd4a059
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718891(v=AX.60)
ms:contentKeyID: 49707927
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateFiscalPrinterWorkerSetup\_PL Upgrade Script 


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
<td><p>updateFiscalPrinterWorkerSetup_PL</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates fiscal printer worker setup information.</p></td>
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
<td><p>PlFiscalPrinterWorkerSetup</p></td>
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
<th><p>From Table: HcmWorker</p></th>
<th><p>To Table: PlFiscalPrinterWorkerSetup</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Worker</p></td>
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
<th><p>From Table: DEL_EmplTable</p></th>
<th><p>To Table: PlFiscalPrinterWorkerSetup</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>FiscalPrinterCode_PL</p></td>
<td><p>FiscalPrinterCode</p></td>
</tr>
<tr class="even">
<td><p>FiscalPrinterUser_PL</p></td>
<td><p>FiscalPrinterUserCode</p></td>
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
<td><p>PlFiscalPrinterWorkerSetup</p></td>
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
<td><p>DEL_EmplTable</p></td>
<td><p>FiscalPrinterCode_PL</p></td>
</tr>
<tr class="even">
<td><p>DEL_EmplTable</p></td>
<td><p>FiscalPrinterUser_PL</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

