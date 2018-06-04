---
title: ReleaseUpdateDB41_Basic.updateAddressRemitTo Upgrade Script
TOCTitle: ReleaseUpdateDB41_Basic.updateAddressRemitTo Upgrade Script
ms:assetid: 0b8fc087-3253-df62-520d-4cf038ee3013
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735652(v=AX.60)
ms:contentKeyID: 49706563
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Basic.updateAddressRemitTo Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateAddressRemitTo</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This scrip converts third party data from an acquired product, which enables users to create multiple Remit-To type addresses.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>DEL_Address</p></td>
</tr>
</tbody>
</table>


## Remarks

The conversion will retain the first, or lowest Record ID, Remit-To address found for each Vendor (AddrTableId = tablenum(VendTable), by changing the Type value to AddressType::RemitTo (10). When this is done, any remaining Addresses with Type=100 will have their Type value set to AddressType::None (0).

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

