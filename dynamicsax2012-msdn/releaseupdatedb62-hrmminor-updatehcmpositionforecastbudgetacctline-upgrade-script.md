---
title: ReleaseUpdateDB62_HRMMinor.updateHcmPositionForecastBudgetAcctLine Upgrade Script
TOCTitle: ReleaseUpdateDB62_HRMMinor.updateHcmPositionForecastBudgetAcctLine Upgrade Script
ms:assetid: 69713cda-310c-7b5f-51a1-d66450341073
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn702755(v=AX.60)
ms:contentKeyID: 65236211
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_HRMMinor.updateHcmPositionForecastBudgetAcctLine Upgrade Script [AX 2012]


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB62_HRMMinor</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateHcmPositionForecastBudgetAcctLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the &lt;c&gt;HcmPositionForecastBudgetAcctLine&lt;/c&gt; table.</p></td>
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
<td><p>HRM</p></td>
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
<td><p>DEL_HCMPOSITIONFORECASTDURATION</p></td>
</tr>
<tr class="odd">
<td><p>HCMBUDGETPURPOSETYPEDETAIL</p></td>
</tr>
<tr class="even">
<td><p>HCMPOSITIONFORECASTACCTLINENOTE</p></td>
</tr>
<tr class="odd">
<td><p>HCMPOSITIONFORECASTDETAIL</p></td>
</tr>
<tr class="even">
<td><p>HCMPOSITIONFORECASTSCENARIO</p></td>
</tr>
<tr class="odd">
<td><p>HCMFORECASTSCENARIO</p></td>
</tr>
<tr class="even">
<td><p>BUDGETCYCLE</p></td>
</tr>
<tr class="odd">
<td><p>BUDGETPLANNINGPROCESS</p></td>
</tr>
<tr class="even">
<td><p>FISCALCALENDARPERIOD</p></td>
</tr>
<tr class="odd">
<td><p>HCMPOSITIONFORECASTBUDGETDEFAULTVALUE</p></td>
</tr>
</tbody>
</table>


## Remarks

1\. Copies \<c\>HcmPositionForecastBudgetAcctLine\</c\> record and links it to the \<c\>HcmPositionForecastScenario\</c\> table. 2. Updates the \<c\>EffectiveDate\</c\> and \<c\>ExpirationDate\</c\> fields with the \<c\>HcmPositionForecastScenario\</c\> table for the \<c\>ActivationDateTime\</c\> and the \<c\>RetirementDateTime\</c\> or Budget Cycle start and end date. 2. Updates the \<c\>BudgetPurposeTypeDetail\</c\> field of the \<c\>HcmPositionForecastBudgetAcctLine\</c\> table through the references in the \<c\>HcmBudgetPurposeTypeDetail\</c\> table. 3. Updates all cost elements as fixed amount type setting the same value to the \<c\>AmountCur\</c\> field and the \<c\>BudgetAmountCur\</c\> field, setting No to the \<c\>isPercentageBased\</c\> and setting ZERO to the \<c\>PercentageOfDefaultBasisAmount\</c\> of the \<c\>HcmPositionForecastBudgetAcctLine\</c\> table. 4. Inserts notes into the \<c\>HcmPositionForecastAcctLineNote\</c\> table if the record in the \<c\>HcmPositionForecastBudgetAcctLine\</c\> table is percentage based.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

