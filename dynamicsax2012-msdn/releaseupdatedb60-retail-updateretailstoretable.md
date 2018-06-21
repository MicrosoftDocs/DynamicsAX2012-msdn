---
title: ReleaseUpdateDB60_Retail.updateRetailStoreTable
TOCTitle: ReleaseUpdateDB60_Retail.updateRetailStoreTable
ms:assetid: 862faee8-a5ee-7003-44a2-cc9ac5a74bb2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686051(v=AX.60)
ms:contentKeyID: 49709502
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.updateRetailStoreTable [AX 2012]


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
<td><p>updateRetailStoreTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the &lt;c&gt;Dimensions&lt;/c&gt; field to &lt;c&gt;DefaultDimension&lt;/c&gt; in &lt;c&gt;RetailStoreTable&lt;/c&gt; table. Updates the &lt;c&gt;roundingAccount&lt;/c&gt; field to &lt;c&gt;RoundingAccountLedgerDimension&lt;/c&gt; in &lt;c&gt;RetailStoreTable&lt;/c&gt; table.</p></td>
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
<td><p>DEL_RBOSTORETABLE</p></td>
</tr>
<tr class="even">
<td><p>DEL_RETAILASSORTMENTITEMLIST</p></td>
</tr>
<tr class="odd">
<td><p>DEL_RETAILASSORTMENTSTORELIST</p></td>
</tr>
<tr class="even">
<td><p>DEL_RETAILUPGRADEDSTRINGID</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONATTRIBUTE</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONATTRIBUTEDIRCATEGORY</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONATTRIBUTELEVELVALUE</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONATTRIBUTESET</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONATTRIBUTESETITEM</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONATTRIBUTEVALUE</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONATTRIBUTEVALUECOMBINATION</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONATTRIBUTEVALUECOMBINATIONSTATUS</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONATTRIBUTEVALUEGROUP</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONATTRIBUTEVALUEGROUPCOMBINATION</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONATTRIBUTEVALUEGROUPSTATUS</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONATTRIBUTEVALUESET</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONATTRIBUTEVALUESETITEM</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONFINANCIALTAG</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONHIERARCHY</p></td>
</tr>
<tr class="even">
<td><p>DIMENSIONHIERARCHYLEVEL</p></td>
</tr>
<tr class="odd">
<td><p>DIMENSIONVALUEGROUPJOURNALCONTROLSTATUS</p></td>
</tr>
<tr class="even">
<td><p>DIRPARTYCONTACTINFOVIEW</p></td>
</tr>
<tr class="odd">
<td><p>DIRPARTYLOCATION</p></td>
</tr>
<tr class="even">
<td><p>DIRPARTYLOCATIONROLE</p></td>
</tr>
<tr class="odd">
<td><p>DIRPARTYPOSTALADDRESSVIEW</p></td>
</tr>
<tr class="even">
<td><p>FINANCIALTAGCATEGORY</p></td>
</tr>
<tr class="odd">
<td><p>LEDGERPARAMETERS</p></td>
</tr>
<tr class="even">
<td><p>LOGISTICSELECTRONICADDRESS</p></td>
</tr>
<tr class="odd">
<td><p>LOGISTICSLOCATION</p></td>
</tr>
<tr class="even">
<td><p>LOGISTICSPOSTALADDRESS</p></td>
</tr>
<tr class="odd">
<td><p>MAINACCOUNT</p></td>
</tr>
<tr class="even">
<td><p>OMHIERARCHYTYPE</p></td>
</tr>
<tr class="odd">
<td><p>OMOPERATINGUNIT</p></td>
</tr>
<tr class="even">
<td><p>RETAILASSORTMENTCHANNELLINE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILASSORTMENTPRODUCTLINE</p></td>
</tr>
<tr class="even">
<td><p>RETAILASSORTMENTTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCHANNELTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILSTORETABLE</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

