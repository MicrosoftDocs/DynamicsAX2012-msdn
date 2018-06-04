---
title: ReleaseUpdateDB60_Ledger.allowNoDupDefermentSchedule_INTaxRegistr
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupDefermentSchedule_INTaxRegistr
ms:assetid: a9697377-b7ec-7745-e82d-2a8bf1c5a144
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686415(v=AX.60)
ms:contentKeyID: 49710371
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupDefermentSchedule\_INTaxRegistr 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>allowNoDupDefermentSchedule_INTaxRegistr</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;TaxRegistrationNumberIdx&lt;/c&gt; in the table &lt;c&gt;DefermentSchedule_IN&lt;/c&gt; not to allow duplicate records.</p></td>
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
<td><p>DEFERMENTSCHEDULE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the surrogate key fields TaxRegistrationNumberTable with the value of the RecId field of the tables, the index TaxRegistrationNumberTableIdx is reset not to allow duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

