---
title: ReleaseUpdateDB60_Trv.updateAdminCustomFields Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateAdminCustomFields Upgrade Script
ms:assetid: 6e55b17e-9f92-289b-bc46-09a77fd07f57
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685745(v=AX.60)
ms:contentKeyID: 49708946
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateAdminCustomFields Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Trv</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateAdminCustomFields</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Removes the obsolete values from the TrvAdminCustomFields table and adds the fields added in Microsoft Dynamics AX 2012.</p></td>
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
<td><p>Expense management</p></td>
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
<td><p>TrvAdminCustomFields</p></td>
</tr>
</tbody>
</table>


## Remarks

The TrvAdminCustomFields table contains data that corresponds to fields that are marked DEL\_ in Microsoft Dynamics AX 2012. This script deletes such records. It maps the city and zip code settings to the new edit methods that are added to the table and also inserts the default settings for newly added fields in the TrvExpTable and TrvExpTrans tables.

  


