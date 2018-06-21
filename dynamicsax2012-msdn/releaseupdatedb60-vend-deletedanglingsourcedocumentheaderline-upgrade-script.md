---
title: ReleaseUpdateDB60_Vend.deleteDanglingSourceDocumentHeaderLine Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.deleteDanglingSourceDocumentHeaderLine Upgrade Script
ms:assetid: 647515ea-852f-7a48-18aa-9cddc35a3fa4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719162(v=AX.60)
ms:contentKeyID: 49708701
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.deleteDanglingSourceDocumentHeaderLine Upgrade Script [AX 2012]


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
<td><p>deleteDanglingSourceDocumentHeaderLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Deletes the SourceDocumentLine and SourceDocumentHeader records for the deleted PurchLine and PurchTable records.</p></td>
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
<td><p>SourceDocumentHeader</p></td>
</tr>
<tr class="even">
<td><p>SourceDocumentLine</p></td>
</tr>
</tbody>
</table>


## Remarks

The SourceDocumentLine and SourceDocumentHeader records are created in the pre upgrade scripts. When the PurchLine or PurchTable records were created they need to be deleted as well.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

