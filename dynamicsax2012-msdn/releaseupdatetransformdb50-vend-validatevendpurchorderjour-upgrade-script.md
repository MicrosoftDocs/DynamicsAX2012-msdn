---
title: ReleaseUpdateTransformDB50_Vend.validateVendPurchOrderJour Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Vend.validateVendPurchOrderJour Upgrade Script
ms:assetid: 8b06a659-6ec0-f322-1bcc-581a76ebdef2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736420(v=AX.60)
ms:contentKeyID: 49709610
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Vend.validateVendPurchOrderJour Upgrade Script 


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
<td><p>validateVendPurchOrderJour</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates whether the PurchLine and VendPurchOrderTrans tables contain undeleted or duplicated records.</p></td>
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
<td><p>Accounts payable</p></td>
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
   
	 The records that should be deleted were not deleted.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 The PurchLine record with the same InventTransId value exists in the PurchLineDelete or SalesLine tables. The VendPurchOrderTrans record with the same InventTransId value but a different OrigPurchId value exists in the VendPurchOrderTransDup table. 
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 Deletes the orphan records.
  </p>
  </td></tr>
            </table>


## Remarks

This is a validation script.

  


