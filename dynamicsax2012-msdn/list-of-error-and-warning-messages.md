---
title: List of Error and Warning Messages
TOCTitle: List of Error and Warning Messages
ms:assetid: 005c5e10-e0e0-4c89-8897-232cf2daa5bb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb530207(v=AX.60)
ms:contentKeyID: 35239982
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# List of Error and Warning Messages 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When using the Microsoft Dynamics AX development environment, you should adhere to a set of best practices. The X++ compiler checks the code for best practice issues. These issues can result in best practice errors, warnings, or informational messages. This topic also includes information about compilation errors.

Error and warning messages require changes in the X++ code, but informational messages do not require any user action. Informational messages are rare and self-explanatory.

The following sections list error and warning messages. The usage of these messages can vary in Microsoft Dynamics AX. For example, if you cannot find a warning message in the warning message table, it might be in the error message table. Each table is sorted alphabetically by the message text. All error and warning messages are shown exactly as they appear in the code.

## Error Messages

The following table lists the best practice error messages. Many error messages are also discussed in more detail in other Help topics. Where appropriate, the table contains links to specific locations in other Help topics where messages are discussed in further detail.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Error message text <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></th>
<th><p>Description</p></th>
<th><p>BPError code and label</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>%1 %2 not used</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="best-practices-for-methods.md">Best Practices for Methods</a></p></li>
<li><p><a href="best-practices-for-parameters.md">Best Practices for Parameters</a></p></li>
<li><p><a href="best-practices-for-class-declarations.md">Best Practices for Class Declarations</a></p></li>
</ul></td>
<td><p>Method Variable Not Used, @SYS60464</p></td>
</tr>
<tr class="even">
<td><p>The class %1 is obsolete. Instead, use the class %2.</p></td>
<td><p>Use the class indicated by the error message.</p></td>
<td><p>BPErrorClassDiscontinuedInLaterVers, @SYS69514</p></td>
</tr>
<tr class="odd">
<td><p>%1 is an unwanted object name.</p></td>
<td><p>For more information, see <a href="how-to-add-rules-for-elements.md">How to: Add Rules for Elements</a>.</p></td>
<td><p>Unwanted Object, @SYS85681</p></td>
</tr>
<tr class="even">
<td><p>%1 property of %2 is not valid.</p></td>
<td><p>Ensure that the menu item name assigned to the form Web control is valid.</p></td>
<td><p>Form Web Control Unknown Menu Item Name, @SYS93552</p></td>
</tr>
<tr class="odd">
<td><p>Action menu item not defined</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowNoActionMenuItem, @SYS108556</p></td>
</tr>
<tr class="even">
<td><p>Approve outcome must exist and be enabled</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowApprovalOutcomesInvalid, @SYS108546</p></td>
</tr>
<tr class="odd">
<td><p>Category not defined</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowTemplateNoCategory, @SYS108536</p></td>
</tr>
<tr class="even">
<td><p>Class name must by postfixed with %1</p></td>
<td><p>For more information, see <a href="best-practices-for-interfaces.md">Best Practices for Interfaces</a>.</p></td>
<td><p>Class Name, @SYS87660</p></td>
</tr>
<tr class="odd">
<td><p>Code to handle the InventDimId field must be added to the Multisite Activation Wizard.</p></td>
<td><p>For more information, see <a href="best-practices-table-fields.md">Best Practices: Table Fields</a>.</p></td>
<td><p>BPErrorTableFieldInventDimIdNotMultiSiteActivated, @SYS123160</p></td>
</tr>
<tr class="even">
<td><p>Configuration key must be provided for a perspective.</p></td>
<td><p>For more information, see <a href="best-practices-for-perspectives.md">Best Practices for Perspectives</a>.</p></td>
<td><p>Perspective Missing Configuration Key, @SYS94657</p></td>
</tr>
<tr class="odd">
<td><p>Configuration key not defined</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowNoConfigKey, @SYS108553</p></td>
</tr>
<tr class="even">
<td><p>Configuration Key with ID %1 is unknown.</p></td>
<td><p>Ensure that renamed configuration keys have not created a mismatch between the name referenced and the current IDs.</p></td>
<td><p>Configuration Key Unknown, @SYS73068</p></td>
</tr>
<tr class="odd">
<td><p>Control label is a copy of its display method label</p></td>
<td><p>For more information, see <a href="forms-best-practices.md">Forms Best Practices</a>.</p></td>
<td><p>Label Is Copy Of Display Method, @SYS60361</p></td>
</tr>
<tr class="even">
<td><p>Control label is a copy of its field label</p></td>
<td><p>For more information, see <a href="forms-best-practices.md">Forms Best Practices</a>.</p></td>
<td><p>Report Label Is Copy Of Fields Label, @SYS57599</p></td>
</tr>
<tr class="odd">
<td><p>Control name %1 is not unique.</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="best-practices-for-extended-data-type-properties.md">Best Practices for Extended Data Type Properties</a></p></li>
<li><p><a href="best-practices-for-form-control-properties.md">Best Practices for Form Control Properties</a></p></li>
</ul></td>
<td><p>Form Control Name Not Unique, @SYS87713</p></td>
</tr>
<tr class="even">
<td><p>CodeField does not use an extended data type derived from CurrencyCode.</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Field Currency Code Field Invalid, @SYS89379</p></td>
</tr>
<tr class="odd">
<td><p>CurrencyCodeField must not be blank when CurrencyCode is set to CurrencyCodeField.</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Field Currency Code Field Empty, @SYS89329</p></td>
</tr>
<tr class="even">
<td><p>CurrencyCodeTable must not be blank when CurrencyCode is set to CurrencyCodeField.</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Field Currency Code Table Empty, @SYS89328</p></td>
</tr>
<tr class="odd">
<td><p>CurrencyDateField %1 does not use an extended data type derived from Date.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Field Currency Date Field Invalid, @SYS97998</p></td>
</tr>
<tr class="even">
<td><p>CurrencyDateField must not be blank when CurrencyDate is set to CurrencyDateField.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Field Currency Date Field Empty, @SYS98000</p></td>
</tr>
<tr class="odd">
<td><p>CurrencyDateTable %1 does not have a relationship with this table, or no unique index exists on the target end of a relationship with that table</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Field Currency Date Table Invalid, @SYS98002</p></td>
</tr>
<tr class="even">
<td><p>CurrencyDateTable must not be blank when CurrencyDate is set to CurrencyDateField.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Field Currency Date Table Empty, @SYS97995</p></td>
</tr>
<tr class="odd">
<td><p>Current table and table %1 have Delete Actions in both directions.</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Table Delete Action Both Directions, @SYS74301</p></td>
</tr>
<tr class="even">
<td><p>Delete Actions related to an unknown table with ID: %1</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a></p></li>
<li><p><a href="best-practice-parameters.md">Best practice parameters</a></p></li>
</ul></td>
<td><p>Table Delete Action Unknown Table, @SYS74302</p></td>
</tr>
<tr class="odd">
<td><p>Display/Edit method must be defined using a type</p></td>
<td><p>For more information, see <a href="using-the-display-method-modifier.md">Using the display Method Modifier</a>.</p></td>
<td><p>Display Edit No Extended Return Type, @SYS55403</p></td>
</tr>
<tr class="even">
<td><p>Display menu item not defined</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowNoDisplayMenuItem, @SYS108559</p></td>
</tr>
<tr class="odd">
<td><p>Due date provider does not reference a valid class implementing the WorkflowDueDateProvider interface</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowElementDueDateProviderInvalid, @SYS108545</p></td>
</tr>
<tr class="even">
<td><p>Element outcome '%1' ActionMenuItem property does not reference a valid action menu item</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowElementOutcomeActionMIInvalid, @SYS108549</p></td>
</tr>
<tr class="odd">
<td><p>Element outcome '%1' ActionMenuItem property not defined</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowElementOutcomeNoActionMI, @SYS108547</p></td>
</tr>
<tr class="even">
<td><p>Element outcome '%1' ActionWebMenuItem property does not reference a valid web action menu item</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowElementOutcomeActionWMIInvalid, @SYS108548</p></td>
</tr>
<tr class="odd">
<td><p>Element outcome '%1' EventHandler property does not reference a valid class implementing the '%2' interface</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowElementOutcomeEHInvalid, @SYS108551</p></td>
</tr>
<tr class="even">
<td><p>Enum with ID %1 does not exist.</p></td>
<td><p>Ensure that renamed objects have not created a mismatch between the name referenced and the current IDs.</p></td>
<td><p>Enum Not Exist, @SYS57821</p></td>
</tr>
<tr class="odd">
<td><p>Event handler does not reference a valid class implementing the '%1' interface</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowEventHandlerInvalid, @SYS108564</p></td>
</tr>
<tr class="even">
<td><p>Event handler not defined</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowNoEventHandlerError, @SYS108563 </p></td>
</tr>
<tr class="odd">
<td><p>Extended Data Type is set to be right justified, should be set to left justified</p></td>
<td><p>For more information, see <a href="best-practices-performance-optimizations.md">Best Practices: Performance Optimizations</a></p></td>
<td><p>BPErrorEnumRightJustified, @SYS107157</p></td>
</tr>
<tr class="even">
<td><p>Extended data types that refer to record IDs must use Ref table or a derived extended data type.</p></td>
<td><p>For more information, see <a href="best-practices-table-fields.md">Best Practices: Table Fields</a>.</p></td>
<td><p>Type Extends Rec Id, @SYS92962</p></td>
</tr>
<tr class="odd">
<td><p>Extended data types that refer to table IDs must use RefTableId or a derived extended data type.</p></td>
<td><p>For more information, see <a href="best-practices-table-fields.md">Best Practices: Table Fields</a>.</p></td>
<td><p>Type Extends Table Id, @SYS92963</p></td>
</tr>
<tr class="even">
<td><p>Field %1 with DEL_ prefix has configuration %2 instead of SysDeletedObjects.</p></td>
<td><p>For more information, see <a href="best-practices-tables.md">Best Practices: Tables</a>.</p></td>
<td><p>BPErrorTableFieldDelConfigKeyConflict, @SYS107044</p></td>
</tr>
<tr class="odd">
<td><p>Table is using CreatedDateTime or ModifiedDateTime, RecId index needs to be created.</p></td>
<td><p>For more information, see <a href="best-practices-tables.md">Best Practices: Tables</a>.</p></td>
<td><p>BPErrorRecIDNeededCreatedModifiedDateTime, @SYS127410</p></td>
</tr>
<tr class="even">
<td><p>RecID field cannot be part of the NaturalKey index.</p></td>
<td><p>For more information, see <a href="best-practices-tables.md">Best Practices: Tables</a>.</p></td>
<td><p>BPErrorTableNaturalKeyWithRecID, @SYS129768</p></td>
</tr>
<tr class="odd">
<td><p>Field group autoreport contains too few fields (%1).</p></td>
<td><p>For more information, see <a href="best-practices-for-field-groups.md">Best Practices for Field Groups</a>.</p></td>
<td><p>Table Field Group Missing Fields, @SYS55439</p></td>
</tr>
<tr class="even">
<td><p>Field Help is a copy of the Enum Help</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Field Help Is Copy Of Enum Help, @SYS55431</p></td>
</tr>
<tr class="odd">
<td><p>Field Help is a copy of the Extended Data Type Help of the field</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Field Help Is Copy Of Extended Help, @SYS55429</p></td>
</tr>
<tr class="even">
<td><p>Field is not a member of a field group</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="best-practice-parameters.md">Best practice parameters</a></p></li>
<li><p><a href="best-practices-for-field-groups.md">Best Practices for Field Groups</a></p></li>
</ul></td>
<td><p>Table Field Not In Field Group, @SYS55434</p></td>
</tr>
<tr class="odd">
<td><p>Field label is a copy of the Enum label</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Field Label Is Copy Of Enum Help, @SYS55430</p></td>
</tr>
<tr class="even">
<td><p>Field label is a copy of the Extended Data Type label of the field</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a></p></li>
<li><p><a href="best-practices-for-labels.md">Best Practices for Labels</a></p></li>
</ul></td>
<td><p>Field Label Is Copy Of Extended Help, @SYS55428</p></td>
</tr>
<tr class="odd">
<td><p>Field must be defined using a type</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Table Field Not Defined Using Type, @SYS55426</p></td>
</tr>
<tr class="even">
<td><p>Field with ID %1 does not exist in table %2</p></td>
<td><p>A field in a table can be referenced by the field ID in several ways. For example, the field ID can be referenced by a relation, or by a field group. This error can be resolved by determining where the field ID is being referenced.</p></td>
<td><p>Form Group Field Id Unknown In Table (Also: Table Relation Unknown Extern Field, Table Relation Unknown Field, Type Field Not Exist In Table), @SYS55418</p></td>
</tr>
<tr class="odd">
<td><p>Fields using RefRecId or a derived type must have a relation defined for that field.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-relations.md">Best Practices for Table Relations</a>.</p></td>
<td><p>Table Field Ref Rec Id Without Relation, @SYS92956</p></td>
</tr>
<tr class="even">
<td><p>Form group (%1) and table group (%2) have different numbers of fields. Consequently, they cannot be AOS optimized.</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Form Group Control Dif Num Of Fields, @SYS68381</p></td>
</tr>
<tr class="odd">
<td><p>Form reference does not exist %1</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Table Unknown Form Ref, @SYS55414</p></td>
</tr>
<tr class="even">
<td><p>Help defined on a control that cannot display Help</p></td>
<td><ul>
<li><p>For more information, see <a href="best-practices-for-form-control-properties.md">Best Practices for Form Control Properties</a>.</p></li>
</ul></td>
<td><p>Help Not Defined, @SYS85234</p></td>
</tr>
<tr class="odd">
<td><p>Hierarchy provider does not reference a valid class implementing the WorkflowHierarchyProvider interface</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowElementHierarchyProviderInvalid, @SYS108543</p></td>
</tr>
<tr class="even">
<td><p>Index %1 has no fields</p></td>
<td><p>For more information, see <a href="best-practices-for-indexes.md">Best Practices for Indexes</a>.</p></td>
<td><p>Table Index Without Fields, @SYS87147</p></td>
</tr>
<tr class="odd">
<td><p>Index %1 is overlapped by index %2.</p></td>
<td><p>For more information, see <a href="best-practices-for-indexes.md">Best Practices for Indexes</a>.</p></td>
<td><p>Table Overlapping Index, @SYS87145</p></td>
</tr>
<tr class="even">
<td><p>Invalid reference to workflow category</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowTemplateCategory, @SYS108537</p></td>
</tr>
<tr class="odd">
<td><p>Label %1 cannot end with a period ('.').</p></td>
<td><ul>
<li><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></li>
</ul></td>
<td><p>Label Wrong End Sign, @SYS55433</p></td>
</tr>
<tr class="even">
<td><p>Label and Help are equal</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="best-practices-for-perspectives.md">Best Practices for Perspectives</a></p></li>
<li><p><a href="best-practices-for-extended-data-type-properties.md">Best Practices for Extended Data Type Properties</a></p></li>
</ul></td>
<td><p>Label And Help Are Equal, @SYS55404</p></td>
</tr>
<tr class="odd">
<td><p>Method is not referenced in X++ code or indirectly</p></td>
<td><p>Add a call to the unused method, or remove the method.</p></td>
<td><p>Method Not Used, @SYS55408</p></td>
</tr>
<tr class="even">
<td><p>Method run on %1 and has AOSRunMode set to %2</p></td>
<td><p>For more information, see <a href="application-object-runon-property-overview.md">Application Object RunOn Property Overview</a>.</p></td>
<td><p>Method Bound Wrong, @SYS85345</p></td>
</tr>
<tr class="odd">
<td><p>Missing tag '%1' in XML documentation.</p></td>
<td><p>For more information, see <a href="best-practices-xml-documentation.md">Best Practices: XML Documentation</a>.</p></td>
<td><p>BPErrorXmlDocumentationParamTagMissing, @SYS107110</p></td>
</tr>
<tr class="even">
<td><p>Missing tag 'returns' in XML documentation.</p></td>
<td><p>For more information, see <a href="best-practices-xml-documentation.md">Best Practices: XML Documentation</a>.</p></td>
<td><p>BPErrorXmlDocumentationReturnsTagMissing, @SYS107110</p></td>
</tr>
<tr class="odd">
<td><p>Missing tag 'summary' in XML documentation.</p></td>
<td><p>For more information, see <a href="best-practices-xml-documentation.md">Best Practices: XML Documentation</a>.</p></td>
<td><p>BPErrorXmlDocumentationSummaryTagMissing, @SYS107110</p></td>
</tr>
<tr class="even">
<td><p>More than one tree node with this path: %1</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>AOT Path Not Unique, @SYS68375</p></td>
</tr>
<tr class="odd">
<td><p>No caching set up for the Table</p></td>
<td><p>For more information, see <a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a>.</p></td>
<td><p>Table No Caching, @SYS55412</p></td>
</tr>
<tr class="even">
<td><p>No caption defined</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="reports-best-practices.md">Reports Best Practices</a></p></li>
<li><p><a href="best-practices-for-report-properties.md">Best Practices for Report Properties</a></p></li>
</ul></td>
<td><p>Caption Not Defined, @SYS60369</p></td>
</tr>
<tr class="odd">
<td><p>No Help defined</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Help Not Defined, @SYS55407</p></td>
</tr>
<tr class="even">
<td><p>No Label defined</p></td>
<td><p>Add a label using <strong>Tools</strong> &gt; <strong>Labels</strong> &gt; <strong>Label Editor</strong>. For more information, see the following topics:</p>
<ul>
<li><p><a href="best-practices-for-labels.md">Best Practices for Labels</a></p></li>
<li><p><a href="best-practices-for-form-control-properties.md">Best Practices for Form Control Properties</a></p></li>
<li><p><a href="menu-items-best-practices.md">Menu Items Best Practices</a></p></li>
<li><p><a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a></p></li>
</ul></td>
<td><p>Label Not Defined, @SYS55406</p></td>
</tr>
<tr class="odd">
<td><p>No such data source %1</p></td>
<td><p>For more information, see <a href="best-practices-for-form-design-properties.md">Best Practices for Form Design Properties</a>.</p></td>
<td><p>Form Group Control Unknown DS, @SYS68379</p></td>
</tr>
<tr class="even">
<td><p>Object has changed ID since previous release. Old ID was %1.</p></td>
<td><p>It is recommended that object IDs remain unchanged, especially for tables and fields. Changing an ID value can cause errors during upgrade.</p>
<p>For more information, see the following topics:</p>
<ul>
<li><p><a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a></p></li>
<li><p><a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a></p></li>
<li><p><a href="best-practices-for-index-properties.md">Best Practices for Index Properties</a></p></li>
<li><p><a href="best-practices-for-extended-data-type-properties.md">Best Practices for Extended Data Type Properties</a></p></li>
<li><p><a href="best-practices-for-enum-properties.md">Best Practices for Enum Properties</a></p></li>
<li><p><a href="best-practices-for-class-declarations.md">Best Practices for Class Declarations</a></p></li>
</ul></td>
<td><p>Object Id Conflict, @SYS93546</p></td>
</tr>
<tr class="odd">
<td><p>Object has changed name since previous release. Old name was %1.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Object Name Conflict, @SYS93547</p></td>
</tr>
<tr class="even">
<td><p>One of the properties ParticipantProvider or HierarchyProvider must be defined</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowElementNoProvider, @SYS108542</p></td>
</tr>
<tr class="odd">
<td><p>Parent class contains abstract methods. Make class abstract or implement abstract methods %1.</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Class Not Marked Abstract, @SYS74077</p></td>
</tr>
<tr class="even">
<td><p>Parent Configuration Key with ID %1 is unknown.</p></td>
<td><p>Ensure that the configuration key value assigned to the ParentKey property is valid.</p></td>
<td><p>Configuration Parent Key Unknown, @SYS73075</p></td>
</tr>
<tr class="odd">
<td><p>Participant provider does not reference a valid class implementing the WorkflowParticipantProvider interface</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowElementParticipantProviderInvalid, @SYS108541</p></td>
</tr>
<tr class="even">
<td><p>Primary index %1 allows duplicates.</p></td>
<td><p>For more information, see <a href="best-practices-for-index-properties.md">Best Practices for Index Properties</a>.</p></td>
<td><p>Table Primary Index Not Unique, @SYS90099</p></td>
</tr>
<tr class="odd">
<td><p>Property %1 must contain a label ID such as @SYS4711, not %2</p></td>
<td><p>For more information, see <a href="best-practices-for-extended-data-type-properties.md">Best Practices for Extended Data Type Properties</a>.</p></td>
<td><p>Help Is Text, @SYS60289</p></td>
</tr>
<tr class="even">
<td><p>Property %1 must contain a label ID such as @SYS4711, not %2</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="best-practices-for-extended-data-type-properties.md">Best Practices for Extended Data Type Properties</a></p></li>
<li><p><a href="best-practices-for-labels.md">Best Practices for Labels</a></p></li>
</ul></td>
<td><p>Label Is Text, @SYS60289</p></td>
</tr>
<tr class="odd">
<td><p>Reference to action menu item is invalid</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowActionMenuItemInvalid, @SYS108557</p></td>
</tr>
<tr class="even">
<td><p>Reference to display menu item is invalid</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowDisplayMenuItemInvalid, @SYS108560</p></td>
</tr>
<tr class="odd">
<td><p>Reference to object not in version control (%1)</p></td>
<td><p>In the version control system, ensure that you have created all the new objects that the code depends on.</p></td>
<td><p>Method Refers Local Object, @SYS86883</p></td>
</tr>
<tr class="even">
<td><p>Reference to web action menu item is invalid</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPError WorkflowWebActionMenuItemInvalid, @SYS108558</p></td>
</tr>
<tr class="odd">
<td><p>Reference to web URL menu item is invalid</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowWebURLMenuItemInvalid, @SYS108561</p></td>
</tr>
<tr class="even">
<td><p>Referenced menu does not exist</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Menu Reference Unknown Ref Menu, @SYS55488</p></td>
</tr>
<tr class="odd">
<td><p>Relation %1 has no fields.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-relations.md">Best Practices for Table Relations</a>.</p></td>
<td><p>Table Relation No Fields, @SYS92955</p></td>
</tr>
<tr class="even">
<td><p>Required element '%1' does not reference a valid workflow element</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowTemplateRequiredElementInvalid, @SYS108538</p></td>
</tr>
<tr class="odd">
<td><p>Required element '%1' does not reference same document as the workflow template</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowTemplateRequiredDocumentInvalid, @SYS108539</p></td>
</tr>
<tr class="even">
<td><p>RunBase classes should be able to run on 'Called From' (Ensure pac and unpack are implemented correctly to allow PromptProm to marshal the class across tiers)</p></td>
<td><p>For more information, see <a href="best-practices-performance-optimizations.md">Best Practices: Performance Optimizations</a></p></td>
<td><p>BPErrorClassRunBaseMarkedOnServer, @SYS107159</p></td>
</tr>
<tr class="odd">
<td><p>RunBase implementations must have a static description method.</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Class No Static Description, @SYS72474</p></td>
</tr>
<tr class="even">
<td><p>Table %1 does not exist.</p></td>
<td><p>For more information, see <a href="best-practices-for-form-design-properties.md">Best Practices for Form Design Properties</a>.</p></td>
<td><p>Form Property Non Standard Value, @SYS75683</p></td>
</tr>
<tr class="odd">
<td><p>Table %1 with DEL_prefix has configuration %2 instead of SysDeletedObjects.</p></td>
<td><p>For more information, see <a href="best-practices-tables.md">Best Practices: Tables</a>.</p></td>
<td><p>BPErrorTableDelConfigKeyConflict, @SYS107042</p></td>
</tr>
<tr class="even">
<td><p>Table %1 with SysDeletedObjects configuration key (%2) has no DEL_ prefix.</p></td>
<td><p>For more information, see <a href="best-practices-tables.md">Best Practices: Tables</a>.</p></td>
<td><p>BPErrorTableDelPrefixConflict, BPErrorTableDelPrefixConflict, BPErrorTableIndexDelConfigKeyConflict, @SYS107043</p></td>
</tr>
<tr class="odd">
<td><p>Table fields that refer to record IDs must use RefRecId or a derived extended data type.</p></td>
<td><p>For more information, see <a href="best-practices-for-extended-data-types.md">Best Practices for Extended Data Types</a>.</p></td>
<td><p>Table Field Uses Rec Id, @SYS92960</p></td>
</tr>
<tr class="even">
<td><p>Table fields that refer to table IDs must use RefTableId or a derived extended data type.</p></td>
<td><p>For more information, see <a href="best-practices-for-extended-data-types.md">Best Practices for Extended Data Types</a>.</p></td>
<td><p>Table Field Uses Table Id, @SYS92961</p></td>
</tr>
<tr class="odd">
<td><p>Table group %1 is unknown (%2)</p></td>
<td><p>Check whether the reference by the form group to the table group is still valid.</p>
<p>You might need to delete the form group control, create a new field group, and then add a new form group control.</p></td>
<td><p>Form Group Control No Rel Table Group, @SYS73328</p></td>
</tr>
<tr class="even">
<td><p>Table is missing Clustered Index</p></td>
<td><p>For more information, see <a href="best-practices-performance-optimizations.md">Best Practices: Performance Optimizations</a></p></td>
<td><p>BPErrorTableNoClusteredIndex, @SYS107155</p></td>
</tr>
<tr class="odd">
<td><p>Table is missing Primary Index</p></td>
<td><p>For more information, see <a href="best-practices-performance-optimizations.md">Best Practices: Performance Optimizations</a></p></td>
<td><p>BPErrorTableNoPrimaryIndex, @SYS107156</p></td>
</tr>
<tr class="even">
<td><p>Table with ID %1 does not exist</p></td>
<td><p>Ensure that renamed tables have not created a mismatch between the name referenced and the current IDs.</p></td>
<td><p>Table Relation Unknown Extern Table (Also: Table Relation Unknown Table, Type Extern Table Unknown), @SYS55416</p></td>
</tr>
<tr class="odd">
<td><p>Tag '%1' exists more than once in XML documentation.</p></td>
<td><p>For more information, see <a href="best-practices-xml-documentation.md">Best Practices: XML Documentation</a>.</p></td>
<td><p>BPErrorXmlDocumentationDuplicated, @SYS107215</p></td>
</tr>
<tr class="even">
<td><p>Tag '%1' has no content in XML documentation.</p></td>
<td><p>For more information, see <a href="best-practices-xml-documentation.md">Best Practices: XML Documentation</a>.</p></td>
<td><p>BPErrorXmlDocumentationParamMissing, @SYS107150</p></td>
</tr>
<tr class="odd">
<td><p>Tag '%1' in XML documentation doesn't match actual implementation.</p></td>
<td><p>For more information, see <a href="best-practices-xml-documentation.md">Best Practices: XML Documentation</a>.</p></td>
<td><p>BPErrorXmlDocumentationParamWrongName, @SYS107113</p></td>
</tr>
<tr class="even">
<td><p>Tag '%1' in XML documentation is not supported.</p></td>
<td><p>For more information, see <a href="best-practices-xml-documentation.md">Best Practices: XML Documentation</a>.</p></td>
<td><p>BPErrorXmlDocumentationUnsupported, @SYS107111</p></td>
</tr>
<tr class="odd">
<td><p>Tag 'exception' has no content in XML documentation.</p></td>
<td><p>For more information, see <a href="best-practices-xml-documentation.md">Best Practices: XML Documentation</a>.</p></td>
<td><p>BPErrorXmlDocumentationExceptionMissing, @SYS107150</p></td>
</tr>
<tr class="even">
<td><p>Tag 'permission' has no content in XML documentation.</p></td>
<td><p>For more information, see <a href="best-practices-xml-documentation.md">Best Practices: XML Documentation</a>.</p></td>
<td><p>BPErrorXmlDocumentationPermissionMissing, @SYS107150</p></td>
</tr>
<tr class="odd">
<td><p>Task outcomes must contain one enabled outcome of type Complete</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowTaskNoCompleteOutcome, @SYS108552</p></td>
</tr>
<tr class="even">
<td><p>The caption of the group control is a copy of its table data group label</p></td>
<td><p>For more information, see <a href="forms-best-practices.md">Forms Best Practices</a>.</p></td>
<td><p>Caption Is Copy Of Data Group Label, @SYS68389</p></td>
</tr>
<tr class="odd">
<td><p>The class will be discontinued in a later version %1. Use: %2.</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Method Discontinued In Later Vers, @SYS69514</p></td>
</tr>
<tr class="even">
<td><p>The Client/Server setup is different from the parent class.</p></td>
<td><p>For more information, see <a href="best-practices-for-method-modifiers.md">Best Practices for Method Modifiers</a>.</p></td>
<td><p>Class Run On, @SYS74731</p></td>
</tr>
<tr class="odd">
<td><p>The configuration key for the Table Field is a copy of the configuration key for the Base Enum.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Table Field Configuration Key Is Copy, @SYS91245</p></td>
</tr>
<tr class="even">
<td><p>The configuration key for the Table Field is a copy of the configuration key for the Extended Data Type.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Table Field Configuration Key Is Copy, @SYS91243</p></td>
</tr>
<tr class="odd">
<td><p>The control Help text is a bad copy, and it should not be defined here.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Field Help Is Copy Of Enum Help (Also: Field Help Is Copy Of Extended Help), @SYS72533</p></td>
</tr>
<tr class="even">
<td><p>The CurrencyCodeTable %1 does not have a relationship with this table, or no unique index exists on the target end of a relationship with that table.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Field Currency Code Table Invalid, @SYS89330</p></td>
</tr>
<tr class="odd">
<td><p>The Dimension field must always be the only field in the Dimension group.</p></td>
<td><p>For more information, see <a href="best-practices-for-field-groups.md">Best Practices for Field Groups</a>.</p></td>
<td><p>Table Field Group Missing Fields, @SYS74735</p></td>
</tr>
<tr class="even">
<td><p>The fields in the relation are incompatible. '%1.%2' is %3 characters too short.</p></td>
<td><p>Ensure that the data types of the fields are identical, or at least compatible between the two sides of the relation. Ensure that the strings in the foreign key are at least as long as the strings in the corresponding primary key.</p></td>
<td><p>Table Relation Fields Incompatible (Also: Type Fields Incompatible), @SYS55422</p></td>
</tr>
<tr class="odd">
<td><p>The form size exceeds the maximum of %1 * %2 pixels. Current size %3 * %4 (%5\% * %6\%).</p></td>
<td><p>For more information, see <a href="forms-best-practices.md">Forms Best Practices</a>.</p></td>
<td><p>Form To High, @SYS75346</p></td>
</tr>
<tr class="even">
<td><p>The form must include a grid that contains ValidFrom and ValidTo fields when that form has a data source with ValidTimeStateAutoQuery set to DateRange.</p></td>
<td><p>Checks that a grid exists that contains the ValidFrom and ValidTo fields when a form has a data source with ValidTimeStateAutoQuery property set to DateRange. For more information, see <a href="valid-time-state-tables-and-date-effective-data.md">Valid Time State Tables and Date Effective Data</a>.</p></td>
<td><p>BPErrorFormValidTimeStateMissingValidToOrFromDate, @SYS133561</p></td>
</tr>
<tr class="odd">
<td><p>The keyword forceliterals must not be used in the query expression</p></td>
<td><p>For more information, see <a href="x-standards-select-statements.md">X++ Standards: select Statements</a>.</p></td>
<td><p>TwC Dangerous API, @SYS81941</p></td>
</tr>
<tr class="even">
<td><p>The method will be discontinued in a later version %1%2%3. Use %4</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Method Discontinued In Later Vers (Also: Method Dict Method Display Id Not Used), @SYS68910</p></td>
</tr>
<tr class="odd">
<td><p>The primary key field cannot be edited on update (AllowEdit must be set to No)</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Table Primary Key Editable, @SYS60598</p></td>
</tr>
<tr class="even">
<td><p>The primary key field must be mandatory.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Table Primary Key Not Mandatory, @SYS56378</p></td>
</tr>
<tr class="odd">
<td><p>The referenced application object does not exist (%1 %2).</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Menu Function Unknown Ref Object, @SYS72553</p></td>
</tr>
<tr class="even">
<td><p>Title field %1 must be declared.</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Table Title Field1 Not Declared, @SYS56377</p></td>
</tr>
<tr class="odd">
<td><p>Title field 2 must be different from title field 1</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="best-practice-parameters.md">Best practice parameters</a></p></li>
<li><p><a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a></p></li>
</ul></td>
<td><p>Table Title Field2 Not Declared, @SYS83885</p></td>
</tr>
<tr class="even">
<td><p>TwC: Assert usage of API %1 because it is protected by Code Access Security.</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="code-access-security.md">Code Access Security</a></p></li>
<li><p><a href="secured-apis.md">Secured APIs</a></p></li>
</ul></td>
<td><p>TwC Dangerous API, @SYS98156</p></td>
</tr>
<tr class="odd">
<td><p>TwC: Parameters to API %1 must be validated.</p></td>
<td><p>When code contains calls to system or kernel methods that may harm Microsoft Dynamics AX, the parameter data passed into those calls must be reviewed to ensure that the calls are harmless. After review, you may need to suppress the best practice error. For more information, see the following topics:</p>
<ul>
<li><p><a href="apis-turned-off-by-default.md">APIs Turned Off by Default</a></p></li>
<li><p><a href="best-practices-checks.md">Best Practices Checks</a></p></li>
</ul></td>
<td><p>TwC Dangerous API, @SYS90609</p></td>
</tr>
<tr class="even">
<td><p>TwC: Validate data displayed in form is fetched using record level security. Dangerous API %1 used.</p></td>
<td><p>For more information, see <a href="best-practices-avoiding-potential-security-issues.md">Best Practices: Avoiding Potential Security Issues</a>.</p></td>
<td><p>BPErrorTwCEnsureRecordLevelSecurity, @SYS98155</p></td>
</tr>
<tr class="odd">
<td><p>Type Help is a copy of the Enum Help</p></td>
<td><p>For more information, see <a href="best-practices-for-extended-data-type-properties.md">Best Practices for Extended Data Type Properties</a>.</p></td>
<td><p>Type Help Is Copy Of Enum Help, @SYS55451</p></td>
</tr>
<tr class="even">
<td><p>Type label is a copy of the Enum label</p></td>
<td><p>For more information, see <a href="best-practices-for-extended-data-type-properties.md">Best Practices for Extended Data Type Properties</a>.</p></td>
<td><p>Type Help Is Copy Of Enum Help, @SYS55450</p></td>
</tr>
<tr class="odd">
<td><p>Type label is a copy of the Extended (..) Data Type label of the type</p></td>
<td><p>For more information, see <a href="best-practices-for-extended-data-type-properties.md">Best Practices for Extended Data Type Properties</a>.</p></td>
<td><p>Type Label Is Copy Of Extended Help, @SYS55448</p></td>
</tr>
<tr class="even">
<td><p>Unique index %1 contains field %2 with SysDelete configuration config key assigned to it.</p></td>
<td><p>A field in an index has been made obsolete by an upgrade to Microsoft Dynamics AX because it was marked with SysDelete. This field was part of a unique index. Redesign the unique index. For more information, see <a href="unique-indexes.md">Unique Indexes</a>.</p></td>
<td><p>Table Sys Delete Field Index, @SYS99948</p></td>
</tr>
<tr class="odd">
<td><p>Unique index error: Fields removed from unique index: %1. Upgrade script required.</p></td>
<td><p>For more information, see <a href="unique-indexes.md">Unique Indexes</a>.</p></td>
<td><p>Table Unique Index Error, @SYS93535</p></td>
</tr>
<tr class="even">
<td><p>Unique index error: Previous nonunique index is now unique. Upgrade script required.</p></td>
<td><p>For more information, see <a href="unique-indexes.md">Unique Indexes</a>.</p></td>
<td><p>Table Unique Index Error, @SYS93534</p></td>
</tr>
<tr class="odd">
<td><p>Unique index error: Unique index introduced. Upgrade script required.</p></td>
<td><p>For more information, see <a href="unique-indexes.md">Unique Indexes</a>.</p></td>
<td><p>Table Unique Index Error, @SYS93533</p></td>
</tr>
<tr class="even">
<td><p>Use Client/Server neutral functionality. Do not use: %1%2%3. Use: %4.</p></td>
<td><p>For more information, see <a href="best-practices-for-method-modifiers.md">Best Practices for Method Modifiers</a>.</p></td>
<td><p>Method Neutral Funct Not Used, @SYS54379</p></td>
</tr>
<tr class="odd">
<td><p>Version mismatch of packed container. Check implementation of SysPackable interface.</p></td>
<td><p>For more information, see <a href="best-practices-for-interfaces.md">Best Practices for Interfaces</a>.</p></td>
<td><p>Class Sys Packable, @SYS93536</p></td>
</tr>
<tr class="even">
<td><p>Class is packing element IDs instead of element names.</p></td>
<td><p>For more information, see <a href="best-practices-for-interfaces.md">Best Practices for Interfaces</a>.</p></td>
<td><p>BPErrorClassSysPackableElementIds, @SYS130592</p></td>
</tr>
<tr class="odd">
<td><p>Workflow document does not reference a valid class deriving from WorkflowDocument</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowDocumentInvalid, @SYS108555</p></td>
</tr>
<tr class="even">
<td><p>Workflow document not defined</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowNoDocument, @SYS108554</p></td>
</tr>
<tr class="odd">
<td><p>XML documentation is not well-formed.</p></td>
<td><p>For more information, see <a href="best-practices-xml-documentation.md">Best Practices: XML Documentation</a>.</p></td>
<td><p>BPErrorXmlDocumentationNotWellFormed, @SYS107112</p></td>
</tr>
<tr class="even">
<td><p>Do not use braces around the case blocks in a switch statement.</p></td>
<td><p>You have braces around a case block in a switch statement that must be removed. For more information, see <a href="switch-statements.md">Switch Statements</a>.</p></td>
<td><p>BPErrorMethodNoBracketsInCaseBlocks, @SYS152524</p></td>
</tr>
<tr class="odd">
<td><p>Do not use the &lt;syntax&gt; tag in XML documentation. The syntax is automatically derived from the method declaration, and must not be explicitly provided.</p></td>
<td><p>You have a &lt;syntax&gt; tag in XML documentation that must be removed. XML documentation is denoted by triple slash (///) comments at the start of a method.</p></td>
<td><p>BPErrorXmlDocumentationSyntaxForbidden, @SYS152515</p></td>
</tr>
<tr class="even">
<td><p>Line item workflow '%1' event handler does not reference a valid class implementing the '%2' interface</p></td>
<td><p>Best practice rule for event handling that is now supported for approvals and tasks. For more information, see <a href="how-to-create-a-workflow-event-handler.md">How to: Create a Workflow Event Handler</a>.</p></td>
<td><p>BPErrorWorkflowLineItemWorkflowEHInvalid , @SYS152823</p></td>
</tr>
<tr class="odd">
<td><p>Line item workflow relation '%1' not found on workflow document query '%2’</p></td>
<td><p>Best practice rule for event handling that is now supported for approvals and tasks. For more information, see <a href="how-to-create-a-workflow-event-handler.md">How to: Create a Workflow Event Handler</a>.</p></td>
<td><p>BPErrorWorkflowLineItemWorkflowRelationNotFound, @SYS152835</p></td>
</tr>
<tr class="even">
<td><p>Line item workflow relation '%1' is invalid. Relation must be configured with a fetch mode of 1:n on workflow document query '%2'</p></td>
<td><p>Best practice rule to support event handling that is now supported for approvals and tasks. For more information, see <a href="how-to-create-a-workflow-event-handler.md">How to: Create a Workflow Event Handler</a>.</p></td>
<td><p>BPErrorWorkflowLineItemWorkflowRelationInvalid, @SYS152836</p></td>
</tr>
<tr class="odd">
<td><p>Line item workflow relation not defined</p></td>
<td><p>Best practice rule to support event handling that is now supported for approvals and tasks. For more information, see <a href="how-to-create-a-workflow-event-handler.md">How to: Create a Workflow Event Handler</a>.</p></td>
<td><p>BPErrorWorkflowLineItemWorkflowRelationEmpty, @SYS152837</p></td>
</tr>
<tr class="even">
<td><p>Line item workflow type '%1' not found</p></td>
<td><p>Best practice rule to support event handling that is now supported for approvals and tasks. For more information, see <a href="how-to-create-a-workflow-event-handler.md">How to: Create a Workflow Event Handler</a>.</p></td>
<td><p>BPErrorWorkflowLineItemWorkflowTypeNotFound, @SYS152839</p></td>
</tr>
<tr class="odd">
<td><p>Workflow document query not found on line item workflow type '%1'</p></td>
<td><p>Best practice rule to support event handling that is now supported for approvals and tasks. For more information, see <a href="how-to-create-a-workflow-event-handler.md">How to: Create a Workflow Event Handler</a>.</p></td>
<td><p>BPErrorWorkflowLineItemWorkflowTypeQueryNotFound, @SYS152840</p></td>
</tr>
<tr class="even">
<td><p>Line-item workflow relation '%1' does not match root datasource on line item workflow type document query '%2'</p></td>
<td><p>Best practice rule to support event handling that is now supported for approvals and tasks. For more information, see <a href="how-to-create-a-workflow-event-handler.md">How to: Create a Workflow Event Handler</a>.</p></td>
<td><p>BPErrorWorkflowLineItemWorkflowTypeQueryNoMatch, @SYS152841</p></td>
</tr>
<tr class="odd">
<td><p>Line item workflow must have at least one line item workflow type</p></td>
<td><p>Best practice rule to support event handling that is now supported for approvals and tasks. For more information, see <a href="how-to-create-a-workflow-event-handler.md">How to: Create a Workflow Event Handler</a>.</p></td>
<td><p>BPErrorWorkflowLineItemWorkflowNoTypes, @SYS152842</p></td>
</tr>
<tr class="even">
<td><p>The Company association type cannot be used for this workflow type because the table for the primary data source used by the workflow type is not configured to 'Save Data Per Company'.</p></td>
<td><p>Choose an alternative association type. This best practice rule was added to support organizational model types in workflow. For more information, see <a href="https://msdn.microsoft.com/en-us/library/hh538464(v=ax.60)">Associate a workflow with an organization</a>.</p></td>
<td><p>BPErrorWorkflowInvalidAssociationTypeCompany, @SYS190334</p></td>
</tr>
<tr class="odd">
<td><p>The Global and Other association types cannot be used for this workflow type because the table for the primary data source used by the workflow type is configured to 'Save Data Per Company'.</p></td>
<td><p>Best practice rule to support organizational model types in workflow. For more information, see <a href="https://msdn.microsoft.com/en-us/library/hh538464(v=ax.60)">Associate a workflow with an organization</a>.</p></td>
<td><p>BPErrorWorkflowInvalidAssociationTypeGlobalOther, @SYS190335</p></td>
</tr>
<tr class="even">
<td><p>An association type relation must be selected when the association type is Other</p></td>
<td><p>Best practice rule to support organizational model types in workflow. For more information, see <a href="https://msdn.microsoft.com/en-us/library/hh538464(v=ax.60)">Associate a workflow with an organization</a>.</p></td>
<td><p>BPErrorWorkflowMissingAssociationTypeRelation, @SYS190336</p></td>
</tr>
<tr class="odd">
<td><p>A class extending the SysTableExtension class should not have any member variables.</p></td>
<td><p>Best practice rule to enforce that the SysTableExtension class does not have any member variables. It is used to support the extension of the base class SysTableExtension. Use the SysTableExtension class to override the table data defaults.</p></td>
<td><p>BPErrorSysTableExtensionHasStates, @SYS190373</p></td>
</tr>
<tr class="even">
<td><p>The node's path exceeds the maximum length of 400 characters. Reduce number of nesting levels or rename nodes.</p></td>
<td><p>Reports tree node paths that exceed a string size of 400.</p></td>
<td><p>BPErrorTreenodePathExceedsMaxLength, @SYS300071</p></td>
</tr>
<tr class="odd">
<td><p>Table is using CreatedDateTime or ModifiedDateTime, RecId index needs to be created.</p></td>
<td><p></p></td>
<td><p>BPErrorRecIDNeededCreatedModifiedDateTime, @SYS127410</p></td>
</tr>
<tr class="even">
<td><p>The upgrade script is missing required attribute %1.</p></td>
<td><p>Checks that the upgrade script has the required <strong>Description</strong> attribute.</p></td>
<td><p>BPErrorMissingReqDesc</p>
<p>@SYS309412</p></td>
</tr>
<tr class="odd">
<td><p>The upgrade script is missing required attribute %1.</p></td>
<td><p>Checks that the upgrade script has the required <strong>Type</strong> attribute.</p></td>
<td><p>BPErrorMissingReqType, @SYS309412</p></td>
</tr>
<tr class="even">
<td><p>The upgrade script is missing required attribute %1.</p></td>
<td><p>Checks that the upgrade script has the required <strong>Stage</strong> attribute.</p></td>
<td><p>BPErrorMissingReqStage, @SYS309412</p></td>
</tr>
<tr class="odd">
<td><p>The upgrade script is missing required attribute %1.</p></td>
<td><p>Checks that the upgrade script has the required <strong>Table</strong> attribute.</p></td>
<td><p>BPErrorMissingReqTable, @SYS309412</p></td>
</tr>
<tr class="even">
<td><p>The upgrade script method cannot be static.</p></td>
<td><p>Checks that the upgrade script is a non-static method.</p></td>
<td><p>BPErrorMethodIsStatic, @SYS309410</p></td>
</tr>
<tr class="odd">
<td><p>The upgrade script method cannot accept parameters.</p></td>
<td><p>Checks that the upgrade script method has no parameters.</p></td>
<td><p>BPErrorMethodHasParams, @SYS309411</p></td>
</tr>
<tr class="even">
<td><p>Table %1 specified in the UpgradeScriptTableAttribute is not valid.</p></td>
<td><p>Checks that the table stated in the attribute of an upgrade script exists in the AOT.</p></td>
<td><p>BPErrorTableNotFound, @SYS309400</p></td>
</tr>
<tr class="odd">
<td><p>Configuration Key %1 specified in the UpgradeScriptConfigKeyAttribute is not valid.</p></td>
<td><p>Checks that the configuration key stated in the attribute of an upgrade script exists in the AOT.</p></td>
<td><p>BPErrorConfigurationKeyNotFound, @SYS309401</p></td>
</tr>
<tr class="even">
<td><p>Class %1 specified in the UpgradeDependsOnModuleAttribute is not valid.</p></td>
<td><p>Checks that the class name stated in the attribute of an upgrade script exists in the AOT.</p></td>
<td><p>BPErrorClassNameNotFound, @SYS309404</p></td>
</tr>
<tr class="odd">
<td><p>Method %1 in class %2 specified in the UpgradeDependsOnModuleAttribute is not valid.</p></td>
<td><p>Checks that the method name stated in the attribute of an upgrade script exists in the AOT.</p></td>
<td><p>BPErrorMethodNameNotFound, @SYS309403</p></td>
</tr>
<tr class="even">
<td><p>The upgrade script does not have a valid version defined [#define.version(sysReleasedVersion)] in the class declaration.</p></td>
<td><p>Checks that the script version stated in the attribute of an upgrade script exists in the AOT.</p></td>
<td><p>BPErrorInvalidScriptVersion, @SYS309415</p></td>
</tr>
<tr class="odd">
<td><p>Return type covariance: Return values must both be either tables or maps (%1.%2).</p></td>
<td><p>Checks that the inherited return values must both be tables or both be maps.</p></td>
<td><p>BPErrorInheritedReturnTypeMustBeTableOrMap, @SYS309721</p></td>
</tr>
<tr class="even">
<td><p>Return type covariance: Methods must return the same map (%1.%2).</p></td>
<td><p>Checks that the inherited methods must return the same map.</p></td>
<td><p>BPErrorInheritedReturnTypeMustBeSameMap, @SYS309722</p></td>
</tr>
<tr class="odd">
<td><p>The %1 relation to the %2 table does not have an upgrade script assigned. You must assign an upgrade script or exclude it from upgrade validation.</p></td>
<td><p>The unit of measure table is now global. At upgrade, company-specific units will be merged using user-defined mapping. This requires that existing tables that have relations to the unit of measure also apply the mapping. This best practice checks for relations to unit of measure and confirms that the relation to unit of measure is registered with an upgrade script or that the table is marked to be excluded from the upgrade.</p>
<p>The following code illustrates how to register a unit of measure upgrade job:</p>
<p>UnitOfMeasureUpgradeExecutor::registerUpgradeJobs()</p>
<p>The following code illustrates how to exclude a unit of measure table:</p>
<p>UnitOfMeasureUpgradeValidator::registerExcludedRelations()</p>
<p>For information on pre-upgrade tasks regarding units of measure see the following topics, <a href="https://msdn.microsoft.com/en-us/library/gg731802(v=ax.60)">Units</a>, <a href="https://msdn.microsoft.com/en-us/library/gg751370(v=ax.60)">Unit conversions</a>, <a href="https://msdn.microsoft.com/en-us/library/gg731896(v=ax.60)">Fixed units</a>, and <a href="https://msdn.microsoft.com/en-us/library/gg731921(v=ax.60)">Unit texts</a>.</p></td>
<td><p>BPErrorTableRelationNoUnitUpgrade, @SYS310791</p></td>
</tr>
<tr class="even">
<td><p>A non-surrogate key primary index is not valid for a company-specific table</p></td>
<td><p>Checks that the primary key for a company-specific table is a surrogate key.</p></td>
<td><p>BPErrorNonSurrogateKeyForPerCompanyTable, @SYS315491</p></td>
</tr>
<tr class="odd">
<td><p>Use of labels for developer documentation</p></td>
<td><p>Checks that all the tables have a description of the table specified in the <strong>DeveloperDocumentation</strong> property.</p></td>
<td><p>BPErrorDeveloperDocumentationNotDefined, @SYS118413</p></td>
</tr>
<tr class="even">
<td><p>Framework classes must have a disclaimer in the ClassDeclaration to discourage customizations.</p></td>
<td><p>Checks that the framework classes providing platform functionality have a message on them to discourage developers from customizing them. Customizing and extending classes that provide platform functionality may cause problems with future upgrades.</p></td>
<td><p>BPErrorClassFrameworkDisclaimer, @SYS316340</p></td>
</tr>
<tr class="odd">
<td><p>The framework class disclaimer must be placed after the XML documentation.</p></td>
<td><p>Framework classes have a disclaimer to discourage developers from customizing them. Customizing and extending classes providing platform functionality may cause problems with future upgrades.</p>
<p>Checks that the disclaimer is placed after the XML documentation, meaning after the /// comments.</p></td>
<td><p>BPErrorClassFrameworkDisclaimerPosition, @SYS316341</p></td>
</tr>
<tr class="even">
<td><p>Each perspective entity (table or view) must have at most 1 parent.</p></td>
<td><p>Checks that the perspective entity (table or view) has at most one parent.</p></td>
<td><p>BPErrorPerspectiveEntityMultipleParents, @SYS316698</p></td>
</tr>
<tr class="odd">
<td><p>Each perspective entity (table or view) must have at most 1 child.</p></td>
<td><p>Checks that the perspective entity (table or view) has at most one child.</p></td>
<td><p>BPErrorPerspectiveEntityMultipleChildren, @SYS316701</p></td>
</tr>
<tr class="even">
<td><p>Each perspective entity (table or view) must have a corresponding child for each parent.</p></td>
<td><p>Checks that the perspective entity (table or view) has a corresponding child for each parent.</p></td>
<td><p>BPErrorPerspectiveEntityMissingChild, @SYS316700</p></td>
</tr>
<tr class="odd">
<td><p>Each perspective entity (table or view) must have a corresponding parent for each child.</p></td>
<td><p>Checks that the perspective entity (table or view) has a corresponding parent for each child.</p></td>
<td><p>BPErrorPerspectiveEntityMissingParent, @SYS316699</p></td>
</tr>
<tr class="even">
<td><p>In each perspective entity the parent type should be the same as the child type if present.</p></td>
<td><p>Checks that in a perspective entity, the parent type is the same as the child type if one exists.</p></td>
<td><p>BPErrorPerspectiveEntityParentChildTypesNotEqual, @SYS316702</p></td>
</tr>
<tr class="odd">
<td><p>Perspectives where SharedDimensionContainer=Yes cannot have fields where AnalysisUsage is Measure or Both. Perspective %1, table or view %2, field %3.</p></td>
<td><p>When a perspective has the SharedDimensionContainer property set to <strong>True</strong>, the AnalysisUsage property for fields should not be marked as Measure or Both. Setting the SharedDimensionContainer property to <strong>True</strong> indicates that the perspective will be used to create dimensions only. The perspective will not be used to create a cube, measure group, or measure. For more information, see <a href="best-practices-for-perspectives.md">Best Practices for Perspectives</a>.</p></td>
<td><p>BPErrorPerspectiveMeasureInSharedDimensionContainer, @SYS322558</p></td>
</tr>
<tr class="even">
<td><p>%1 or %2 must not be used in the sys layer.</p></td>
<td><p>Checks that the UpgradeModuleDependsOnMeAttribute attribute and UpgradeTaskDependsOnMeAttribute attribute are not used in the SYS layer.</p></td>
<td><p>BPErrorExternalUseOnlyAttribute, @SYS327183</p></td>
</tr>
<tr class="odd">
<td><p>Inconsistent usage of AOSAuthorization property for a table in chain of inheritance. Ensure that both tables %1 and %2 have authorization either enabled or disabled.</p></td>
<td><p>Checks that all the tables in the inheritance hierarchy have the same value for authorization: either Enabled or Disabled.</p></td>
<td><p>BPErrorTableTPFIntegrity, @SYS327320</p></td>
</tr>
<tr class="even">
<td><p>Allowed CacheLookUp values for this TableGroup is %1</p></td>
<td><p>Checks that the cache lookup is valid for the table group.</p></td>
<td><p>BPErrorInvalidCacheLookUpAndTableGroup, @SYS327950</p></td>
</tr>
<tr class="odd">
<td><p>Service group must have a valid description</p></td>
<td><p>Checks that the <strong>Description</strong> property for a service group is provided. The description value must be a valid label.</p></td>
<td><p>BPErrorServiceGroupMustHaveDescription, @SYS328359</p></td>
</tr>
<tr class="even">
<td><p>Service must have a valid Namespace property</p></td>
<td><p>Checks that the <strong>Namespace</strong> property for a service is set to a valid namespace. You may not use the default URI, for example http://tempuri.org.</p></td>
<td><p>BPErrorServiceMustHaveNamespace, @SYS328364</p></td>
</tr>
<tr class="odd">
<td><p>Entry point is not in any privilege</p></td>
<td><p>Checks that the entry point is in a privilege. A menu item (display, output, action), service operation, Web URL, Web action, and Web content managed nodes must be added as an entry point in a privilege.</p></td>
<td><p>BPErrorSecEntryPointNotCoveredByPrivilege, @SYS329300</p></td>
</tr>
<tr class="even">
<td><p>Menu item points to a class that is not a RunBase class; it should probably have a linked permission object</p></td>
<td><p>Checks that the menu item has a linked permission. If the class that executes from the menu item launches a form, then the linked permission should point to the form. If the class is executing X++ code that requires access to tables that enable AOS authorization, then the linked permission should point to a code permission that grants the appropriate access.</p></td>
<td><p>BPErrorSecClassMenuDoesNotHaveLinkedPermission, @SYS329302</p></td>
</tr>
<tr class="odd">
<td><p>All duties should be part of a role</p></td>
<td><p>Checks that a duty is assigned to a process cycle that is assigned to a role.</p></td>
<td><p>BPErrorSecDutyNotCoveredByRole, @SYS329307</p></td>
</tr>
<tr class="even">
<td><p>All duties should be part of a process cycle</p></td>
<td><p>Checks that a duty is assigned to a process cycle that is assigned to a role.</p></td>
<td><p>BPErrorSecDutyNotCoveredByProcessCycle, @SYS329308</p></td>
</tr>
<tr class="odd">
<td><p>A form that is not associated with other forms should be linked to at least one menu item</p></td>
<td><p>Checks that a form is linked to a menu item. If a form is not associated with another form or linked to a menu item, it will not be accessible. Forms are launched from a menu item or from another form.</p></td>
<td><p>BPErrorSecFormNotLinkedToMenuItem, @SYS329310</p></td>
</tr>
<tr class="even">
<td><p>Non-system-managed %1 resource with incorrect managed by value %2</p></td>
<td><p>Best practice security check that a non-system-managed resource has <strong>Managed By</strong> value set to <strong>Manual</strong>.</p></td>
<td><p>BPErrorSecNonSystemResourceDoesNotHaveManagedBy, @SYS329375</p></td>
</tr>
<tr class="odd">
<td><p>Privilege is not in any duty.</p></td>
<td><p>Best practice security rule that checks that the privilege is set to a valid duty.</p></td>
<td><p>BPErrorSecPrivilegeNotPartofDuty, @SYS329303</p></td>
</tr>
<tr class="even">
<td><p>Missing SysEntryPointAttribute on service operation</p></td>
<td><p>Checks that the SysEntryPointAttribute attribute on the service operation because it is exposed externally.</p></td>
<td><p>BPErrorSecServiceOperationDoesNotHaveSEP, @SYS329376</p></td>
</tr>
<tr class="odd">
<td><p>Missing processReport method</p></td>
<td><p>Checks that the report has a processReport method.</p></td>
<td><p>BPErrorSecSSRSRDPPR, @SYS329374</p></td>
</tr>
<tr class="even">
<td><p>Missing SysEntryPointAttribute on SSRS RDP class</p></td>
<td><p>Checks that the SQL Server Reporting Services report data provider class has a processReport method defined with a SysEntryPointAttributeSysEntryPointAttribute attribute specified.</p></td>
<td><p>BPErrorSecSSRSRDPSysEP, @SYS329373</p></td>
</tr>
<tr class="odd">
<td><p>Info part not linked to menu items</p></td>
<td><p>Best practice security rule that checks that an Info Part is linked to a menu item. An Info Part is a collection of related data fields you can associate with a record in a form. You use Info Parts to create a FactBox for a form or the preview pane for a list page. To add an Info Part to a form, you use a menu item that links to the Info Part.</p></td>
<td><p>BPErrorSecInfoPartNotInMenuItem, @SYS329309</p></td>
</tr>
<tr class="even">
<td><p>DeveloperDocumentation label should not be marked to be translated.</p></td>
<td><p>Checks that the <strong>DeveloperDocumentation</strong> property will not be translated. The label used in the <strong>DeveloperDocumentation</strong> property should have the {Locked} keyword in the comment for the label.</p></td>
<td><p>BPErrorDeveloperDocumentationNotLocked, @SYS330248</p></td>
</tr>
<tr class="odd">
<td><p>The help provider class isn't specified for this online documentation set</p></td>
<td><p>The <strong>HelpProviderClass</strong> property must be set if the <strong>ContentLocation</strong> property is set to Online for a Help Document Set.</p></td>
<td><p>BPErrorHelpProviderClassEmpty, @SYS331955</p></td>
</tr>
<tr class="even">
<td><p>Query %1 can not be made searchable because it has zero or more that one data sources.</p></td>
<td><p>Checks that a searchable query has exactly one data source. You will get a best practice violation if no data source is specified or if more than one data source is specified.</p></td>
<td><p>BPErrorSearchableQueryNoDataSource, @SYS333623</p></td>
</tr>
<tr class="odd">
<td><p>Query %1 cannot be made searchable because it does not have the SearchLinkRefName property or the FormRef property set on the root table %2.</p></td>
<td><p>Checks that the searchable query has the <strong>SearchLinkRefName</strong> property or the <strong>FormRef</strong> property set on the root table. If not, the search results will not appear.</p></td>
<td><p>BPErrorSearchableQueryNoSearchLinkOnTable, @SYS334877</p></td>
</tr>
<tr class="even">
<td><p>Query %1 is searchable but it does not have the SearchLinkRefName property set to a URL menu item on the root table %2. The search results in will not appear in Enterprise Portal.</p></td>
<td><p>Checks that the searchable query has the <strong>SearchLinkRefName</strong> property set to a URL menu item on the root table. If not, the search results will not appear in Enterprise Portal.</p></td>
<td><p>BPErrorSearchableQueryNoSearchLinkRefUrl, @SYS334878</p></td>
</tr>
<tr class="odd">
<td><p>Query %1 is searchable but it does not have the FormRef property set to a form on the root table %2. The search results in will not appear in the Microsoft Dynamics AX client.</p></td>
<td><p>Checks that the searchable query has the <strong>FormRef</strong> property set to a form on the root table or the search results will not appear in the Microsoft Dynamics AX client.</p></td>
<td><p>BPErrorSearchableQueryNoFormRef, @SYS334879</p></td>
</tr>
<tr class="even">
<td><p>Query %1 cannot be made searchable because it does not have the TitleField1 or TitleField2 set on the root table %2.</p></td>
<td><p>Checks that the valid searchable query has the TitleField1 or the TitleField2 fields set on the root table.</p></td>
<td><p>BPErrorSearchableQueryNoTitleFields, @SYS334876</p></td>
</tr>
<tr class="odd">
<td><p>Update permissions for the search crawler role</p></td>
<td><p>Checks that the search crawler role has permissions for the table that was used in the query.</p></td>
<td><p>BPErrorSearchableQueryNoTablePermissions, @SYS334872</p></td>
</tr>
<tr class="even">
<td><p>Query %1 cannot be made searchable because it has a root table that is a transaction table with no index on the ModifiedDateTime field.</p></td>
<td><p>Checks that the searchable query has a root table that is a transaction table with an index on the ModifiedDateTime field.</p></td>
<td><p>BPErrorSearchableQueryNoIndexOnTransactionTable, @SYS333624</p></td>
</tr>
<tr class="odd">
<td><p>Element has changed name since previous release. If the rename is intentional then suppress this violation; otherwise, update the LegacyID. Old name was: %1</p></td>
<td><p>Checks that the element has the same name as for the previous release of Microsoft Dynamics AX. If the change was intentional, suppress the violation.</p>
<p>This best practice check is not new, the message has been updated. This check has been modified due to the changes regarding installation specific IDs.</p></td>
<td><p>BPErrorObjectNameConflict, @SYS335103</p></td>
</tr>
<tr class="even">
<td><p>The element has an origin value that is different from the origin value in a previous version of Microsoft Dynamics AX.</p></td>
<td><p>Checks that the element had the same origin value in earlier versions of Microsoft Dynamics AX. The origin value is the beginning value of the element. This check was added due to the changes regarding installation specific IDs.</p></td>
<td><p>BPErrorObjectOriginMismatch, @SYS335100</p></td>
</tr>
<tr class="odd">
<td><p>Element has no LegacyID assigned and was shipped in a previous version. All ID-based elements already shipped must have a LegacyID. Set Legacy ID to %1.</p></td>
<td><p>Checks that the element has a <strong>LegacyID</strong> property assigned because the element was shipped in an earlier version of Microsoft Dynamics AX. This check was added due to the changes regarding installation specific IDs.</p></td>
<td><p>BPErrorLegacyIdMissing, @SYS335102</p></td>
</tr>
<tr class="even">
<td><p>Element has a different LegacyID than previous shipped version. Please update LegacyID, old LegacyId was %1.</p></td>
<td><p>Checks that the value specified in the <strong>LegacyID</strong> property occurs in the earlier version of Microsoft Dynamics AX. A LegacyID specifies an identifier element from a previous version of Microsoft Dynamics AX. This check was added due to the changes regarding installation specific IDs.</p></td>
<td><p>BPErrorLegacyIDConflict, @SYS335101</p></td>
</tr>
<tr class="odd">
<td><p>The element does not have an origin value. This element must have a non-null origin value.</p></td>
<td><p>Checks that the element has an origin value. This element must have an origin value that is not NULL. This check was added due to the changes regarding installation specific IDs.</p></td>
<td><p>BPErrorOriginNull, @SYS335099</p></td>
</tr>
<tr class="even">
<td><p>Do not use a deprecated field as title field. Please select another title field.</p></td>
<td><p>Checks that deprecated fields are not used as title fields.</p></td>
<td><p>BPErrorTableTitleFieldDeprecated, @SYS338823</p></td>
</tr>
<tr class="odd">
<td><p>Do not use deprecated field %1 in non-deprecated index %2. Please remove the field or deprecate the index.</p></td>
<td><p>Checks that deprecated fields are not used as indexes. Replace the deprecated field or remove the index.</p></td>
<td><p>BPErrorTableIndexFieldDeprecated, @SYS338822</p></td>
</tr>
<tr class="even">
<td><p>Do not use deprecated field %1 in field group %2. Please remove the field from the field group.</p></td>
<td><p>Checks that the deprecated field is not used in a field group. Remove the deprecated field from the field group.</p></td>
<td><p>BPErrorTableTableFieldGroupDeprecated, @SYS338821</p></td>
</tr>
<tr class="odd">
<td><p>Control %1 bound to table field group has name that does not match default name of %2, consequently the control requires storage and cannot be optimized</p></td>
<td><p>For more information, see <a href="best-practices-for-form-control-properties.md">Best Practices for Form Control Properties</a>.</p></td>
<td><p>BPErrorFormGroupCannotBeOptimized, @SYS68376</p></td>
</tr>
<tr class="even">
<td><p>The form group and table group have different fields at position %1: '%2' != '%3', consequently the control requires storage and cannot be optimized</p></td>
<td><p>For more information, see <a href="best-practices-for-form-control-properties.md">Best Practices for Form Control Properties</a>.</p></td>
<td><p>BPErrorFormGroupControlDifFieldsAtPos, @SYS68382</p></td>
</tr>
</tbody>
</table>


## Warning Messages

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Warning message text <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p></th>
<th><p>Description</p></th>
<th><p>BPError code and label</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>%1 on control is set to nonauto (Date format)</p></td>
<td><p>For more information, see <a href="x-standards-dates.md">X++ Standards: Dates</a>.</p></td>
<td><p>Report Date Format Set Non Auto, @SYS60296 + @SYS23272</p></td>
</tr>
<tr class="even">
<td><p>%1 on control is set to nonauto (Decimal separator)</p></td>
<td><p>For more information, see <a href="best-practices-for-extended-data-type-properties.md">Best Practices for Extended Data Type Properties</a>.</p></td>
<td><p>Report Date Format Set Non Auto, @SYS60296 + @SYS24260</p></td>
</tr>
<tr class="odd">
<td><p>%1 on control is set to nonauto (%2)</p></td>
<td><p>For more information, see <a href="best-practices-for-extended-data-type-properties.md">Best Practices for Extended Data Type Properties</a>.</p></td>
<td><p>Report Thousand Sep Set Non Auto, @SYS60296</p></td>
</tr>
<tr class="even">
<td><p>A data entry form should have at least two tab pages.</p></td>
<td><p>For more information, see <a href="forms-best-practices.md">Forms Best Practices</a>.</p></td>
<td><p>Form Property Non Standard Value, @SYS84385</p></td>
</tr>
<tr class="odd">
<td><p>A display or edit method has the same name as this field. Rename the method or the field, and check whether field groups that contain this field should contain the method instead.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Table Field Has Same Name As Method, @SYS97063</p></td>
</tr>
<tr class="even">
<td><p>Adjustment property for field %1 of table %2 does not match its related field %3 of table %4</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Table Relationship Field Adjustment, @SYS91673</p></td>
</tr>
<tr class="odd">
<td><p>A document handling button on an Action Pane should have its Name property set to &quot;Attachments&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageDocHandlingCmdButtonNameNotAttachments, @SYS116209</p></td>
</tr>
<tr class="even">
<td><p>A document handling button on an Action Pane should use the label @SYS114630 for its Text property.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageDocHandlingCmdButtonTextNotAttachments, @SYS116210</p></td>
</tr>
<tr class="odd">
<td><p>A List Page must have a grid.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageFormHasNoGrid, @SYS116225</p></td>
</tr>
<tr class="even">
<td><p>A List Page must have a single Action Pane.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageFormHasNoActionPane , BPErrorListPageFormHasTooManyActionPanes, @SYS116224</p></td>
</tr>
<tr class="odd">
<td><p>All buttons on an Action Pane should have their ShowShortcut properties set to &quot;No&quot; to suppress the addition of extra characters for pneumonic usage.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageActionPaneButtonShowShortcutNotNo, @SYS116207</p></td>
</tr>
<tr class="even">
<td><p>An Action Pane should not be present on a form that isn't a List Page or other Content Page.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorFormHasActionPane, @SYS116229</p></td>
</tr>
<tr class="odd">
<td><p>AnalysisSelection should not be Auto for a table that is visible for analysis.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a>.</p></td>
<td><p>Table Analysis Selection Auto, @SYS89276</p></td>
</tr>
<tr class="even">
<td><p>AnalysisVisibility should not be Auto for a field in a table that is visible for analysis.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Field Analysis Visibility Auto, @SYS89279</p></td>
</tr>
<tr class="odd">
<td><p>AnalysisVisibility should not be Auto for a nonsystem table.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a>.</p></td>
<td><p>Table Analysis Visibility Auto, @SYS89275</p></td>
</tr>
<tr class="even">
<td><p>Class should have at least one member</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Class Missing Member, @SYS55390</p></td>
</tr>
<tr class="odd">
<td><p>Configuration Key is %1</p></td>
<td><p>Ensure a valid configuration key name is being used, rather than a placeholder value like &quot;Not decided.&quot;</p></td>
<td><p>Configuration Key Specific (Also: Configuration Parent Key Specific), @SYS72461</p></td>
</tr>
<tr class="even">
<td><p>Consider %1 method to run on %2 because it uses: %3</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="application-object-runon-property-overview.md">Application Object RunOn Property Overview</a></p></li>
<li><p><a href="https://msdn.microsoft.com/en-us/library/gg922592(v=ax.60)">Object Class</a></p></li>
</ul></td>
<td><p>Method Consider Run On, @SYS54211</p></td>
</tr>
<tr class="odd">
<td><p>Consider alternative to single quoted text %1 appearing in %2</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Method Single Quoted Text, @SYS68040</p></td>
</tr>
<tr class="even">
<td><p>Consider autodeclaring the form control %1</p></td>
<td><p>For more information, see <a href="best-practices-for-form-control-properties.md">Best Practices for Form Control Properties</a>.</p></td>
<td><p>Method Not Auto Declared, @SYS68393</p></td>
</tr>
<tr class="odd">
<td><p>Consider restructuring the %1 method because it has calls to the %2 server methods: %3, and the %4 client methods: %5.</p></td>
<td><p>For more information, see <a href="best-practices-for-method-modifiers.md">Best Practices for Method Modifiers</a>.</p></td>
<td><p>Method Consider Restructuring, @SYS54324</p></td>
</tr>
<tr class="even">
<td><p>Consider use of delete_from because method contains 'while select ... ..delete()'</p></td>
<td><p>For more information, see <a href="best-practices-for-table-methods.md">Best Practices for Table Methods</a>.</p></td>
<td><p>Method Delete From Not Used, @SYS55398</p></td>
</tr>
<tr class="odd">
<td><p>Consider use of more specialized intrinsic functionality because method contains %1</p></td>
<td><p>For more information, see <a href="intrinsic-functions.md">Intrinsic Functions</a>.</p></td>
<td><p>Method Identifier Str Used, @SYS55399</p></td>
</tr>
<tr class="even">
<td><p>Consider using a field list for select of %1. Only %2% of record size is used.</p></td>
<td><p>For more information, see <a href="x-standards-select-statements.md">X++ Standards: select Statements</a>.</p></td>
<td><p>Select Using Field List, @SYS91289</p></td>
</tr>
<tr class="odd">
<td><p>Consider using keyword 'firstonly' for select of %1.</p></td>
<td><p>For more information, see <a href="x-standards-select-statements.md">X++ Standards: select Statements</a>.</p></td>
<td><p>Select Using First Only, @SYS91288</p></td>
</tr>
<tr class="even">
<td><p>Control is not defined using anything (type, field or method)</p></td>
<td><p>Assign a source of information to the report control. Bind the control to a type, field, or method, or remove the control.</p></td>
<td><p>Report Control Use Not Defined, @SYS60363</p></td>
</tr>
<tr class="odd">
<td><p>Control is set to fixed width</p></td>
<td><p>For more information, see <a href="best-practices-for-form-control-properties.md">Best Practices for Form Control Properties</a>.</p></td>
<td><p>Report Control Set Fixed Width, @SYS60297</p></td>
</tr>
<tr class="even">
<td><p>CurrencyCode should be SecondaryCurrency when the field uses an extended data type derived from AmountMSTSecondary and the field is visible for analysis.</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Field Currency Code Secondary Currency, @SYS89712</p></td>
</tr>
<tr class="odd">
<td><p>CurrencyDate should not be Auto when a field is using an extended data type derived from money or moneyMST and the field is visible for analysis</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Field Currency Date Auto, @SYS98001</p></td>
</tr>
<tr class="even">
<td><p>Display methods must be typed ('%1 %2')</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Table No Extended Return Type, @SYS60362</p></td>
</tr>
<tr class="odd">
<td><p>Display/edit method does not use an Enum or Extended Data Type as return type: %1</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Table No Extended Return Type, @SYS72489</p></td>
</tr>
<tr class="even">
<td><p>Do not disable the control by setting Enabled to No. Set AllowEdit to No and Skip to Yes.</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Form Disabling Technique, @SYS72538</p></td>
</tr>
<tr class="odd">
<td><p>Do not write to parameters (such as %1 in line %2, column %3)</p></td>
<td><p>For more information, see <a href="best-practices-for-parameters.md">Best Practices for Parameters</a>.</p></td>
<td><p>Method Variable Dont Write To Parms, @SYS60115</p></td>
</tr>
<tr class="even">
<td><p>Duplicated user interface texts. Fields: %1.</p></td>
<td><p>For more information, see <a href="best-practices-for-labels.md">Best Practices for Labels</a>.</p></td>
<td><p>Table Duplicate UI Text Field, @SYS75650</p></td>
</tr>
<tr class="odd">
<td><p>Duplicated user interface texts. Method %1.</p></td>
<td><p>For more information, see <a href="best-practices-for-labels.md">Best Practices for Labels</a>.</p></td>
<td><p>Table Duplicate UI Text Method, @SYS72498</p></td>
</tr>
<tr class="even">
<td><p>Element outcome '%1' EventHandler property should be defined</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowElementOutcomeNoEH, @SYS108550</p></td>
</tr>
<tr class="odd">
<td><p>Enum field is Mandatory</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Table Field Enum Is Mandatory, @SYS55432</p></td>
</tr>
<tr class="even">
<td><p>Enum is not referenced in X++ code, in the table field or in an Extended Type</p></td>
<td><p>For more information, see <a href="best-practices-for-extended-data-type-properties.md">Best Practices for Extended Data Type Properties</a>.</p></td>
<td><p>Enum Not Used, @SYS55470</p></td>
</tr>
<tr class="odd">
<td><p>Event handler should be defined</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowNoEventHandlerWarning, @SYS108562</p></td>
</tr>
<tr class="even">
<td><p>Field is not referenced in X++ code</p></td>
<td><p>Add a reference to the field, or remove the unreferenced field.</p></td>
<td><p>Table Field Not Used, @SYS55427</p></td>
</tr>
<tr class="odd">
<td><p>FieldGroup AutoReport does not exist.</p></td>
<td><p>For more information, see <a href="best-practices-for-field-groups.md">Best Practices for Field Groups</a>.</p></td>
<td><p>Table Missing Group Auto Report, @SYS55415</p></td>
</tr>
<tr class="even">
<td><p>Help must end with a period or a question mark.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Help End Wrong Sign, @SYS72462</p></td>
</tr>
<tr class="odd">
<td><p>If Adjustment is set to Left, the StringSize for field %1 of table %2 must be greater than or equal to its related field %3 of table %4.</p></td>
<td><p>Increase the StringSize of the foreign key field.</p></td>
<td><p>Table Relationship Foreign Key To Short, @SYS91675</p></td>
</tr>
<tr class="even">
<td><p>If Adjustment is set to Right', the StringSize for field %1 of table %2 must match that of its related field %3 of table %4.</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a></p></li>
<li><p><a href="best-practices-for-extended-data-types.md">Best Practices for Extended Data Types</a></p></li>
</ul></td>
<td><p>Table Relationship Field String Length, @SYS91674</p></td>
</tr>
<tr class="odd">
<td><p>Illegal name %1 %2: %3. Use parent, child, or sibling.</p></td>
<td><p>Terms like father, mother, sister, and brother should not be part of a member name. Replace the improper term with parent, child, or sibling.</p></td>
<td><p>Method Illegal Name, @SYS57827</p></td>
</tr>
<tr class="even">
<td><p>Implement static construct to allow for modifications.</p></td>
<td><p>For more information, see <a href="best-practices-for-static-construct-methods.md">Best Practices for Static Construct Methods</a>.</p></td>
<td><p>Class No Static Construct, @SYS82256</p></td>
</tr>
<tr class="odd">
<td><p>Label is changed on the control from %1 to %2</p></td>
<td><p>For more information, see <a href="best-practices-for-form-control-properties.md">Best Practices for Form Control Properties</a>.</p></td>
<td><p>Label Changed At Control, @SYS60298</p></td>
</tr>
<tr class="even">
<td><p>Label on control is set to fixed width</p></td>
<td><p>For more information, see <a href="form-control-properties.md">Form Control Properties</a>.</p></td>
<td><p>Report Controls Label Set Fixed, @SYS60295</p></td>
</tr>
<tr class="odd">
<td><p>List Page Action Panes must have their VerticalSpacing property set to zero.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageControlVerticalSpacingNotZero, @SYS116212</p></td>
</tr>
<tr class="even">
<td><p>List Page Action Panes must have their Width property set to &quot;Column width&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageActionPaneWidthNotColumnWidth, @SYS116211</p></td>
</tr>
<tr class="odd">
<td><p>List Page controls must not have any vertical spacing between them.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageControlVerticalSpacingNotZero, @SYS116208</p></td>
</tr>
<tr class="even">
<td><p>List Page datasources must have their AllowCreate set to &quot;No&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageFormDataSourceAllowsCreate, @SYS116227</p></td>
</tr>
<tr class="odd">
<td><p>List Page datasources must have their AllowEdit set to &quot;No&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageFormDataSourceAllowsEdit, @SYS116226</p></td>
</tr>
<tr class="even">
<td><p>List Page datasources must have their StartPosition set to &quot;First&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageFormDataSourceStartPositionNotFirst, @SYS116228</p></td>
</tr>
<tr class="odd">
<td><p>List Page grids must have their AllowEdit property set to &quot;No&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageGridAllowsEdit, @SYS116213</p></td>
</tr>
<tr class="even">
<td><p>List Page grids must have their Datasource property set to a valid datasource.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageGridDataSourceEmpty, @SYS116217</p></td>
</tr>
<tr class="odd">
<td><p>List Page grids must have their DefaultAction property set to a button on the form. The DefaultAction property should normally point to a button that performs the &quot;Open&quot; action.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageGridDefaultActionEmpty, @SYS116214</p></td>
</tr>
<tr class="even">
<td><p>List Page grids must have their Height property set to &quot;Column height&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageGridHeightNotColumnHeight, @SYS116215</p></td>
</tr>
<tr class="odd">
<td><p>List Page grids must have their ShowRowLabels property set to &quot;Yes&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageGridShowRowLabelIsNotYes, @SYS116216</p></td>
</tr>
<tr class="even">
<td><p>List Page grids must have their Width property set to &quot;Column width&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageGridWidthNotColumnWidth, @SYS117724</p></td>
</tr>
<tr class="odd">
<td><p>List Pages  must have a name that ends with &quot;ListPage&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageFormNameDoesNotEndInListPage, @SYS116218</p></td>
</tr>
<tr class="even">
<td><p>List Pages must have their BottomMargin property set to &quot;Auto&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageFormBottomMarginNotAuto, @SYS116222</p></td>
</tr>
<tr class="odd">
<td><p>List Pages must have their LeftMargin property set to &quot;Auto&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageFormLeftMarginNotAuto, @SYS116220</p></td>
</tr>
<tr class="even">
<td><p>List Pages must have their RightMargin property set to &quot;Auto&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageFormRightMarginNotAuto, @SYS116221</p></td>
</tr>
<tr class="odd">
<td><p>List Pages must have their TitleDatasource property set.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>List Pages must have their TopMargin property set to &quot;Auto&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageFormTopMarginNotAuto, @SYS116219</p></td>
</tr>
<tr class="odd">
<td><p>List Page Action Panes must have their VerticalSpacing property set to zero.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageControlVerticalSpacingNotZero, @SYS116212</p></td>
</tr>
<tr class="even">
<td><p>List Page Action Panes must have their Width property set to &quot;Column width&quot;.</p></td>
<td><p>For more information, see <a href="best-practices-list-pages.md">Best Practices: List Pages</a>.</p></td>
<td><p>BPErrorListPageActionPaneWidthNotColumnWidth, @SYS116211</p></td>
</tr>
<tr class="odd">
<td><p>Method availability can be set explicitly to %1 via the Standard Public setting.</p></td>
<td><p>For more information, see <a href="best-practices-for-method-modifiers.md">Best Practices for Method Modifiers</a>.</p></td>
<td><p>Method Access Can Be Set Explicitely, @SYS68392</p></td>
</tr>
<tr class="even">
<td><p>Method contains code in unrequired braces %1 .... }</p></td>
<td><p>For more information, see <a href="x-layout.md">X++ Layout</a>.</p></td>
<td><p>Method Non Needed Block Style Used, @SYS59225</p></td>
</tr>
<tr class="odd">
<td><p>Method contains constant numeric value: %1</p></td>
<td><p>For more information, see <a href="x-standards-constants.md">X++ Standards: Constants</a>.</p></td>
<td><p>Method Constant Numeric Arg Used, @SYS55396</p></td>
</tr>
<tr class="even">
<td><p>Method contains labels in single quotes: &gt;%1&lt;</p></td>
<td><p>For more information, see <a href="x-standards-constants.md">X++ Standards: Constants</a>.</p></td>
<td><p>Method Label In Single Quotes, @SYS55395</p></td>
</tr>
<tr class="odd">
<td><p>Method contains parenthesis round case constant: %1</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="x-layout.md">X++ Layout</a></p></li>
<li><p><a href="x-standards-if-else-and-switch-statements.md">X++ Standards: if ... else and switch Statements</a></p></li>
</ul></td>
<td><p>Method Parenthesis Round Case Const, @SYS55397</p></td>
</tr>
<tr class="even">
<td><p>Method is empty</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Method Is Empty, @SYS68904</p></td>
</tr>
<tr class="odd">
<td><p>MinNoOfDecimals is greater than NoOfDecimals</p></td>
<td><p>For more information, see <a href="form-control-properties.md">Form Control Properties</a>.</p></td>
<td><p>Form Control Min No Of Decimals (Also: Report Control Min No Of Decimals), @SYS96235</p></td>
</tr>
<tr class="even">
<td><p>Missing super call in new method of sub class.</p></td>
<td><p>For more information, see <a href="best-practices-for-new-and-static-new-methods.md">Best Practices for new and static new... Methods</a>.</p></td>
<td><p>Method Missing Super Call, @SYS62822</p></td>
</tr>
<tr class="odd">
<td><p>Module not defined</p></td>
<td><p>For more information, see <a href="workflow-best-practices.md">Workflow Best Practices</a>.</p></td>
<td><p>BPErrorWorkflowCategoryNoModuleDefined, @SYS108540</p></td>
</tr>
<tr class="even">
<td><p>New should be protected.</p></td>
<td><p>For more information, see <a href="best-practices-for-new-and-static-new-methods.md">Best Practices for new and static new... Methods</a>.</p></td>
<td><p>Class New Not Protected, @SYS82255</p></td>
</tr>
<tr class="odd">
<td><p>No self relation set up for the Table. Rename function will not be available.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-relations.md">Best Practices for Table Relations</a>.</p></td>
<td><p>Table No Self Relation, @SYS56050</p></td>
</tr>
<tr class="even">
<td><p>No unique index set up for the table</p></td>
<td><p>For more information, see <a href="unique-indexes.md">Unique Indexes</a>.</p></td>
<td><p>Table No Unique Index, @SYS60691</p></td>
</tr>
<tr class="odd">
<td><p>Only parameters must start with an underscore, not variables such as %1</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="best-practices-for-parameters.md">Best Practices for Parameters</a></p></li>
<li><p><a href="naming-conventions-underscores.md">Naming Conventions: Underscores</a></p></li>
</ul></td>
<td><p>Method Variable With Underscore, @SYS60113</p></td>
</tr>
<tr class="even">
<td><p>Relation line %1 has possible errors in setup of the Configuration Keys. Field %2 has Configuration Key set %3 and field %4 has Configuration Key set %5.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-relations.md">Best Practices for Table Relations</a>.</p></td>
<td><p>Configuration Key Sets Not Ok, @SYS74477</p></td>
</tr>
<tr class="odd">
<td><p>Relation line %1 has possible errors in setup of the Configuration Keys. Type %2 has Configuration Key set %3 and field %4 has Configuration Key set %5.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-relations.md">Best Practices for Table Relations</a>.</p></td>
<td><p>Configuration Key Sets Not Ok, @SYS74534</p></td>
</tr>
<tr class="even">
<td><p>Relation to table %1 (using %2) which is not in this table collection</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Table Collection Relation, @SYS68398</p></td>
</tr>
<tr class="odd">
<td><p>Relations defined for a single record ID field should be defined on the extended data type for that field.</p></td>
<td><p>For more information, see <a href="best-practices-table-fields.md">Best Practices: Table Fields</a>.</p></td>
<td><p>Table Field Ref Rec Id Relation On Table, @SYS92957</p></td>
</tr>
<tr class="even">
<td><p>Report design orientation is not set to Auto</p></td>
<td><p>For more information, see <a href="best-practices-for-report-properties.md">Best Practices for Report Properties</a>.</p></td>
<td><p>Report Des Orientation Not Set Auto, @SYS60368</p></td>
</tr>
<tr class="odd">
<td><p>Report has generated design %1</p></td>
<td><p>For more information, see <a href="best-practices-for-report-design.md">Best Practices for Report Design</a>.</p></td>
<td><p>Report Has Generated Design, @SYS60365</p></td>
</tr>
<tr class="even">
<td><p>Report template %1 does not exist</p></td>
<td><p>For more information, see <a href="best-practices-for-report-properties.md">Best Practices for Report Properties</a>.</p></td>
<td><p>Report Unknown Template, @SYS60367</p></td>
</tr>
<tr class="odd">
<td><p>SingularLabel should be provided for a table that is visible for analysis.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a>.</p></td>
<td><p>Table Singular Label Empty, @SYS89278</p></td>
</tr>
<tr class="even">
<td><p>Table fields with AnalysisVisibility set to DefaultField or High should be in included in at least one perspective</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Field Visible But Not In Perspective, @SYS94645</p></td>
</tr>
<tr class="odd">
<td><p>Table group is %1.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a>.</p></td>
<td><p>Table No Table Group, @SYS55413</p></td>
</tr>
<tr class="even">
<td><p>Table has a record ID index but does not seem to use the record ID field explicitly for lookup</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="unique-indexes.md">Unique Indexes</a></p></li>
<li><p><a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a></p></li>
</ul></td>
<td><p>Table Rec Id Field Used Useless, @SYS60597</p></td>
</tr>
<tr class="odd">
<td><p>Table has no record ID index but does use the record ID field explicitly in relation in %1</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="unique-indexes.md">Unique Indexes</a></p></li>
<li><p><a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a></p></li>
</ul></td>
<td><p>Table No Record Id Index, @SYS60524</p></td>
</tr>
<tr class="even">
<td><p>Table has no record ID index but does use the record ID field explicitly in select ... where in %1</p></td>
<td><p>For more information, see <a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a>.</p></td>
<td><p>Table No Record Id Index Select, @SYS60523</p></td>
</tr>
<tr class="odd">
<td><p>Table has no record ID index but uses it %1 times</p></td>
<td><p>For more information, see <a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a>.</p></td>
<td><p>Table No Record Id Index But Used, @SYS60522</p></td>
</tr>
<tr class="even">
<td><p>Table has record ID index but does not use record ID field explicitly</p></td>
<td><p>For more information, see <a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a>.</p></td>
<td><p>Table Record Id Index Not Use Field, @SYS60520</p></td>
</tr>
<tr class="odd">
<td><p>Table is using CreatedDateTime +or ModifiedDateTime, RecId index needs to be created.</p></td>
<td><p>For more information, see <a href="best-practices-tables.md">Best Practices: Tables</a>.</p></td>
<td><p>BPErrorRecIDNeededCreatedModifiedDateTime, @SYS127410</p></td>
</tr>
<tr class="even">
<td><p>Tables with AnalysisVisibility set to High, Medium, or Low should be included in at least one perspective</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Table Visible But Not In Perspective, @SYS94641</p></td>
</tr>
<tr class="odd">
<td><p>Tables with only one index should have it defined as a cluster index</p></td>
<td><p>For more information, see <a href="clustered-indexes.md">Clustered Indexes</a>.</p></td>
<td><p>Table One Index Not Cluster, @SYS68395</p></td>
</tr>
<tr class="even">
<td><p>Tag '%1' in XML documentation is not supported.</p></td>
<td><p>For more information, see <a href="best-practices-xml-documentation.md">Best Practices: XML Documentation</a>.</p></td>
<td><p>BPErrorXmlDocumentationUnsupported, @SYS107111</p></td>
</tr>
<tr class="odd">
<td><p>The Construct method must only instantiate the class. Consider using a static new pattern instead.</p></td>
<td><p>For more information, see <a href="best-practices-for-static-construct-methods.md">Best Practices for Static Construct Methods</a>.</p></td>
<td><p>Class Construct Pattern, @SYS82257</p></td>
</tr>
<tr class="even">
<td><p>The CurrencyCode property should not be <strong>Auto</strong> if the field is derived from the money Extended Data Type and the AnalysisVisibility property is set to High or Low.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-field-properties.md">Best Practices for Table Field Properties</a>.</p></td>
<td><p>Field Currency Code Auto, @SYS89378</p></td>
</tr>
<tr class="odd">
<td><p>The designs property %1 is disabled and data source %2 has property %3 on table %4 set to true. Set the designs property %1 to Yes to ensure that the form restarts in the previous company.</p></td>
<td><p>Set the design property to Yes.</p></td>
<td><p>Form Property Non Standard Value, @SYS77537</p></td>
</tr>
<tr class="even">
<td><p>The design property %1 is enabled, but the property %3 on table %4 for data source %2 has not been set correctly. Set the design property %1 to No to prevent the form from restarting in the previous company.</p></td>
<td><p>Set the design property to No.</p></td>
<td><p>Form Property Non Standard Value, @SYS77486</p></td>
</tr>
<tr class="odd">
<td><p>The group could be based on a (new) table field group</p></td>
<td><p>For more information about groups on forms, see <a href="forms-best-practices.md">Forms Best Practices</a>.</p></td>
<td><p>Form Group Could Be Based On New Group, @SYS68387</p></td>
</tr>
<tr class="even">
<td><p>The group is empty</p></td>
<td><p>For more information about groups on forms, see <a href="forms-best-practices.md">Forms Best Practices</a>.</p></td>
<td><p>Form Group Is Empty, @SYS68388</p></td>
</tr>
<tr class="odd">
<td><p>The group should be given a logical name</p></td>
<td><p>For more information about groups on forms, see <a href="forms-best-practices.md">Forms Best Practices</a>.</p></td>
<td><p>Form Group No Logical Name, @SYS68385 = @SYS68384</p></td>
</tr>
<tr class="even">
<td><p>The primary index should be defined because a unique index exists</p></td>
<td><p>For more information, see the following topics:</p>
<ul>
<li><p><a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a></p></li>
<li><p><a href="best-practice-parameters.md">Best practice parameters</a></p></li>
</ul></td>
<td><p>Table Unique Index No Primary, @SYS68396</p></td>
</tr>
<tr class="odd">
<td><p>The property %1 has a nondefault value %2. Expected %3.</p></td>
<td><p>All form properties that have an Auto or Default setting should be kept at that setting. For more information, see <a href="best-practices-for-form-design-properties.md">Best Practices for Form Design Properties</a>.</p></td>
<td><p>Form Property Non Standard Value, @SYS72374</p></td>
</tr>
<tr class="even">
<td><p>The property %1 should be set to %2.</p></td>
<td><p>For more information, see <a href="best-practices-for-form-design-properties.md">Best Practices for Form Design Properties</a>.</p></td>
<td><p>Form Property Non Standard Value, @SYS84109</p></td>
</tr>
<tr class="odd">
<td><p>The word %1 is not spelled correctly.</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Doc Node Spelling Mistake, @SYS84009</p></td>
</tr>
<tr class="even">
<td><p>This class without members does not extend any other class</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Class No Member Not Extend, @SYS55391</p></td>
</tr>
<tr class="odd">
<td><p>This date construction can be illegal: %1</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Method Illegal Date Construction, @SYS68391</p></td>
</tr>
<tr class="even">
<td><p>ttsbegin/ttscommit are unbalanced with %1</p></td>
<td><p>For more information, see <a href="x-standards-ttsbegin-and-ttscommit.md">X++ Standards: ttsBegin and ttsCommit</a>.</p></td>
<td><p>Method Unbalanced Ttsbegin Commit, @SYS57826</p></td>
</tr>
<tr class="odd">
<td><p>TypicalRowCount should not be Auto for a table that is visible for analysis.</p></td>
<td><p>For more information, see <a href="best-practices-for-table-properties.md">Best Practices for Table Properties</a>.</p></td>
<td><p>Table Typical Row Count Auto, @SYS89277</p></td>
</tr>
<tr class="even">
<td><p>Unextended class without members is not extended by any other class</p></td>
<td><p>Add a member to the class, or remove the class.</p></td>
<td><p>Class Unextended Not Extend, @SYS55392</p></td>
</tr>
<tr class="odd">
<td><p>The class %1 cannot be constructed with the X++ keyword New. You can use %2.</p></td>
<td><p>For more information, see <a href="best-practices-for-static-construct-methods.md">Best Practices for Static Construct Methods</a>.</p></td>
<td><p>Method Illegal Construction Used, @SYS55400</p></td>
</tr>
<tr class="even">
<td><p>Variable %1 is not written, but read.</p></td>
<td><p>For more information, see <a href="best-practice-parameters.md">Best practice parameters</a>.</p></td>
<td><p>Method Variable Read But Not Written, @SYS60114</p></td>
</tr>
<tr class="odd">
<td><p>XML documentation not written for this method.</p></td>
<td><p>For more information, see <a href="best-practices-xml-documentation.md">Best Practices: XML Documentation</a>.</p></td>
<td><p>BPErrorXmlDocumentationMissing, @SYS107198</p></td>
</tr>
</tbody>
</table>


## Compilation Errors

The following table lists the compiler error messages. Many error messages are also discussed in more detail in other Help topics.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Error Message Text</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span id="err976"></span>Illegal second format.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err977"></span>Minute is not between 00-59.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err978"></span>Illegal Time.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err979"></span>Second is not between 00-59.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err980"></span>Minute is not between 00-59.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err981"></span>Hour is not between 00-23.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err982"></span>Unicode escape requires exactly 4 or 8 hexadecimal digits after \u or \U.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err983"></span>Number is too big.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err984"></span>Illegal date .</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err985"></span>Month is not between 1-12.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err986"></span>Year is not between 1900-2154.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err987"></span>The macro has already been defined with a different value.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err988"></span>An } (end brace) is missing in the macro.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err989"></span>An ) (end parenthesis) is missing in the macro.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err990"></span>The macro was terminated prematurely.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err992"></span>The macro is too complex.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err993"></span>Too many arguments have been specified for the macro.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err994"></span>The %1 macro does not exist.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err995"></span>This symbol cannot be used in scripts.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err996"></span>Lexical error.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err997"></span>The script was terminated prematurely.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err998"></span>An overflow occurred in the internal parser stack.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err999"></span>Syntax error.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1001"></span>Operand types are not compatible with the operator.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1002"></span>Table %1 does not exist.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1260"></span>The table does not contain this index.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1004"></span>Assignment or comparison loses precision.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1005"></span>Empty compound statement.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1006"></span>The table is out of range or does not exist.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1007"></span>The table %1 does not contain the field %2.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1008"></span>System fields may not be inserted or updated.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1009"></span>Variable %1 has not been declared.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1010"></span>The wrong number of arguments has been specified for the method .</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1011"></span>Argument '%1' is incompatible with the required type.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1012"></span>%1 </p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1013"></span>The enumeration does not exist .</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1014"></span>The name %1 has already been assigned to another variable.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1015"></span>The internal  object code must not exceed 64K.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1016"></span>Overflow in an internal compiler stack.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1018"></span>Insufficient memory to run job. </p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1261"></span>Best Practice: Class names should start with an uppercase letter.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1020"></span>Unreachable code.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1021"></span>Method %1 never returns a value.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1022"></span>Not all paths in %1 return a value.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1023"></span>A SWITCH statement may not contain more than one default part.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1024"></span>A BREAK statement was found in an illegal context. BREAK statements occur in the context of a SWITCH, WHILE, DO, or FOR statement.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1025"></span>This modifier is not allowed on interfaces.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1026"></span>The new method of a derived class does not call super().</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1027"></span>The new method of a derived class is not guaranteed to call super() on the inherited class. Provide an unconditional call to super().</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1028"></span>Array index %1 is out of bounds. Maximum value is %2.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1030"></span>Best Practice: Member name %1 should start with a lowercase letter.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1031"></span>The field must be a data element that allows assignment.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1032"></span>Abstract and interface methods can not  be static or final.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1033"></span>Declarations are illegal in interfaces.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1035"></span>%1 is not a class. Only classes (not interfaces) can extend classes.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1036"></span>This data element cannot be used here.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1037"></span>Interfaces must extend interfaces, not classes.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1038"></span>%1 is not a class. Only classes can implement interfaces.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1039"></span>%1 is not an interface.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1040"></span>EDIT and DISPLAY methods must be public.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1041"></span>Object could not be created because class %1 is abstract.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1042"></span>Object could not be created because abstract method %1 has not been implemented.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1043"></span>Column %1 has been specified more than once in the ORDER BY list. Columns in the ORDER BY list must be unique.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1044"></span>An error occurred while running the job .</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1048"></span> Abstract methods may only be declared in abstract classes.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1049"></span>Edit and Display modifiers are illegal here.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1050"></span>The Client and Server modifiers may only be used on static methods.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1052"></span>This access modifier has already been supplied.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1053"></span>Conflicting access modifier given.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1054"></span>AND and OR are used at the same level in an expression. </p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1055"></span>The variable is not an array.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1056"></span>The variable is an array.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1057"></span>Final class %1 may not be extended.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1058"></span>Numbered field references in keys cannot be used.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1059"></span>Derived method %1 may not restrict access level defined for superclass.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1060"></span>Method %1 is declared final and may not be overridden.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1061"></span>Index type must be numeric.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1062"></span>Method %1 is declared private and may not be overridden.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1063"></span>The method is declared protected and may only be called from methods in classes derived from %1.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1064"></span>The method is declared private and may only be called from methods in class %1.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1065"></span>An aggregate function is not allowed for a read-only field.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1066"></span>A field has not been selected in the SEARCH command.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1067"></span>The field has already been selected .</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1068"></span>The type does not exist. </p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1069"></span>A method named %1 has already been declared.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1071"></span>The field is not an array.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1072"></span>Illegal use of WHERE expression.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1073"></span>The class %1 does not contain this method .</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1074"></span>The variable is not of the type CLASS.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1076"></span>%1 is not a class.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1077"></span>%1 is not a class method.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1078"></span>RETRY is used outside a CATCH command.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1079"></span>The table %1 does not contain the method %2.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1080"></span>The map does not exist.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1081"></span>The map does not contain this method .</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1082"></span>The operand is not compatible with the type of the method.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1083"></span>The method cannot return a value.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1084"></span>The method %1 has not been declared.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1085"></span>The method override must be declared with the same return type as the base method.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1086"></span>The method override has an incorrect number of parameters.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1087"></span>One of the parameters for the overridden function  has an incorrect type.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1088"></span>The display method has an incorrect parameter profile.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1089"></span>The edit method has an incorrect parameter profile.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1090"></span>Super() not allowed here.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1091"></span>The class variable cannot be initialized here. Use the new method.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1092"></span>The specified class hierarchy is incorrect.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1093"></span>The name of the overridden method cannot be changed.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1094"></span>The method already exists.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1095"></span>The class already exists.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1096"></span>The operand for the method is not an element.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1099"></span> Nofetch is not allowed here.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1100"></span>The name %1 is already used in an outer scope.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1101"></span>Cannot execute on server.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1103"></span>Container and unbounded string fields are not allowed in a WHERE expression.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1104"></span>Container and unbounded string fields are not allowed in an ORDER BY or GROUP BY list.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1105"></span>Cannot add or remove static keyword for this method.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1106"></span>Variables declaration is too long. Legal size is approximately 32K in chars. </p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1107"></span>The argument should be a class.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1108"></span>The RecId index is not enabled on the table.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1109"></span>Illegal base type in array %1.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1110"></span>Name is too long. Truncate name to %1.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1111"></span>Interfaces may not be instantiated.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1112"></span>Abstract methods cannot contain code or declarations.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1128"></span>The selection field list (%1 fields) does not match the insertion field list (%2 fields).</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1129"></span>Attempt to match a specific array field element (%1) to an array (%2).</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1130"></span>Cannot match field %1 to field %2.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1131"></span>Field selections using * are illegal in INSERT statements.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1132"></span>Updating views is not supported.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1133"></span>Keyword is not allowed for this statement type.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1134"></span>Inner or outer join is illegal in this context.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1137"></span>'%1' table hint is not compatible with '%2' table hint.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1138"></span>Cannot implicitly convert type '%1' to '%2'. An explicit conversion might exist; use System.Convert.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1139"></span>No more Rec IDs. </p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1140"></span>The Client modifier may not be used on data access methods.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1141"></span>Illegal use of SETTING expression.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1142"></span>Attempt to use a field from an exists or notexists join in an illegal context.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1143"></span>Order by and group by clauses are not allowed in update_recordset statements.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1144"></span>Unable to run an update query that references both temporary and permanent database tables. Rewrite your query to only reference one type of table.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1145"></span>Qualified field names are required to use an ORDER BY and GROUP BY clause in the same SELECT statement. When using qualified field names, SELECT statements can only contain a maximum of one ORDER BY clause and one GROUP BY clause. When using unqualified field names, SELECT statements can either contain multiple ORDER BY clauses or multiple GROUP BY clauses.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1146"></span>Cannot mix unqualified ORDER BY or GROUP BY clauses with qualified ORDER BY or GROUP BY clauses.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1147"></span>When using qualified field names, statements can only contain a maximum of one ORDER BY clause and one GROUP BY clause. When using unqualified field names, statements can either contain multiple ORDER BY clauses or multiple GROUP BY clauses.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1148"></span>Unqualified and qualified field names cannot be used in the same ORDER BY or GROUP BY clause.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1149"></span>Qualified field names cannot be used in field SELECT statements.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1150"></span>Table names do not match. The table referenced in the qualified field name must match the table referenced  in the SELECT statement.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1151"></span>Invalid join mode in union query. Join mode of the second level data source for query of type union can only be exists or notexist.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1152"></span>Field mismatch in union query. Field '%1' is not compatible with field '%2'.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1153"></span>Field number mismatch in union query. Field number in '%1' is not the same as the field number in '%2'.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1154"></span>Field ‘%1’ can only be used once in the ORDER BY clause. Fields used in the ORDER BY clause must be unique.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1155"></span>Field ‘%1’ can only be used once in the GROUP BY clause. Fields used in the GROUP BY clause must be unique.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1156"></span>Temporary tables can have either Group By or Order By fields, but not both.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1157"></span>The specified sequence of Group By and Order By fields is not supported.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1158"></span>Variable %1 is not an array.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1159"></span>The variable %1 does not match the field %2.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1160"></span>The variable %1 does not match field %2.Each must be defined using the same extended data type.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1161"></span>Variable %1 must be a container.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1162"></span>The use of the keyword CROSSCOMPANY  is invalid in this context.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1165"></span>An aggregate field cannot be specified on a query data source that is selected for update.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1166"></span>There was an invalid use of %1 unbound string during insert. </p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1167"></span>The size of variable %1 does not match the size of field %2. A loss of data is possible.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1168"></span>Invalid use of the DataAreaId field in a cross-company query.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1169"></span>Invalid use of a container field during insert.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1170"></span>A cross-company UNION ALL query cannot contain both a company specific and global table unless the data area field is explicitly selected.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1173"></span>Field '%1' is used in an EXISTS JOIN or NOTEXISTS JOIN clause and cannot be used in a GROUP BY and ORDER BY clause.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1176"></span>Invalid usage of crosscompany  in this context.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1182"></span>Cannot set a table as temporary which is part of inheritance hierarchy .</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1183"></span>The %1 attribute class has not been declared.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1184"></span>The name %1 is not a class that extends the %2 class.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1185"></span>Attribute classes cannot be used on the %1 function. Attribute classes can be used only on class or table methods, class declarations, or delegates.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1186"></span>Argument %1 loses precision during assignment or comparison.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1187"></span>Variables %1 and %2 to validTimeState has to be date or utcdatetime type. </p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1188"></span>Variable %1 has to  be date or utcDateTime.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1189"></span>Invalid usage of validtimestate in this context .</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1190"></span>The %1 class is obsolete. %2</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1191"></span>The %1 method is obsolete. %2</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1192"></span>Calling setTmp is not allowed on a valid time state table buffer.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1193"></span>Table does not contain a valid time state key. A unique index needs to be marked as a valid time state key.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1195"></span>The type %1 must designate a compatible class, an interface, or a table.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1196"></span>The managed type %1 is not known. Add a reference to the assembly containing the type.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1097"></span>The static type of the expression is incompatible with the type %1.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1198"></span>The class %1 should not be declared as private.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1201"></span>The .NET managed namespace %1 was not found. The corresponding assembly is not registered in the AOT References, or the assembly file has not been copied to the Client\Bin\ directory under the installation path.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1202"></span>Table %1 cannot be filtered with a validTimeState  clause because its ValidTimeStateFieldType property is None.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1203"></span>The wrong number of parameters are passed during object creation.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1204"></span>Parameter %1 must have a default value.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1205"></span>The type on the throw statement must be a value of the Exception enum. </p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1206"></span>The array parameter %1 cannot specify the array size.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1207"></span>Parameter %1 cannot be a str type array. Use the Array class for a parameter of str values .</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1214"></span>Managed arrays do not support the syntax of a direct indexer. Use the GetValue and SetValue methods to access the elements in managed arrays.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1232"></span>The event handler definition is invalid. The static method %1 does not exist in the class %2.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1233"></span>The event handler definition is invalid. The static method %1 in class %2 cannot be used because it is not public.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1234"></span>The event handler definition is invalid. The static method %1 in class %2 does not return void.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1235"></span>The number of parameters in the method %1, in class %2, does not match the event definition.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1236"></span>A parameter in the method %1, in class %2, does not match the event definition.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1239"></span>The event handler definition is invalid. The method %1 does not exist in the class %2.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1240"></span>The event handler definition is invalid. The method %1 in class %2 cannot be used because it is not public.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1241"></span>The event handler definition is invalid. The method %1 in class %2 does not return void.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1242"></span>Map and view fields cannot be assigned to fields in an update_recordset  statement.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1243"></span>%1 %2  method is not supported when the Data Sources ChangeGroupMode property is set to None.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1244"></span>%1 %2 method is not supported when the Data Sources ChangeGroupMode property is set to ImplicitInnerOuter.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1245"></span>The join  keyword is illegal in this context.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1246"></span>Static constructors are not supported.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1248"></span>Invalid call to abstract method .</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1249"></span>An event handler cannot subscribe to itself.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1250"></span>Overriding a delegate is not supported.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1251"></span>A derived table in table inheritance cannot override system  field.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1252"></span>The assignment is invalid because the variable %1 is read only.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="err1253"></span>To use the attribute SysEntryPointAttribute, the method must run on the server tier. Add the server  keyword to the X++ method declaration, or change the RunOn property of the class that contains the method.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="err1258"></span>The event handler definition is invalid. The method %1 in class %2 must have exactly one argument of type XppPrePostArgs or must match the method signature exactly.</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## See also

[Best Practices Checks](best-practices-checks.md)

[Best Practices: Avoiding Potential Security Issues](best-practices-avoiding-potential-security-issues.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

