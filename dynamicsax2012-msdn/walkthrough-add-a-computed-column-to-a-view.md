---
title: 'Walkthrough: Add a Computed Column to a View'
TOCTitle: 'Walkthrough: Add a Computed Column to a View'
ms:assetid: 6153fb85-489f-4fef-8930-8e3e8ceddf0e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg845841(v=AX.60)
ms:contentKeyID: 35244535
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- sql
---

# Walkthrough: Add a Computed Column to a View [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This walkthrough describes how you can add a computed column to a view in Microsoft Dynamics AX.

A computed column is the output of a computation that inputs a regular column. For example, suppose your table has a column that is named AnnualRent. Your view could return a computed column that is named MonthlyRent and which calculates AnnualRent/12.

You can add the computed column to the select list of columns only. If the computed column is itself a select statement with a where clause, you can include the name of a real column in that where clause.

## Prerequisites

To fully understand this walkthrough you must know how to do the following:

  - How to use the Application Object Tree ([AOT](application-object-tree-aot.md)).

  - How to write an [method in X++](methods-in-x.md).

## Create a View

In this section you [create a view](how-to-create-a-view-based-on-a-query.md) named **TestCompColView**.

1.  Click **AOT** \> **Data Dictionary** \> **Views** \> **New View**.

2.  Right-click the new **View1** node, and then click **Properties**.

3.  In the **Properties** window, change the **Name** property to **TestCompColView**.

4.  Expand the **Views** \> **TestCompColView** \> **Metadata** \> **Data Sources** node.

5.  Open a second AOT window and drop the node **AOT** \> **Data Dictionary** \> **Tables** \> **CustTable** onto the **TestCompColView** \> **Metadata** \> **Data Sources** node in the first AOT window.

6.  Expand the **TestCompColView** \> **Metadata** \> **Data Sources** \> **CustTable\_1** \> **Fields** node.

7.  In the other AOT window, expand the **TestCompColView** \> **Fields** node.

8.  From under the **TestCompColView** \> **Metadata** \> **Data Sources** \> **CustTable\_1** \> **Fields** node, drop the **AccountNum** field onto the **TestCompColView** \> **Fields** node of the other AOT. Also drop the **SubsegmentId** field in the same way.

9.  Click **TestCompColView** \> **Save**.

## Add a Static Method to the View

The technique to add a computed column begins with you adding a static method to the view. The method must return a string. The system automatically concatenates the returned string with other strings that the system generates to form an entire T-SQL create view statement.

The method that you add to the view typically has at least one call to the DictView.computedColumnString method. The parameters into the computedColumnString method include the name of a data source on the view, and one field name from that data source. The computedColumnString method returns the name of the field after qualifying the name with the alias of the associated table. For example, if the computedColumnString method is given the field name of AccountNum, it returns a string such as A.AccountNum or B.AccountNum.

### ![Gg845841.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845841.collapse_all(en-us,AX.60).gif")Steps to add a method to a view

1.  Under **AOT** \> **Data Dictionary** \> **Views**, expand the node for your **TestCompColView** view that you created in the previous section.

2.  Under your view, click **Methods** \> **New Method**. The method editor window is displayed.

3.  Change the method definition to the following:
    
    private static server str compColSubsegAcctMethod()
    

    > [!NOTE]
    > <P>The method name can be anything, but all the other keywords are required as shown.</P>
    > <P>Often no parameters are allowed for the method. For more information, see <A href="walkthrough-add-a-computed-column-to-a-union-view.md">Walkthrough: Add a Computed Column to a Union View</A>.</P>



4.  Write X++ code in the body of the compColSubsegAcct method, as is described in the following section.

## Write X++ Code in the Body of the Method

This section provides the entire method for a computed column example. Nothing in the method is tied to any particular computed column. However, later when you add a computed column to the view, you set the **ViewMethod** property of the column to this method name.

The following string is returned from this method:

substring(A.SUBSEGMENTID,1,1) + ' - ' + A.ACCOUNTNUM
```X++  
    private static server str compColSubsegAcctMethod()
    {
        #define.ViewName(TestCompColView)
        #define.DataSourceName("CustTable_1")
        #define.FieldSubsegmentId("SubsegmentId")
        #define.FieldAccountNum("AccountNum")
        str sReturn,
            sAccountNum,
            sSubsegmentId;
        DictView dictView2;
    
        // Construct a DictView object for the present view.
        dictView2 = new DictView(tableNum(#ViewName));
    
        // Get a string that has the target field name
        // propertly qualified with an alias (such
        // as "A." or "B.").
        sAccountNum = dictView2.computedColumnString
            (#DataSourceName,
            #FieldAccountNum,
            FieldNameGenerationMode::FieldList,
            true);
    
        sSubsegmentId = dictView2.computedColumnString
            (#DataSourceName,
            #FieldSubsegmentId,
            FieldNameGenerationMode::FieldList,
            true);
    
        sReturn = "substring("
            + sSubsegmentId
            + ",1,1) + ' - ' + "
            + sAccountNum;
    
        // Helpful confirming or diagnostic information.
        info(sAccountNum);
        info(sSubsegmentId);
        info(sReturn);
    
        return sReturn;
    }
```
The output to the Infolog from the previous method is shown in the following.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Displayed in the Infolog</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Synchronize database</p>
<p>A.ACCOUNTNUM</p>
<p>A.SUBSEGMENTID</p>
<p>substring(A.SUBSEGMENTID,1,1) + ' - ' + A.ACCOUNTNUM</p></td>
</tr>
</tbody>
</table>


## Add a Computed Column to the View

In this section you add a computed column to the view.

1.  Right-click the **Fields** node under your view, and then click **String Computed Column**.

2.  For the new field or column, change the **Name** property to **compCol\_Subseg\_Acct**.

3.  Change the **StringSize** property to **32**.

## Link the Computed Column to the Method

In this section you relate the computed column to the static method that you added in a previous section.

1.  For the computed column, you set the **ViewMethod** property to the name of the **compColSubsegAcctMethod** method that you wrote in a previous step.

## Synchronize the View to the Database

In this section you synchronize the changes to your view from the AOT into the underlying database.

1.  Right-click the AOT node for your view, and then click **Save**. This causes the Microsoft Dynamics AX system to send the T-SQL create view statement to the underlying database.

### ![Gg845841.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845841.collapse_all(en-us,AX.60).gif")Activities During Synchronization

During synchronization the Microsoft Dynamics AX system detects the computed column. The system obtains the name of the static method that builds the computed column from the **ViewMethod** property of the computed column. At that moment the system calls your method.

The system enhances the string that your method returns by wrapping it in a T-SQL cast function. The enhanced string is then added to the whole string that contains the T-SQL create view statement. Your view is created in the database before synchronization finishes.

Later, your method is not called when the view is queried. Your method is called only if the view is resynchronized to the database.


> [!TIP]
> <P>If your view fails to synchronize, it might be that your method for the computed column generates invalid T-SQL syntax. It can help you diagnose the problem if you activate the SQL tracing feature of Microsoft Dynamics AX. In the trace you can see the entire create view statement and your substring in it. For information about how to activate SQL tracing, see <A href="tracing-with-the-tools-menu.md">Tracing with the Tools Menu</A>.</P>



## The Final View

The following T-SQL create view statement is sent by Microsoft Dynamics AX to the database.

``` sql
CREATE VIEW [dbo].[TESTCOMPCOLVIEW]
AS
    SELECT
        A.SUBSEGMENTID AS SUBSEGMENTID,
        A.ACCOUNTNUM AS ACCOUNTNUM,
        A.DATAAREAID AS DATAAREAID,
        A.RECID AS RECID,
        (CAST
            (
                (substring(A.SUBSEGMENTID,1,1)
                + ' - '
                + A.ACCOUNTNUM
                )
                    AS
                    NVARCHAR(32)
            )
        )
            AS COMPCOL_SUBSEG_ACCT
    FROM
        CUSTTABLE A
```

### ![Gg845841.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845841.collapse_all(en-us,AX.60).gif")The String Returned from the Method

The previous compColSubsegAcct method returns the following string:

substring(A.SUBSEGMENTID,1,1) + ' - ' + A.ACCOUNTNUM

The system enhances the returned string into the following T-SQL code segment. The enhancements include the following:

  - The CAST function

  - The datatype is added – which here is NVARCHAR(32).

  - The name of the computed column – which here is COMPCOL\_SUBSEG\_ACCT.

The enhancements are used to build the following T-SQL code segment, which you can see is part of the final create view statement.

``` sql
        (CAST
            (
                (substring(A.SUBSEGMENTID,1,1)
                + ' - '
                + A.ACCOUNTNUM
                )
                    AS
                    NVARCHAR(32)
            )
        )
            AS COMPCOL_SUBSEG_ACCT
```

## See the Data in the Computed Column

The data that is generated for the computed column can be seen by using the AOT. Click **AOT** \> **Data Dictionary** \> **Views** \> **TestCompColView** \> **Open**.

### ![Gg845841.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845841.collapse_all(en-us,AX.60).gif")Sample Data from the View

The following table displays sample data that includes the computed column.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>SubsegmentId</p></th>
<th><p>AccountNum</p></th>
<th><p>CompCol_Subseg_Acct</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Medium</p></td>
<td><p>4000</p></td>
<td><p>M - 4000</p></td>
</tr>
<tr class="even">
<td><p>Gross</p></td>
<td><p>4001</p></td>
<td><p>G - 4001</p></td>
</tr>
</tbody>
</table>


## See also

[How to: Create a View Based on a Query](how-to-create-a-view-based-on-a-query.md)

[View Overview](view-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

