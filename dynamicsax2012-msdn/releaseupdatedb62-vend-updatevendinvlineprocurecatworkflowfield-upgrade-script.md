---
title: ReleaseUpdateDB62_Vend.updateVendInvLineProcureCatWorkflowField Upgrade Script
TOCTitle: ReleaseUpdateDB62_Vend.updateVendInvLineProcureCatWorkflowField Upgrade Script
ms:assetid: 3d6a0175-3382-a1da-6a49-a631a129b03d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn702718(v=AX.60)
ms:contentKeyID: 65236174
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_Vend.updateVendInvLineProcureCatWorkflowField Upgrade Script 


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
<td><p>updateVendInvLineProcureCatWorkflowField</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Workflow information for the ProcurementCategory field for the VendInvoiceLine table.</p></td>
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
<td><p>ExpressionElement</p></td>
</tr>
<tr class="even">
<td><p>ExpressionPredicate</p></td>
</tr>
</tbody>
</table>


## Remarks

The upgrade script converts existing data in the ExpressionElement and ExpressionPredicate tables that are related to the VendInvoiceLine.ProcurementCategory field. The Equals operator is converted to an IsAt operator. The NotEquals operator is converted to the grouped predicate of (IsAbove OR IsBelow).

  


