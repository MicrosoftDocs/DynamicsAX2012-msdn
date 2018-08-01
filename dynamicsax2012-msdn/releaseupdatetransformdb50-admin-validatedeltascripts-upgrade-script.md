---
title: ReleaseUpdateTransformDB50_Admin.validateDeltaScripts Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Admin.validateDeltaScripts Upgrade Script
ms:assetid: b4f7e9de-688f-945c-aa84-4eede4115619
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736978(v=AX.60)
ms:contentKeyID: 49710661
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Admin.validateDeltaScripts Upgrade Script 


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
<td><p>validateDeltaScripts</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Detects all transformations that have a source table and do not have a delta script.</p></td>
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
   
	 The framework is not checking for the scenario where a developer writes a transformation that has a Live Script but not a Delta or Single User mode scripts. The issue here is that users might run through preprocessing without getting any kind of message. Once they get to Bulk Copy, the source table of the transformation will be set to the waiting state indefinitely. It is not until then that they will realize they need to write a Delta or Single User Mode script for that transformation.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 Scans through all transformations to make sure each of them has at least one delta script.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 Create a delta script for the transformation.
  </p>
  </td></tr>
            </table>

  


