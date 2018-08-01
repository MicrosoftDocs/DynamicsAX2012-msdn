---
title: ReleaseUpdateTransformDB40_Prod.validateWrkCtrTableEmplIdField Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Prod.validateWrkCtrTableEmplIdField Upgrade Script
ms:assetid: 8382e39a-7767-10d3-5012-bd0e0eab0287
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685985(v=AX.60)
ms:contentKeyID: 49709438
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Prod.validateWrkCtrTableEmplIdField Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>validateWrkCtrTableEmplIdField</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates if employees referenced by work centers are of type 'Human Resource'.</p></td>
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
   
	 The work center is linked to an employee even though the work center is not of type 'Human resource'. The employee information of the work center will be lost during upgrade.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 Work centers of type other than 'Human resource' in which the employee ID is specified.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 Change the work center type to 'Human resource' to avoid having the employee information removed during upgrade.
  </p>
  </td></tr>
            </table>

  


