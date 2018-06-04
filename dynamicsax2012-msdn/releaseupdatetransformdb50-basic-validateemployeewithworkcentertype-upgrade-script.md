---
title: ReleaseUpdateTransformDB50_Basic.validateEmployeeWithWorkCenterType Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Basic.validateEmployeeWithWorkCenterType Upgrade Script
ms:assetid: 183a1a70-07ce-795d-b998-2335b8d92ef2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718599(v=AX.60)
ms:contentKeyID: 49706883
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Basic.validateEmployeeWithWorkCenterType Upgrade Script 


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
<td><p>validateEmployeeWithWorkCenterType</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates whether there are records in the HRMPartyEmployeeRelationship table and that the value in the EmployeeType field is the HRMEmployeeType::WorkCenter. enumeration value</p></td>
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
   
	 Validates whether there are records in the HRMPartyEmployeeRelationship table and that the value in the EmployeeType field is the HRMEmployeeType::WorkCenter enumeration value.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
			 
		
   <p>
   
	 HRMPartyEmployeeRelationship.EmployeeType == HRMEmployeeType::WorkCenter
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 The user is informed that the value of the EmployeeType field in the HRMPartyEmployeeRelationship table is equal to the HRMEmployeeType::WorkCenter enumeration value; the record will be upgraded as Employee type.
  </p>
  </td></tr>
            </table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

