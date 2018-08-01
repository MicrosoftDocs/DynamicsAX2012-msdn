---
title: ReleaseUpdateDB60_PBA.updatePBATreeRouteOpr
TOCTitle: ReleaseUpdateDB60_PBA.updatePBATreeRouteOpr
ms:assetid: 0a781260-a5c0-8ebc-cba8-625fb646f4e8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735620(v=AX.60)
ms:contentKeyID: 49706531
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_PBA.updatePBATreeRouteOpr 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_PBA</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePBATreeRouteOpr</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates &lt;c&gt;WrkCtrpbaTreeRouteOprActivity&lt;/c&gt;, &lt;c&gt;WrkCtrActivity&lt;/c&gt;, &lt;c&gt;WrkCtrActivityRequirementSet&lt;/c&gt;, &lt;c&gt;WrkCtrActivityRequirement&lt;/c&gt;,</p></td>
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
<td><p>Product Builder</p></td>
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
<td><p>DEL_PBATreeRouteWrkCtrFixing</p></td>
</tr>
<tr class="even">
<td><p>PBATreeRouteOpr</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrActivity</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrActivityCapabilityRequirement</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrActivityRequirement</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrActivityRequirementSet</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrActivityResourceGroupRequirement</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrActivityResourceRequirement</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrCapability</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrCapabilityResource</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrPBATreeRouteOprActivity</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrResourceGroup</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrResourceGroupResource</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The resource model introduced in AX 6.0 has a different database schema and requires that the resource information from the route operation nodes be migrated to the respective tables.

  


