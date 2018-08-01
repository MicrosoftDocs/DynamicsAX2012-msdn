---
title: ReleaseUpdateDB60_Vend.updatePurchCRisModified
TOCTitle: ReleaseUpdateDB60_Vend.updatePurchCRisModified
ms:assetid: b56ffa0e-06df-7604-cdcc-72dc9674d50d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736987(v=AX.60)
ms:contentKeyID: 49710671
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updatePurchCRisModified 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePurchCRisModified</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Initializes the &lt;c&gt;isModfied&lt;/c&gt; field to the &lt;c&gt;NoYes::Yes&lt;/c&gt; enumeration value for all records that have been upgraded from an earlier version. Initializes the &lt;c&gt;DocumentState&lt;/c&gt; on &lt;c&gt;PurchTable&lt;/c&gt; dependent on &lt;c&gt;PurchStatus&lt;/c&gt; Initialized the &lt;c&gt;isFinalized&lt;/c&gt; on &lt;c&gt;PurchLine&lt;/c&gt; dependent on &lt;c&gt;PurchStatus&lt;/c&gt;</p></td>
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
<td><p>PurchTable</p></td>
</tr>
<tr class="even">
<td><p>PurchLine</p></td>
</tr>
<tr class="odd">
<td><p>MarkupTrans</p></td>
</tr>
<tr class="even">
<td><p>VendPaymSched</p></td>
</tr>
<tr class="odd">
<td><p>VendPaymSchedLine</p></td>
</tr>
</tbody>
</table>


## Remarks

As the history tables are new to the current version, no information is stored in these tables for upgraded purchase orders.All records are marked as modified to be included in the first copy to the history tables.The \<c\>DocumentState\</c\> field on all existing purchase orders is set to a \<c\>VersioningDocumentState::Approved\</c\> enumeration value.The method is based on direct SQL to make sure that it has best possible performance.

  


