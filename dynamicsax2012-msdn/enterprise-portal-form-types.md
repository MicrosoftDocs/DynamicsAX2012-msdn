---
title: Enterprise Portal Form Types
TOCTitle: Enterprise Portal Form Types
ms:assetid: f3c5d42b-df2a-49d1-93e0-a9d07a567f8f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886617(v=AX.60)
ms:contentKeyID: 35267981
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Enterprise Portal Form Types 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX 2012 provides form types that allow users to perform tasks in a consistent manner. Enterprise Portal for Microsoft Dynamics AX 2012 uses the following forms. All Enterprise Portal forms will be displayed in the modal popover control.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Form type</p></th>
<th><p>Work patterns</p></th>
<th><p>Usage examples</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Entity details</strong></p></td>
<td><p>View and edit master data *</p>
<p>Other uses:</p>
<ul>
<li><p>View and edit line item details</p></li>
<li><p>Editable list</p></li>
</ul></td>
<td><ul>
<li><p>View customer information</p></li>
<li><p>Create a new vendor</p></li>
<li><p>Create a project</p></li>
<li><p>Create a catalog</p></li>
<li><p>View and edit line item details</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Source documents</strong></p></td>
<td><p>Details forms for viewing and editing data</p></td>
<td><ul>
<li><p>Add travel delegate</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Wizard</strong></p></td>
<td><p>Present tasks in a multi-step format with a specific sequence that can include sub-tasks</p></td>
<td><ul>
<li><p>Dispute credit card</p></li>
<li><p>Import compliance controls</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Dialog</strong></p></td>
<td><p>Secondary window that allows commands and questions, and provides information or progress feedback.</p></td>
<td><ul>
<li><p>Add activity</p></li>
<li><p>Add address</p></li>
<li><p>Edit case association</p></li>
<li><p>Workflow actions such as <strong>Submit</strong>, <strong>Approve</strong>, <strong>Reject</strong>, and <strong>Request change</strong></p></li>
<li><p>New purchase requisition</p></li>
</ul></td>
</tr>
</tbody>
</table>


\* Document data mostly appears in edit mode, which is used for editing entities that reference data from other tables, for example, Project, which pulls in resources, categories, and so on. Typically, the user will need to spend several hours creating the document, coming back to edit it many times over a long period of time, which is different from transient entities, such as sales orders.

## Glossary

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Term</p></th>
<th><p>Definition</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Master data</strong></p></td>
<td><p>Data that is generally persistent over time and that represent the items that are important to track in the ERP system. Master data is the <em>nouns</em> of the system, such as <em>Customers</em>, <em>Vendors</em>, <em>Sales people</em>, and <em>Employees</em>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source documents</strong></p></td>
<td><p>Business events generated from the occurrence of an economic transaction are documented on source documents and recorded in accounting journals when the source document is journalized.</p>
<p>Transactions will generally affect master data and make use of reference data and parameters.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Reference data</strong></p></td>
<td><p>Reference data is data that is used by both master and transaction data. Reference data is found in the setup areas of the system and is fairly stable over time.</p></td>
</tr>
</tbody>
</table>


## Form examples

Example of an Enterprise Portal details form in view mode

  
![Enterprise Portal details form in view mode](images/Gg886617.formtype_03(AX.60).png "Enterprise Portal details form in view mode")Example of an Enterprise Portal details form in view mode

Example of an Enterprise Portal details form in edit mode

  
![Enterprise Portal details form in edit mode](images/Gg886617.formtype_04(AX.60).png "Enterprise Portal details form in edit mode")Example of an Enterprise Portal details form in edit mode

Example of a wizard form

  
![Wizard form](images/Gg886615.formtype_09(AX.60).png "Wizard form")Example of a wizard form

