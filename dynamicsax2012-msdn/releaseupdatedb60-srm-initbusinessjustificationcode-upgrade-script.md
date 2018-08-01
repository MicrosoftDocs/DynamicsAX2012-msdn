---
title: ReleaseUpdateDB60_Srm.initBusinessJustificationCode Upgrade Script
TOCTitle: ReleaseUpdateDB60_Srm.initBusinessJustificationCode Upgrade Script
ms:assetid: e24d2cbf-6916-1cb9-8eea-c3c90ef7dfbc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737323(v=AX.60)
ms:contentKeyID: 49711766
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Srm.initBusinessJustificationCode Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Srm</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>initBusinessJustificationCode</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Initializes the BusinessJustificationCodes field with default value.</p></td>
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
<td><p>SRM</p></td>
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
<td><p>PurchReqTable</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
</tr>
</tbody>
</table>


## Remarks

A mandatory BusinessJustificationCodes field has been introduced in this release. This method is used to initialize the default value during ugprade.

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
<td><p>PurchReqTable</p></td>
<td><p>BusinessJustification</p></td>
<td><p>BusinessJustificationRefRecId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>BusinessJustification</p></td>
<td><p>BusinessJustificationRefRecId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

