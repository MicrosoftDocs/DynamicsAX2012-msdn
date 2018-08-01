---
title: Select Statement with an Outer Join
TOCTitle: Select Statement with an Outer Join
ms:assetid: 5e4468a7-7f83-4f12-8815-ba5e08102797
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg845763(v=AX.60)
ms:contentKeyID: 35244453
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Select Statement with an Outer Join [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, the X++ SELECT statement supports filtering an OUTER JOIN in the WHERE clause. In the JOIN clause of standard SQL there is an ON keyword for filter criteria. But there is no such ON keyword in X++ SQL.

An inner join rejects all table rows that fail to match a row in the other joined table. But an outer join includes rows from the first table even though there is no matching row in the other joined table. Default values are substituted for the data that could not be obtained from a matching row in the other joined table.

It is possible to filter an outer join at the equivalent of an ON clause that is part of the JOIN clause. For more information, see [How to: Use the QueryFilter Class with Outer Joins](how-to-use-the-queryfilter-class-with-outer-joins.md). For an inner join there is no behavioral difference between filtering on an ON clause versus on the WHERE clause.

## Tables and Test Data for this Demonstration

This section shows two tables that the code example in this topic relies on. The field types and sample data are included.

There is a 1-to-many relationship between the SalesOrder parent table and the SalesOrderLine child table. There are 0 or more rows in the SalesOrderLine table for each row in the SalesOrder table.

### ![Gg845763.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845763.collapse_all(en-us,AX.60).gif")SalesOrder Table

There are two rows in the SalesOrder table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>SalesOrderID (integer, primary key)</p></th>
<th><p>DateAdded (date)</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>2010-01-01</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>2010-02-02</p></td>
</tr>
</tbody>
</table>


### ![Gg845763.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845763.collapse_all(en-us,AX.60).gif")SalesOrderLine Table

The SalesOrderLine table contains a foreign key field, named SalesOrderID, that references the primary key column of the SalesOrder table. The SalesOrderID value 2 does not occur in the data for SalesOrderLine table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>SalesOrderLineID (string, primary key)</p></th>
<th><p>Quantity (integer)</p></th>
<th><p>SalesOrderID (integer, foreign key)</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AA</p></td>
<td><p>32</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>BB</p></td>
<td><p>67</p></td>
<td><p>1</p></td>
</tr>
<tr class="odd">
<td><p>CC</p></td>
<td><p>66</p></td>
<td><p>1</p></td>
</tr>
</tbody>
</table>


## Code Example

The following X++ code example has a SELECT statement that reads the tables which are described in the previous section. The SELECT statement includes a left OUTER JOIN clause. The join criteria and the data filter are both on the WHERE clause.

   ```X++
    static void OuterJoinSelectJob3(Args _args)
    {
        SalesOrder recSalesOrder;
        SalesOrderLine recSalesOrderLine;
        struct struct4;
        ;
        struct4 = new struct
            ("int SalesOrderID;"
            + "date DateAdded;"
            + "str SalesOrderLineID;"
            + "int Quantity"
            );
    
        while
        SELECT
            from
                recSalesOrder
                OUTER JOIN recSalesOrderLine
            WHERE
                recSalesOrder.SalesOrderID == recSalesOrderLine.SalesOrderID
                && recSalesOrderLine.Quantity == 66
        {
            struct4.value("SalesOrderID", recSalesOrder.SalesOrderID);
            struct4.value("DateAdded", recSalesOrder.DateAdded);
            struct4.value("SalesOrderLineID", recSalesOrderLine.SalesOrderLineID);
            struct4.value("Quantity", recSalesOrderLine.Quantity);
            info(struct4.toString());
        }
    }
   ```

### ![Gg845763.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845763.collapse_all(en-us,AX.60).gif")Output Displayed in the Infolog

This section displays the output from the preceding outer join code example. The second record in the output has a SalesOrderID value of 2. That value of 2 is not present in the SalesOrderLine table. Therefore, some of the fields in the second record have default values, namely 0 for an integer and a zero length string for a string.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>(SalesOrderID:1; DateAdded:2010/1/1; SalesOrderLineID:&quot;CC&quot;; Quantity:66)</p>
<p>(SalesOrderID:2; DateAdded:2010/2/2; SalesOrderLineID:&quot;&quot;; Quantity:0)</p></td>
</tr>
</tbody>
</table>


## See also

[Select Statements](select-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

