---
title: 'Walkthrough: Creating a Form Based on a Composite Query'
TOCTitle: 'Walkthrough: Creating a Form Based on a Composite Query'
ms:assetid: 17cc81b9-2bf5-4836-a7ee-a94ac3b652ce
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc566883(v=AX.60)
ms:contentKeyID: 35240676
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Creating a Form Based on a Composite Query 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A [composite query](query-reuse-by-composite-queries.md) is one that uses another query as its data source. In this scenario you create a form that uses a composite query as a data source. The scenario is a realistic example that has form UI grids coordinated to match the parent-to-child (or foreign key) relationships of the underlying tables.

A composite query automatically starts with all the code from your original query. You benefit from more code reuse when you build forms and reports from a composite query, instead of creating a new query from scratch.

This walkthrough illustrates the following tasks:

  - Creating a query

  - Joining tables in a data source

  - Creating a form that uses a base query
    
      - Creating a form with a data source
    
      - Building a form UI of three grids
    
      - Linking the child grids to their parent grids

  - Testing the form

  - Adding ranges to the query

  - Creating a composite query with more ranges

  - Creating a form based on the composite query

  - Inheriting X++ code from methods overridden in the base query

## Prerequisites

To complete this walkthrough, you need:

  - Microsoft Dynamics AX

  - A license file that has access to the client (MorphX)

  - Data in **SalesLine** table for a company you can access

## The Plan for this Scenario

The scenario is based on the three tables **CustTable**, **SalesTable**, and **SalesLine**. The parent-to-child relationships among these tables are as follows:

  - Parent: **CustTable**, child: **SalesTable**

  - Parent: **SalesTable**, child: **SalesLine**

You build a query that uses these tables for its data sources. You build a form that uses the query as its data source. You create a second query that extends the first query. We call the second query a composite query. You build a second form on the second query.

You can demonstrate the behavior of ranges added to the query and composite query is illustrated when you click different rows in the grids on the form. You can see the inheritance relationship between the query and the composite query when you override methods.

## Creating a Query

In this procedure you create a query that uses three tables for its data sources.

### To create a query

1.  In the AOT, right-click the **Queries** node, and then click **New Query**.

2.  Right-click the node for the new query, and then click **Properties**.

3.  In the **Properties** window, change the **Name** to be **QryCogBase1**.

4.  In the AOT, expand the **QryCogBase1** node, and then expand the **Data Sources** node to see that it is empty and does not expand.

5.  Right-click the **Data Sources** node, and then click **New Data Source**.

6.  In the **Properties** window, click the drop-down list for the **Table** property and select **CustTable**. Then click the **Name** property to have the name automatically updated to match the selected table name.

7.  Expand the **CustTable\_1(CustTable)** node that is under the **Data Sources** node of our query.

8.  Under the **CustTable\_1(CustTable)** node, right-click **Data Sources**, and then click **New Data Source**.

9.  In the **Properties** window, click the drop-down list for the **Table** property and select **SalesTable**.

10. Under the **SalesTable\_1** node, right-click **Data Sources**, and then click **New Data Source**.

11. In the **Properties** window, click the drop-down list for the **Table** property and select **SalesLine**.

12. In the AOT, right-click the **QryCogBase1** node and click Save.

## Joining Tables in a Data Source

In this procedure you join the tables listed under the **Data Sources** node of **QryCogBase1**.

### To join tables in a data source

1.  In the AOT under the **Queries** node, expand **QryCogBase1**, expand **Data Sources**, expand **CustTable\_1(CustTable)**, expand **Data Sources**, and then expand **SalesTable\_1(SalesTable)**.

2.  Right-click the **Relations** node, and then click **New Relation**. A new relation is automatically added, and it is often created as we want it.

3.  Ensure the automatically added relation says **CustTable\_1.AccountNum == SalesTable\_1.CustAccount**. If necessary, change the value by using the drop-down lists in the **Properties** window.

4.  Under the **SalesTable\_1(SalesTable)** node, expand **Data Sources**, and then expand **SalesLine\_1(SalesLine)**.

5.  Right-click the **Relations node**, and then click **New Relation**.

6.  Ensure the automatically added relation says **SalesTable\_1.SalesId == SalesLine\_1.SalesId**. Change the value if you have to.

7.  In the AOT, expand **Queries**, **QryCogBase1**, **Data Sources**, **CustTable\_1(CustTable)**, **Data Sources**, and then click **SalesTable\_1(SalesTable)**.

8.  In the **Properties** window, verify the **JoinMode** value is **InnerJoin**.

9.  Verify the **FetchMode** is **1:n**.

10. In the AOT, right-click the **QryCogBase1** node and click **Save**.

## Creating a Form That Uses a Base Query

This procedure is divided into smaller procedures.

### ![Cc566883.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc566883.collapse_all(en-us,AX.60).gif")Creating a Form With a Data Source

In this procedure you create a form that uses **QryCogBase1** as its data source.

### To create a form with a data source

1.  In a second AOT window, right-click the **Forms** node, and then click **New Form**.

2.  In the **Properties** window, rename the form to **FormCogBase2**.

3.  Expand the **FormCogBase2** node to see its **Data Sources** node.

4.  In a new AOT window, expand the **Queries** node, and click **QryCogBase1**.

5.  Drop **QryCogBase1** onto **Data Sources** under **FormCogBase2** in the other AOT window. Under the **Data Sources** node there are now nodes for three tables.

### ![Cc566883.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc566883.collapse_all(en-us,AX.60).gif")Building a Form UI of Three Grids

In this procedure you design a user interface (UI) on **FormCogBase2**. You add one grid for each table in the data source of the query.

The grids are created on the UI. In the next procedure the behavior of the grids is coordinated to reflect the parent-to-child relations between the tables. The goal is to have each grid display only the data that pertains to the row that is currently highlighted in its parent grid.

### To build a form UI of three grids

1.  In the AOT under the **FormCogBase2** node, expand **Data Sources**. This shows the tables that are used by **QryCogBase1**.

2.  Expand each table node to see the **Fields** node of each. Any **Fields** node can be expanded to show the available fields.

3.  In the AOT under the **FormCogBase2** node, right-click the **Data Sources** node, and then click **Open New Window**.

4.  In the AOT under the **FormCogBase2** node, expand **Designs**.

5.  Right-click the **Design** node, click **New Control**, and then click **Grid**.

6.  Rename the new grid node to **Grid1CT**.

7.  Create two more grids and name them **Grid2ST** and **Grid3SL**.

8.  In the **Properties** window, set the **DataSource** property for each grid as follows:
    
      - **Grid1CT** to **CustTable\_1**
    
      - **Grid2ST** to **SalesTable\_1**
    
      - **Grid3SL** to **SalesLine\_1**

9.  Onto the **Grid1CT** node, drop the **CustTable\_1(CustTable)** fields named **AccountNum**, **Name**, and **PaymTermId**.

10. Onto **Grid2ST** drop the **SalesTable\_1(SalesTable)** fields named **SalesId**, **SalesName**, **CustAccount**, and **DocumentStatus**.

11. Onto **Grid3SL** drop the **SalesLine\_1(SalesLine)** fields named **SalesId**, **LineNum**, **Name**, and **SalesStatus**.

### ![Cc566883.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc566883.collapse_all(en-us,AX.60).gif")Linking the Child Grids to Their Parent Grids

In this procedure you make the behavior of grids match the parent-to-child relations among their corresponding tables.

### To link the child grids to their parent grids

1.  In the AOT, expand **Forms**, **FormCogBase2**, **Data Sources**. A node for each table should be visible (together with a node for **QryCogBase1**).

2.  Expand the node for the first child table, in this case **SalesTable\_1**. Expand the **Links** node. A node for each of the other two tables is visible underneath.

3.  Underneath, click the node for the table that is the parent of the current table. In this case click the **CustTable\_1** node. (Ignore the node for child table **SalesLine\_1**.)

4.  In the **Properties** window, set the **LinkType** to **Delayed**.

5.  Expand **Forms**, **FormCogBase2**, **Data Sources**, **SalesLine\_1**, Links. Click on **SalesTable\_1** (the node for the parent table).

6.  In the **Properties** window, set the **LinkType** to **Delayed**.

## Testing the Form

In this procedure you test **FormCogBase2** to make sure that it is working.

### To test the form

1.  In the AOT, expand **Forms**, right-click **FormCogBase2**, and then select **Open**. This runs the form and populates its UI with data.

2.  In **Grid1CT** (the top grid), click the first row.

3.  Verify in **Grid2ST** (the middle grid) that all the rows have the same **Customer account** number as the one highlighted row in **Grid1CT**.

4.  Click different rows in **Grid1CT** and verify that the **Customer account** values change appropriately in **Grid2ST**.

5.  Click a row in **Grid2ST**.

6.  Verify in **Grid3SL** (the bottom grid) that all the rows have the same **Sales order** value as the one highlighted row in **Grid2ST**.

## Adding Ranges to the Query

In this procedure you add ranges to a query to reduce the amount of data that is returned.

To continue the scenario you must note three **Customer account** (**AccountNum**) values that are visible in **Grid1CT** on the form's UI. Those three values can vary between installations. Here they are referred to as 4000, 4009, and 4010. But you must use values obtained from your installation.

### To add ranges to the query

1.  In the AOT, expand **Queries**, **QryCogBase1**, **Data Sources**, **CustTable\_1(CustTable)**. The **Ranges** node becomes visible.

2.  Right-click the **Ranges** node, and then click **New Range**. A default range node is generated.

3.  In the **Properties** window, click the **Field** property drop-down list and select **AccountNum**.

4.  Set the **Value** property to 4000.

5.  Right-click the **Ranges** node again, and add another range for this same field **AccountNum**. Set its value to 4009.

6.  Add a third range for **AccountNum**, with a value of 4010.
    

    > [!NOTE]
    > <P>These three ranges are treated with the Boolean OR operator, because they all have the same <STRONG>Field</STRONG> property setting, and because they are all part of the same query. In a later procedure it is explained that ranges on a composite query are always treated with Boolean AND operations in conjunction with the ranges of its base query.</P>



7.  Test the form. In the AOT, right-click **FormCogBase2**, and then click **Open**. Note that **Grid1CT** shows only rows with the **Customer account** values that are specified in the ranges.

8.  Add a range on the **Field** called **Name**, with a **Value** of the five characters \*xxx\*.

9.  Save **QryCogBase1**, and reopen **FormCogBase2**. The absence of all data shows the range on **Name** is conjoined with the **AccountNum** ranges by a Boolean AND operation. The AND is used to conjoin ranges that have different **Field** property values.

10. Right-click the range on **Name**, and then click **Delete**. Save **QryCogBase1**.

For more information about ranges, see [Query Elements in the AOT](query-elements-in-the-aot.md).

## Creating a Composite Query With More Ranges

In this procedure you create a composite query. You add a range to the composite query. The new range causes less data to be returned than would be returned by the base query.

### To create a composite query with more ranges

1.  In the AOT, create a second query named **QryCogCompos5**.

2.  Expand **QryCogCompos5**. The **Composite Query** node is visible.

3.  Drop **QryCogBase1** onto the **Composite Query** node.
    

    > [!NOTE]
    > <P>The new <STRONG>QryCogBase1</STRONG> node has a <STRONG>Composite Query</STRONG> node underneath. Nevertheless there is no meaningful scenario where you would drop a query onto that <STRONG>Composite Query</STRONG> node.</P>



4.  Expand **QryCogCompos5**, **Composite Query**, **QryCogBase1**, **Data Sources**, **CustTable\_1(CustTable)**, **Ranges**.

5.  Right-click **Ranges**, and then click **New Range**.
    

    > [!WARNING]
    > <P>In the AOT the new range node for the composite query appears as one more range on the base query. However, the new range belongs to the composite query only. The new range is treated with a Boolean AND operator whereas the original ranges are treated with Boolean OR. The AND is used even when the new range refers to the same field that the original ranges refer to.</P>



6.  In the **Properties** window for the new range, set the **Field** to **AccountNum** and the **Value** to 4022.

7.  Save **QryCogCompos5**.

## Creating a Form Based on the Composite Query

In this procedure you create a form to display the output of **QryCogCompos5**. You also test the effects of adding new ranges to **QryCogCompos5**.

**FormCogBase2** cannot be reused for the composite query without erasing all the work done to design **FormCogBase2** in the AOT.

### To create a form that is based on the composite query

1.  Create a form named **FormCogCompos6** with **QryCogCompos5** as its data source.

2.  Design a UI of three grids for **FormCogCompos6**, just as you did for **FormCogBase2**.

3.  Test **FormCogCompos6**. Notice that no data is displayed\!
    

    > [!NOTE]
    > <P>No data is displayed because the range added to the composite query is treated with a Boolean AND in conjunction with the inherited ranges for the same <STRONG>Field</STRONG>. No one CustTable&nbsp;.AccountNum value can be 4022 and 4010.</P>
    > <P>You can force empty data to be displayed by setting the property <STRONG>InsertIfEmpty</STRONG> to <STRONG>Yes</STRONG>. You set this property on the node <STRONG>AOT</STRONG> &gt; <STRONG>Forms</STRONG> &gt; <STRONG>FormCogCompos6</STRONG> &gt; <STRONG>Data Sources</STRONG> &gt; <STRONG>QryCogCompos5</STRONG>.</P>



4.  Click the node for the new range. Change its **Field** property to **Name**, and its value property to \*Light\*,\*Lamp\*.  
    Your data might require different strings to filter in only a subset of the CustTable rows that would be returned without this range.

5.  Test **FormCogCompos6** again. This time some data should appear.

## Inheriting X++ Code From Methods Overridden in the Base Query

In this procedure you override a method on the base query. Then you open a form that is based on the composite query, and you see that the method override is run.

### To inherit X++ code from methods overridden in the base query

1.  In the AOT, expand **Queries**, **QryCogBase1**, **Methods**.

2.  Right-click **Methods**, click **Override Method**, and then click **init**.

3.  In the X++ code **Editor** window that pops up, add this one line of code:  
     info("QryCogBase1 .init override.");

4.  Save **QryCogBase1**. Open **FormCogCompos6**. Verify that an **Infolog** message window appears and says **QryCogBase1 .init override**.

## Next Steps

When you create a query, you should consider whether a composite query is an option. When an existing query resembles the new query you need, consider whether range modifications or method overrides would be sufficient to describe the new query. When you create a form or a report, you should consider creating a query first, for the data source of the form or report.

## See also

[Query Properties](https://msdn.microsoft.com/en-us/library/aa842737\(v=ax.60\))

[Query Framework in the AOT](query-framework-in-the-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

