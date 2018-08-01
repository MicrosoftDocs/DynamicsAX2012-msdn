---
title: ReleaseUpdateTransformDB50_EnterprisePortl.webControlValidate Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_EnterprisePortl.webControlValidate Upgrade Script
ms:assetid: 7da8c9b3-0236-4a11-21a9-dfffc8b43847
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719499(v=AX.60)
ms:contentKeyID: 49709289
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_EnterprisePortl.webControlValidate Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_EnterprisePortl</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>webControlValidate</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Checks source files of web controls for references to the Microsoft.Dynamics.Portal.Application.Proxy unsupported namespace. Any webcontrol using this namespace is logged so the source files can be revised.</p></td>
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
<tr class="even">
<td><p>Basic</p></td>
</tr>
<tr class="odd">
<td><p>Expense management</p></td>
</tr>
<tr class="even">
<td><p>Human Resources</p></td>
</tr>
<tr class="odd">
<td><p>Production</p></td>
</tr>
<tr class="even">
<td><p>Service</p></td>
</tr>
<tr class="odd">
<td><p>SRM</p></td>
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
   
	 There are web controls that reference a namespace that is not supported in Microsoft Dynamics AX 2012. See detail messages for the list of web controls and namespaces. Revise each one as appropriate.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 This script scans through each webcontrol in the AOT and checks the namespace references in code for a reference to the unsupported namespace.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 Revise the web control code to not reference the unsupported namespace.
  </p>
  </td></tr>
            </table>

  


