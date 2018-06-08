---
title: ReleaseUpdateDB60_Basic.updateDirPartyTableForCustVend_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateDirPartyTableForCustVend_BR Upgrade Script
ms:assetid: 8d451448-0fb8-943f-645e-bf108b2210cb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736477(v=AX.60)
ms:contentKeyID: 49709667
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateDirPartyTableForCustVend\_BR Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateDirPartyTableForCustVend_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>It defines the right party for customers and vendors according to their properties.</p></td>
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
<td><p>DirPartyTable</p></td>
</tr>
<tr class="even">
<td><p>DirPerson</p></td>
</tr>
<tr class="odd">
<td><p>DirPersonName</p></td>
</tr>
<tr class="even">
<td><p>DirOrganization</p></td>
</tr>
<tr class="odd">
<td><p>DirOrganizationName</p></td>
</tr>
<tr class="even">
<td><p>CustTable</p></td>
</tr>
<tr class="odd">
<td><p>VendTable</p></td>
</tr>
<tr class="even">
<td><p>DirPartyLocation</p></td>
</tr>
<tr class="odd">
<td><p>DirPartyLocationRole</p></td>
</tr>
<tr class="even">
<td><p>BrazilParameters</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade organizes the customers and vendors into the proper parties according to their properties such as fiscal information and party type.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

