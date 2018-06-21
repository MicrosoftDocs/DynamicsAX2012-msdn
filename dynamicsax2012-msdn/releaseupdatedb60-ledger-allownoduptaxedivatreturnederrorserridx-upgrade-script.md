---
title: ReleaseUpdateDB60_Ledger.allowNoDupTaxEdivatReturnedErrorsErrIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupTaxEdivatReturnedErrorsErrIdx Upgrade Script
ms:assetid: da35dcc7-83c2-d69b-ad62-98b666d30822
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737163(v=AX.60)
ms:contentKeyID: 49711606
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupTaxEdivatReturnedErrorsErrIdx Upgrade Script [AX 2012]


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
<td><p>allowNoDupTaxEdivatReturnedErrorsErrIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ErrorIdx index in the TaxEdivatReturnedErrors table not to allow for duplicate records.</p></td>
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
<td><p>TaxEdivatReturnedErrors</p></td>
</tr>
</tbody>
</table>


## Remarks

The name of this method is truncated from allowNoDupTaxEdivatReturnedErrorsErrorIdx to allowNoDupTaxEdivatReturnedErrorsErrIdx. After updating the TaxEdivatGeneral surrogate key field with the value of the RecId field of the TaxEdivatGeneral table, the ErrorIdx index is reset not to allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

