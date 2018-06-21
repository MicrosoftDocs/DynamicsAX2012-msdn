﻿---
title: ReleaseUpdateDB60_Invent.allowNoDupShipCarrierCompanyAccounts
TOCTitle: ReleaseUpdateDB60_Invent.allowNoDupShipCarrierCompanyAccounts
ms:assetid: 1c642710-ff55-a597-58b0-5ef6e6f6b798
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718700(v=AX.60)
ms:contentKeyID: 49706983
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.allowNoDupShipCarrierCompanyAccounts [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Invent</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupShipCarrierCompanyAccounts</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;AccountCodeIdx&lt;/c&gt; in the table &lt;c&gt;ShipCarrierCompanyAccounts&lt;/c&gt; not to allow duplicate records.</p></td>
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
<td><p>Inventory management</p></td>
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
<td><p>ShipCarrierCompanyAccounts</p></td>
</tr>
</tbody>
</table>


## Remarks

After removing duplicate records violating the uniqeness of the index, the index AccountCodeIdx is reset not to allow duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

