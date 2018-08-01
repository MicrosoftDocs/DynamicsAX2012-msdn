---
title: 'How to: Include a Filter for Partition in Direct Transact-SQL'
TOCTitle: 'How to: Include a Filter for Partition in Direct Transact-SQL'
ms:assetid: 5ce90a42-e862-464e-90bc-1eb16a8afd1a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ129502(v=AX.60)
ms:contentKeyID: 46661156
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- sql
---

# How to: Include a Filter for Partition in Direct Transact-SQL [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

In your X++ method, you can use the Statement class to issue Transact-SQL directly to Microsoft SQL Server. If the database that your T-SQL accesses is the database that is created and used by Microsoft Dynamics AX to store your business data, you must consider adding Where clause filters for both partition and legal entity (or company).

When you run X++ SQL statements, the Application Object Server (AOS) converts the statements into T-SQL. The AOS modifies the T-SQL to restrict data access to the current contexts of partition and legal entity.

You bypass the AOS when you use the Statement class to issue T-SQL. This means the AOS cannot add the partition and legal entity filters. Therefore you must consider adding the filters to your T-SQL yourself. This topic explains how to add these filters.

## Situations for using the Statement Class

Ideally you can design your partitions to minimize or eliminate the need for cross-partition queries. However, there might be rare situations when you need to query data that is in partitions other than the current partition. The following table discusses such situations.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Situation</p></th>
<th><p>Discussion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>You need to access data that resides in a partition other than the partition of current context.</p></td>
<td><p>Your T-SQL needs filters to restrict data access to a partition other than the partition of current context. Your X++ code that builds the T-SQL code needs a partition identifier other than the values offered by the X++ language functions named getCurrentPartition or getCurrentPartitionRecId. Those functions refer to the current partition.</p></td>
</tr>
<tr class="even">
<td><p>You need to access data in multiple partitions in one query.</p></td>
<td><p>Your T-SQL might need filters for the current partition plus a hardcoded PartitionKey value for a second partition.</p>
<p>Or your T-SQL might have no partition filters. Then your T-SQL would access data across all partitions.</p></td>
</tr>
</tbody>
</table>



> [!WARNING]
> <P>You must be careful if you use the Statement class to modify data. Partition integrity is only one concern. You must be certain that you understand all the effects the data modifications have on the system.</P>



## X++ Code Example for Direct T-SQL that Filters by Partition

The X++ code example in this section builds a T-SQL Select statement. The statement selects data from the InventDimCleanUp table. The example then submits the T-SQL directly to SQL Server. The code example demonstrates the X++ techniques you can use to account for partitions and legal entities.

Many tables have system fields named Partition and DataAreaId. These fields are not shown under  
 **AOT** \> **Data Dictionary** \> **Tables** \> Your Table \> **Fields**.  
Table records that share the same value in their Partition field are storing data for the same partition. Within one partition, the table records that share the same value for their DataAreaId field are storing data for the same legal entity.

The following code example is contained in a demonstration class named DirectSqlDataPartition. The example shows all methods of the class that together demonstrate how you can issue direct T-SQL in X++. Notice the following items:

  - The X++ language functions named getCurrentPartition and curext are important to this example.

  - The X++ language functions named getCurrentPartition and curext are important to this example.

  - The executeDirectSql method of this example sends the T-SQL statement to SQL Server. This method has the following characteristics:
    
      - The method must be declared with the server keyword of the X++ language.
    
      - The method must assert the SqlStatementExecutePermission permission.

  - You can run this code example by loading its Main method into the code editor, and then pressing F5.

### ![JJ129502.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129502.collapse_all(en-us,AX.60).gif")classDeclaration

This is the classDeclaration portion of the DirectSqlDataPartition class.

```X++
// The classDeclaration node under AOT > Classes > DirectSqlDataPartition.
    
    public class DirectSqlDataPartition
    {
    }
```

### ![JJ129502.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129502.collapse_all(en-us,AX.60).gif")Main Method

This is the Main method of the DirectSqlDataPartition class. To run this code example in the MorphX development workspace, you first right-click the node for **Main**, and then click **View Code**. Then in the code editor, you press F5, or click the green **Go** arrow icon on the toolbar.

```X++
// A method under AOT > Classes > DirectSqlDataPartition.
    
    static public void Main(Args _args)
    {
        str sSql;
        str sResultField;
        
        sSql = DirectSqlDataPartition::buildDirectSql();
        sResultField = DirectSqlDataPartition::executeDirectSql(sSql);
        
        Global::info("SQL:  " + sSql);
        info("Results:  " + sResultField);
        return;
    }
```

### ![JJ129502.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129502.collapse_all(en-us,AX.60).gif")executeDirectSql Method

The X++ language keyword server is required in the following executeDirectSql method.

```X++
// A method node under AOT > Classes > DirectSqlDataPartition.
    
    static server public str executeDirectSql(str _sSql)
    {
        SqlStatementExecutePermission  oSqlStatementExecutePermission;
    
        Connection        oConnection;
        Statement         oStatement;
        ResultSet         oResultSet;
    
        str               sResultField = "";
        str               sNewLine;
        //---------------------------------------
    
        // For Test clarity only.  .NET interop from X++.
        sNewLine = System.Environment::get_NewLine();
    
        if (";" != subStr(_sSql, strLen(_sSql), -1))
            { _sSql += ";"; }
        
        oSqlStatementExecutePermission = new SqlStatementExecutePermission(_sSql);
        oSqlStatementExecutePermission.assert();
        //oSqlStatementExecutePermission.demand();
    
        oConnection = new Connection();
        oStatement = oConnection.createStatement();
        oResultSet = oStatement.executeQuery(_sSql);
    
        while ( oResultSet.next() )
        {
            sResultField += oResultSet.getString(1) + sNewLine;
        }
    
        CodeAccessPermission::revertAssert();
    
        return sResultField;
    }
```

### ![JJ129502.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129502.collapse_all(en-us,AX.60).gif")buildDirectSql Method

In the following buildDirectSql method, notice that the two calls to the X++ language functions named getCurrentPartition and curext are commented out. This example instead uses literal identifiers for a particular partition and a particular legal entity. The approach you take depends on your situation.

There is a unique index on the InventDimId field in the InventDim and InventDimCleanUp tables.

```X++
// A method node under AOT > Classes > DirectSqlDataPartition.
    
    static public str buildDirectSql()
    {
        str sSql;
        str sNewLine;
    
        sNewLine = System.Environment.NewLine(); // .NET interop from X++.
    
        sSql  = "SELECT cc.InventDimId" + sNewLine;
        sSql += " FROM" + sNewLine;
        sSql += "   InventDimCleanUp AS cc" + sNewLine;
        sSql += "  INNER JOIN" + sNewLine;
        sSql += "   Partitions AS pp";
        sSql +=     " on pp.RecId = cc.Partition" + sNewLine;
        sSql += " WHERE" + sNewLine;
    
      // Choose either approach for the PartitionKey value:    
      //sSql += "   pp.PartitionKey = N'" + getCurrentPartition() + "'" + sNewLine;
        sSql += "   pp.PartitionKey = N'TestPar3'" + sNewLine;
        
        sSql += "  AND" + sNewLine;
    
      // Choose either approach for the DataAreaId value:    
      //sSql += "   cc.DataAreaId = N'" + curext() + "'" + sNewLine;
        sSql += "   cc.DataAreaId = N'ceu'" + sNewLine;
    
        sSql += "  AND" + sNewLine;
        sSql += "   EXISTS" + sNewLine;
        sSql += "    (" + sNewLine;
        sSql += "     SELECT N'x'" + sNewLine;
        sSql += "      FROM" + sNewLine;
        sSql += "        InventDim AS ii" + sNewLine;
        sSql += "      WHERE" + sNewLine;
        sSql += "        ii.InventDimId = cc.InventDimId" + sNewLine;
        sSql += "       --AND" + sNewLine;
        sSql += "        --ii.DataAreaId = cc.DataAreaId" + sNewLine;
        sSql += "       --AND" + sNewLine;
        sSql += "        --ii.Partition = cc.Partition" + sNewLine;
        sSql += "    )" + sNewLine;
        sSql += ";" + sNewLine;
    
        return sSql;
    }
```

### ![JJ129502.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129502.collapse_all(en-us,AX.60).gif")The Built Transact-SQL

This section shows the string of Transact-SQL code that is output by the method buildDirectSql. The string is sent to SQL Server. In the Where clause you can see the following filters for partition and legal entity:

  - Partition filter:   PartitionKey = N'TestPar3'

  - Legal entity filter:   DataAreaId = N'ceu'

<!-- end list -->

``` sql
--   Built  Transact-SQL
SELECT cc.InventDimId
 FROM
   InventDimCleanUp AS cc
  INNER JOIN
   Partitions AS pp on pp.RecId = cc.Partition
 WHERE
   pp.PartitionKey = N'TestPar3'
  AND
   cc.DataAreaId = N'ceu'
  AND
   EXISTS
    (
     SELECT N'x'
      FROM
        InventDim AS ii
      WHERE
        ii.InventDimId = cc.InventDimId
       --AND
        --ii.DataAreaId = cc.DataAreaId
       --AND
        --ii.Partition = cc.Partition
    )
;
```

## See also

[Partitions, Companies, and Data Isolation in Microsoft Dynamics AX](partitions-companies-and-data-isolation-in-microsoft-dynamics-ax.md)

[How to: Connect to an External Database from X++ Code](how-to-connect-to-an-external-database-from-x-code.md)

[Statement Class](https://msdn.microsoft.com/en-us/library/gg926457\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

