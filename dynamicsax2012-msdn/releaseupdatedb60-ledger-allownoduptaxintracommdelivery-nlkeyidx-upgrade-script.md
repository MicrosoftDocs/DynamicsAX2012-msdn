---
title: ReleaseUpdateDB60_Ledger.allowNoDupTaxIntraCommDelivery_NLKeyIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupTaxIntraCommDelivery_NLKeyIdx Upgrade Script
ms:assetid: 99562320-c932-bdf6-339e-ea04bd9b53bc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686266(v=AX.60)
ms:contentKeyID: 49709969
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupTaxIntraCommDelivery\_NLKeyIdx Upgrade Script 


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
<td><p>allowNoDupTaxIntraCommDelivery_NLKeyIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the KeyIdx index in the TaxIntraCommDelivery_NL table not to allow for duplicate records.</p></td>
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
<td><p>TaxIntraCommDelivery_NL</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the TaxIntraCommTable\_NL surrogate key field with the value of the RecId field of the TaxIntraCommTable\_NL table, the KeyIdx index is reset not to allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

