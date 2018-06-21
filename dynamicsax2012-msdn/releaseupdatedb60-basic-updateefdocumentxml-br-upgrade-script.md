---
title: ReleaseUpdateDB60_Basic.updateEFDocumentXML_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateEFDocumentXML_BR Upgrade Script
ms:assetid: b95dade6-c332-3308-8403-81d1cccd291d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737108(v=AX.60)
ms:contentKeyID: 49710790
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateEFDocumentXML\_BR Upgrade Script [AX 2012]


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
<td><p>updateEFDocumentXML_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the EFDocumentXML_BR table to move content of the XMLDocApproved and XMLDocDenied fields to the new SubmitReturnResponse field.</p></td>
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
<td><p>Accounts receivable</p></td>
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
<td><p>EFDocumentXML_BR</p></td>
</tr>
</tbody>
</table>


## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EFDocumentXML_BR</p></td>
<td><p>SubmissionResponse</p></td>
<td><p>EFDocXML_BR</p></td>
</tr>
<tr class="even">
<td><p>EFDocumentXML_BR</p></td>
<td><p>SubmitReturn</p></td>
<td><p>EFDocXML_BR</p></td>
</tr>
<tr class="odd">
<td><p>EFDocumentXML_BR</p></td>
<td><p>SubmitReturnResponse</p></td>
<td><p>EFDocXML_BR</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EFDocumentXML_BR</p></td>
<td><p>XMLDocApproved</p></td>
</tr>
<tr class="even">
<td><p>EFDocumentXML_BR</p></td>
<td><p>XMLDocDenied</p></td>
</tr>
</tbody>
</table>


## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name: EFDocumentXML_BR</p></th>
<th><p>New Table Name: EFDocumentXML_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>XMLDocCancelMsg</p></td>
<td><p>Cancel</p></td>
</tr>
<tr class="odd">
<td><p>XMLDocCancelledReturn</p></td>
<td><p>CancelResponse</p></td>
</tr>
<tr class="even">
<td><p>XMLDocSent</p></td>
<td><p>Submission</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

