---
title: ReleaseUpdateDB60_Ledger.allowNoDupCustEinvoiceIntegrationPaymMod Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupCustEinvoiceIntegrationPaymMod Upgrade Script
ms:assetid: ae3fcfab-6b27-1af5-604b-a7be235a6b4a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686533(v=AX.60)
ms:contentKeyID: 49710488
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupCustEinvoiceIntegrationPaymMod Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupCustEinvoiceIntegrationPaymMod</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TypeStatusFromIdx index in the CustEinvoiceIntegrationPaymModeChg table not to allow for duplicate records.</p></td>
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
<td><p>CustEinvoiceIntegrationPaymModeChg</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the CustEinvoiceIntegrationTypeTable surrogate key field with the value of the record ID field of the CustEinvoiceIntegrationTypeTable table, the TypeStatusFromIdx index is reset not to allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

