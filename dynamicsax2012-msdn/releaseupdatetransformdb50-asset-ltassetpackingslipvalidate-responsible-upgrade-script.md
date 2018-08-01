---
title: ReleaseUpdateTransformDB50_Asset.ltAssetPackingSlipValidate_Responsible Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Asset.ltAssetPackingSlipValidate_Responsible Upgrade Script
ms:assetid: 7bd43b88-324b-a060-edb5-a6451097607c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719455(v=AX.60)
ms:contentKeyID: 49709245
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Asset.ltAssetPackingSlipValidate\_Responsible Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Asset</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>ltAssetPackingSlipValidate_Responsible</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates a string value of the &lt;c&gt;ResponsibleTo&lt;/c&gt; and &lt;c&gt;ResponsibleFrom&lt;/c&gt; fields in &lt;c&gt;LtAssetPackingSlip&lt;/c&gt; table and verifies whether it is actually a valid user in the system.</p></td>
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
<td><p>Fixed Asset</p></td>
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
<td><p>VendInvoiceTrans</p></td>
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
   
	 Validates a string value of the &lt;c&gt;ResponsibleTo&lt;/c&gt; and &lt;c&gt;ResponsibleFrom&lt;/c&gt; fields in &lt;c&gt;LtAssetPackingSlip&lt;/c&gt; table
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 Whether the values entered in the fields are valid.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 User will have to recreate missing values or update the corresponding record in &lt;c&gt;LtAssetPackingSlip&lt;/c&gt; table
  </p>
  </td></tr>
            </table>

  


