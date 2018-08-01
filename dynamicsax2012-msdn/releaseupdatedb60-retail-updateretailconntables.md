---
title: ReleaseUpdateDB60_Retail.updateRetailConnTables
TOCTitle: ReleaseUpdateDB60_Retail.updateRetailConnTables
ms:assetid: 8f373e23-3654-dc5c-25f7-8655567302dc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736529(v=AX.60)
ms:contentKeyID: 49709719
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.updateRetailConnTables 


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
<td><p>updateRetailConnTables</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Post-sync upgrade script for RetailConn tables. Removes the records from the &lt;c&gt;RetailConnAOSProfile&lt;/c&gt; table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId is not equal to RetailConnAOSProfile.DEL_DataAreaId field. Removes the records from the &lt;c&gt;retailConnConnectionProfile&lt;/c&gt; table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId is not equal to retailConnConnectionProfile.DEL_DataAreaId field. Removes the records from the &lt;c&gt;retailConnCustomConnectionProfile&lt;/c&gt; table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId is not equal to retailConnCustomConnectionProfile.DEL_DataAreaId field. Removes the records from the &lt;c&gt;retailConnDatabaseProfile&lt;/c&gt; table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId is not equal to retailConnDatabaseProfile.DEL_DataAreaId field. Removes the records from the &lt;c&gt;retailConnDistributionGroup&lt;/c&gt; table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId is n</p></td>
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
<td><p>DEL_RETAILCONNCHILDLOCATIONS</p></td>
</tr>
<tr class="even">
<td><p>DEL_RETAILCONNDISTRIBUTIONINCEXCLIST</p></td>
</tr>
<tr class="odd">
<td><p>DEL_RETAILCONNINITIALREPLICATIONCOUNTER</p></td>
</tr>
<tr class="even">
<td><p>DEL_RETAILCONNSCHEDULERJOBTYPE</p></td>
</tr>
<tr class="odd">
<td><p>DEL_RETAILDEFAULTCOMPANYFORPARAMETERSUPG</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNAOSPROFILE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNCONNECTIONPROFILE</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNCUSTOMCONNECTIONPROFILE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNDATABASEPROFILE</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNDISTRIBUTIONGROUP</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNDISTRIBUTIONGROUPMEMBER</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNDISTRIBUTIONLIST</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNDISTRIBUTIONLOCATION</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNDISTRIBUTIONSUBGROUP</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNDISTRIBUTIONSUBLOCATIONTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNPARAMETERS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNPREACTIONLOG</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNSCHEDULERDISTRIBUTIONFILTER</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNSCHEDULERLOG</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNSCHEDULERREPLICATIONCOUNTER</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNSTORECONNECTPROFILE</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNSTORECONNECTUPLOADOPTIONS</p></td>
</tr>
</tbody>
</table>

  


