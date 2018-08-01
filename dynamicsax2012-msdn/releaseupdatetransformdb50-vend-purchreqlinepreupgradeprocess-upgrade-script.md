---
title: ReleaseUpdateTransformDB50_Vend.purchReqLinePreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Vend.purchReqLinePreUpgradeProcess Upgrade Script
ms:assetid: 64da26ef-f647-bcf2-50f3-29e7c7fd0621
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719191(v=AX.60)
ms:contentKeyID: 49708730
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Vend.purchReqLinePreUpgradeProcess Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>purchReqLinePreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates data in the SourceDocumentLine table and initializes the DefaultDimension and SourceDocumentLine fields on the PurchReqLine table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>PurchReqLine</p></td>
</tr>
<tr class="even">
<td><p>SourceDocumentLine</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to create records in the SourceDocumentLine table, which is a mandatory foreign key to the PurchReqLine table in the next release.

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
<td><p>PurchReqLine</p></td>
<td><p>SourceDocumentLine</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>DefaultDimension</p></td>
<td><p>RefRecId</p></td>
</tr>
</tbody>
</table>

  


