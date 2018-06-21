---
title: 'Walkthrough: Leveraging Foreign Keys in Query Relations'
TOCTitle: 'Walkthrough: Leveraging Foreign Keys in Query Relations'
ms:assetid: e403459a-74fb-4684-b5cc-1abbd2669eae
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg847984(v=AX.60)
ms:contentKeyID: 35253179
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Leveraging Foreign Keys in Query Relations [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can take advantage of the foreign key relationship that exists between two tables when you create a query that joins the two tables.

This walkthrough illustrates the following tasks:

  - Creating the parent and child tables

  - Creating the query

  - Creating a form to display the query results

## Prerequisites

The following topics can help you understand this topic:

  - [How to: Add a Relation to a Table](how-to-add-a-relation-to-a-table.md) – explains how to add a foreign key relation.

  - [How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md) – explains how to create simple queries.

## Creating the Parent and Child Tables

In this section, you create two tables. The child table has a foreign key field that contains the same value that the primary key field contains in the parent table.

1.  In the AOT, create a table. Name the table **TabParent**. The **RecId** field is the default primary key.

2.  Add a string field named **ParentComment**, and set its **Mandatory** property to **Yes**.

3.  Create a table named **TabChild**. Add a string field named **ChildComment**, and make it mandatory.

4.  On **TabChild**, add a foreign key relation that references **TabParent**. Set the **RelatedTableRole** property to **masterParent**. For more information, see [How to: Add a Relation to a Table](how-to-add-a-relation-to-a-table.md).

5.  The **TabChild** table now has a field named **TabParent**. Rename the field to **TabParentFky**.

6.  Right-click the **TabParent** node, and then select **Open**. The **Table Browser** form is displayed. Use the form to add a row of data to **TabParent**.

7.  Add a row of data to **TabChild**.

## Creating the Query

In this section, you create a query that joins the parent and child tables. The system uses the foreign key information to help you specify the join.

1.  In the AOT, right-click the high level **Queries** node, and then select **New Query**.

2.  Right-click the new query node, and then select **Properties**. The **Properties** window is displayed. Set the **Name** property to **QryPF**.

3.  Under the **QryPF** node, right-click **Data Sources**, and then select **New Data Source**.

4.  For the new data source node, set the **Table** property to **TabParent**. This creates a new node under **Data Sources**, and the system might name it **TabParent\_1**.

5.  Another **Data Sources** node is under the **TabParent\_1** node. Right-click this **Data Sources** node, and add **TabChild** as a data source. This creates a **TabChild\_1** node.

6.  Expand the **TabChild\_1** node, right-click the **Relations** node, and then select **New Relation**. A new relation node is displayed.

7.  For the new relation node, set the **JoinDataSource** property to **TabParent**.

8.  Set the **RelatedField** property the empty value. Make sure the property value contains no text and no icons. Set the **Field** property to empty also.

9.  Click the drop-down list for the **JoinRelation** property, and then choose **masterParent**. This completes the action of adding the **New Relation** to the query

### ![Gg847984.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg847984.collapse_all(en-us,AX.60).gif")Alternative Way to Add the New Relation

There is an alternative to using the **New Relation** menu that is described in the previous steps. You can set the **Relations** property to **Yes** on the **AOT** \> **Queries** \> **QryPF** \> **Data Sources** \> **TabParent\_1** \> **Data Sources** \> **TabChild\_1** node.

This technique automatically adds a relation node under **AOT** \> **Queries** \> **QryPF** \> **Data Sources** \> **TabParent\_1** \> **Data Sources** \> **TabChild\_1** \> **Relations** node. If there are multiple relationships between the parent and child tables, you must verify that the system selected the relationship that you intended.

## Create a Form to Display the Query Results

You can create a simple form to display the results of your query. You can verify that the table join is working as expected by examining the data that the form displays.

1.  In the AOT, right-click the **Forms** node, and then select **New Form**.

2.  Right-click the new form node, and then select **Properties**. The **Properties** window is displayed. Set the **Name** property to **FormPF**.

3.  Drag the **QryPF** node onto the **FormPF** \> **Data Sources** node.

4.  Click **FormPF** \> **Designs** \> **Design** \> **New Control** \> **Grid**.

5.  From the **FormPF** \> **Data Sources** \> **TabParent** \> **Fields** node, drag the fields that are named **RecId** and **ParentComment** to the **Grid** node.
    

    > [!NOTE]
    > <P>You cannot drag these fields from the <STRONG>FormPF</STRONG> &gt; <STRONG>Data Sources</STRONG> &gt; <STRONG>QryPF</STRONG> &gt; <STRONG>Data Sources</STRONG> &gt; <STRONG>TabParent</STRONG> &gt; <STRONG>Fields</STRONG> node.</P>



6.  From the **FormPF** \> **Data Sources** \> **TabChild** \> **Fields** node, drag the fields that are named **RecId**, **ChildComment**, and **TabParentFky** to the **Grid** node.

7.  Right-click the **FormPF** node, and then select **Open**. The form displays the data.

## Next Steps

For more information, see the FormReferenceControl.

## See also

[Query Framework in the AOT](query-framework-in-the-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

