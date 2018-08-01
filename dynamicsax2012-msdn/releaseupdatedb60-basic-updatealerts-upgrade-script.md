---
title: ReleaseUpdateDB60_Basic.updateAlerts Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateAlerts Upgrade Script
ms:assetid: 31fec757-6402-3e59-7ae8-2f117daa50ae
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685065(v=AX.60)
ms:contentKeyID: 49707518
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateAlerts Upgrade Script 


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
<td><p>updateAlerts</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades and disables all alert rules. Also resolves all duplicate rule IDs, because rules are now global and no longer bound by company.</p></td>
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
<td><p>EventRule</p></td>
</tr>
<tr class="even">
<td><p>EventRuleData</p></td>
</tr>
<tr class="odd">
<td><p>EventRuleField</p></td>
</tr>
<tr class="even">
<td><p>EventRuleIgnore</p></td>
</tr>
<tr class="odd">
<td><p>EventRuleIgnoreAggregation</p></td>
</tr>
<tr class="even">
<td><p>EventRuleRel</p></td>
</tr>
<tr class="odd">
<td><p>EventRuleRelData</p></td>
</tr>
</tbody>
</table>


## Remarks

As alert tables have become global in Microsoft Dynamics AX 2012, duplicate rule IDs could exist after the bulk copy is performed from the source system. These are resolved in this upgrade script. The resolution is to suffix the company name against all duplicate rules.

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
<td><p>EventRule</p></td>
<td><p>ActionNames</p></td>
<td><p>BlobData</p></td>
</tr>
<tr class="even">
<td><p>EventRule</p></td>
<td><p>AlertInstanceRelationshipType</p></td>
<td><p>EventInstanceRelationshipType</p></td>
</tr>
<tr class="odd">
<td><p>EventRule</p></td>
<td><p>CompanyId</p></td>
<td><p>SelectableDataArea</p></td>
</tr>
<tr class="even">
<td><p>EventRule</p></td>
<td><p>GlobalRule</p></td>
<td><p>EventIsGlobalRule</p></td>
</tr>
<tr class="odd">
<td><p>EventRule</p></td>
<td><p>PrimInstanceRelationType</p></td>
<td><p>EventInstanceRelationType</p></td>
</tr>
<tr class="even">
<td><p>EventRuleField</p></td>
<td><p>uInstanceRelationType</p></td>
<td><p>EventInstanceRelationType</p></td>
</tr>
<tr class="odd">
<td><p>EventRuleRel</p></td>
<td><p>CudInstanceRelationType</p></td>
<td><p>EventInstanceRelationshipType</p></td>
</tr>
<tr class="even">
<td><p>EventRuleRel</p></td>
<td><p>RelType</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EventRuleRelData</p></td>
<td><p>FieldNameList</p></td>
<td><p>EventFieldLis</p></td>
</tr>
<tr class="even">
<td><p>EventRuleRelData</p></td>
<td><p>Data</p></td>
<td><p>BlobData</p></td>
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
<td><p>EventRule</p></td>
<td><p>ActionIds</p></td>
</tr>
<tr class="even">
<td><p>EventRuleData</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="odd">
<td><p>EventRuleField</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="even">
<td><p>EventRuleIgnore</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="odd">
<td><p>EventRuleIgnoreAggregation</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="even">
<td><p>EventRuleRel</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="odd">
<td><p>EventRuleRelData</p></td>
<td><p>FieldList</p></td>
</tr>
<tr class="even">
<td><p>EventRuleRelData</p></td>
<td><p>DataAreaId</p></td>
</tr>
</tbody>
</table>

  


