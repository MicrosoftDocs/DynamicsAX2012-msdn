---
title: EDT Relation Migration Tool
TOCTitle: EDT Relation Migration Tool
ms:assetid: da71a84d-1414-47ce-91d7-773f4a0d29bc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg989788(v=AX.60)
ms:contentKeyID: 35405145
ms.date: 05/18/2015
mtps_version: v=AX.60
f1_keywords:
- MsDynAx060.Forms.SysEDTMigrationForm
- Forms.SysEDTMigrationForm
---

# EDT Relation Migration Tool 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX 2012, relations can no longer be created under extended data type (EDT) nodes in the Application Object Tree (AOT). Relations that are defined under EDT nodes are still effective, but in a future release they will be obsolete and deleted. The EDT relation migration tool helps you move relations from EDT nodes to table nodes. The EDT relation migration tool is found on the client menu, under **Tools** \> **Code upgrade** \> **EDT relation migration tool**.

## The Representation of Relations

Before Microsoft Dynamics AX 2012, relations could be defined under the **Relations** node of an EDT node, or under a table node.

The following table describes the differences between how relations were handled in Microsoft Dynamics AX 2009 and how relations are handled in Microsoft Dynamics AX 2012.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Microsoft Dynamics AX 2009</p></th>
<th><p>Microsoft Dynamics AX 2012</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Both table and EDT relations were supported. EDT relations could not contain metadata such as cardinality and relation type.</p></td>
<td><p>New EDT relations cannot be created. Use table relations instead. Table relations can contain metadata.</p></td>
</tr>
<tr class="even">
<td><p>Table relations could not be used for dynamic links.</p></td>
<td><p>Table relations now support dynamic links.</p></td>
</tr>
<tr class="odd">
<td><p>Table relations could not be used for unbound control lookup.</p></td>
<td><p>Table relations now support unbound control lookup.</p></td>
</tr>
<tr class="even">
<td><p>Having both types of relations on a single table could introduce ordering problems in certain circumstances.</p></td>
<td><p>New EDT relations cannot be created. We recommend that you convert all existing EDT relations to table relations. To preserve existing behavior, a new property that is named <strong>Reference Table</strong> has been added to the EDT structure. Each EDT node in the AOT contains a new <strong>Table References</strong> node that stores lookup information.</p></td>
</tr>
</tbody>
</table>


## Using the EDT Relation Migration Tool

When you first start the EDT relation migration tool, a message may be displayed: **The data on existing EDT relations needs to be refreshed. Do you want to continue?** Click **Yes** to refresh the list of EDT relations.

## Automating the Migration Process

You can use the EDT relation migration tool to help you complete the migration process. The tool can perform the following actions:

  - Copy EDT relations to all referencing tables.

  - Add relation metadata under the table nodes.
    
      - Derive the cardinality from the index on the foreign key.
    
      - Derive the relationship type from the delete action or key composition.
    
      - Determine the role names.

  - Generate a report of the data artifacts that are affected by the migration, for all given relations. The affected artifacts can include the following:
    
      - Queries
    
      - Forms
    
      - Delete actions on tables
    
      - Data sets
    
      - X++ reports

For examples of specific operations and typical migration scenarios, see the [Migrating EDT Relations](http://go.microsoft.com/fwlink/?linkid=213126&clcid=0x409) white paper.

## Navigating the Form

The following figure displays the EDT relation migration tool.

![EDT relation migration tool](images/Gg989788.EDT_Migration_Tool(en-us,AX.60).png "EDT relation migration tool")

**The EDT relation migration tool, displaying the EDT relations for the WrkCtrTable**

The left pane displays a list of tables that contain EDT relations. When you select a table in the left pane, the right pane displays the metadata of the selected table that may be affected by the migration.

The following items describe how to navigate the form:

1.  The left pane contains the **Table name** list, which displays all the tables that contain EDT relations.

2.  Select a table in the **Table name** list. A list of EDT relations that are used by that table is displayed on the **EDT Relations** FastTab in the pane on the right side.

3.  Select an EDT relation on the **EDT relations** FastTab. Details of that EDT relation are displayed on the FastTabs under the **EDT relations** section.

4.  If the **Migration status** field for an EDT relation is set to **Not migrated**, you can select the migration action in the **Migration action** field.

## Controls in the Form

The following tables provide descriptions for the controls in this form.

### ![Gg989788.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg989788.collapse_all(en-us,AX.60).gif")Left Side Pane

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>List</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Table name</strong></p></td>
<td><p>The tables that use EDT relations.</p></td>
</tr>
</tbody>
</table>


### ![Gg989788.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg989788.collapse_all(en-us,AX.60).gif")Right Side Pane

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>FastTab</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>EDT relations</strong></p></td>
<td><p>View the list of EDT relations that are used by the selected table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Relation properties</strong></p></td>
<td><p>View the properties of the selected EDT relation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Affected delete action</strong></p></td>
<td><p>View whether the EDT relation is used in a delete action of the table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Affected forms</strong></p></td>
<td><p>View the forms that are affected by this relation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Affected queries</strong></p></td>
<td><p>View the queries that are affected by this relation.</p></td>
</tr>
<tr class="even">
<td><p><strong>Affected data sets</strong></p></td>
<td><p>View the data sets that are affected by this relation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Affected X++ reports</strong></p></td>
<td><p>View the X++ reports that are affected by this relation.</p></td>
</tr>
</tbody>
</table>


### ![Gg989788.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg989788.collapse_all(en-us,AX.60).gif")Menu Actions

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Action</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Refresh relation data</strong></p></td>
<td><p>Refresh the relation data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Scan test artifacts</strong></p></td>
<td><p>Scan the test artifacts.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Migrate multiple tables</strong></p></td>
<td><p>Migrate the selected tables. More than one table must be selected. Otherwise, this action is not available.</p></td>
</tr>
<tr class="even">
<td><p><strong>Migrate single table</strong></p></td>
<td><p>Migrate the selected table. Only one table can be selected. Otherwise, this action is not available.</p></td>
</tr>
</tbody>
</table>


### ![Gg989788.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg989788.collapse_all(en-us,AX.60).gif")Buttons

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Button</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Migrate all</strong></p></td>
<td><p>Set the <strong>Migration action</strong> field to <strong>Migrate</strong> for every relation for which the <strong>Migration status</strong> field is set to <strong>Not migrated</strong>.</p></td>
</tr>
</tbody>
</table>


## See also

[Extended Data Types in the Database](extended-data-types-in-the-database.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

