---
title: ReleaseUpdateDB62_Vend.updateVendInvLineWorkFlowXPathQuery Upgrade Script
TOCTitle: ReleaseUpdateDB62_Vend.updateVendInvLineWorkFlowXPathQuery Upgrade Script
ms:assetid: 662db9de-c3cc-849c-3a47-3814b5ba8a42
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn702752(v=AX.60)
ms:contentKeyID: 65236208
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_Vend.updateVendInvLineWorkFlowXPathQuery Upgrade Script 


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB62_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateVendInvLineWorkFlowXPathQuery</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Workflow XPathQuery information for the ProcurementCategory field for the VendInvoiceLine table.</p></td>
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
<td><p>ExpressionTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The upgrade script converts existing data in the ExpressionTable table that is related to the VendInvoiceLine.ProcurementCategory field. Data in the ExpressionTable.XPathQuery field is updated to reflect the new expression. This script is dependent on the ReleaseUpdateDB62\_Vend.updateVendInvLineProcureCatWorkflowField script.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

