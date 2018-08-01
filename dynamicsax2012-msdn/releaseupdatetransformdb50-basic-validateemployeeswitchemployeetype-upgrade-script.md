---
title: ReleaseUpdateTransformDB50_Basic.validateEmployeeSwitchEmployeeType Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Basic.validateEmployeeSwitchEmployeeType Upgrade Script
ms:assetid: 50da62c7-f807-23c4-742a-5d7dc090134f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685510(v=AX.60)
ms:contentKeyID: 49708213
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Basic.validateEmployeeSwitchEmployeeType Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validateEmployeeSwitchEmployeeType</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates whether there are multiple associated records in the HRMPartyEmployeeRelationship table and the value in the EmployeeType field changes, for any given EmplTable record.</p></td>
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
<td><p>Human Resources</p></td>
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
   
	 Validates whether there are multiple associated records in the HRMPartyEmployeeRelationship table and the value in the EmployeeType field for changes, for any given EmplTable record.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 Checks whether EmployeeType field values are found for a given employee.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 The user is informed that only the EmployeeType value in the current record or latest record in the HRMPartyEmployeeRelationship table will be upgraded.
  </p>
  </td></tr>
            </table>

  


