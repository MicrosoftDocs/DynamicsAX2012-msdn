---
title: ReleaseUpdateDB60_Req.updateReqPlan Upgrade Script
TOCTitle: ReleaseUpdateDB60_Req.updateReqPlan Upgrade Script
ms:assetid: 2db0dbce-09e8-2e0e-4aba-27ed51571779
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736008(v=AX.60)
ms:contentKeyID: 49707423
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Req.updateReqPlan Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Req</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateReqPlan</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates four new fields that are related to forecast on the ReqPlan table.</p></td>
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
<td><p>Master planning</p></td>
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
<td><p>ReqPlan</p></td>
</tr>
</tbody>
</table>


## Remarks

Four new fields for including inventory forecast has been introduced for all types of master plans, that is, forecast plans and master plans. This removes the requirement to execute a forecast plan before a master plan in order to include inventory forecast. Settings from existing forecast plans are copied to the new fields on the ReqPlan table. Settings from existing master plans are merged with related forecast plan settings and copied to the new fields on the ReqPlan table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: reqPlanForecast</p></th>
<th><p>To Table: reqPlan</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_UsePurchForecast</p></td>
<td><p>UseForecastSupply</p></td>
</tr>
<tr class="even">
<td><p>del_UseSalesForecast</p></td>
<td><p>UseForecastDemand</p></td>
</tr>
<tr class="odd">
<td><p>del_ForecastModelId</p></td>
<td><p>ForecastModelId</p></td>
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
<th><p>From Table: reqPlanSched</p></th>
<th><p>To Table: reqPlan</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_ReduceType</p></td>
<td><p>ForecastReduceType</p></td>
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
<td><p>ReqPlan</p></td>
<td><p>UseForecastDemand</p></td>
<td><p>ReqUseForecastDemand</p></td>
</tr>
<tr class="even">
<td><p>ReqPlan</p></td>
<td><p>UseForecastSupply</p></td>
<td><p>ReqUseForecastSupply</p></td>
</tr>
<tr class="odd">
<td><p>ReqPlan</p></td>
<td><p>ForecastModelId</p></td>
<td><p>ForecastModelId</p></td>
</tr>
<tr class="even">
<td><p>ReqPlan</p></td>
<td><p>ForecastReduceType</p></td>
<td><p>ReqReduceType</p></td>
</tr>
</tbody>
</table>


## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name: reqPlanForecast</p></th>
<th><p>New Table Name:</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>ForecastModelId</p></td>
<td><p>DEL_ForecastModelId</p></td>
</tr>
<tr class="odd">
<td><p>UsePurchForecast</p></td>
<td><p>DEL_UsePurchForecast</p></td>
</tr>
<tr class="even">
<td><p>UseSalesForecast</p></td>
<td><p>DEL_UseSalesForecast</p></td>
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
<th><p>Old Table Name: reqPlanSched</p></th>
<th><p>New Table Name:</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>ReqPlanIdForecast</p></td>
<td><p>DEL_ReqPlanIdForecast</p></td>
</tr>
<tr class="odd">
<td><p>UseForecastPlan</p></td>
<td><p>DEL_UseForecastPlan</p></td>
</tr>
<tr class="even">
<td><p>ReduceType</p></td>
<td><p>DEL_ReduceType</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

