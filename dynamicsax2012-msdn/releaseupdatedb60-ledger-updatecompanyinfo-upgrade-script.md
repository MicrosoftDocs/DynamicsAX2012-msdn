---
title: ReleaseUpdateDB60_Ledger.updateCompanyInfo Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateCompanyInfo Upgrade Script
ms:assetid: 9a44a32d-f6e9-f3a0-88bb-9fe0fc296620
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686298(v=AX.60)
ms:contentKeyID: 49710001
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateCompanyInfo Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCompanyInfo</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the &lt;c&gt;IsConsolidationCompany&lt;/c&gt; and &lt;c&gt;IsEliminationCompany&lt;/c&gt; fields of the &lt;c&gt;CompanyInfo&lt;/c&gt; table.</p></td>
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
<td><p>CompanyInfo</p></td>
</tr>
<tr class="even">
<td><p>LedgerParameters</p></td>
</tr>
</tbody>
</table>


## Remarks

Sets the \<c\>IsConsolidationCompany\</c\> and \<c\>IsEliminationCompany\</c\> fields with values from the \<c\>del\_Consolidation\</c\> and \<c\>del\_Elimination\</c\> fields of the \<c\>LedgerParameters\</c\> table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerParameters</p></th>
<th><p>To Table: CompanyInfo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_Consolidation</p></td>
<td><p>IsConsolidationCompany</p></td>
</tr>
<tr class="even">
<td><p>del_Elimination</p></td>
<td><p>IsEliminationCompany</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

