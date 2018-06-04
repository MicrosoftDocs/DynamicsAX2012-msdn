---
title: ReleaseUpdateDB60_Invent.allowNoDupInvtFsclLIFOJrnllTrnsAdjGrpIdx
TOCTitle: ReleaseUpdateDB60_Invent.allowNoDupInvtFsclLIFOJrnllTrnsAdjGrpIdx
ms:assetid: 1f2a85fd-f91d-7184-01b0-6c1632521e56
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684863(v=AX.60)
ms:contentKeyID: 49707070
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.allowNoDupInvtFsclLIFOJrnllTrnsAdjGrpIdx 


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
<td><p>allowNoDupInvtFsclLIFOJrnllTrnsAdjGrpIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;GroupItemYearIdx&lt;/c&gt; in the table &lt;c&gt;InventFiscalLIFOJournalTransAdj&lt;/c&gt; not to allow duplicate records.</p></td>
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
<td><p>InventFiscalLIFOJournalTransAdj</p></td>
</tr>
</tbody>
</table>


## Remarks

Truncated method name from allowNoDupInventFiscalLIFOJournalTransAdjGroupItemYearIdx. After updating the surrogate key field InventFiscalLIFOGroup with the value of the RecId field of the table InventFiscalLIFOGroup, the index GroupItemYearIdx is reset not to allow duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

