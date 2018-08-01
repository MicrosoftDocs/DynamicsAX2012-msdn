---
title: ReleaseUpdateDB60_Retail.allowNoDupRetailColorGroupIdx
TOCTitle: ReleaseUpdateDB60_Retail.allowNoDupRetailColorGroupIdx
ms:assetid: 746d74e0-b5ae-d555-4493-7ff6180c91ca
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719278(v=AX.60)
ms:contentKeyID: 49709070
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.allowNoDupRetailColorGroupIdx 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Retail</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupRetailColorGroupIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Post-sync script to enable unique index on the color group tables. Updates the indexes &lt;c&gt;groupIdx&lt;/c&gt; in the table &lt;c&gt;RetailColorGroupTable&lt;/c&gt; and &lt;c&gt;ColorGroupColorIdIdx&lt;/c&gt; in the table &lt;c&gt;RetailColorGroupTrans&lt;/c&gt; not to allow no duplicate records.</p></td>
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
<td><p>Retail</p></td>
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
<td><p>RETAILCOLORGROUPTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILCOLORGROUPTRANS</p></td>
</tr>
</tbody>
</table>

  


