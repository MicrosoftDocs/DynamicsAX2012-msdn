﻿---
title: ReleaseUpdateDB60_Basic.allowNoDupRTax25StdExpressionTable_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowNoDupRTax25StdExpressionTable_RU Upgrade Script
ms:assetid: 2b813746-59a9-c225-ba22-86d3deb16a27
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735950(v=AX.60)
ms:contentKeyID: 49707366
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowNoDupRTax25StdExpressionTable\_RU Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupRTax25StdExpressionTable_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the SeqProfitIdx index in the table RTax25StdExpressionTable not to allow duplicate records.</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>RTax25StdExpressionTable</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the RTax25ProfitTable surrogate key field with the value of the record ID field of the RTax25ProfitTable table, the SeqProfitIdx index is reset not to allow duplicate records.

  


