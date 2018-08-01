---
title: ReleaseUpdateDB60_Basic.deletePreviousFiscalDocumentText Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.deletePreviousFiscalDocumentText Upgrade Script
ms:assetid: 12e17b56-7e86-4e00-fa60-42c575ec7dd2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735842(v=AX.60)
ms:contentKeyID: 49706753
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.deletePreviousFiscalDocumentText Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>deletePreviousFiscalDocumentText</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method deletes existing fiscal document texts from AX 2012 in order to achieve idem potency when re-running the script after recovering from a failure. It is used internally by the other fiscal document text methods.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>DocuRef</p></td>
</tr>
<tr class="even">
<td><p>DocuRefExt_BR</p></td>
</tr>
</tbody>
</table>


## Remarks

Given a Common record where the fiscal document texts are attached to, it first deletes all the related DocuRef records that have a linked DocuRefExt\_BR record, thus restricting the action to actual fiscal document texts. Secondly, it deletes all the orphan DocuRefExt\_BR records that may exist.

  


