---
title: ReleaseUpdateTransformDB50_Admin.perfomanceBoostingHint Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Admin.perfomanceBoostingHint Upgrade Script
ms:assetid: 63b81eed-8665-1201-d717-f1ab47334f38
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719140(v=AX.60)
ms:contentKeyID: 49708679
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Admin.perfomanceBoostingHint Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Admin</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>perfomanceBoostingHint</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Reminds the user to run the performance-boosting SQL scripts before preprocessing upgrade.</p></td>
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
<td><p>Administration</p></td>
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
   
	 During Preprocessing, updating the shadow tables’ statistics increases performance significantly. We should have a mechanism to run these scripts (direct SQL) as part of the preprocessing upgrade. That way, we can make sure customers are running the upgrade process on optimized tables.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
 Checked Conditions

  </p>
  </td><td>
		
   <p>
   
	 N/A
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
 Mitigation/How-to-fix

  </p>
  </td><td>
		
   <p>
   
	 Reminds user to run the performance-boosting SQL scripts before preprocessing upgrade.
  </p>
  </td></tr>
            </table>

  


