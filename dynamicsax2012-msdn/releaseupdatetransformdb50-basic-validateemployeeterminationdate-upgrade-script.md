---
title: ReleaseUpdateTransformDB50_Basic.validateEmployeeTerminationDate Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Basic.validateEmployeeTerminationDate Upgrade Script
ms:assetid: 9811d341-b949-78b1-5726-072bfdb07ea9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686233(v=AX.60)
ms:contentKeyID: 49709937
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Basic.validateEmployeeTerminationDate Upgrade Script 


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
<td><p>validateEmployeeTerminationDate</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates whether there are any records in the HRMPartyEmployeeRelationship table in which the TerminationDate field is not populated and the corresponding status field of the EmplTable record is equal to the HRMEmplStatus::Resigned enumeration value.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Upgrade readiness scripts</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 2009</p></td>
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
   
	 Validates whether there are any records in the HRMPartyEmployeeRelationship table in which the TerminationDate field is not populated and the corresponding status field of the EmplTable record is equal to the HRMEmplStatus::Resigned enumeration value.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
			 
		
   <p>
   
	 HRMPartyEmployeeRelationship.TerminationDate != DateTimeUtil::minValue() &amp;&amp; EmplTable.status == HRMRmplStatus::Resigned
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 The user is informed that the TerminationDate field in the HRMPartyEmployeeRelationship table needs to be set.
  </p>
  </td></tr>
            </table>

  


