---
title: ReleaseUpdateDB60_Retail.allowNoDupRetailPosTablesIdx
TOCTitle: ReleaseUpdateDB60_Retail.allowNoDupRetailPosTablesIdx
ms:assetid: d887e0ed-617f-920a-2f16-1bf0c18212ef
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687120(v=AX.60)
ms:contentKeyID: 49711567
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.allowNoDupRetailPosTablesIdx 


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
<td><p>allowNoDupRetailPosTablesIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Post-sync script to enable unique index on the retail POS tables. Updates the index &lt;c&gt;LayoutId&lt;/c&gt; in the table &lt;c&gt;RetailFormLayout&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;profileIdx&lt;/c&gt; in the table &lt;c&gt;RetailFunctionalityProfile&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;profileIdx&lt;/c&gt; in the table &lt;c&gt;RetailHardwareProfile&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;PictureIdIdx&lt;/c&gt; in the table &lt;c&gt;RetailImages&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;keyboardIdx&lt;/c&gt; in the table &lt;c&gt;RetailKeyboardMappingTable&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;keyboardASCIIValueIdx&lt;/c&gt; in the table &lt;c&gt;RetailKeyboardMappingTrans&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;profileMapFromIdx&lt;/c&gt; in the table &lt;c&gt;RetailKeyMapping&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;OperationIdIdx&lt;/c&gt; in the table &lt;c&gt;RetailOperations&lt;/c&gt; to allow no duplicate records. Updates the index &lt;c&gt;Primary&lt;/c&gt; in the table &lt;c</p></td>
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
<td><p>RETAILFORMLAYOUT</p></td>
</tr>
<tr class="even">
<td><p>RETAILFUNCTIONALITYPROFILE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILHARDWAREPROFILE</p></td>
</tr>
<tr class="even">
<td><p>RETAILIMAGES</p></td>
</tr>
<tr class="odd">
<td><p>RETAILKEYBOARDMAPPINGTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILKEYBOARDMAPPINGTRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILKEYMAPPING</p></td>
</tr>
<tr class="even">
<td><p>RETAILOPERATIONS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILRECEIPTMASKS</p></td>
</tr>
<tr class="even">
<td><p>RETAILRECEIPTPROFILE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILRECEIPTPROFILELINE</p></td>
</tr>
<tr class="even">
<td><p>RETAILTILLLAYOUT</p></td>
</tr>
<tr class="odd">
<td><p>RETAILVISUALPROFILE</p></td>
</tr>
</tbody>
</table>

  


