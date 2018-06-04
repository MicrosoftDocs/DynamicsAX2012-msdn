---
title: ReleaseUpdateDB60_Retail.updateRetailSharedParameters Upgrade Script
TOCTitle: ReleaseUpdateDB60_Retail.updateRetailSharedParameters Upgrade Script
ms:assetid: e3c951ff-2a48-8749-d0da-f5eb98fe3027
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737381(v=AX.60)
ms:contentKeyID: 49711822
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.updateRetailSharedParameters Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Retail</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateRetailSharedParameters</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the LocalStoreId field with the DEL_localStoreId field of the RetailParameters table. Updates the DefaultCustomerAddressBook field with the DEL_defaultCustomerAddressBook field of the RetailParameters table. Updates the ReplicateUsingPreaction field with the DEL_replicateUsingPreactions field of the RetailParameters table. Updates the NumberOfRetries field with the DEL_numberOfRetries field of RetailParameters table. Updates the MinutesBetweenTries field with the DEL_minutesBetweenTries field of the RetailParameters table. Updates the ItemLabelCreation field with the DEL_itemLabelCreation field of RetailParameters table. Updates the ShelfLabelCreation field with the DEL_shelfLabelCreation field of the RetailParameters table.</p></td>
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
<td><p>Retail</p></td>
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
<td><p>RETAILPARAMETERS</p></td>
</tr>
<tr class="even">
<td><p>RETAILSHAREDPARAMETERS</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

