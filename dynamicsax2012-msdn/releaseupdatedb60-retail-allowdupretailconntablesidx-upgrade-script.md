---
title: ReleaseUpdateDB60_Retail.allowDupRetailConnTablesIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Retail.allowDupRetailConnTablesIdx Upgrade Script
ms:assetid: 5f026c73-0529-d839-b3a0-df4bfe816e76
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719021(v=AX.60)
ms:contentKeyID: 49708561
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.allowDupRetailConnTablesIdx Upgrade Script 


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
<td><p>allowDupRetailConnTablesIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the NameIdx index in the RetailConnAOSProfile table to allow duplicate records. Updates the ProfileIdx index in the RetailConnAOSProfile table to allow duplicate records. Updates the NameIdx index in the RetailConnConnectionProfile table to allow duplicate records. Updates the NameIdx index in the RetailConnCustomConnectionProfile table to allow duplicate records. Updates the ProfileIdx index in the RetailConnCustomConnectionProfile table to allow duplicate records. Updates the NameIdx index in the RetailConnDatabaseProfile table to allow duplicate records. Updates the ProfileIdx index in the RetailConnDatabaseProfile table to allow duplicate records. Updates the groupIdx index in the RetailConnDistributionGroup table to allow duplicate records.</p></td>
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
<td><p>RETAILCONNAOSPROFILE</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNCONNECTIONPROFILE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNCUSTOMCONNECTIONPROFILE</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNDATABASEPROFILE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNDISTRIBUTIONGROUP</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNDISTRIBUTIONGROUPMEMBER</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNDISTRIBUTIONLIST</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNDISTRIBUTIONLOCATION</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNDISTRIBUTIONSUBGROUP</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNDISTRIBUTIONSUBLOCATIONTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNPARAMETERS</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNPREACTIONLOG</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNSCHEDULERDISTRIBUTIONFILTER</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNSCHEDULERLOG</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNSCHEDULERREPLICATIONCOUNTER</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONNSTORECONNECTPROFILE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNSTORECONNECTUPLOADOPTIONS</p></td>
</tr>
</tbody>
</table>

  


