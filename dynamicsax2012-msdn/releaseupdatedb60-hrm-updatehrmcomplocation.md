---
title: ReleaseUpdateDB60_HRM.updateHRMCompLocation
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMCompLocation
ms:assetid: 353f68e5-5a09-4bcb-c5e7-9bdfb0d4b2f3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685141(v=AX.60)
ms:contentKeyID: 49707594
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMCompLocation [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_HRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateHRMCompLocation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>updates the &lt;c&gt;Location&lt;/c&gt; field of the &lt;c&gt;HRMCompLocation&lt;/c&gt; table.</p></td>
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
<td><p>HRM</p></td>
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
<td><p>LogisticsAddressZipCode</p></td>
</tr>
<tr class="even">
<td><p>LogisticsAddresssCity</p></td>
</tr>
<tr class="odd">
<td><p>HRMCompLocation</p></td>
</tr>
<tr class="even">
<td><p>LogisticsLocation</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsPostalAddress</p></td>
</tr>
</tbody>
</table>


## Remarks

creates new record in the \<c\>LogisticsLocation\</c\> table and the \<c\>LogisticsPostalAddress\</c\> table based on address information in the \<c\>HRMCompLocation\</c\> table; and update the \<c\>Location\</c\> field of the \<c\>HRMCompLocation\</c\> table with the corresponding value of the \<c\>RecId\</c\> field of the \<c\>LogisticsLocation\</c\> table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

