---
title: ReleaseUpdateDB41_Basic.updateAddressRemitTo
TOCTitle: ReleaseUpdateDB41_Basic.updateAddressRemitTo
ms:assetid: ad131e0f-2c23-e85a-7963-ef386f4f5353
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686520(v=AX.60)
ms:contentKeyID: 49710475
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Basic.updateAddressRemitTo 


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
<td><p>Converts third party data from an acquired product, which allowed users to create multiple Remit-To type addresses.</p></td>
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

The conversion will retain the first Remit-To address that is found for each Vendor, by changing the type value to AddressType::RemitTo (10). When this is done, any remaining Addresses with Type=100 will have their type value set to AddressType::None (0).

  


