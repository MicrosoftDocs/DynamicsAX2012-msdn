---
title: ReleaseUpdateTransformDB40_LedgerTrx.validateTaxTrans Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_LedgerTrx.validateTaxTrans Upgrade Script
ms:assetid: c374054e-0ed2-40e0-8a23-d50b17b1646c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686847(v=AX.60)
ms:contentKeyID: 49711044
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_LedgerTrx.validateTaxTrans Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_LedgerTrx</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validateTaxTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Performs validation to ensure that the records in TaxTrans table have valid values for the AccountNum and Dimension fields.</p></td>
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
<td><p>General ledger</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Affected Tables</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LedgerTrans</p></td>
</tr>
<tr class="even">
<td><p></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
</tr>
<tr class="even">
<td><p></p></td>
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
   
	 The TaxTrans table contains a record with an invalid value for the AccountNum or Dimension fields. The AccountNum and Dimension values must exist in the LedgerTable table in order for the upgrade to proceed.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 Checks to ensure the AccountNum, OperationAccount, TaxOffsetAccountUseTax and Dimension fields contain values found in LedgerTable table.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 Modify the existing TaxTrans record to hold a valid value for the AccountNum, OperationAccount, TaxOffsetAccountUseTax, and Dimension fields. These values must exist in the LedgerTable table.
  </p>
  </td></tr>
            </table>

  


