---
title: ReleaseUpdateDB60_Retail.allowNoDupRetailStyleGrouplIdx
TOCTitle: ReleaseUpdateDB60_Retail.allowNoDupRetailStyleGrouplIdx
ms:assetid: c58d8b46-deba-dd38-b7f1-0590e9b85901
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719536(v=AX.60)
ms:contentKeyID: 49711104
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.allowNoDupRetailStyleGrouplIdx [AX 2012]


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
<td><p>allowNoDupRetailStyleGrouplIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Post-sync script to enable unique index on the style group tables. Updates the indexes &lt;c&gt;groupIdx&lt;/c&gt; in the table &lt;c&gt;RetailStyleGroupTable&lt;/c&gt; and &lt;c&gt;styleGroupIdIdx&lt;/c&gt; in the table &lt;c&gt;RetailStyleGroupTrans&lt;/c&gt; not to allow no duplicate records.</p></td>
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
<td><p>RETAILSTYLEGROUPTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILSTYLEGROUPTRANS</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

