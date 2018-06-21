---
title: ReleaseUpdateDB60_Vend.updateImportDeclaration_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateImportDeclaration_BR Upgrade Script
ms:assetid: 2e8cbcc2-2d2b-22f4-1449-b6cf3bec7929
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736023(v=AX.60)
ms:contentKeyID: 49707438
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateImportDeclaration\_BR Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateImportDeclaration_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the &lt;c&gt;ImportDeclaration&lt;/c&gt; field in the &lt;c&gt;FiscalDocument_BR&lt;/c&gt; table.</p></td>
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
<td><p>FiscalDocument_BR</p></td>
</tr>
<tr class="even">
<td><p>DEL_PurchImportDeclarationLink_BR</p></td>
</tr>
<tr class="odd">
<td><p>DEL_FiscalDocJour_BR</p></td>
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
<th><p>From Table: DEL_PurchImportDeclarationLink_BR</p></th>
<th><p>To Table: FiscalDocument_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ImportDeclarationRecId</p></td>
<td><p>ImportDeclaration</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

