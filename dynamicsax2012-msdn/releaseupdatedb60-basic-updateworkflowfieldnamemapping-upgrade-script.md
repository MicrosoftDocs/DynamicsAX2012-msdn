---
title: ReleaseUpdateDB60_Basic.updateWorkflowFieldNameMapping Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateWorkflowFieldNameMapping Upgrade Script
ms:assetid: d17e7f5e-27ae-92ae-ba94-2b371a5a1ace
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686932(v=AX.60)
ms:contentKeyID: 49711382
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateWorkflowFieldNameMapping Upgrade Script 


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
<td><p>updateWorkflowFieldNameMapping</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates a mapping from the dataAreaID field to the DataArea field in the WorkflowConfigurationTable table. Creates a mapping from the dataAreaID field to the del_DataAreaID field for rest of the affected tables.</p></td>
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
<td><p>WorkflowConfigurationTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowElementTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowStepTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowSubWorkflowTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowMessageText</p></td>
</tr>
<tr class="even">
<td><p>WorkflowVersionTableNotes</p></td>
</tr>
<tr class="odd">
<td><p>ExpressionTable</p></td>
</tr>
</tbody>
</table>


## Remarks

We cannot use the dataareaId field because this is the intrinsic kernel field to use to store the data area for company bound tables, such as the SaveDataPerCompany field equal to the Yes value. We cannot use this field because our tables now have the SaveDataPerCompany field equal to the No value, which means that the dataareaId field does not exist in our tables, and we cannot add it. Therefore, this is a mapping of the old dataareaId field to a new DataArea field for the WorkflowConfigurationTable table and to the del\_DataAreaID field for the rest of the tables that are mentioned in the list above.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WokflowConfigurationTable</p></th>
<th><p>To Table: WorkflowConfigurationTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DataAreaID</p></td>
<td><p>DataArea</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowElementTable</p></th>
<th><p>To Table: WorkflowElementTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dataAreaID</p></td>
<td><p>del_dataAreaID</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowStepTable</p></th>
<th><p>To Table: WorkflowStepTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dataAreaID</p></td>
<td><p>del_dataAreaID</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowSubWorkflowTable</p></th>
<th><p>To Table: WorkflowSubWorkflowTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dataAreaID</p></td>
<td><p>del_dataAreaID</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowMessageText</p></th>
<th><p>To Table: WorkflowMessageText</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dataAreaID</p></td>
<td><p>del_dataAreaID</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowVersionTableNotes</p></th>
<th><p>To Table: WorkflowVersionTableNotes</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dataAreaID</p></td>
<td><p>del_dataAreaID</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ExpressionTable</p></th>
<th><p>To Table: ExpressionTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dataAreaID</p></td>
<td><p>del_dataAreaID</p></td>
</tr>
</tbody>
</table>

  


