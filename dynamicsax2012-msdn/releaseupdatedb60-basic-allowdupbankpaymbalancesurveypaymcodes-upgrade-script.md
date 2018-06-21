---
title: ReleaseUpdateDB60_Basic.allowDupBankPaymBalanceSurveyPaymCodes Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowDupBankPaymBalanceSurveyPaymCodes Upgrade Script
ms:assetid: 93d72047-f47a-0af2-6307-dbe8f36c4827
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686127(v=AX.60)
ms:contentKeyID: 49709831
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowDupBankPaymBalanceSurveyPaymCodes Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowDupBankPaymBalanceSurveyPaymCodes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the SurveyCodeIdx index in the BankPaymBalanceSurveyPaymCodes table to allow duplicate records.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>BankPaymBalanceSurveyPaymCodes</p></td>
</tr>
</tbody>
</table>


## Remarks

The SurveyCode field is replaced with the new BankPaymBalanceSurvey surrogate key field in the unique SurveyCodeIdx index. Initially this field contains no value. The index is set to allow duplicate records before the field is updated with the value of the record ID field of the BankPaymBalanceSurvey table. The truncated method name from the allowDupBankPaymBalanceSurveyPaymCodesSurveyCodeIdx method due to the 40 characters length limit of the method name.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

