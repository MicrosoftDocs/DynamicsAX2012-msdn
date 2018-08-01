---
title: ReleaseUpdateDB60_Cust.updateCustPaymFormats_SE Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCustPaymFormats_SE Upgrade Script
ms:assetid: 90629091-a1a5-129f-f43c-da26388d072f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736560(v=AX.60)
ms:contentKeyID: 49709748
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCustPaymFormats\_SE Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCustPaymFormats_SE</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates records in the CustPaymModeTable and CustPaymModeSpec tables and deletes records from the CustPaymFormat table for obsolete Swedish payment formats.</p></td>
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
<td><p>CustPaymFormat</p></td>
</tr>
<tr class="even">
<td><p>CustPaymModeTable</p></td>
</tr>
<tr class="odd">
<td><p>CustPaymModeSpec</p></td>
</tr>
</tbody>
</table>


## Remarks

Two Swedish Customer payment formats, that is, Postgirot Autogiro (SE) and Bankgirot Automatisk avprickning (SE), are now obsolete. This script updates the CustPaymFormat payment formats, CustPaymModeTable methods of payment, and CustPaymModeSpec payment specification tables to remove references to these obsolete payment formats.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

