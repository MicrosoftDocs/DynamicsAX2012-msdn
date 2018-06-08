---
title: ReleaseUpdateDB60_Retail.updateRetailStoreGroup Upgrade Script
TOCTitle: ReleaseUpdateDB60_Retail.updateRetailStoreGroup Upgrade Script
ms:assetid: aff46ed1-58bb-2ace-0327-7abf3552c58c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686595(v=AX.60)
ms:contentKeyID: 49710549
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.updateRetailStoreGroup Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Retail</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateRetailStoreGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates OMHierarchyType records to replace each record that existed in the DEL_RetailStoreGroup table.</p></td>
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
<td><p>Retail</p></td>
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
<td><p>DEL_RETAILASSORTMENTSTORELIST</p></td>
</tr>
<tr class="even">
<td><p>DEL_RETAILSTOREGROUP</p></td>
</tr>
<tr class="odd">
<td><p>DEL_RETAILSTOREGROUPTRANS</p></td>
</tr>
<tr class="even">
<td><p>DIRORGANIZATIONBASE</p></td>
</tr>
<tr class="odd">
<td><p>DIRPARTYTABLE</p></td>
</tr>
<tr class="even">
<td><p>DIRRELATIONSHIPTYPETABLE</p></td>
</tr>
<tr class="odd">
<td><p>OMEXPLODEDORGANIZATIONSECURITYGRAPH</p></td>
</tr>
<tr class="even">
<td><p>OMHIERARCHYCHANGELOG</p></td>
</tr>
<tr class="odd">
<td><p>OMHIERARCHYPURPOSE</p></td>
</tr>
<tr class="even">
<td><p>OMHIERARCHYRELATIONSHIP</p></td>
</tr>
<tr class="odd">
<td><p>OMHIERARCHYTYPE</p></td>
</tr>
<tr class="even">
<td><p>OMHIERPURPOSEORGTYPEMAP</p></td>
</tr>
<tr class="odd">
<td><p>OMINTERNALORGANIZATION</p></td>
</tr>
<tr class="even">
<td><p>OMOPERATINGUNIT</p></td>
</tr>
<tr class="odd">
<td><p>OMREVISIONEDIT</p></td>
</tr>
<tr class="even">
<td><p>RETAILASSORTMENTCHANNELLINE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILASSORTMENTTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILCHANNELTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILSTORETABLE</p></td>
</tr>
</tbody>
</table>


## Remarks

This method create a hierarchy type to each existed replace Retail store groups. The newly created hierarchy has a business unit as the root node. And all retail stores are the direct children nodes of the root node.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

