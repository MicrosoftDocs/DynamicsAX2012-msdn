---
title: Form Types
TOCTitle: Form Types
ms:assetid: e5b953dd-4fac-44cb-8851-28375071645b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886615(v=AX.60)
ms:contentKeyID: 35267979
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Form Types [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX 2012 provides form types that allow users to perform tasks in a consistent manner. The Microsoft Dynamics AX 2012 client uses the following forms.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Form type</p></th>
<th><p>Primary work patterns</p></th>
<th><p>Usage examples</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Entity details</strong></p></td>
<td><p>View and edit master data*</p>
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
<td><p>Detail forms for viewing and editing</p>
<p>Other uses:</p>
<ul>
<li><p>View and edit line item details</p></li>
<li><p>Editable list</p></li>
</ul></td>
<td><ul>
<li><p>Purchase requisition</p></li>
<li><p>Purchase order</p></li>
<li><p>Sales order</p></li>
<li><p>Packing slip</p></li>
<li><p>Invoice</p></li>
<li><p>Payment</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Journal</strong></p></td>
<td><p>Data entry in a grid</p>
<p>Other uses:</p>
<ul>
<li><p>View Journal information and lines</p></li>
</ul></td>
<td><ul>
<li><p>Payment journal</p></li>
<li><p>Payment journal vouchers</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Simple list and details</strong></p></td>
<td><p>View and edit reference and dependent data</p></td>
<td><ul>
<li><p>ZIP Codes</p></li>
<li><p>Currencies</p></li>
<li><p>Employee contacts</p></li>
<li><p>Miscellaneous charges</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Table of contents</strong></p></td>
<td><p>Configure data in a multi-step pattern or free-form</p></td>
<td><ul>
<li><p>Accounts payable parameters</p></li>
<li><p>Address format</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Inquiry</strong></p></td>
<td><p>View related data</p></td>
<td><ul>
<li><p>Invoice journal inquiry</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Dialog</strong></p></td>
<td><p>Secondary window that allows commands and questions, and provides information or progress feedback</p></td>
<td><ul>
<li><p>Create transactions</p></li>
<li><p>Submit to workflow</p></li>
<li><p>Confirm delete action</p></li>
<li><p>Workflow actions such as <strong>Submit</strong>, <strong>Approve</strong>, <strong>Reject</strong>, and <strong>Request change</strong></p></li>
<li><p>Two-phase create</p></li>
<li><p>Activity tasks</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Drop dialog</strong> (Also called a quick path)</p></td>
<td><p>Lightweight dialog that displays a small set of options specific to an action or confirms an action without using a full dialog</p></td>
<td><ul>
<li><p>Process hold</p></li>
<li><p>Set date effective options</p></li>
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
<tr class="even">
<td><p><strong>Dependent data</strong></p></td>
<td><p>Dependent data is data that is associated with master data, transaction data, and reference data. Dependent data is generally deleted when the parent is deleted. In UML, dependent data is a <em>composition</em> relationship.</p></td>
</tr>
</tbody>
</table>


## Form examples

Example of a details form

  
![Details form](images/Gg886615.formtype_01(AX.60).png "Details form")Example of a details form

Example of an editable list form

  
![Editable list form](images/Gg886615.formtype_02(AX.60).png "Editable list form")Example of an editable list form

Example of a journal form

  
![Journal form](images/Gg886615.formtype_05(AX.60).png "Journal form")Example of a journal form

Example of a simple list and details form

  
![Simple list and details form](images/Gg886615.formtype_06(AX.60).png "Simple list and details form")Example of a simple list and details form

Example of a table of contents form

  
![Table of contents form](images/Gg886615.formtype_07(AX.60).png "Table of contents form")Example of a table of contents form

Example of an inquiry form

  
![Inquiry form](images/Gg886615.formtype_08(AX.60).png "Inquiry form")Example of an inquiry form

Example of a wizard form

  
![Wizard form](images/Gg886615.formtype_09(AX.60).png "Wizard form")Example of a wizard form

