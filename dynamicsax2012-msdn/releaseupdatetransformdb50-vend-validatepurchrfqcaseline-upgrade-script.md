---
title: ReleaseUpdateTransformDB50_Vend.validatePurchRFQCaseLine Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Vend.validatePurchRFQCaseLine Upgrade Script
ms:assetid: 84113682-249c-bb2f-0e3c-ca7e5a94bb0b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685994(v=AX.60)
ms:contentKeyID: 49709447
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Vend.validatePurchRFQCaseLine Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validatePurchRFQCaseLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates and logs a message for the invalid dimensions value records in the PurchRFQCaseLine table where the dimension value in the PurchRFQCaseLine table is not empty.</p></td>
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
   
	 Validates the Dimension field in the PurchRFQCaseLine table.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 Verifies whether a valid Dimension field value exist in the PurchRFQCaseLine table.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 Creates or updates the valid the Dimension field value in the PurchRFQCaseLine table.
  </p>
  </td></tr>
            </table>


## Remarks

The upgrade script validates the dimension data is in place. This method is run at check upgrade readiness step in preprocessing upgrade checklist.

  


