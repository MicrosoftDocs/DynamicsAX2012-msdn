---
title: ReleaseUpdateDB60_Retail.updateRetailConnTables Upgrade Script
TOCTitle: ReleaseUpdateDB60_Retail.updateRetailConnTables Upgrade Script
ms:assetid: 1310eae6-9804-b345-bf6d-7a4a57a16be0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718475(v=AX.60)
ms:contentKeyID: 49706760
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.updateRetailConnTables Upgrade Script 


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
<td><p>updateRetailConnTables</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Removes the records from the RetailConnAOSProfile table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId field is not equal to the RetailConnAOSProfile.DEL_DataAreaId field. Removes records from the RetailConnConnectionProfile table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId field is not equal to the RetailConnConnectionProfile.DEL_DataAreaId field. Removes the records from the RetailConnCustomConnectionProfile table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId is not equal to the RetailConnCustomConnectionProfile.DEL_DataAreaId field. Removes the records from the RetailConnDatabaseProfile table, if the DEL_RetailDefaultCompanyForParametersUpg.selectedDataAreaId is not equal to RetailConnDatabaseProfile.DEL_DataAreaId field.</p></td>
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

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

