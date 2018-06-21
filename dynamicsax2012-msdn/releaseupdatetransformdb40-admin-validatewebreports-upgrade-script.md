---
title: ReleaseUpdateTransformDB40_Admin.validateWebReports Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Admin.validateWebReports Upgrade Script
ms:assetid: a1484012-215c-8eff-df3e-6ae8b0ab24e6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736725(v=AX.60)
ms:contentKeyID: 49710157
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Admin.validateWebReports Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Admin</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validateWebReports</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Checks if any web reports exist in the AOT. If so, it logs a warning that Microsoft Dynamics AX 2012 uses SQL Server Reporting Services as the primary reporting infrastructure, and that the X++ reporting framework is a legacy system.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Upgrade readiness scripts</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>Product Builder</p></td>
</tr>
<tr class="even">
<td><p>Production</p></td>
</tr>
<tr class="odd">
<td><p>Project</p></td>
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
   
	 Checks if any web reports exist in the AOT. Microsoft Dynamics AX 2012 uses SQL Server Reporting Services as the primary reporting infrastructure. The X++ reporting framework is the legacy reporting system. The X++ reporting framework remains for special reporting requirements and to simplify migration. 
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 Checks the web reports path in the AOT to see if any webreports exist.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 Phase out the use of the X++ reporting framework in favor of the SQL Server Reporting Services.
  </p>
  </td></tr>
            </table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

