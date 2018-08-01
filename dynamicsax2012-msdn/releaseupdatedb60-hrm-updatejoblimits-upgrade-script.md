---
title: ReleaseUpdateDB60_HRM.updateJobLimits Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateJobLimits Upgrade Script
ms:assetid: ad034c0b-705b-2225-1938-9d2c7b557926
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686505(v=AX.60)
ms:contentKeyID: 49710459
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateJobLimits Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_HRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateJobLimits</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates the job limits to the new signing limit model.</p></td>
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
<td><p>SRM</p></td>
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
<td><p>HRPLimitParameters</p></td>
</tr>
<tr class="even">
<td><p>HRPDefaultLimitRule</p></td>
</tr>
<tr class="odd">
<td><p>HRPDefaultLimitDetail</p></td>
</tr>
<tr class="even">
<td><p>HRPDefaultLimitJobRule</p></td>
</tr>
</tbody>
</table>


## Remarks

This method sets the authority basis to the Job value and the organization precedence to the Company value. Then, for each company, that is Data Area, which is not a virtual company, the system creates a policy of Signing Limit Policy type and maps to the policy.

For every signing limit policy that is created, the system creates two rules. The first rule will have a valid from date equal to the first date, which is the minimum date, from the HRPLimitDefaultTableRelationship table and the valid to date equal to one day less than the current date. The second rule will have the valid from date equal to current date and the valid to date equal to the maximum date. Every job in a company can have multiple default limit setup for the same limit type and document type during different date intervals. These jobs are copied to the two rules which were created earlier.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_HRPLimitDefaultTableRelationship</p></th>
<th><p>To Table: HRPDefaultLimitDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DefaultValue</p></td>
<td><p>Amount</p></td>
</tr>
<tr class="even">
<td><p>CurrencyCode</p></td>
<td><p>Currency</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_HRPLimitTypeTable</p></th>
<th><p>To Table: HRPDefaultLimitDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LimitType</p></td>
<td><p>LimitType</p></td>
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
<td><p>HRPDefaultLimitDetail</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>HRPDefaultLimitRule</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>HRPDefaultLimitJobRule</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>HRPLimitParameters</p></td>
<td><p></p></td>
<td><p></p></td>
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
<td><p>DEL_HRPLimitTypeTable</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DEL_HRPLimitDefaultTableRelationship</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


