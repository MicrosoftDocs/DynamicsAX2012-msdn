---
title: ReleaseUpdateDB60_Srm.initPurchReqControlRule Upgrade Script
TOCTitle: ReleaseUpdateDB60_Srm.initPurchReqControlRule Upgrade Script
ms:assetid: 7159aa2c-bbe3-eb17-a408-7d73f83f916a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685780(v=AX.60)
ms:contentKeyID: 49708980
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Srm.initPurchReqControlRule Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Srm</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>initPurchReqControlRule</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Prepares to initializes the values in the PurchReqControlSubmissionParameter record.</p></td>
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
<td><p>SRM</p></td>
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
<td><p>SysPolicyOrganization</p></td>
</tr>
<tr class="even">
<td><p>SysPolicySequence</p></td>
</tr>
<tr class="odd">
<td><p>SysPolicyOrganizationTypeSequence</p></td>
</tr>
<tr class="even">
<td><p>SysPolicyTypeSequence</p></td>
</tr>
<tr class="odd">
<td><p>SysPolicy</p></td>
</tr>
</tbody>
</table>


## Remarks

A new PurchReqControlSubmissionParameter table has been introduced to validate whether a purchase requisition can be submitted to workflow. This method inserts base records into policy framework table if not already inserted and then calls the CreatePurchReqControlRule class.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

