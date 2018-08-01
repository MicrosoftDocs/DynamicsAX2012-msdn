---
title: ReleaseUpdateDB60_Basic.updateInterCompanySetup Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateInterCompanySetup Upgrade Script
ms:assetid: d4d54e4b-8f12-3d89-2db0-87114ec8bf94
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687008(v=AX.60)
ms:contentKeyID: 49711456
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateInterCompanySetup Upgrade Script 


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
<td><p>updateInterCompanySetup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates intercompany trading partners and trading by using the existing intercompany relations in the AIF tables.</p></td>
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
<td><p>InterCompanyTradingPartner</p></td>
</tr>
<tr class="even">
<td><p>InterCompanyTradingRelation</p></td>
</tr>
<tr class="odd">
<td><p>InterCompanyTradingValueMap</p></td>
</tr>
<tr class="even">
<td><p>InterCompanyEndpointActionPolicy</p></td>
</tr>
<tr class="odd">
<td><p>InterCompanyEndpointActionPolicyTransfer</p></td>
</tr>
</tbody>
</table>


## Remarks

The intercompany setup is removed from AIF setup to separate tables. For each intercompany AIF endpoint constraint, an intercompany trading partner is created and trading partners are linked through trading relationships.

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
<td><p>InterCompanyTradingPartner</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>InterCompanyTradingRelation</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


