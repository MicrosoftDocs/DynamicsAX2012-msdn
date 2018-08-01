---
title: ReleaseUpdateTransformDB40_Prod.validateFullPhysicaDimensionSetup Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Prod.validateFullPhysicaDimensionSetup Upgrade Script
ms:assetid: 8c8ac483-8983-2d67-332a-38c83264181e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736462(v=AX.60)
ms:contentKeyID: 49709650
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Prod.validateFullPhysicaDimensionSetup Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Prod</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validateFullPhysicaDimensionSetup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Performs the full multisite validation to verify that for inventory dimension group where warehouse is not a physical dimension, all items are on the same site.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Upgrade readiness scripts</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>Production</p></td>
</tr>
</tbody>
</table>


<table xmlns="http://www.w3.org/1999/xhtml">
              <tr><th colspan="2">
		
   <p>
   
	 Validation Issues
  </p>
  </th></tr>
              <tr><td>
		
   <p>
   
	 
            Validation Issues Description
          
  </p>
  </td><td>
		
   <p>
   
	 Items exist, for which there are transactions that are associated with warehouses on multiple sites, and for which warehouse is not a physical dimension. These transactions cannot be updated, as this may result in negative inventory on some sites.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 Inventory transactions for items which belong to the validated dimension group are spanning across multiple sites.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 Change the dimension group for these items to include warehouse as a physical dimension.
  </p>
  </td></tr>
            </table>

  


