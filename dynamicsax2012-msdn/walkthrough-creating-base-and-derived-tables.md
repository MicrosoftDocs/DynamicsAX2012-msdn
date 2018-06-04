---
title: 'Walkthrough: Creating Base and Derived Tables'
TOCTitle: 'Walkthrough: Creating Base and Derived Tables'
ms:assetid: 195258b6-a698-4e52-958e-d1f13bac7670
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg844024(v=AX.60)
ms:contentKeyID: 35241379
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Creating Base and Derived Tables 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, a table can inherit from another table. The AOT node for each table has the **Extends** property which you can use to derive your table from a table that you specify. There are other table properties related to inheritance which must be assigned values in a specific sequence.

## Background for this Walkthrough

The following topics provide background for this walkthrough:

  - [How to: Create Tables](how-to-create-tables.md)

  - [X++ Keywords](x-keywords.md) – for the extends keyword about inheritance among classes.

  - [When to Use Table Inheritance](when-to-use-table-inheritance.md)

## Create Two Tables

In this section you create a base table named **TabPet**, and you create a derived table named **TabPetDog** that extends the base table.

### To create the TabPet base table

1.  In the AOT, open the **Data Dictionary** node, right-click the **Tables** node, and then click **New Table**.

2.  In the **Properties** window, enter the value **TabPet** for the **Name** property.

3.  For the **SupportInheritance** property, open the drop-down box and select **Yes**.
    

    > [!WARNING]
    > <P>If you cannot set the <STRONG>SupportInheritance</STRONG> property to <STRONG>Yes</STRONG>, it might be because you already have fields in the table. These fields must be deleted before you can set the value to <STRONG>Yes</STRONG>.</P>



### To create the TabPetDog derived table

1.  Create a table named **TabPetDog**.

2.  Set the **SupportInheritance** property to **Yes**.

## Add Fields to the TabPet Base Table

In this section you add fields to the **TabPet** base table. The inheritance rules require that you add a field of type int64 to the base table. The system uses this field to match each row in the base table to the corresponding derived table. This is necessary because several derived tables could all extend from the same base table.

### To add fields to the TabPet base table

1.  Open your **TabPet** table node and right-click the **Fields** node, select **New**, and then click **Int64**.

2.  On the **Properties** window that opens, name the **Int64** field **InstanceRelationType**.

3.  Add a **Date** field named **PetBirthDate**.

4.  In the **Properties** window for **PetBirthDate**, open the drop-down box for the **Mandatory** field and set it to **Yes**.

## Set More Inheritance Properties on the Tables

In this section you set properties on the two tables to establish their inheritance relationship.

The system uses a field on the **TabPet** base table to record the table ID of which ever derived table corresponds to each base table row. The **InstanceRelationType** property tells the system which field must store the table IDs. The field must be of type **Int64**.

The **Extends** property is set on the **TabPetDog** derived table. It is similar to the extends keyword that is used in the **classDeclaration** node for a derived class.

### To set inheritance properties on the tables

1.  In the **Properties** window for your **TabPet** base table, set the **InstanceRelationType** property to **InstanceRelationType**.

2.  In the **Properties** window for your **TabPetDog** derived table, set the **Extends** property to **TabPet**.

## Add Fields to the TabPetDog Derived Table

In this section you add fields to the **TabPetDog** derived table.

### To add fields to the TabPetDog derived table

1.  To your **TabPetDog** derived table, add an **Integer** field named **NumberOfTeeth**.

2.  In the **Properties** window for the **Number of Teeth** field, set its **Mandatory** property to **Yes**.


> [!NOTE]
> <P>The same field name cannot be used in a derived table and its base table.</P>



## Next Steps

Inheritance between tables affects data operations such as select and delete. For a walkthrough that describes these effects, see [Data Operations in X++ on Base and Derived Tables](data-operations-in-x-on-base-and-derived-tables.md).

## See also

[Table Inheritance Overview](table-inheritance-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

