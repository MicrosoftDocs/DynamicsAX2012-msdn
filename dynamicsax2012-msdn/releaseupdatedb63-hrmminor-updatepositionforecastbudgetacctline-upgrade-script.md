---
title: ReleaseUpdateDB63_HRMMinor.updatePositionForecastBudgetAcctLine Upgrade Script
TOCTitle: ReleaseUpdateDB63_HRMMinor.updatePositionForecastBudgetAcctLine Upgrade Script
ms:assetid: 0fa58266-32eb-ef16-d619-c3a2af4ca5ab
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn975034(v=AX.60)
ms:contentKeyID: 65236148
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB63\_HRMMinor.updatePositionForecastBudgetAcctLine Upgrade Script [AX 2012]


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB63_HRMMinor</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePositionForecastBudgetAcctLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates &lt;c&gt;HcmPositionForecastBudgetAcctLine&lt;/c&gt; table records with &lt;c&gt;HcmPositionForecastScenario&lt;/c&gt; table records.</p></td>
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
<td><p>ReleaseUpdateDB63_HRMMinor</p></td>
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
<td><p>HCMPOSITIONFORECASTBUDGETACCTLINE</p></td>
</tr>
<tr class="even">
<td><p>HCMPOSITIONFORECASTSCENARIO</p></td>
</tr>
</tbody>
</table>


## Remarks

The \<c\>PositionForecastCompensationGrid\</c\> field on the \<c\>HcmPositionForecastBudgetAcctLine\</c\> record is set with the data from the \<c\>PositionForecastCompensationGrid\</c\> field on the \<c\>HcmPositionForecastScenario\</c\> table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

