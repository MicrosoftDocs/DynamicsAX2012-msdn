---
title: 'Walkthrough: Add a Computed Column to a Union View'
TOCTitle: 'Walkthrough: Add a Computed Column to a Union View'
ms:assetid: 7226db42-db7d-4766-850f-43774e99ed93
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg846293(v=AX.60)
ms:contentKeyID: 35245842
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- sql
---

# Walkthrough: Add a Computed Column to a Union View [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic explains how you can add a computed column to a union view in Microsoft Dynamics AX. When a T-SQL union is involved, the support method that generates the T-SQL code for the computed column must input an int parameter. The parameter specifies one particular branch of the union query of the view. The T-SQL code that the method must output often differs depending on the branch.

This walkthrough illustrates the following tasks:

  - Create a union query.

  - Create the view with regular columns.

  - Add a computed column to the union view.

  - Examine the T-SQL code that is generated for the view.

## Prerequisites

To complete this walkthrough you need:

  - An understanding of the topic [Walkthrough: Add a Computed Column to a View](walkthrough-add-a-computed-column-to-a-view.md).

## Create a Union Query

In the following subsections you use the Application Object Tree (AOT) to perform the following actions:

  - Create a new query.

  - Change the **QueryType** property from its default of **Join** to **Union**.

  - Add two tables to the query as data sources.

  - Make lists of fields that match by type under each data source.

### ![Gg846293.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg846293.collapse_all(en-us,AX.60).gif")Create a New Query Node

To create a query with a **QueryType** of **Union**, follow these steps:

1.  Click **AOT** \> **Queries** \> **New Query**.

2.  Right-click the new node for your query, and then click **Properties**.

3.  In the **Properties** window, change the **Name** property value to **TestQryUnion**.

4.  Set its **QueryType** property to **Union**.

### ![Gg846293.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg846293.collapse_all(en-us,AX.60).gif")Add Tables as Data Sources for the Query

To add two tables as data sources for the query, follow these steps:

1.  Drag the node **AOT** \> **Data Dictionary** \> **Tables** \> **CustTable** onto the node **AOT** \> **Queries** \> **TestQryUnion** \> **Data Sources**. The system sets the **Name** property of the new node to **CustTable\_1**.

2.  Drag the node **AOT** \> **Data Dictionary** \> **Tables** \> **AssetBook** onto the node **AOT** \> **Queries** \> **TestQryUnion** \> **Data Sources**. The system sets the **Name** property of the new node to **AssetBook\_1**.

### ![Gg846293.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg846293.collapse_all(en-us,AX.60).gif")Add Fields to Each Data Source that Match by Type

To add fields to both data sources, follow these steps:

1.  Delete all fields under **AOT** \> **Queries** \> **TestQryUnion** \> **Data Sources** \> **CustTable\_1** \> **Fields**.

2.  Click **AOT** \> **Queries** \> **TestQryUnion** \> **Data Sources** \> **CustTable\_1** \> **Fields** \> **New** \> **Field**. Then set the **Field** property to **AccountNum**.

3.  Repeat the previous step, except set the **Field** property to **Party**.

4.  Repeat the previous field related steps for the **AOT** \> **Queries** \> **TestQryUnion** \> **Data Sources** \> **AssetBook\_1** \> **Fields** node. Populate the **Fields** node first with the field **CustAccount**, and then with **LifeTime**. Note that the fields must appear in the exact sequence described, so that the corresponding data types match between the two data sources.
    

    > [!WARNING]
    > <P>The field types under the <STRONG>CustTable_1</STRONG> &gt; <STRONG>Fields</STRONG> and <STRONG>AssetBook_1</STRONG> &gt; <STRONG>Fields</STRONG> must match at each ordinal position. In this case, both <STRONG>AccountNum</STRONG> and <STRONG>CustAccount</STRONG> are strings of length 20, and both <STRONG>Party</STRONG> and <STRONG>LifeTime</STRONG> are 32 bit integers.</P>



## Create the View with Regular Columns

In the following subsections you create a view that has regular columns. The data source for the view is the query that you created in the previous section.

### ![Gg846293.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg846293.collapse_all(en-us,AX.60).gif")Create a New View Node

To create a view that uses the previous query as its data source, follow these steps:

1.  Create a view named **TestViewUnion**.

2.  Drag the node **AOT** \> **Queries** \> **TestQryUnion** onto **AOT** \> **Data Dictionary** \> **Views** \> **TestViewUnion** \> **Data Sources**.

3.  Click **TestViewUnion** \> **Metadata** \> **TestQryUnion** \> **Data Sources** \> **AssetBook\_1**. Then set the **Union** property to **UnionAll**.

### ![Gg846293.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg846293.collapse_all(en-us,AX.60).gif")Add Regular Columns to the View

To add regular columns to the view, follow these steps:

1.  Click **TestViewUnion** \> **Fields** \> **New** \> **Field**.

2.  For the new field, set the **DataSource** property to **CustTable\_1**. Set the **DataField** property to **AccountNum**.

3.  Set the **Name** property to **AccountNum**, to match the **DataField** name.

4.  Repeat the previous three steps to add the **Party** field.

## Add a Computed Column to the Union View

In the following subsections you add a method that supports a computed column.

### ![Gg846293.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg846293.collapse_all(en-us,AX.60).gif")Add a Support Method to the View

In this section you add a static method that will support the computed column that you plan to add later. The method outputs part of the T-SQL string that defines the computed column in the underlying database server. The method runs only when the view is synchronized from the AOT to the database server.

The support method must input an int parameter when the method is supporting a union view. The int parameter value tells the method which branch of the union the present call is meant for. The first branch is number 1, not 0. There is one branch for each data source of the **TestQryUnion** query.

1.  Click **TestViewUnion** \> **Methods** \> **New Method**. This opens the code **Editor** window. Paste the following code into the **Editor** window. The method name is Comp\_Party\_LifeTime.
    
        private static server str Comp_Party_LifeTime(int branchNum)
        {
            #define.ViewName(TestViewUnion)
            #define.DataSourceNameBranch1("CustTable_1")
            #define.DataSourceNameBranch2("AssetBook_1")
            #define.FieldToComputeWith1("Party")
            #define.FieldToComputeWith2("LifeTime")
        
            str sReturn,
                sTemp99,
                sTemp98,
                sTemp97;
            DictView dictView2;
            //-------- EndOf variable declarations. ---------
        
            dictView2 = new DictView(tableNum(#ViewName));
        
            // Use T-SQL 'top 1', not X++ 'firstOnly'.
            sTemp99 =
                "(SELECT top 1 bg.DiscNoticeDelayDays"
                + " from BankGroup as bg"
                + " where bg.DiscNoticeDelayDays <= (123 + "
                ;
        
            switch (branchNum)
            {
                case 1:
                    sTemp98 = dictView2.computedColumnString
                        (
                DataSourceNameBranch1, // Branch 1.
                FieldToComputeWith1,
                        FieldNameGenerationMode::WhereClause,
                        true
                        );
                    sTemp97 =
                        ") /*1*/ )";
                    sReturn = sTemp99 + sTemp98 + sTemp97;
                    break;
        
                case 2:
                    sTemp98 = dictView2.computedColumnString
                        (
                DataSourceNameBranch2, // Branch 2.
                FieldToComputeWith2,
                        FieldNameGenerationMode::WhereClause,
                        true
                        );
                    sTemp97 =
                        ") /*2*/ )";
                    sReturn = sTemp99 + sTemp98 + sTemp97;
                    break;
            }
            sTemp99 = "For TestUnionView.Comp_Party_LifeTime, sReturn is: "
                + sReturn;
            info(sTemp99);
        
            return sReturn;
        }

### ![Gg846293.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg846293.collapse_all(en-us,AX.60).gif")Add a Computed Column to the View

To add a computed column to the view, follow these steps:

1.  Click **TestViewUnion** \> **Fields** \> **New** \> **Int Computed Column**.

2.  For the new computed field, set the **Name** property to **ComputedInt**.

3.  Set the **ViewMethod** property to **Comp\_Party\_LifeTime**.

## T-SQL Code Generated for the View

The following subsections show T-SQL code that is generated for the view and its computed column.

### ![Gg846293.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg846293.collapse_all(en-us,AX.60).gif")Two Outputs from the Support Method

There are two data sources in the union view that you created. Therefore, the support method for the computed column is called twice during synchronization, one time for each branch that is delineated by the union keyword in the T-SQL create statement. The outputs from the method, for branches 1 and 2, are shown in the following blocks.

``` sql
(SELECT top 1 bg.DiscNoticeDelayDays
    from BankGroup as bg
    where bg.DiscNoticeDelayDays <= (123 + A.PARTY) /*1*/ )
```

 

``` sql
(SELECT top 1 bg.DiscNoticeDelayDays
    from BankGroup as bg
    where bg.DiscNoticeDelayDays <= (123 + A.LIFETIME) /*2*/ )
```

### ![Gg846293.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg846293.collapse_all(en-us,AX.60).gif")The Whole Create View Statement

The following block shows the whole create view T-SQL statement.

``` sql
CREATE VIEW "DBO".TESTVIEWUNION
AS
  SELECT
     A.ACCOUNTNUM AS ACCOUNTNUM
    ,A.PARTY AS PARTY
    ,A.DATAAREAID AS DATAAREAID
    ,A.RECID AS RECID
    ,
     (CAST (((SELECT top 1 bg.DiscNoticeDelayDays
                from BankGroup as bg
                where bg.DiscNoticeDelayDays <= (123 + A.PARTY) /*1*/ ))
           AS INT))
               AS COMPUTEDINT
  FROM CUSTTABLE A

UNION

  SELECT
     A.CUSTACCOUNT
    ,A.LIFETIME
    ,A.DATAAREAID
    ,A.RECID
    ,
     (CAST (((SELECT top 1 bg.DiscNoticeDelayDays
                from BankGroup as bg
                where bg.DiscNoticeDelayDays <= (123 + A.LIFETIME) /*2*/ ))
           AS INT))
               AS COMPUTEDINT
  FROM ASSETBOOK A
```

## See also

[Walkthrough: Add a Computed Column to a View](walkthrough-add-a-computed-column-to-a-view.md)

[View Overview](view-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

