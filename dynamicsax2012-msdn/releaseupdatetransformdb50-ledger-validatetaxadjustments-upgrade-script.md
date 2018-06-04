---
title: ReleaseUpdateTransformDB50_Ledger.validateTaxAdjustments Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Ledger.validateTaxAdjustments Upgrade Script
ms:assetid: 9a36ccea-cf4c-fa58-06c9-75c7707bb089
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686296(v=AX.60)
ms:contentKeyID: 49709999
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Ledger.validateTaxAdjustments Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validateTaxAdjustments</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates the TaxWorkRegulation table does not contain sales order tax adjustments.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Upgrade readiness scripts</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
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
   
	 Verifies that the TaxWorkRegulation table does not contain sales order tax adjustments.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 Checks that the HeadingTableId field value in the TaxWorkRegulation table does not equal to the SalesTable table ID.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 Delete the tax adjustments for the sales order or post the sales order invoice.
  </p>
  </td></tr>
            </table>


## Remarks

New tax adjustments for sales order invoices in the upgraded version will be stored at the invoice line level. Existing Microsoft Dynamics AX 2009 tax adjustments stored at the invoice document level in the TaxWorkRegulation table will not be used after the upgrade.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

