---
title: ReleaseUpdateDB60_Retail.updateRetailConnOneCompanyTables
TOCTitle: ReleaseUpdateDB60_Retail.updateRetailConnOneCompanyTables
ms:assetid: e1b05e9e-ce84-f75b-5e68-7d662fe24859
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737331(v=AX.60)
ms:contentKeyID: 49711773
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.updateRetailConnOneCompanyTables 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>Post-sync upgrade script for RetailConn tables. Removes the records from the &lt;c&gt;retailConnParameters&lt;/c&gt; table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId is not equal to retailConnParameters.DEL_DataAreaId field. Removes the records from the &lt;c&gt;retailConnPreactionLog&lt;/c&gt; table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId is not equal to retailConnPreactionLog.DEL_DataAreaId field. Removes the records from the &lt;c&gt;retailConnSchedulerLog&lt;/c&gt; table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId is not equal to retailConnSchedulerLog.DEL_DataAreaId field. Removes the records from the &lt;c&gt;retailConnSchedulerReplicationCounter&lt;/c&gt; table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId is not equal to retailConnSchedulerReplicationCounter.DEL_DataAreaId field. Removes the records from the &lt;c&gt;retailConnStoreConnectProfile&lt;/c&gt; table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId is not equ</p></td>
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

  


