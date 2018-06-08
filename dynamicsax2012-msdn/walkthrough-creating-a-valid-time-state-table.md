---
title: 'Walkthrough: Creating a Valid Time State Table'
TOCTitle: 'Walkthrough: Creating a Valid Time State Table'
ms:assetid: 6f4162f7-72b8-4396-91ae-14fcc18ae47a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg841023(v=AX.60)
ms:contentKeyID: 35244861
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Creating a Valid Time State Table 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The scenario in this topic illustrates how to create a valid time state table in Microsoft Dynamics AX.

Date effective data is tracked in a table that has its **ValidTimeStateFieldType** changed from its default value of **None**. Also, an index with its **ValidTimeStateKey** set to **Yes** must be added on the table. The system automatically adds the fields named **ValidFrom** and **ValidTo** to the table, which will be of type **date** or **utcdatetime**. The system automatically prevents overlap between the date ranges in these two fields among rows that track the same entity.

## Prerequisites

Before you read this topic, you should know how create a table, add fields to it, and add an index. For more information, see the following topics:

  - [How to: Create Tables](how-to-create-tables.md)

  - [How to: Create an Index](how-to-create-an-index.md)

## Introduction to Scenario

In this scenario the many-to-many relationship between employees and the projects they work on is tracked by date ranges. For example, for any date, a query can obtain a list of all the employees associated with a given project. In the test table, the fields **EmplID** and **ProjID** are considered to be foreign key fields.

In this scenario we choose to permit gaps between the date ranges in rows that differ only in their **ValidFrom** and **ValidTo** values.

In this scenario you:

  - Create a table and add fields.

  - Prompt the system to automatically add **ValidFrom** and **ValidTo** date fields.

  - Create an alternate key index that includes the **ValidFrom** and **ValidTo** fields, plus at least one more field.

  - Set properties on the index.

## Create a Table and Add Fields to the Valid State Table

Create a table as follows:

1.  In the AOT, create a table. Name the table **TabEmplProjVts**.

2.  Add the following string fields to the table:
    
      - **EmplID**
    
      - **ProjID**
    
      - **EPPrimaryKey**

## Add ValidFrom and ValidTo Date Fields

The system automatically adds the fields **ValidFrom** and **ValidTo** to the table when you change the **ValidTimeStateFieldType** from its default of **None**. These system fields cannot be disabled by configuration keys.

To add the **ValidFrom** and **ValidTo** date fields to the table, you set a property on the table. Do as follows:

1.  In the **Properties** window for the table **TabEmplProjVts**, set the **ValidTimeStateFieldType** property to **Date**.
    

    > [!NOTE]
    > <P>You can change the <STRONG>ValidTimeStateFieldType</STRONG> to any value when the table contains no data. You can change the value to <STRONG>None</STRONG> even if the table contains data.</P>



2.  At the node **AOT** \> **Data Dictionary** \> **Tables** \> **TabEmplProjVts** \> **Fields** \> **ValidFrom**, right-click and select **Properties**.

3.  Verify that the **Mandatory** property is set to **Yes**.

## Create an Alternate Key Index that Includes ValidFrom

In this section you put both of the foreign key fields **EmplID** and **ProjID** into an alternate key index. Then you add the **ValidFrom** and **ValidTo** fields, and set properties on the index. Do as follows:

1.  At the node **AOT** \> **Data Dictionary** \> **Tables** \> **TabEmplProjVts** \> **Indexes**, right-click and select **New Index**.

2.  In the **Properties** window for the new index, set the **Name** property to **idxEPAltKeyVts**.

3.  Right-click the **idxEPAltKeyVts** node, and then select **New Field**.

4.  In the **Properties** window for the newly added field, override the default field name and select **EmplID**.

5.  Add the **ProjID** field to the index.

6.  Add the **ValidFrom** field to the index.

7.  Add the **ValidTo** field to the index.

## Set Properties on the Index

To configure the index to support date effective data, you must set the properties on the index **idxEPAltKeyVts** as follows:

1.  Set **AllowDuplicates** to **No**.

2.  Set **Alternate Key** to **Yes**.

3.  Set **ValidTimeStateKey** to **Yes**.

4.  Set **ValidTimeStateMode** to **Gap**.
    

    > [!NOTE]
    > <P>You can change the <STRONG>ValidTimeStateMode</STRONG> property from <STRONG>Gap</STRONG> to <STRONG>NoGap</STRONG> only if the table contains no data. You can change from <STRONG>NoGap</STRONG> to <STRONG>Gap</STRONG> even if the table contains data.</P>



## Final Steps

If you want to continue with the data phase of this scenario, see [Effects of Valid Time State Tables on Read and Write Operations](effects-of-valid-time-state-tables-on-read-and-write-operations.md).

For information about controlling the cardinality of relationships in a valid time state table, see [Cardinality in Valid Time State Table Relationships](cardinality-in-valid-time-state-table-relationships.md).

## See also

[Valid Time State Tables and Date Effective Data](valid-time-state-tables-and-date-effective-data.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

