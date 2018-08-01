---
title: ReleaseUpdateTransformDB50_Basic.validateWorkflow Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Basic.validateWorkflow Upgrade Script
ms:assetid: 8f2f5e2a-92d4-d6be-a013-8fa0bc6f1d4a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736530(v=AX.60)
ms:contentKeyID: 49709718
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Basic.validateWorkflow Upgrade Script 


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
<td><p>validateWorkflow</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Checks for any active running instances of workflows and allows the user to cancel them.</p></td>
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
<td><p>Basic</p></td>
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
   
	 Validates whether at least one active workflow exists.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 Checks whether there are any records in the SysWorkfowTable table.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 All active workflows in the system must either complete or be cancelled prior to upgrading. A workflow can be cancelled by the user that submitted a record to workflow, the workflow owner, or the system administrator. Active workflows can also be cancelled during upgrade validation. Make sure that the batch processor that processes workflows is running.
  </p>
  </td></tr>
            </table>


## Remarks

The script checks to see the count of records in the SysWorkflowTable table. If the count is greater than 0, it assumes that there are active workflow instances and logs an error. It also gives the user the option to fix them by providing a custom form that allows a user to select multiple running workflow instances and cancel them.

  


