---
title: ReleaseUpdateDB60_Vend.updateMarkupTransPurchLine Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateMarkupTransPurchLine Upgrade Script
ms:assetid: c269dafe-cdb7-accf-8bbc-3fc4aa94d1f8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686827(v=AX.60)
ms:contentKeyID: 49711024
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateMarkupTransPurchLine Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>updateMarkupTransPurchLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates a SourceDocumentLine object for every record in the MarkupTrans table that is associated with a record in the PurchLine table. If the record in the PurchLine table actually points to another PurchLine or PurchTable table record, a ParentSourceDocumentLine object is also created.</p></td>
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
<td><p>MarkupTrans</p></td>
</tr>
</tbody>
</table>

  


