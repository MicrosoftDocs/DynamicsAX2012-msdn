---
title: ReleaseUpdateDB60_Basic.updateFiscalDocumentTextBasic_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateFiscalDocumentTextBasic_BR Upgrade Script
ms:assetid: 2e2db67b-44ef-19a7-8b48-e4290295a14f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736007(v=AX.60)
ms:contentKeyID: 49707422
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateFiscalDocumentTextBasic\_BR Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>updateFiscalDocumentTextBasic_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Configures Microsoft Dynamics AX 2012 to support the new fiscal document text feature, formerly known as legal text in Microsoft Dynamics AX 2009.</p></td>
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
<td><p>DocuType</p></td>
</tr>
<tr class="even">
<td><p>BrazilParameters</p></td>
</tr>
</tbody>
</table>


## Remarks

This method creates a new document type that will be used for fiscal document texts through the whole system. This new document type will be reserved for this purpose only and it is configured at Brazil parameters form.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

