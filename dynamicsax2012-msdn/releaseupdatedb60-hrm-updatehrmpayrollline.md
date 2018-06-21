---
title: ReleaseUpdateDB60_HRM.updateHRMPayrollLine
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMPayrollLine
ms:assetid: 5369b117-91ca-10ae-f6fa-ef98ac91ef21
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736117(v=AX.60)
ms:contentKeyID: 49708293
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMPayrollLine [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateHRMPayrollLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the &lt;c&gt;ReasonCode&lt;/c&gt; field of the &lt;c&gt;HRMPayrollLine&lt;/c&gt; table with the corresponding value from the &lt;c&gt;RecId&lt;/c&gt; field of the &lt;c&gt;HcmReasonCodey&lt;/c&gt; table. Updates the &lt;c&gt;PayrollCategory&lt;/c&gt; field of the &lt;c&gt;HRMPayrollLine&lt;/c&gt; table with the corresponding value from the &lt;c&gt;RecId&lt;/c&gt; field of the &lt;c&gt;HcmPayrollCategory&lt;/c&gt; table. Updates the &lt;c&gt;PayrollPremium&lt;/c&gt; field of the &lt;c&gt;HRMPayrollLine&lt;/c&gt; table with the corresponding value from the &lt;c&gt;RecId&lt;/c&gt; field of the &lt;c&gt;HcmPayrollPremium&lt;/c&gt; table.</p></td>
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
<td><p>HcmPayrollPremium</p></td>
</tr>
<tr class="even">
<td><p>HRMPayrollCategory</p></td>
</tr>
<tr class="odd">
<td><p>HRMPayrollLine</p></td>
</tr>
<tr class="even">
<td><p>HRMReasonCode</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HcmPayrollPremium</p></th>
<th><p>To Table: HRMPayrollLine</p></th>
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
<td><p>HRMPayrollLine</p></td>
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
<td><p>HcmPayrollPremium</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

