---
title: ReleaseUpdateTransformDB50_Vend.validateVendInvoiceTrans_Jour Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Vend.validateVendInvoiceTrans_Jour Upgrade Script
ms:assetid: 942a7760-d13d-ad57-ab66-9a41ec4d24e3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686137(v=AX.60)
ms:contentKeyID: 49709841
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Vend.validateVendInvoiceTrans\_Jour Upgrade Script [AX 2012]


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
<td><p>validateVendInvoiceTrans_Jour</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates the relation between the VendInvoiceTrans and VendInvoiceJour table.</p></td>
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
   
	 Some of the VendInvoiceTrans records do not link to the VendInvoiceJour records.
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Checked Conditions
          
  </p>
  </td><td>
		
   <p>
   
	 vendInvoiceJour.InvoiceId== vendInvoiceTrans.InvoiceId &amp;&amp;  vendInvoiceJour.InvoiceDate == vendInvoiceTrans.InvoiceDate &amp;&amp;         vendInvoiceJour.numberSequenceGroup  == vendInvoiceTrans.numberSequenceGroup &amp;&amp;         vendInvoiceJour.InternalInvoiceId    == vendInvoiceTrans.InternalInvoiceId &amp;&amp;         vendInvoiceJour.PurchId == vendInvoiceTrans.PurchId
  </p>
  </td></tr>
              <tr><td>
		
   <p>
   
	 
            Mitigation/How-to-fix
          
  </p>
  </td><td>
		
   <p>
   
	 Make sure the VendInvoiceTrans records do belong to the VendInvoiceJour records.
  </p>
  </td></tr>
            </table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

