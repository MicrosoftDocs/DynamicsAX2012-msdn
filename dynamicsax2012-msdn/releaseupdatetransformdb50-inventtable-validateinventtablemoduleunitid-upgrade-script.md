---
title: ReleaseUpdateTransformDB50_InventTable.validateInventTableModuleUnitId Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_InventTable.validateInventTableModuleUnitId Upgrade Script
ms:assetid: 6d4a4f81-11d1-b168-5979-226ae8bab4e5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685702(v=AX.60)
ms:contentKeyID: 49708903
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_InventTable.validateInventTableModuleUnitId Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_InventTable</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validateInventTableModuleUnitId</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Verifies that InventTable records with related InventTrans records have an assigned UnitId value.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Upgrade readiness scripts</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>Inventory management</p></td>
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
<td><p>InventTrans</p></td>
</tr>
<tr class="even">
<td><p>InventTableModule</p></td>
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
   
	 InventTableModule.unitId
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 unit assigned
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 assingn a unit
  </p>
  </td></tr>
            </table>


## Remarks

This is a pre-validation script.

  


