---
title: 'How to: Add a Relation to a Table'
TOCTitle: 'How to: Add a Relation to a Table'
ms:assetid: 1b164b99-de08-4557-8da5-1931d9469ca1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa556809(v=AX.60)
ms:contentKeyID: 35241382
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Relation to a Table [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You add relations to a table by using the Application Object Tree (AOT).

A relation on a table can restrict the rows in the table, or restrict the values that can be in particular fields. A common use of relations is to associate rows in one table to corresponding rows in another table. Relations enable many forms to display data from multiple tables.

Some relations restrict the rows in the table by testing the values in each row against constant values. Other relations restrict the rows by comparing values in each row to values in a row in another table.

## Add a Relation to a Table in the AOT

The initial steps for adding a relation are the same regardless of the relation type that you are adding. The later steps diverge based on the relation type.

Remember to save your changes in the AOT.

1.  In the AOT, move to **Data Dictionary** \> **Tables**, and then expand the table that the relation will be added to.

2.  Right-click the **Relations** node, and then select **New Relation**.

3.  Right-click the newly added relation, and then select **Properties**.

4.  Set the name of the new relationship by modifying the **Name** property.

5.  In the **Table** property, select the related table.

6.  Use the **Validate** property to determine whether the relation should be used to validate data when information is entered into forms.

7.  Right-click the new relation, select **New**, and then click one of the following:
    
      - **Normal** to specify relation fields without conditions.
    
      - **Field fixed** to specify relation fields to restrict the records in the primary table.
    
      - **Related field fixed** to specify relation fields that restrict the records in the related table.
    
      - **ForeignKey** to specify a correspondence between a foreign key field in the present table to the primary key field in another parent table.
        

        > [!NOTE]
        > <P>For this option to function, you must first set certain properties on the new relation. A following section explains more about this option.</P>



8.  Proceed to the subsection that corresponds to the relation type that you selected in the earlier step.

## Define the Relation Fields

Now set the properties on the new relation you created under the **Relations** node.

### ![Aa556809.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa556809.collapse_all(en-us,AX.60).gif")Normal Relation

1.  In the **Field** property, select the field in the primary table that relates to a field in the present table.

2.  In the **RelatedField** property, select the field in the related table.

### ![Aa556809.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa556809.collapse_all(en-us,AX.60).gif")Field fixed Relation

1.  In the **Field** property, select the field in the primary table to use to restrict the records.

2.  In the **Value** property, enter the value of the selected field as the filter. This relates only records in the primary table that match that field value. Only numeric values can be entered in the **Value** property. Field fixed relations can be created only on numeric fields. Each of the related fields are AND'ed in the table relation.

### ![Aa556809.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa556809.collapse_all(en-us,AX.60).gif")Related field fixed Relation

1.  In the **Value** property, enter the filter value of the selected field. This causes only records in the related table that match that field value to be related. Only numeric values can be entered in the **Value** property. Related field fixed relations can be created only on numeric fields.

2.  In the **Field** property, select the field in the related table to restrict the records. Each of the related fields are AND'ed in the table relation.

### ![Aa556809.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa556809.collapse_all(en-us,AX.60).gif")ForeignKey Relation

We often use the term child to refer to a table that has a foreign key column. And we use the term parent to refer to the other table that supplies the value for the foreign key column. But we never use the terms parent and child to describe the base and derived [tables in an inheritance relationship](table-inheritance-overview.md).

1.  Set the **Table** property to the name of the parent table, the table that contains the primary key field.

2.  Set the **RelatedTableRole** property to a word or phrase that describes the purpose of the parent in the relationship.
    

    > [!NOTE]
    > <P>This value is added automatically as a method name on the child table. This method is displayed by IntelliSense in the X++ editor, but you cannot see the method in the AOT. For more information about how to use this method, see <A href="how-to-use-the-unitofwork-class-to-manage-database-transactions.md">How to: Use the UnitOfWork Class to Manage Database Transactions</A>.</P>



3.  Set the **Name** property. A helpful value is a combination of the **Table** property and **RelatedTableRole** property values.

4.  Right-click the node for your relation, click **New**, and then click **ForeignKey**. Next click either **PrimaryKey based** or **Single field AlternateKey based**. A new field is instantly added to the child table. This field stores the foreign key values.

5.  Under the **Fields** node, click the new field, and then change its **Name** property value.

6.  For performance benefits, you might decide to add an index on the new foreign key field.

## See also

[How to: Create Tables](how-to-create-tables.md)

[Table Properties](https://msdn.microsoft.com/en-us/library/aa871620\(v=ax.60\))

[Defining Table Relations](defining-table-relations.md)

[Conditional Table Relations](conditional-table-relations.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

