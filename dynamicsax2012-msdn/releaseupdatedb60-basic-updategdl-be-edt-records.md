---
title: ReleaseUpdateDB60_Basic.updateGDL_BE_EDT_Records
TOCTitle: ReleaseUpdateDB60_Basic.updateGDL_BE_EDT_Records
ms:assetid: 8c4e8da8-f7f4-d60e-b7ef-2c38d7e6a138
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736456(v=AX.60)
ms:contentKeyID: 49709644
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateGDL\_BE\_EDT\_Records [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateGDL_BE_EDT_Records</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the surrogate key column in the foreign tables with the value from the &lt;c&gt;RecId&lt;/c&gt; field of the primary table.</p></td>
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
<td><p>AddressCountryRegionBLWI</p></td>
</tr>
<tr class="even">
<td><p>AddressCountryRegionGroupBLWI</p></td>
</tr>
<tr class="odd">
<td><p>BankPaymBalanceSurvey</p></td>
</tr>
<tr class="even">
<td><p>BankPaymBalanceSurveyPaymCodes</p></td>
</tr>
<tr class="odd">
<td><p>IntrastatArchiveDetail</p></td>
</tr>
<tr class="even">
<td><p>IntrastatArchiveGeneral</p></td>
</tr>
<tr class="odd">
<td><p>TradeBLWILines</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the \<c\>IntrastatArchiveGeneral\</c\> field in the table \<c\>IntrastatArchiveDetail\</c\> with the value from the \<c\>RecId\</c\> field of the \<c\>IntrastatArchiveGeneral\</c\> table. Updates the \<c\>AddressCountryRegionGroupBLWI\</c\> field in the tables \<c\>AddressCountryRegionBLWI\</c\> and \<c\>TradeBLWILines\</c\> with the value from the \<c\>RecId\</c\> field of the \<c\>AddressCountryRegionGroupBLWI\</c\> table. Updates the \<c\>BankPaymBalanceSurvey\</c\> field in the tables \<c\>TradeBLWILines\</c\> and \<c\>BankPaymBalanceSurveyPaymCodes\</c\> with the value from the \<c\>RecId\</c\> field of the \<c\>BankPaymBalanceSurvey\</c\> table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

