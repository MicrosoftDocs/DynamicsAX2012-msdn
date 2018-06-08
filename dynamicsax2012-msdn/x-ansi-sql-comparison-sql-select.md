---
title: 'X++, ANSI SQL Comparison: SQL Select'
TOCTitle: 'X++, ANSI SQL Comparison: SQL Select'
ms:assetid: 34589af7-6ded-4fca-b06c-272dace2c6fc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dd261457(v=AX.60)
ms:contentKeyID: 35242000
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++, ANSI SQL Comparison: SQL Select 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In X++, the SQL select statement syntax differs from the American National Standards Institute (ANSI) specification.

## Single Table Select

The following table lists differences between the select statements of X++ SQL and ANSI SQL.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>X++ SQL</p></th>
<th><p>ANSI SQL</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Table name on the from clause.</p></td>
<td><p>The from clause lists a record buffer instance that is declared from a table, such as from the CustTable table.</p></td>
<td><p>The from clause lists a table name, not the name of a buffer.</p></td>
<td><p>The record buffer has all the methods that the xRecordclass has in X++.</p></td>
</tr>
<tr class="even">
<td><p>Syntax sequence of the order by versus where clauses.</p></td>
<td><p>The order by clause must appear before the where clause. The order by clause must appear after the from or join clause. The group by clause must follow the same syntax positioning rules that the order by follows.</p></td>
<td><p>The order by clause must appear after the where clause. The where clause must appear after the from or join clause.</p></td>
<td><p>In both X++ and ANSI SQL, the from and join clauses must appear before the order by and where clauses.</p></td>
</tr>
<tr class="odd">
<td><p>Condition negation.</p></td>
<td><p>The exclamation mark ('!') is used for negation.</p></td>
<td><p>The not keyword is used for negation.</p></td>
<td><p>X++ does not support the syntax !like. Instead, you must apply the ! operator to a clause.</p></td>
</tr>
<tr class="even">
<td><p>Wildcard characters for the like operator.</p></td>
<td><ul>
<li><p>0 to many – Asterisk ('*')</p></li>
<li><p>Exactly 1 – Question mark ('?')</p></li>
</ul></td>
<td><ul>
<li><p>0 to many – Percent sign ('%')</p></li>
<li><p>Exactly 1 – Underbar ('_')</p></li>
</ul></td>
<td><p>For more information, see <a href="relational-operators.md">Relational Operators</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Logical operators in the where clause.</p></td>
<td><ul>
<li><p>And – &amp;&amp;</p></li>
<li><p>Or – ||</p></li>
</ul></td>
<td><ul>
<li><p>And – and</p></li>
<li><p>Or – or</p></li>
</ul></td>
<td><p>For more information, see <a href="relational-operators.md">Relational Operators</a>.</p></td>
</tr>
</tbody>
</table>


### ![Dd261457.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dd261457.collapse_all(en-us,AX.60).gif")Code Example

The following code example illustrates features in the previous table.

    static void OByWhere452Job(Args _args)
    {
        // Declare the table buffer variable.
        CustTable tCustTable;
        ;
        while
        SELECT * from tCustTable
            order by tCustTable.AccountNum desc
            where (!(tCustTable.Name like '*i*i*') && tCustTable.Name like 'T?e *')
        {
            info(tCustTable.AccountNum + " , " + tCustTable.Name);
        }
    }
    /*** InfoLog output
    Message (04:02:29 pm)
    4010 , The Lamp Shop
    4008 , The Warehouse
    4001 , The Bulb
    ***/

### ![Dd261457.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dd261457.collapse_all(en-us,AX.60).gif")X++ SQL Keywords

The following X++ SQL keywords are among those that are not part of ANSI SQL:

  - crosscompany

  - firstonly100

  - forceliterals

  - forcenestedloop

  - forceplaceholders

  - forceselectorder

  - validtimestate

## Join Clause

The following table lists differences about the join keyword of X++ SQL and ANSI SQL.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>X++ SQL</p></th>
<th><p>ANSI SQL</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Columns list.</p></td>
<td><p>The columns in the columns list must all come from the table listed in the from clause, and not from any table in a join clause. Columns in the list cannot be qualified by their table name.</p></td>
<td><p>The columns in the columns list can come from any table in the from or join clauses. It helps others to maintain your code when you qualify the columns in the list with their table name.</p></td>
<td><p>For more information, see <a href="select-statements-on-fields.md">Select Statements on Fields</a>.</p></td>
</tr>
<tr class="even">
<td><p>Join clause syntax.</p></td>
<td><p>The join clause follows the where clause.</p></td>
<td><p>The join clause follows a table in the from clause.</p></td>
<td><p>In the X++ code example, the join criteria is an equality of SalesPoolId values.</p></td>
</tr>
<tr class="odd">
<td><p>Inner keyword.</p></td>
<td><p>The default join mode is inner join. There is no inner keyword.</p></td>
<td><p>The default join mode is inner join. The inner keyword is available to make the code explicit.</p></td>
<td><p>The outer keyword exists in both X++ SQL and ANSI SQL.</p></td>
</tr>
<tr class="even">
<td><p>Left and right keywords.</p></td>
<td><p>The left and right keywords are not available. All joins are left.</p></td>
<td><p>The left and right keywords are available to modify the join keyword.</p></td>
<td><p>No comments.</p></td>
</tr>
<tr class="odd">
<td><p>Equality operator.</p></td>
<td><p>The double equal sign operator ('==') is used to test for the equality of two values.</p></td>
<td><p>The single equal sign operator ('=') is used to test for the equality of two values.</p></td>
<td><p>No comments.</p></td>
</tr>
</tbody>
</table>


### ![Dd261457.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dd261457.collapse_all(en-us,AX.60).gif")Code Example

The following code example illustrates the join syntax in X++ SQL.

    static void OByWhere453Job(Args _args)
    {
        // Declare table buffer variables.
        CustTable tCustTable;
        SalesPool tSalesPool;
        ;
        while
        SELECT
                // Not allowed to qualify by table buffer.
                // These fields must be from the table
                // in the from clause.
                AccountNum,
                Name
            from tCustTable
                order by tCustTable.AccountNum desc
                where (tCustTable.Name like 'The *')
            join tSalesPool
                where tCustTable.SalesPoolId == tSalesPool.SalesPoolId
        {
            info(tCustTable.AccountNum + " , " + tCustTable.Name);
        }
    }

## Aggregate Fields

The following table lists some differences in how aggregate fields in the select column list are referenced between X++ SQL and ANSI SQL. Aggregate fields are those that are derived by functions such as sum or avg.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>X++ SQL</p></th>
<th><p>ANSI SQL</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Aggregate field name alias.</p></td>
<td><p>The aggregate value is in the field that was aggregated.</p></td>
<td><p>You can use the as keyword to tag an aggregate field with a name alias. The alias can be referenced in subsequent code.</p></td>
<td><p>For more information, see <a href="aggregate-functions-differences-between-x-and-sql.md">Aggregate Functions: Differences Between X++ and SQL</a></p></td>
</tr>
</tbody>
</table>


### ![Dd261457.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dd261457.collapse_all(en-us,AX.60).gif")Code Example

In the following code example, the call to the info method illustrates the way to reference aggregate fields (see tPurchLine.QtyOrdered).

    static void Null673Job(Args _args)
    {
        PurchLine tPurchLine;
        ;
        while
        select
            // This aggregate field cannot be assigned an alias name.
            sum(QtyOrdered)
            from tPurchLine
        {
            info(
                // QtyOrdered is used to reference the sum.
                "QtyOrdered:  " + num2str(tPurchLine.QtyOrdered, 
                3,  // Minimum number of output characters.
                2,  // Required number of decimal places in the output.
                1,  // '.'  Separator to mark the start of the decimal places.
                2   // ','  The thousands separator.
                ));
        }
        info("End.");
    }
    /***
    Message (12:23:08 pm)
    QtyOrdered:  261,550.00
    End.
    ***/

## Other Differences

The following table lists other differences of the select statement between the X++ SQL and ANSI SQL.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>X++ SQL</p></th>
<th><p>ANSI SQL</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>The having keyword.</p></td>
<td><p>There is no having keyword.</p></td>
<td><p>The having keyword enables you to specify filter criteria for rows that are generated by the group by clause.</p></td>
<td><p>No comments.</p></td>
</tr>
<tr class="even">
<td><p>Null results.</p></td>
<td><p>In a while select statement, if the where clause filters out all rows, no special count row is returned to report that.</p></td>
<td><p>In a select, if the where clause filters out all rows, a special count row is returned. The count value is 0.</p></td>
<td><p>No comments.</p></td>
</tr>
<tr class="odd">
<td><p>Cursors for navigating returned rows.</p></td>
<td><p>The while select statement provides cursor functionality. The alternative is to use the next keyword.</p></td>
<td><p>You can declare a cursor for looping through the rows that are returned from a select statement.</p></td>
<td><p>For more information, see <a href="methods-in-x.md">Methods in X++</a>.</p></td>
</tr>
<tr class="even">
<td><p>From clause.</p></td>
<td><p>The from keyword is optional when no columns are listed and only one table is referenced. The following two syntax options are equivalent:</p>
<p>select * from tCustTable;</p>
<p>select tCustTable;</p></td>
<td><p>A select statement cannot read from a table unless the from clause is used.</p></td>
<td><p>In X++ SQL, the simple select statement fills the table buffer variable with the first row that was returned. This is illustrated by the following code fragment:</p>
<p>select * from tCustTable;</p>
<p>info(tCustTable.Name);</p></td>
</tr>
</tbody>
</table>


## See also

[X++, C\# Comparisons](x-csharp-comparisons.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

