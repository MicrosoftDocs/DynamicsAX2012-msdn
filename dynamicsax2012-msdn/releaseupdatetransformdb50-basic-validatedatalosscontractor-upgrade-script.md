---
title: ReleaseUpdateTransformDB50_Basic.validateDataLossContractor Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Basic.validateDataLossContractor Upgrade Script
ms:assetid: e739f40a-1797-90be-4b65-0db1db65ffcc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719801(v=AX.60)
ms:contentKeyID: 49711874
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Basic.validateDataLossContractor Upgrade Script 


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
<td><p>validateDataLossContractor</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validate if there are records in the EmplTable and HRMPartyEmployeeRelationship table that have the HRMEmployeeType::Contractor value in the hrmEmployeeType field.</p></td>
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
<td><p>CRM</p></td>
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
   
	 Validate if there are records in &lt;c&gt;EmplTable&lt;/c&gt; table and &lt;c&gt;HRMPartyEmployeeRelationship&lt;/c&gt; table which have HRMEmployeeType::Contractor in &lt;c&gt;hrmEmployeeType&lt;/c&gt; field.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 hrmPartyEmployeeRelationshipTable.hrmEmployeeType == HRMEmployeeType::Contrator
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 User is informed that some data related to records with Contractor type will be lost since the data model changes.
  </p>
  </td></tr>
            </table>

  


