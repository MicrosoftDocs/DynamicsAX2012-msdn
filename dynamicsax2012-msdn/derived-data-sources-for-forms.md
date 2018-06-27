---
title: Derived Data Sources for Forms
TOCTitle: Derived Data Sources for Forms
ms:assetid: 66736c45-7ace-4d0f-9aec-a81c045620e2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272120(v=AX.60)
ms:contentKeyID: 36536790
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Derived Data Sources for Forms 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You create a derived data source when you use a table from a table inheritance hierarchy as the primary table in a form data source. A derived data source enables you to show records from all the tables in an inheritance hierarchy on a form. This topic describes how the client framework helps you use the tables from a table inheritance hierarchy like any other table in a form data source.

You find the **Derived Data Sources** node under the **Data Sources** \> Your Form Data Source node of a form in the AOT. However, not every table in an inheritance hierarchy creates a **Derived Data Sources** node. For information about how to create an inheritance hierarchy, see [Table Inheritance Overview](table-inheritance-overview.md).

## Table Inheritance Trees and Hierarchies

To use a derived data source, you start with a table inheritance hierarchy. An inheritance hierarchy is a collection of tables where each table derives from another table in the hierarchy. The table at the base of the hierarchy is known as the base table. You use table inheritance to create new table types that are related to each other through a common ancestor or base. Each derived table adds fields that extend the type described by the table that is the common base.

An inheritance hierarchy can also be part of a broader hierarchy called a table inheritance tree. The table at the base of the tree is known as the root table. The following illustration represents a table inheritance tree for people and organizations. Notice how Party is the root table of the tree. Also notice how Organization is the base table for an inheritance hierarchy that includes the Nonprofit and Government tables. For information about how to design a table inheritance tree, see [When to Use Table Inheritance](when-to-use-table-inheritance.md).

![Table inheritance from the Party base table.](images/Gg881064.Party-Org-Nonprofit_TableHierarchy(en-us,AX.60).gif "Table inheritance from the Party base table.")

To create an inheritance hierarchy you use the following table properties to define the inheritance relationship between tables. For more information about how to create the tables in an inheritance hierarchy, see [Walkthrough: Creating Base and Derived Tables](walkthrough-creating-base-and-derived-tables.md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Abstract</strong></p></td>
<td><p>Specify whether a table is a concrete or abstract table. The default value is <strong>No</strong>. You use the default value to specify that the table is a concrete type. When you use a form with a derived data source to create a new record, you are prompted to select the record type from a list. The list includes the concrete table types in the table inheritance hierarchy.</p>
<p>To create an abstract table type, set the property to <strong>Yes</strong>. An abstract type is a member of the table inheritance hierarchy that you do not explicitly create from the form. The fields in an abstract table are always accessed from a concrete descendant in the inheritance hierarchy. When you use the form to create a new record, the prompt that lists the types of records to create does not include the abstract table type.</p>
<p>To use the Party hierarchy as an example, you set the <strong>Abstract</strong> property of the Organization table to <strong>Yes</strong>. The <strong>Abstract</strong> property of Government and Nonprofit are set to <strong>No</strong>. You then add Organization as the primary table of a form data source. If you then use that form to create a record, the list of types shows Government and Nonprofit but does not show Organization.</p></td>
</tr>
<tr class="even">
<td><p><strong>Extends</strong></p></td>
<td><p>Specify the table that the current table derives from. To use the Party hierarchy as an example, you populate the <strong>Extends</strong> property of the Organization table with <strong>Party</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InstanceRelationType</strong></p></td>
<td><p>Specifies the name of the field you use for the identification (ID) values that are used in the table inheritance hierarchy. To populate the property, select the name of the field that you added. Typically, you add an Int64 field that has the name <strong>InstanceRelationType</strong>. There is more information about <strong>InstanceRelationType</strong> later in this topic.</p></td>
</tr>
<tr class="even">
<td><p><strong>SupportInheritance</strong></p></td>
<td><p>Specify whether the table supports inheritance. The default value is <strong>No</strong>. To include a table in an inheritance hierarchy, set the property to <strong>Yes</strong>. This is necessary for both base and derived tables.</p>

> [!caution]  
> <P>You cannot change the values of the <strong>Abstract</strong> or <strong>Extends</strong> properties until you set the <strong>SupportInheritance</strong> property to <strong>Yes</strong>.</P>

</td>
</tr>
</tbody>
</table>


To complete the table inheritance hierarchy, add an Int64 field named **InstanceRelationType** to the base table of the hierarchy. Populate the **ExtendedDataType** property of that field by using **RelationType**. Use the name of the field to populate the **InstanceRelationType** property of the base table. The field enables the tables in the hierarchy to store ID values. The client framework populates the ID values and then uses them to create a query that retrieves the field values that appear in the form.


> [!WARNING]
> <P>You should never bind the <STRONG>InstanceRelationType</STRONG> and <STRONG>relationType</STRONG> fields to controls. These fields contain ID values and should not appear on a form.</P>



## Form Data Sources and Table Inheritance

You can use any table from an inheritance hierarchy tree as the primary table in the data source of a form. For example, you use a table that is the base table in a hierarchy when you want records from different table types to appear in the same form. When you add a table from an inheritance hierarchy to the form data source, the framework constructs a query that can retrieve, update, or create records for any of the concrete types in the hierarchy.

If you view the **Data Sources** node of the form in the AOT, you see the primary table that you added. If the table is a base table in an inheritance hierarchy, you will see the derived data sources associated with that table. Finally, you can view the fields associated with each table.

### ![Hh272120.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh272120.collapse_all(en-us,AX.60).gif")Using a Base Table as the Primary Table

A base table is a table that is the common ancestor for one or more derived tables in an inheritance hierarchy. You use a base table as the form data source when you want to view, update, and create all the descendant types in a single form. To use the earlier example, you add the Party table as the data source for a form. You can then use that form to view, update, and create records for the Party, Person, Organization, Government, and Nonprofit tables.

When you use the AOT to drag the base table onto the **Data Sources** node of the form, the table is added as the primary table of the form data source. The table includes the **Fields** node that lists all the fields from the base table. In addition, the table has a **Derived Data Sources** node that includes each derived table from the hierarchy. The table in each derived data source includes a **Fields** node that lists the fields for that table.

If you use a base table that extends another table, the **Fields** node in the form data source includes fields from the ancestors of that table in the inheritance tree. To continue the earlier example, you use Organization as the primary table in the form data source. The **Fields** list for Organization includes NumEmployees but also includes the NickName field from the Party table.

A table in the **Derived Data Sources** node can also include derived data sources. The node lists the tables from the inheritance hierarchy that are derived from that table. For example, Organization includes two tables in the **Derived Data Sources** node. The nodes represent derived data sources for the Nonprofit and Government tables. The following illustration shows **Data Sources** for a form that uses the Party table as the form data source.

![The form data source for a base table](images/Hh272120.FormDDSBase(en-us,AX.60).png "The form data source for a base table")

### ![Hh272120.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh272120.collapse_all(en-us,AX.60).gif")Using a Derived Table as the Primary Table

A derived table is the table at the end of a table inheritance hierarchy. A derived table extends a table but is not extended by any other table. You use the derived table when you want the form to show only a single type from the inheritance hierarchy. To use the earlier example, Person, Nonprofit, and Government are derived tables.

When you use the AOT to drag a derived table onto the **Data Sources** node of the form, the table is added as the form data source. The table includes a **Fields** node that lists all the fields from that table. The field list also contains the fields from any table that is closer to the root in the inheritance hierarchy. To continue the earlier example, the **Fields** list for Government includes AgencyDescription but also includes NumEmployees from the Organization table and NickName from the Party table. The following illustration shows **Data Sources** for a form that uses the Government table as the form data source.

![The data source for a derived table](images/Hh272120.FormDDSDerived(en-us,AX.60).png "The data source for a derived table")

## Form Design and Derived Data Sources

To design the form, you use a derived data source like any other form data source. You use the fields from the primary table and the tables in the derived data sources to add controls to the form. You drag the field from the form data source or a derived data sources to the **Design** node of the form.

If you have derived data sources, you can use the form to show records from different table types. The derived data source enables you to add fields to the form that are unique to a single table type in the hierarchy. For example, you use the Organization table as a form data source. You then add the AnnualContribution field from the NonProfit derived data source and the AgencyDescription field from the Government derived data source to the form.

As a result, you might have fields that do not apply to each type of record that appears in the form. The form shows an image of the null symbol in grid cells or other control when the field does not apply to the current record. The following illustration shows a grid that has fields that contain the null image.

![Not applicable images for fields](images/Hh272120.FormDDSNotApplicable(en-us,AX.60).png "Not applicable images for fields")

### ![Hh272120.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh272120.collapse_all(en-us,AX.60).gif")Changes to Control Properties

When you drag a field from a derived data source to the **Design** node of a form, the following properties are populated for you.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Name</strong></p></td>
<td><p>The framework supplies a name that uniquely identifies the control. You can change the name.</p></td>
</tr>
<tr class="even">
<td><p><strong>DataField</strong></p></td>
<td><p>The framework populates the property by using the field name. The value is set when you drag the field to the <strong>Design</strong> node of the form.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DataSource</strong></p></td>
<td><p>The framework populates the property by using the name of the table. The value is set when you drag the field to the <strong>Design</strong> node of the form.</p></td>
</tr>
</tbody>
</table>



> [!TIP]
> <P>If you drag fields to a control that contains other controls, you might have to populate the <STRONG>DataSource</STRONG> property of the container control with the name of the primary table. For example, you add a grid to the form. You must populate the <STRONG>DataSource</STRONG> property of the grid control.</P>



## Specifying the Type of a New Record

A form with a derived data source can create more than one type of record. As a result, you must specify the type any time that you create a new record. For example, you you click a button to create a new record, a dialog window appears that lists the available types of records. You use the dialog window to click the record type, and then click **Create**. A new record of the specified type appears in the form. The following illustration shows the type selection dialog window.

![List of types for a form](images/Hh272120.FormDDSTypeDialog(en-us,AX.60).png "List of types for a form")

The client framework dynamically creates the dialog and populates the list. The list includes all the concrete table types from the form data source.

## See also

[Data Sources for Forms](data-sources-for-forms.md)

[Table Inheritance Overview](table-inheritance-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

