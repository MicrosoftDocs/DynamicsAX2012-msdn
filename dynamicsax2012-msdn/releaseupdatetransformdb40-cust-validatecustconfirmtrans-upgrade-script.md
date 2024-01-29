﻿---
title: ReleaseUpdateTransformDB40_Cust.validateCustConfirmTrans Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Cust.validateCustConfirmTrans Upgrade Script
ms:assetid: 3b359f57-cfee-8259-9901-676c827f07c3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685276(v=AX.60)
ms:contentKeyID: 49707728
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Cust.validateCustConfirmTrans Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validateCustConfirmTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates whether the CustConfirmTrans table contains the records without existing dimensions.</p></td>
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
<td><p>Accounts receivable</p></td>
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
   
	 The records with invalid dimensions exist.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 The dimensions for the CustConfirmTrans record does not exist in the Dimensions table.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 Delete the records with invalid dimensions or create missing dimensions.
  </p>
  </td></tr>
            </table>


## Remarks

This is a validation script.

  

