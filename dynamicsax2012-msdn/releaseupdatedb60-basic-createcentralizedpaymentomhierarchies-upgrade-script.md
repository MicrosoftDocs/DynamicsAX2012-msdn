---
title: ReleaseUpdateDB60_Basic.createCentralizedPaymentOMHierarchies Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.createCentralizedPaymentOMHierarchies Upgrade Script
ms:assetid: 364ec456-336e-7367-dac7-df9089b9900c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685168(v=AX.60)
ms:contentKeyID: 49707621
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.createCentralizedPaymentOMHierarchies Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>createCentralizedPaymentOMHierarchies</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Converts the virtual companies that are using the centralized payments table collection and constructs organization model hierarchies by using the company accounts that are selected for the virtual company. The virtual companies are then deleted.</p></td>
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
<td><p>Accounts payable</p></td>
</tr>
<tr class="even">
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
<td><p>DataArea</p></td>
</tr>
<tr class="even">
<td><p>TableCollectionList</p></td>
</tr>
<tr class="odd">
<td><p>VirtualDataAreaList</p></td>
</tr>
<tr class="even">
<td><p>OMHierarchyType</p></td>
</tr>
<tr class="odd">
<td><p>OMHierarchyPurpose</p></td>
</tr>
<tr class="even">
<td><p>OMHierarchyRelationship</p></td>
</tr>
<tr class="odd">
<td><p>OMExplodedOrganizationSecurityGraph</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

