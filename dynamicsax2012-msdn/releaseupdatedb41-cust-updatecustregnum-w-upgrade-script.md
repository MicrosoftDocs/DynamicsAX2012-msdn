---
title: ReleaseUpdateDB41_Cust.updateCustRegNum_W Upgrade Script
TOCTitle: ReleaseUpdateDB41_Cust.updateCustRegNum_W Upgrade Script
ms:assetid: d35fe3aa-5227-faf0-4648-5f1985ed81dd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686973(v=AX.60)
ms:contentKeyID: 49711423
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Cust.updateCustRegNum\_W Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCustRegNum_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the customer registration number field from the del_CustVendRegNum_EE and del_RegNumber_LV fields.</p></td>
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
<td><p>CustTable</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CustTable</p></th>
<th><p>To Table: CustTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_CustVendRegNum_EE</p></td>
<td><p>RegNum_W</p></td>
</tr>
<tr class="even">
<td><p>del_RegNumber_LV</p></td>
<td><p>RegNum_W</p></td>
</tr>
</tbody>
</table>

  


