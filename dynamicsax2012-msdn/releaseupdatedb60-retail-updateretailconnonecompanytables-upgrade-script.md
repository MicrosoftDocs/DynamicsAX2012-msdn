---
title: ReleaseUpdateDB60_Retail.updateRetailConnOneCompanyTables Upgrade Script
TOCTitle: ReleaseUpdateDB60_Retail.updateRetailConnOneCompanyTables Upgrade Script
ms:assetid: 6aa597ab-e7ea-1bc3-8062-0e877c0ba855
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685660(v=AX.60)
ms:contentKeyID: 49708862
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.updateRetailConnOneCompanyTables Upgrade Script 


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
<td><p>updateRetailConnOneCompanyTables</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Post-sync upgrade script for the RetailConn tables. Removes the records from the retailConnParameters table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId field is not equal to the retailConnParameters.DEL_DataAreaId field. Removes the records from the retailConnPreactionLog table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId field is not equal to retailConnPreactionLog.DEL_DataAreaId field. Removes the records from the retailConnSchedulerLog table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId field is not equal to the retailConnSchedulerLog.DEL_DataAreaId field. Removes the records from the retailConnSchedulerReplicationCounter table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId field is not equal to the retailConnSchedulerReplicationCounter.DEL_DataAreaId field. Removes the records from the retailConnStoreConnectProfile table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId field is not equal.</p></td>
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
<td><p>DEL_RETAILDEFAULTCOMPANYFORPARAMETERSUPG</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNPARAMETERS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNPREACTIONLOG</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNSCHEDULERLOG</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNSCHEDULERREPLICATIONCOUNTER</p></td>
</tr>
<tr class="even">
<td><p>DEL_RETAILCONNCHILDLOCATIONS</p></td>
</tr>
<tr class="odd">
<td><p>DEL_RETAILCONNDISTRIBUTIONINCEXCLIST</p></td>
</tr>
<tr class="even">
<td><p>DEL_RETAILCONNINITIALREPLICATIONCOUNTER</p></td>
</tr>
<tr class="odd">
<td><p>DEL_RETAILCONNSCHEDULERJOBTYPE</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

