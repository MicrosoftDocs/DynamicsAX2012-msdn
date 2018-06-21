---
title: ReleaseUpdateDB60_Retail.allowNoDupRetailConnTablesIdx
TOCTitle: ReleaseUpdateDB60_Retail.allowNoDupRetailConnTablesIdx
ms:assetid: 99792c1b-60f1-947d-05d3-2d44ff3f18fc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686272(v=AX.60)
ms:contentKeyID: 49709974
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.allowNoDupRetailConnTablesIdx [AX 2012]


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
<td><p>allowNoDupRetailConnTablesIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Post-sync script to enable unique index on the RetailConn tables. Updates the index &lt;c&gt;NameIdx&lt;/c&gt; in the table &lt;c&gt;RetailConnAOSProfile&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;ProfileIdx&lt;/c&gt; in the table &lt;c&gt;RetailConnAOSProfile&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;NameIdx&lt;/c&gt; in the table &lt;c&gt;RetailConnConnectionProfile&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;NameIdx&lt;/c&gt; in the table &lt;c&gt;RetailConnCustomConnectionProfile&lt;/c&gt; to no allow duplicate records. Updates the index &lt;c&gt;ProfileIdx&lt;/c&gt; in the table &lt;c&gt;RetailConnCustomConnectionProfile&lt;/c&gt; to no allow duplicate records. Updates the index &lt;c&gt;NameIdx&lt;/c&gt; in the table &lt;c&gt;RetailConnDatabaseProfile&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;ProfileIdx&lt;/c&gt; in the table &lt;c&gt;RetailConnDatabaseProfile&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;groupIdx&lt;/c&gt; in the table &lt;c&gt;RetailConnDistributionGroup&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;groupLocation</p></td>
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

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

