---
title: ReleaseUpdateDB60_Cust.updateInterestCalcAccountChoice Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateInterestCalcAccountChoice Upgrade Script
ms:assetid: aa525378-e888-7d9d-2e97-1c941badf708
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686437(v=AX.60)
ms:contentKeyID: 49710393
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateInterestCalcAccountChoice Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateInterestCalcAccountChoice</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the Account Choice Information for all the interest notes to the Account enumeration value where the Posting Profile that is associated with the interest note is same as the default posting profile. It sets the Account Choice to the Selection enumeration value if the posting profile does not match with the default posting profile.</p></td>
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
<td><p>Accounts receivable</p></td>
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
<td><p>CustInterestJour</p></td>
</tr>
</tbody>
</table>


## Remarks

Sets the Account Choice Information for all the interest notes to the Account enumeration value where the Posting Profile that is associated with the interest note is the same as the default posting profile; otherwise, the Selection enumeration value.

## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustInterestTrans</p></td>
<td><p>InterestCalcAccountChoice</p></td>
<td><p>InterestCalcAccountChoice</p></td>
</tr>
</tbody>
</table>

  


