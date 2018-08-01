---
title: ReleaseUpdateTransformDB50_HCM.validateHRMCompFixedEmpl Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_HCM.validateHRMCompFixedEmpl Upgrade Script
ms:assetid: fe144b7c-4da5-03a5-bad2-71858dea31ee
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720151(v=AX.60)
ms:contentKeyID: 49712456
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_HCM.validateHRMCompFixedEmpl Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_HCM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validateHRMCompFixedEmpl</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates whether the account and dimension reference data is in place for the account and dimension fields in the table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Upgrade readiness scripts</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>5.0</p></td>
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
   
	 Validates the Dimension field.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 Verifies that the Dimension values exist in the Dimensions table
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 Create the corresponding Dimensions record or update the reference in the HRMCompFixedEmpl table.
  </p>
  </td></tr>
            </table>

  


