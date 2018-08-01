---
title: ReleaseUpdateTransformDB40_Ledger.validateTaxAdjustments Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Ledger.validateTaxAdjustments Upgrade Script
ms:assetid: a23ab5a5-8619-459b-6e5c-4ed82fbd4e9f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736743(v=AX.60)
ms:contentKeyID: 49710175
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Ledger.validateTaxAdjustments Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validateTaxAdjustments</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates the TaxWorkRegulation table does not contain sales order or purchase order tax adjustments.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Upgrade readiness scripts</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
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
<tr class="even">
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
   
	 Verifies the TaxWorkRegulation table does not contain sales order or purchase order tax adjustments.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 Checks that the HeadingTableId field value in the TaxWorkRegulation table does not equal to the SalesTable or the PurchTable table ID.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 Delete the tax adjustments or post the sales order or purchase order invoice.
  </p>
  </td></tr>
            </table>


## Remarks

New tax adjustments for sales order and purchase order invoices in the upgraded version will be stored at the invoice line level. Existing Microsoft Dynamics AX 4.0 tax adjustments stored at the invoice document level in the TaxWorkRegulation table will not be used after the upgrade.

  


