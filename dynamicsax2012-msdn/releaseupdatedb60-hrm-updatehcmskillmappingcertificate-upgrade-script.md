---
title: ReleaseUpdateDB60_HRM.updateHcmSkillMappingCertificate Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmSkillMappingCertificate Upgrade Script
ms:assetid: 7926d71c-617a-8503-2f8e-406118fc7b43
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719391(v=AX.60)
ms:contentKeyID: 49709182
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmSkillMappingCertificate Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_HRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateHcmSkillMappingCertificate</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmSkillMappingCertificate table from the HRMSkillMappingCertificate table.</p></td>
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
<td><p>Human Resources</p></td>
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
<td><p>HcmSkillMappingCertificate</p></td>
</tr>
<tr class="even">
<td><p>HcmSkillMappingHeader</p></td>
</tr>
<tr class="odd">
<td><p>HRMCertificateType</p></td>
</tr>
<tr class="even">
<td><p>HRMSkillMappingCertificate</p></td>
</tr>
</tbody>
</table>


## Remarks

The SkillMappingHeader field holding the RecId value from the HcmSkillMappingTable table replaces the hrmSkillMappingTableId field. The Certificate field holding the RecId value from the HcmCertificateType table replaces the hrmCertificateTypeId field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMSkillMappingCertificate</p></th>
<th><p>To Table: HcmSkillMappingCertificate</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
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
<td><p>HcmSkillMappingCertificate</p></td>
<td><p></p></td>
<td><p></p></td>
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
<td><p>HRMSkillMappingCertificate</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


