---
title: Change Group and Optional Record Modes
TOCTitle: Change Group and Optional Record Modes
ms:assetid: 31c19b4b-f88d-4a6a-8c23-a393180c62d0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ129662(v=AX.60)
ms:contentKeyID: 46687528
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Change Group and Optional Record Modes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You use change group and optional record modes to specify the behavior you want to occur when a parent record is created, updated, or deleted. You use the **ChangeGroupMode** and **OptionalRecordMode** properties of the form data source to specify how a record that includes joined tables is created, updated, or deleted. The following sections describe change groups and optional records.

## Specifying the Behavior of Joins in a Form Data Source

If the AOT shows that the database tables in the form data source have a **Relation**, you can use the properties in the form data source to create an inner or outer join between the tables. For more information about joins between form data source tables, see [How to: Join Data Sources for a Form](how-to-join-data-sources-for-a-form.md).

To use joined tables in a form data source, you have to make sure that create, update, and delete operations support the following behavior:

  - A record that uses joined tables must include foreign key values that identify the related records.

  - A record in a joined table is created when it is needed. For example, the record in an outer joined table can be optional. As a result, you might not create a record in the outer joined table until a field for that table is populated.

  - The data changes in create, update, or delete operations are consistently applied to all the related tables for the specified record. If an error occurs, the changes are rolled back across all joined tables.

To help you efficiently implement each behavior, you can use change groups and optional records.

## Change Groups

A change group is a set of joined tables in a form data source. You can use a change group when the data that appears on a form includes fields from one or more joined tables. You use a change group to simplify how you create, update, or delete a record that includes a join to another table. You use the change group to help complete the following actions:

  - Add and maintain the foreign key values that identify the related records.

  - Use a database transaction when you make a change to any of the tables in the group. If the create, update, or delete operation fails for any of the tables in the change group, the change is rolled back for all the tables in the group.

To implement a database transaction, the change group uses the UnitOfWork class on the server to create and manage the transaction. For more information about UnitOfWork class on the server, see [How to: Use the UnitOfWork Class to Manage Database Transactions](how-to-use-the-unitofwork-class-to-manage-database-transactions.md).

To support a change group, the **Relation** between the joined tables must be **Normal**. For information about table relations, see [How to: Add a Relation to a Table](how-to-add-a-relation-to-a-table.md).

You should use a change group when the form data source includes an inner or outer join relationship between tables. You can use a change group that has a join that includes one-to-zero, one-to-one, or one-to-many type relationships.


> [!IMPORTANT]
> <P>If you have a relationship between tables that uses a dynalink, the change group does not span the dynalink. Each query is treated like a separate change group.</P>



### ![JJ129662.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129662.collapse_all(en-us,AX.60).gif")Setting the ChangeGroupMode property

To create a change group, you use the **ChangeGroupMode** property of the **Data Source** node of the form. However, the default behavior is not to use a change group together with a form. You can use **ChangeGroupMode** to create a change group for any of the following types of forms:

  - A new form that you create in the AOT.

  - A form that includes date effective data.

  - A form with a data source where a parent table has a join relationship to a child table where the child holds a reference to the parent table. The reference can be either mandatory or optional.

To specify whether to use a change group, you populate the **ChangeGroupMode** property by using one of the following values.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ImplicitInnerOuter</strong></p></td>
<td><p>Use a change group for the tables in the form data source.</p></td>
</tr>
<tr class="even">
<td><p><strong>None</strong></p></td>
<td><p>Do not use a change group for the tables in the form data source. This is the default value.</p></td>
</tr>
</tbody>
</table>


If you set the **ChangeGroupMode** to **None**, you might have to override the Write or Delete method of the data source table. You would override these methods when you want to how the form updates the database tables on the server. Most existing Microsoft Dynamics AX forms have the **ChangeGroupMode** property set to **None**.

### ![JJ129662.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129662.collapse_all(en-us,AX.60).gif")Overriding of methods

When you save changes to a joined record, you might have actions that you want to perform before the write operation and after the write operation. To complete these operations you can override methods of the form data source table.

For example, you have a form with a data source table named FDS1 and a joined data source table named FDS2. You want to complete the following actions:

  - Validate the data for fields.

  - Perform a series of actions before you write the changes to the database table.

  - Perform actions after you write the changes to the database.

The following table shows the sequence of transactions and methods for a form where the **ChangeGroupMode** property is set to **None**. This is the same behavior that was used with Microsoft Dynamics AX 2009. Notice that each table has its own dedicated transaction.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Transaction</p></th>
<th><p>Method sequence</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Transaction 1</p></td>
<td><p>FDS1.ValidateWrite</p>
<p>FDS1.write</p></td>
<td><p>In the write method, you add pre-write code before the call to super and post-write code after the call to super.</p></td>
</tr>
<tr class="even">
<td><p>Transaction 2</p></td>
<td><p>FDS2.ValidateWrite</p>
<p>FDS2.write</p></td>
<td><p>In the write method, you add pre-write code before the call to super and post-write code after the call to super.</p></td>
</tr>
</tbody>
</table>


The use of a change group alters the sequence of transactions and method calls. Now each table does not have its own dedicated transaction. The following table shows the sequence of transactions and methods that are used when the **ChangeGroupMode** property is set to **ImplicitInnerOuter**. Notice that all the pre-write, server call, and post-write actions for FDS1 and FDS2 are included in a single transaction.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Transaction</p></th>
<th><p>Method sequence</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>None</p></td>
<td><p>FDS1.ValidateWrite</p>
<p>FDS2.ValidateWrite</p></td>
<td><p>Validation on the client is completed before the transaction starts.</p></td>
</tr>
<tr class="even">
<td><p>Transaction 1</p></td>
<td><p>FDS1.writing</p>
<p>FDS2.writing</p>
<p>The UnitOfWork class runs on the server</p>
<p>FDS1.written</p>
<p>FDS2.written</p></td>
<td><p>You use the writing methods to perform any pre-write actions.</p>
<p>You use the written method for any post-write actions.</p></td>
</tr>
</tbody>
</table>


If you change the **ChangeGroupMode** from **None** to **ImplicitInnerOuter**, you must refactor any code in the write methods of the data source tables.

  - Code that you had put in the write method before the call to super must be moved to the writing method.

  - Code you had in the writing method after the call to super must be moved to the written method.

There is a similar pattern for a delete operation. If you use a change group, you have to override the deleting method for any pre-delete actions and the deleted method for any post-delete actions.

## Optional Records

An optional record is a child record found in an outer join table where the child record does not have to be created at the time the parent record is created. You can use the optional record mode of the form data source to specify the create behavior for the child record.


> [!IMPORTANT]
> <P>To use optional records, the <STRONG>Relations</STRONG> between the database tables must be <STRONG>Normal</STRONG>.</P>



Optional record mode enables you to use one of the following behavior to create the child record in the outer joined table.

  - You can specify that the record be created when a field in the child record has a value assigned to it. The assignment can be explicit or a configured default.

  - You can use a check box control to specify how the system treats child records during create or delete operations on the parent record of a joined table.

  - You can use the same behavior that was used in Microsoft Dynamics AX 2009.

To use optional record mode, you set the following values for properties in the form data source.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Location</p></th>
<th><p>Value</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ChangeGroupMode</strong></p></td>
<td><p><strong>Data Sources</strong> properties</p></td>
<td><p><strong>ImplicitInnerOuter</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>LinkType</strong></p></td>
<td><p>Form data source table properties</p></td>
<td><p><strong>OuterJoin</strong></p></td>
</tr>
</tbody>
</table>


A form data source can include more than one join relationship between tables. You can use different optional record modes to independently define the optional record behavior for each join relationship in the form data source. For example the **UnitOfMeasure** form in the AOT has joins that uses both implicit and explicit create behavior.

### ![JJ129662.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129662.collapse_all(en-us,AX.60).gif")Setting the OptionalRecordMode property

To create optional records in a form data source, you set the **OptionalRecordMode** property on the table in the form data source where the child record is created. To control optional records, you set the **OptionalRecordMode** property to one of the following values.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ExplicitCreate</strong></p></td>
<td><p>You use a check box control to explicitly specify whether to create or delete the joined record. If the check box is selected, the record is always created. If the check box is cleared, the record is always deleted.</p></td>
</tr>
<tr class="even">
<td><p><strong>ImplicitCreate</strong></p></td>
<td><p>When you create the parent record, an empty child record is created implicitly in memory. However, if no fields in the child record are populated, the empty child record is discarded when the parent record is written to the database.</p>
<p>This is the default value that appears when you add a table to the <strong>Data Sources</strong> node of a form.</p></td>
</tr>
<tr class="odd">
<td><p><strong>None</strong></p></td>
<td><p>The outer join behaves the same as in Microsoft Dynamics AX 2009. To add or delete a child record, you use the write or delete method for that data source table. The create method is not used to initialize the child record.</p>
<p>Use this value when you want to use a change group but you want to retain the existing overrides of write or other methods.</p></td>
</tr>
</tbody>
</table>


### ![JJ129662.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129662.collapse_all(en-us,AX.60).gif")Implicit create

An implicit create occurs when you set the **OptionalRecordMode** property to **ImplicitCreate**. When a parent record is created, the create method of the child data source is also called by the system. The create method of the child data source adds an empty record in memory. However, the write method is not called unless a change is made that populates a field in the child record. If no fields are populated, the empty record is deleted from memory.


> [!WARNING]
> <P>If you initialize the child record and specify default values for one or more fields, the optional record will always be saved. The use of default values in a field will cause the implicit create behavior to write the child record to the database table.</P>



### ![JJ129662.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129662.collapse_all(en-us,AX.60).gif")Explicit create

An explicit create occurs when you set the **OptionalRecordMode** property to **ExplicitCreate**. When you use **ExplicitCreate**, you must add a check box to the **Design** node of the form that specifies whether to create or delete the child record. To enable the check box control to create or delete the optional child record, set the following properties of the check box control.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Value</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DataSource</strong></p></td>
<td><p>Specify the table where you set the <strong>OptionalRecordMode</strong> property to <strong>ExplicitCreate</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>OptionalRecordControl</strong></p></td>
<td><p><strong>Yes</strong></p></td>
</tr>
</tbody>
</table>


When you set the **OptionalRecordControl** to **Yes**, the create method of the specified data source is called when you select the check box. When you save the record, the writing and written methods of the specified data source are called. If you later clear the check box, the deleting and deleted methods of the specified data source are called.

To see an example of a form that uses explicit create, review the form data source of the **UnitOfMeasure** form in the AOT. The data sources of that form include a join to the **UnitOfMeasureInternalCode** where the **OptionalRecordMode** is set to **ExplicitCreate**.

## See also

[Data Sources for Forms](data-sources-for-forms.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

