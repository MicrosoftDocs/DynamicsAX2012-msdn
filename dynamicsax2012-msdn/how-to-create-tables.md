---
title: 'How to: Create Tables'
TOCTitle: 'How to: Create Tables'
ms:assetid: e83b5c11-f77b-4eb5-b57b-e73ad0fd4b3e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa882181(v=AX.60)
ms:contentKeyID: 35253225
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create Tables [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Create tables to store data in by using the Application Object Tree (AOT).


> [!NOTE]
> <P>Before creating new tables, review the tables that ship with Microsoft Dynamics AX to determine whether you can use existing tables. For more information, see <A href="https://msdn.microsoft.com/en-us/library/aa852568(v=ax.60)">Application Tables</A>.</P>



Table fields are based on a primitive data type or an extended data type. For more information, see [Primitive Data Types](primitive-data-types.md) and [How to: Create an Extended Data Type](how-to-create-an-extended-data-type.md).

The AutoReport and AutoLookup groups are automatically created when you create a table. For more information, see [Implementing Automatic Reports for Forms](implementing-automatic-reports-for-forms.md) and [How to: Add a Control with a Lookup Form](how-to-add-a-control-with-a-lookup-form.md).

To manage changes to AOT objects, a version control system is available. For more information, see [Version Control System](version-control-system.md).

## Create a Table

1.  In the AOT, expand the **Data Dictionary** node.

2.  Right-click the **Tables** node, and then select **New Table**.

3.  Right-click the table, and then click **Properties**.

4.  Rename the table by modifying the **Name** property.

5.  To specify the table as temporary, set the **Temporary** property to Yes. For more information, see [Table Properties](https://msdn.microsoft.com/en-us/library/aa871620\(v=ax.60\)).

6.  Modify additional table properties, as needed. For more information, see [Table Properties](https://msdn.microsoft.com/en-us/library/aa871620\(v=ax.60\)).

7.  To delete the table, right-click it, and then click **Delete**.

## Add Fields to a Table


> [!NOTE]
> <P>You can delete only fields that do not contain data in any of the table records. You cannot modify the data type of an existing field.</P>



1.  Right-click the **Fields** node of your table.

2.  Click **New**, and then choose a primitive data type to base your field on. If you plan to base the field on a specific extended data type, you must choose a primitive data type that the extended data type is based on.

3.  To base the field on an extended data type, set the **ExtendedDataType** property.

4.  Modify additional field properties, as needed. For more information, see [Table Field Properties](https://msdn.microsoft.com/en-us/library/aa577032\(v=ax.60\)).

5.  To delete the field, right-click it, and then click **Delete**.

### ![Aa882181.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa882181.collapse_all(en-us,AX.60).gif")Restart the AOS after Adding Fields to Tables

When you insert data in a table during development, the SQL statement you use to insert the data is cached in the AOS. Next you might add a new field to the table and persist the change to the database. This causes the SQL statement in the cache to become stale, because the statement is not updated to include the new field. If you reuse the stale statement, the new field is ignored, or an error might occur.

To avoid this problem, restart the AOS after you persist table schema changes to the database. The cache is empty when the AOS restarts.

## See also

[Use the Table Browser to View, Add, Modify, or Delete Records](use-the-table-browser-to-view-add-modify-or-delete-records.md)

[How to: Add a Relation to a Table](how-to-add-a-relation-to-a-table.md)

[How to: Create a Field Group](how-to-create-a-field-group.md)

[How to: Create an Index](how-to-create-an-index.md)

[Tables, Views, and Maps](tables-views-and-maps.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

