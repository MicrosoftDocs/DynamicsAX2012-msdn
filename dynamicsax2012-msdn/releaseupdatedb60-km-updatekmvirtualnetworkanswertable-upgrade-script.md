---
title: ReleaseUpdateDB60_KM.updateKMVirtualNetworkAnswerTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_KM.updateKMVirtualNetworkAnswerTable Upgrade Script
ms:assetid: ee652087-05bf-cde1-6dd7-30ff13d9ec5d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719972(v=AX.60)
ms:contentKeyID: 49712044
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_KM.updateKMVirtualNetworkAnswerTable Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_KM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateKMVirtualNetworkAnswerTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ExecutedBy and EvaluationOf fields of the KMVirtualNetworkAnswerTable table with the corresponding value from the RecId field of the DirPerson table.</p></td>
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
<td><p>Human Resources</p></td>
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
<td><p>KMVirtualNetworkAnswerTable</p></td>
</tr>
<tr class="even">
<td><p>HRMVirtualNetworkTable</p></td>
</tr>
<tr class="odd">
<td><p>HRMInterviewTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The ExecutedBy and EvaluationOf fields, which has the RecId value from the DirPerson table, replaces the HrmVirtualNetworkId and TargetVirtualNetworkId fields.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: KMVirtualNetworkAnswerTable</p></th>
<th><p>To Table: KMVirtualNetworkAnswerTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>hrmVirtualNetworkId</p></td>
<td><p>ExecutedBy</p></td>
</tr>
<tr class="even">
<td><p>targetVirtualNetworkId</p></td>
<td><p>EvaluationOf</p></td>
</tr>
<tr class="odd">
<td><p>hrmInterviewId</p></td>
<td><p>DiscussionId</p></td>
</tr>
</tbody>
</table>


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
<td><p>KMVirtualNetworkAnswerTable</p></td>
<td><p>ExecutedBy</p></td>
<td><p>HcmPersonRecId</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>EvaluationOf</p></td>
<td><p>HcmPersonRecId</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>DiscussionId</p></td>
<td><p>HcmDiscussionId</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HRMVirtualNetworkTable</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>HRMInterviewTable</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


