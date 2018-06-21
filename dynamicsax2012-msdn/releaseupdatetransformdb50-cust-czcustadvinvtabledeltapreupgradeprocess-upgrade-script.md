---
title: ReleaseUpdateTransformDB50_Cust.czCustAdvInvTableDeltaPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Cust.czCustAdvInvTableDeltaPreUpgradeProcess Upgrade Script
ms:assetid: 75b2c37d-3f79-a94d-153a-99dff2864e93
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719306(v=AX.60)
ms:contentKeyID: 49709098
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Cust.czCustAdvInvTableDeltaPreUpgradeProcess Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>czCustAdvInvTableDeltaPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the &lt;c&gt;Dimension&lt;/c&gt; field to the &lt;c&gt;DefaultDimension&lt;/c&gt; field and the &lt;c&gt;SalesTaker&lt;/c&gt; field to the &lt;c&gt;WorkerSalesTaker&lt;/c&gt; field in the &lt;c&gt;CzCustAdvanceInvoiceTable&lt;/c&gt; table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>CzCustAdvanceInvoiceTable</p></td>
</tr>
<tr class="even">
<td><p>Shadow_CzCustAdvanceInvoiceTable</p></td>
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
<th><p>From Table: CzCustAdvanceInvoiceTable</p></th>
<th><p>To Table: Shadow_CzCustAdvanceInvoiceTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dimension</p></td>
<td><p>DefaultDimension</p></td>
</tr>
<tr class="even">
<td><p>SalesTaker</p></td>
<td><p>WorkerSalesTaker</p></td>
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
<td><p>CzCustAdvanceInvoiceTable</p></td>
<td><p>DefaultDimension</p></td>
<td><p>DimensionDefault</p></td>
</tr>
<tr class="even">
<td><p>CzCustAdvanceInvoiceTable</p></td>
<td><p>WorkerSalesTaker</p></td>
<td><p>SalesTaker</p></td>
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
<td><p>CzCustAdvanceInvoiceTable</p></td>
<td><p>Dimension</p></td>
</tr>
<tr class="even">
<td><p>CzCustAdvanceInvoiceTable</p></td>
<td><p>SalesTaker</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

