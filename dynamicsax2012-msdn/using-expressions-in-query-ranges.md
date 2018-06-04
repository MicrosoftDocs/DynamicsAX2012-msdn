---
title: Using Expressions in Query Ranges
TOCTitle: Using Expressions in Query Ranges
ms:assetid: ff839bb9-67f7-4184-a5bd-a853089e5426
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa893981(v=AX.60)
ms:contentKeyID: 35254216
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using Expressions in Query Ranges 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Query range value expressions can be used in any query where you need to express a range that is more complex than is possible with the usual dot-dot notation (such as 5012..5500).

For example, to create a query that selects the records from the table MyTable where field A equals x or field B equals y, do the following.

1.  Add a range on field A.

2.  Set the value of that range to the expression (if x = 10 or y = 20), as a string: ((A == 10) || (B == 20))

The rules for creating query range value expressions are:

  - Enclose the whole expression in parentheses.

  - Enclose all subexpressions in parentheses.

  - Use the relational and logical operators available in X++.

  - Only use field names from the range's data source.

  - Use the dataSource.field notation for fields from other data sources in the query.

Values must be constants in the expression, so any function or outside variable must be calculated before the expression is evaluated by the query. This is typically done by using the strFmt function.

The example above will then look like the following code example.

strFmt('((A == %1) || (B == %2))',x,y)

To get complete compile-time stability, use intrinsic functions to return the correct field names, as shown in the following code example.

strFmt('((%1 == %2) || (%3 == %4))',

fieldStr(MyTable,A), x,

fieldStr(MyTable,B), y)


> [!NOTE]
> <P>Query range value expressions are evaluated only at run time, so there is no compile-time checking. If the expression cannot be understood, a modal box will appear at run time that states "Unable to parse the value."</P>



## Example of adding a range to a query

The following code programmatically adds a range to a query and uses string substitution to specify the data source and field name. The range expression is associated with the CustTable.AccountNum field; however, because the expression specifies the data sources and field names, the expression can be associated with any field in the CustTable table.

    static void AddRangeToQuery3Job(Args _args)
    {
        Query q = new Query();  // Create a new query.
        QueryRun qr;
        CustTable ct;
        QueryBuildDataSource qbr1;
        str strTemp;
        ;
    
        // Add a single datasource.
        qbr1 = q.addDataSource(tablenum(CustTable));
        // Name the datasource 'Customer'.
        qbr1.name("Customer");
    
        // Create a range value that designates an "OR" query like:
        // customer.AccountNum == "4000" || Customer.CreditMax > 2500.
    
        // Add the range to the query data source.
        qbr1.addRange(fieldNum(CustTable, AccountNum)).value(
        strFmt('((%1.%2 == "4000") || (%1.%3 > 2500))',
            qbr1.name(),
            fieldStr(CustTable, AccountNum),
            fieldStr(CustTable, CreditMax)));
    
        // Print the data source.
        print qbr1.toString();
        info(qbr1.toString());
    
        // Run the query and print the results.
        qr = new QueryRun(q);
    
        while (qr.next())
        {
            if (qr.changedNo(1))
            {
                ct = qr.getNo(1);
                strTemp = strFmt("%1 , %2", ct.AccountNum, ct.CreditMax);
                print strTemp;
                info(strTemp);
            }
        }
        pause;
    }

## See also

[Accessing Data](accessing-data.md)

[Create Queries Using X++](how-to-create-queries-by-using-x.md)

[Query System Classes](query-object-model.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

