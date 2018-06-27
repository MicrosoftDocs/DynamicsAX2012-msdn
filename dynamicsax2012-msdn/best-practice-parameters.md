---
title: Best practice parameters
TOCTitle: Best practice parameters
ms:assetid: e3fbc873-9121-4f78-9c54-40a2d9cfedaf
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa880220(v=AX.60)
ms:contentKeyID: 35253171
ms.date: 05/18/2015
mtps_version: v=AX.60
f1_keywords:
- Forms.SysBPSetup
- MsDynAx060.Forms.SysBPSetup
---

# Best practice parameters 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Best practice checks help to make sure that the best practice guidelines are followed. Use the **Best practice parameters** form to select which best practice checks to verify.

Select from the **Warning level:** drop-down to specify the kinds of messages produced. The warning levels are as follows:

  - **Errors only** - Messages only about best practice errors.

  - **Errors and warnings** - Messages only about best practice errors and warnings.

  - **All** - Messages about violations to all best practices checks.

Select from the **Layer setting:** drop-down to specify the layers that will be checked for best practice violations. The layer settings are as follows:

  - **Check all nodes** – All layers will be checked for best practice violations.

  - **Skip nodes from lower layers** – Only the nodes defined in the current layer and above will be checked for best practice violations.

Use the check box to select or clear individual checks.


> [!NOTE]
> <P>Disabling a check suppresses the messages about violations to the check, not the check itself.</P>



The following table provides information on the best practice checks.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Check</p></td>
<td><p>Description</p></td>
</tr>
<tr class="even">
<td><p><strong>Best Practice checks</strong></p></td>
<td><p>Select or clear this check box to select or clear all <strong>Best Practice checks</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>General checks</strong></p></td>
<td><p>Select or clear this check box to select or clear all best practice checks under the <strong>General checks</strong> node.</p></td>
</tr>
<tr class="even">
<td><p><strong>Properties</strong></p></td>
<td><p>Check the use of default values on properties.</p>
<p>This option checks only the properties where default values are expected. The setup of properties that do not have default values is evaluated by other, more specific, checks.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Unique tree node names in the AOT</strong></p></td>
<td><p>Check whether the tree node names are unique in the Application Object Tree (AOT).</p>
<p>Each path in the AOT must be unique. This means that within a node identical names must not exist.</p></td>
</tr>
<tr class="even">
<td><p><strong>Object ID</strong></p></td>
<td><p>Check for changed legacy IDs, name, and origin compared to the base line version.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AOS Performance</strong></p></td>
<td><p>Check Application Object Server (AOS) performance.</p>
<p>Check that methods are bound to the client or server tier in the most optimal way regarding performance.</p></td>
</tr>
<tr class="even">
<td><p><strong>Trustworthy Computing</strong></p></td>
<td><p>Check whether trustworthy computing best practices have been followed.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Existence of referenced application objects</strong></p></td>
<td><p>Check the existence of referenced application objects.</p>
<p>This check scans specific areas to see whether the specific referenced application object exists. Also examines whether a field of a specific data type is sufficiently long enough to hold the related value.</p></td>
</tr>
<tr class="even">
<td><p><strong>Use of discontinued functionality</strong></p></td>
<td><p>Check whether functionality used in the system has been replaced by new features.</p>
<p>If an application object is planned to be discontinued in an upcoming version, it is a best practice to not use the application object in this version. This check scans for usage of objects that are planned to be discontinued.</p>

> [!note]  
> <P>It is possible that other application objects that are not checked by this method might also be discontinued.</P>

</td>
</tr>
<tr class="odd">
<td><p><strong>Record and table ID references</strong></p></td>
<td><p>Check that metadata is valid for fields that contain record or table ID references.</p></td>
</tr>
<tr class="even">
<td><p><strong>Configuration Keys</strong></p></td>
<td><p>Check the use of configuration keys.</p>
<p>Each configuration key should have a unique name and ID.</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Labels</strong></p></td>
<td><p>Select or clear this check box to select or clear all best practice checks under the <strong>Labels</strong> node.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Use of labels</strong></p></td>
<td><p>Check the use of labels.</p></td>
</tr>
<tr class="even">
<td><p><strong>Use of labels for Help</strong></p></td>
<td><p>Check the use of labels for Help text.</p>
<p>This check examines whether labels are used on Help properties, and also whether they are used correctly.</p>
<p>The following list describes the main rules about how to use labels for help.</p>
<ul>
<li><p>Use labels for user interface text.</p></li>
<li><p>Use quotation marks for user interface text in the source code.</p></li>
<li><p>Help must not be a copy of the elements label.</p></li>
<li><p>Sentences must always end with a period.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Specific checks</strong></p></td>
<td><p>Select or clear this check box to select or clear all best practice checks under the <strong>Specific checks</strong> node.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tables</strong></p></td>
<td><p>Select or clear this check box to select or clear all best practice checks under the <strong>Tables</strong> node.</p></td>
</tr>
<tr class="even">
<td><p><strong>Unique labels</strong></p></td>
<td><p>Check whether table fields have unique labels.</p>
<p>Examines the table fields and the display and edit methods to make sure that the user interface texts are unique.</p>
<p>If a display or edit method does not use an enumeration value or an extended data type as a return type, a warning will be displayed.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Use of indexes</strong></p></td>
<td><p>Check the use of indexes.</p>
<p>The following list describes the various areas that are checked.</p>
<ul>
<li><p>Cluster index – Tables with only one index should have that index defined as a cluster index.</p></li>
<li><p>Primary index – A primary index should be defined if there is a unique index.</p></li>
<li><p>The use of the RecID value.</p></li>
<li><p>No overlapping indexes.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Delete actions</strong></p></td>
<td><p>Check the use of delete actions.</p>
<p>Checks that tables do not have delete actions pointing to each other.</p>
<p>If Table A has a delete action to Table B, it is not valid for Table B to have a delete action to Table A.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Declared title fields</strong></p></td>
<td><p>Check that the title fields have been declared.</p>
<p>The two best fields for the TitleField1 and TitleField2 fields must be declared.</p>
<p>The following list describes the guidelines.</p>
<ul>
<li><p>TitleField1: The key field for the records in the table.</p></li>
<li><p>TitleField2: The description for the records in the table.</p></li>
<li><p>For example:</p>
<p>TitleField1: ItemGroupId</p>
<p>TitleField2: Name</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Form reference</strong></p></td>
<td><p>Check the existence of the referenced menu item.</p>
<p>Checks whether a referenced display menu item that links to the View details form exists for certain table types, or if it is explicitly declared on the FormRef property.</p>
<p>The default form is the form that the system displays when the user starts the <strong>View details</strong> action by using the shortcut menu for a field on a form.</p>
<p>The form is referenced through a menu item the <strong>Display</strong> type.</p>
<p>If the FormRef property is left blank, Microsoft Dynamics AX attempts to open a form that has the same name as the table.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AxBC fields</strong></p></td>
<td><p>Check the use of AxBC fields.</p></td>
</tr>
<tr class="even">
<td><p><strong>Use of labels for developer documentation</strong></p></td>
<td><p>Check whether labels are used for developer documentation.</p>
<p>The <strong>DeveloperDocumentation</strong> property is used to describe the purpose of an element so that application developers are able to understand what the element is used for. The <strong>DeveloperDocumentation</strong> property appears in the <strong>Properties</strong> window for tables, views, and maps. The description provided for the <strong>DeveloperDocumentation</strong> property is typically no more than five sentences, and is written as a single paragraph.</p>
<p>This check examines the value entered for the <strong>DeveloperDocumentation</strong> property to ensure that labels are used. If a string rather than a label is used, an error displays indicating that the property must contain a label ID. If nothing is entered for the <strong>DeveloperDocumentation</strong> property, no warnings or errors display.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fields belong to a field group</strong></p></td>
<td><p>Check whether fields belong to a field group.</p>
<p>Any field that appears in the user interface must belong to a field group. This menas that field groups can always be used when you design a form.</p>
<p>A field group must be defined when several fields logically belong together and are shown together on forms and reports.</p>
<p>Field groups must be named by using a label on the <strong>Name</strong> property.</p>
<p>The following is a list of standardized group names.</p>
<ul>
<li><p>Identification</p></li>
<li><p>Description</p></li>
<li><p>Administration</p></li>
<li><p>Address</p></li>
<li><p>A module name; for example, Ledger</p></li>
<li><p>Setup</p></li>
<li><p>Dimension</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Field name/Method name conflict</strong></p></td>
<td><p>Check a table does not have a field and a method with the same name.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Financial dimensions</strong></p></td>
<td><p>Check whether fields intending to hold foreign keys to a LedgerDimension (DimensionAttributeValueCombination.RecId) are properly defined in the table.</p>
<p>Fields must adhere to the following standards:</p>
<ol>
<li><p>The field name must contain LedgerDimension. For example, OffsetLedgerDimension, or PostedLedgerDimension.</p></li>
<li><p>The field must extend an EDT that extends LedgerDimensionBase. For example, LedgerDimensionAccount, or LedgerDimensionDefaultAccount.</p></li>
<li><p>The field must not directly extend LedgerDimensionBase.</p></li>
<li><p>The field must have a proper Primary Key Foreign Key relationship set up to the DimensionAttributeValueCombination table RecId field.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>Number of fields in field groups</strong></p></td>
<td><p>Check the number of fields in a field group.</p>
<p>A field group must be defined when several fields logically belong together and are shown together on forms and reports.</p>
<p>Field groups must be named by using a label on the <strong>Name</strong> property.</p>
<p>The AutoReport field group is defined on every table.</p>
<p><strong>AutoReport</strong></p>
<p>At least two fields must be included in the AutoReport field group on each table. These are the fields that the user expects to print when <strong>Print</strong> is clicked from the <strong>File</strong> menu. Often the fields specified for the <strong>TitleField1</strong> and <strong>TitleField2</strong> properties are candidates for the <strong>AutoReport</strong> field group.</p>
<p><strong>Dimension</strong></p>
<p>The dimension field must be the only field in the <strong>Dimension</strong> field group.</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Currency code fields</strong></p></td>
<td><p>Check the use of the <strong>CurrencyCode</strong> related properties.</p>
<p>The <strong>CurrencyCode</strong> property must be set on all fields by using an extended data type derived from the Money system type, if the <strong>AnalysisVisibility</strong> property is set to <strong>High</strong>, <strong>Medium</strong>, or <strong>Low</strong>. It should not be set on any other fields. You must set <strong>CurrencyCode</strong> to <strong>SecondaryCurrency</strong> if the field uses an extended data type derived from AmountMSTSecondary; otherwise, set it to <strong>CurrencyCodeField</strong>.</p>
<p>If the <strong>CurrencyCode</strong> property is set to <strong>CurrencyCodeField</strong>, you must also set the <strong>CurrencyCodeTable</strong> property to the table that contains that field, or to a table for which a relationship exists from the table that contains this field, and in which a unique index exists for the fields on the target end of the relationship. If <strong>CurrencyCode</strong> is set to <strong>CurrencyCodeField</strong>, you must also set the <strong>CurrencyCodeField</strong> property to a field that uses an extended data type derived from the <strong>CurrencyCode</strong> property.</p>

> [!note]  
> <P>Do not use master currency amounts to set the <strong>CurrencyCode</strong> properties, because master currency amounts are always in the master currency for the associated company.</P>

</td>
</tr>
<tr class="odd">
<td><p><strong>Currency date fields</strong></p></td>
<td><p>Check the use of the currency date fields.</p></td>
</tr>
<tr class="even">
<td><p><strong>Check table relations</strong></p></td>
<td><p>Check that related string fields have the same length and justification.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Use of labels for entity relationship role</strong></p></td>
<td><p>Check whether labels are used when describing the role of a table relation.</p>
<p>The <strong>EntityRelationshipRole</strong> property is used to clarify the semantics of a relationship defined on a table. A role name should be either a noun or a noun phrase. The role name should indicate the role of the associated table in relation to the associating object, or it should be a short phrase that starts with a present-tense verb that indicates the role that the table plays in the relationship. Role names are not required when the relationship is unambiguous.</p>
<p>This check examines the value entered for the <strong>EntityRelationshipRole</strong> property to make sure that labels are used. If a string instead of a label is used, an error displays indicating that the property must contain a label ID. If nothing is entered for the <strong>EntityRelationshipRole</strong> property, no warnings or errors display.</p></td>
</tr>
<tr class="even">
<td><p><strong>Unit of measure upgrade</strong></p></td>
<td><p>Check that an upgrade rule is set for all tables that use unit of measure.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Check for identical right and left parts of relation</strong></p></td>
<td><p>Check whether normal relations contain identical fields from the same table.It is not a best practice to have identical fields from the same table belong to the same normal relation.</p></td>
</tr>
<tr class="even">
<td><p><strong>Table collections</strong></p></td>
<td><p>Select or clear this check box to select or clear all best practice checks under the <strong>Table collections</strong> node.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Relations</strong></p></td>
<td><p>Check that the referenced tables exist in the table collections.</p></td>
</tr>
<tr class="even">
<td><p><strong>Classes</strong></p></td>
<td><p>Select or clear this check box to select or clear all best practice checks under the <strong>Classes</strong> node.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Abstract</strong></p></td>
<td><p>Check that abstract classes are marked abstract.</p>
<p>A class must be marked as abstract if it extends an abstract class and does not implement all the abstract methods.</p>
<p>This can cause runtime errors when the abstract method is called.</p></td>
</tr>
<tr class="even">
<td><p><strong>RunBase implementation</strong></p></td>
<td><p>Check that classes are implemented according to the guidelines in the RunBase framework.</p>
<p>This check examines whether the description method is implemented.</p>
<p>RunBase framework implementations must have a static description method.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Missing member function</strong></p></td>
<td><p>Check the class for missing member functions.</p>
<p>Check that the class is not empty meaning no member variables and no methods.</p>
<p>The possible inheritance and declaration of variables are checked to determine if a member should be present.</p>
<p>At least one member function that does not calculate the ClassDeclaration must always be present in a class.</p></td>
</tr>
<tr class="even">
<td><p><strong>Constructors</strong></p></td>
<td><p>Check the implementation of class constructors.</p>
<p>This check validates that each class contains a static construct method.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Methods</strong></p></td>
<td><p>Select or clear this check box to select or clear all best practice checks under the <strong>Methods</strong> node.</p></td>
</tr>
<tr class="even">
<td><p><strong>Empty methods</strong></p></td>
<td><p>Check for methods with no code.</p>
<p>By checking for empty methods, you can detect whether any member functions have been created and left in the system without any code.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Date features</strong></p></td>
<td><p>Check the use of date features.</p>
<p>By checking the overall use of date features, you can check various problems related to date functionality.</p>
<p>It is typically not necessary to format a date to a string. Instead, use date fields, variables, and date controls directly on forms and reports.</p>
<p>Never permanently store a date in anything other than a date field.</p>
<p>If you must format a date to a string, do the following:</p>
<ul>
<li><p>For user interface situations - use strFmt, or date2str with -1, in all the formatting parameters, to use the formatting the user has specified in Regional Settings.</p></li>
<li><p>For other specific system related situations, such as communication with external systems - use date2str, with the relevant parameters dictated by the situation.</p></li>
</ul>
<p>If Regional Settings dictates the format, be aware that the format can change from user to user, and that it might not be a suitable format for external communication.</p>
<p>When you use date2str, always make sure that the resultant string can be held in the receiving place. For example, ensure that the receiving variables are long enough.</p>
<p>Str2Date</p>
<p>Using str2date indicates that dates are being used that have previously had a string format.</p>
<p>Today</p>
<p>The system date provided by the today function should be used only where the actual machine date is needed.</p>
<p>Most application logic should use the system function systemDateGet, which holds the logic date of the system.</p></td>
</tr>
<tr class="even">
<td><p><strong>Access modifier</strong></p></td>
<td><p>Check whether the access modifier of a method can be set to private, protected, or public based on how it is called.</p>
<p>This check examines how the access modifier of a method can be set to private, protected, or public, based on where it is called from.</p>
<p>A tip will be displayed if the access modifier of the method has not been set, and:</p>
<p>the method can be set to private instead of public.</p>
<p>-or-</p>
<p>the method can be explicitly specified as public.</p>
<p>If the programmer has explicitly specified any of the possible access modfiers, the check is skipped.</p>
<p>The compiler will check whether combinations are possible.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Print &amp; pause</strong></p></td>
<td><p>Check the source code for the use of print and pause statements.</p>
<p>Avoid the use of print and pause statements for any purpose other than testing.</p></td>
</tr>
<tr class="even">
<td><p><strong>Use of variables</strong></p></td>
<td><p>Check how variables are used.</p>
<p>This check examines how variable are declared and used. Unused parameters and variables will be exposed. Additional checks for good programming styles, such as some of the naming rules of variables, are also covered by this check.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Future reserved words</strong></p></td>
<td><p>Check whether any names conflict with future reserved words.</p>
<p>This check examines whether a word is used that might be treated as a reserved word in an upcoming version. It is not possible to predict all future reserved words, but the check includes the words that are most likely to be used.</p></td>
</tr>
<tr class="even">
<td><p><strong>Text in single quotation marks</strong></p></td>
<td><p>Check the use of text in single quotes.</p>
<p>This check examines whether system-oriented text in the source is written in single quotes.</p>
<p>The system must be maintainable, so if a text or a numeric constant is used with the same meaning in more than one place, the text is defined as locally as possible: a member function, in a class declaration, or globally in a macro.</p>
<p>Always consider an alternative way to get the &quot;constant&quot;; often, it is defined in another place, from where it can be reused.</p></td>
</tr>
<tr class="odd">
<td><p><strong>XML documentation</strong></p></td>
<td><p>Check the XML documentation for errors.</p>
<p>This check verifies that the XML documentation comments are properly formatted and contain required information.</p>
<p>The following list describes the main rules.</p>
<ul>
<li><p>Tag pairs must match containing an opening and closing tag.</p></li>
<li><p>Documentation is missing after certain tags are used.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Version control references</strong></p></td>
<td><p>Check whether referenced elements are under version control.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SysOperation label attribute</strong></p></td>
<td><p>Check whether a label defined is a label ID and not a string. When using the SysOperationLabelAttribute or SysOperationGroupAttribute attributes, you can specify the label as part of its constructor.</p></td>
</tr>
<tr class="even">
<td><p><strong>Forms</strong></p></td>
<td><p>Select or clear this check box to select or clear all best practice checks under the <strong>Forms</strong> node.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Form style</strong></p></td>
<td><p>Check that the form follows user experience guidelines for the specified style of the form.</p></td>
</tr>
<tr class="even">
<td><p><strong>Form size</strong></p></td>
<td><p>Check that the form size does not exceed the maximum size.</p>
<p>A form must fit into a screen with a resolution of 1024x768 pixels. If the screen resolution exceeds 1024x768 pixels a warning is issued. If the screen resolution exceeds 1280x1024 pixels an error is issued.</p>
<p>To calculate the form size, the check will open and close the form, and will therefore cause the screen to flicker.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Disabling technique</strong></p></td>
<td><p>Check the setup of form control disabling.</p>
<p>The following list describes how fields that the user should not be able to change should be set on the property sheet or from code.</p>
<p><strong>AllowEdit</strong>: Set to <strong>No</strong>, so that the user cannot change the value. The <strong>AllowEdit</strong> property is available on each field in a table, each field in a form data source, and each control on a form. If <strong>AllowEdit</strong> is set to <strong>No</strong>, set it as close to the table field as possible.</p>
<p><strong>Skip</strong>: Set to <strong>Yes</strong>. Set <strong>Skip</strong> to <strong>Yes</strong> if the user should not enter the field when he or she is tabbing through the form.</p>
<p><strong>Enabled</strong>: Set to <strong>Yes</strong>. The user can explicitly navigate to the field to see the Help text or to copy the field value.</p></td>
</tr>
<tr class="even">
<td><p><strong>Control names</strong></p></td>
<td><p>Check the naming of controls.</p>
<p>This check validates that each control on a form has a unique name.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tab</strong></p></td>
<td><p>Check the form has correct tab pages with correct captions.</p></td>
</tr>
<tr class="even">
<td><p><strong>Perspectives</strong></p></td>
<td><p>Select or clear this check box to select or clear all best practice checks under the <strong>Perspectives</strong> node.</p></td>
</tr>
<tr class="odd">
<td><p><strong>All analysis visible objects are included</strong></p></td>
<td><p>Check that all perspectives contain a configuration key, have a label, and have help text.</p></td>
</tr>
<tr class="even">
<td><p><strong>Workflow</strong></p></td>
<td><p>Select or clear this check box to select or clear all best practice checks under the <strong>Workflow</strong> node.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Workflow categories</strong></p></td>
<td><p>Check the properties of workflow categories.</p>
<p>This check verifies that the workflow category properties are correctly configured for execution.</p></td>
</tr>
<tr class="even">
<td><p><strong>Workflow types</strong></p></td>
<td><p>Check the properties of workflow types.</p>
<p>This check verifies that the workflow type properties are correctly configured for execution.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Workflow approvals</strong></p></td>
<td><p>Check the properties of workflow approvals.</p>
<p>This check verifies that the workflow approval properties are correctly configured for execution.</p></td>
</tr>
<tr class="even">
<td><p><strong>Workflow tasks</strong></p></td>
<td><p>Check the properties of workflow tasks.</p>
<p>This check verifies that the workflow task properties are correctly configured for execution.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Application Integration Framework</strong></p></td>
<td><p>Select or clear this check box to select or clear all best practice checks under the <strong>Application Integration Framework</strong> node.</p></td>
</tr>
<tr class="even">
<td><p><strong>Entity and Data Objects Classes</strong></p></td>
<td><p>Check that data objects are current.</p>
<p>This verifies that the data objects are synchronized with the underlying artifacts that were used to define the data object. The best practice check is for missing or extra methods in the table. Use the <strong>Update document service</strong> form to keep the data objects synchronized with the underlying artifacts.</p></td>
</tr>
</tbody>
</table>


## See also

[Best Practices for Microsoft Dynamics AX Development](best-practices-for-microsoft-dynamics-ax-development.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

