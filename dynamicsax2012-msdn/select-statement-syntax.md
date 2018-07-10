---
title: Select Statement Syntax
TOCTitle: Select Statement Syntax
ms:assetid: 778e0f99-41c4-4f55-a5fe-0ef37381950c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa656402(v=AX.60)
ms:contentKeyID: 35245999
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Select Statement Syntax 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>SelectStatement</p></td>
<td><p>=</p></td>
<td><p>select Parameters</p></td>
</tr>
<tr class="even">
<td><p>Parameters</p></td>
<td><p></p></td>
<td><p>[ [  FindOptions  ] [  FieldList  from ] ] TableBufferVariable [ IndexClause ] [  Options  ] [  WhereClause  ] [  JoinClause  ]</p></td>
</tr>
<tr class="odd">
<td><p>FindOptions</p></td>
<td><p>=</p></td>
<td><p>crossCompany | reverse | firstFast | [ firstOnly | firstOnly10 | firstOnly100 | firstOnly1000 ] | forUpdate | noFetch | [forcePlaceholders | forceLiterals] | forceselectorder | forceNestedLoop | repeatableRead | validTimeState</p></td>
</tr>
<tr class="even">
<td><p>FieldList</p></td>
<td><p>=</p></td>
<td><p>Field  { ,  Field  } | *</p></td>
</tr>
<tr class="odd">
<td><p>Field</p></td>
<td><p>=</p></td>
<td><p>Aggregate  (  FieldIdentifier  ) |  FieldIdentifier</p></td>
</tr>
<tr class="even">
<td><p>Aggregate</p></td>
<td><p>=</p></td>
<td><p>sum | avg | minof | maxof | count</p></td>
</tr>
<tr class="odd">
<td><p>Options</p></td>
<td><p>=</p></td>
<td><p>[ order by , group by ,  FieldIdentifier  [ asc | desc ] { ,  FieldIdentifier  [ asc | desc ] }] | [  IndexClause  ]</p></td>
</tr>
<tr class="even">
<td><p>IndexClause</p></td>
<td><p>=</p></td>
<td><p>index  IndexName | index hint  IndexName</p></td>
</tr>
<tr class="odd">
<td><p>WhereClause</p></td>
<td><p>=</p></td>
<td><p>where  Expression</p></td>
</tr>
<tr class="even">
<td><p>JoinClause</p></td>
<td><p>=</p></td>
<td><p>[exists | notexists | outer ] join  Parameters</p></td>
</tr>
</tbody>
</table>


## Keywords Used in the Select Syntax




<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Keyword</p></th>
<th><p>Description</p></th>
<th><p>Example</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>asc</p></td>
<td><p>An option on the order by or group by clause. The sorting is ascending. (Sort is ascending by default.)</p></td>
<td><p>select * from custTable</p>
<p>    order by Name asc;</p></td>
</tr>
<tr class="even">
<td><p>avg</p></td>
<td><p>Returns the average of the fields.</p></td>
<td><p>CustTable custTable;</p>
<p>;</p>
<p>select avg(value) from custTable;</p>
<p>print custTable.value;</p></td>
</tr>
<tr class="odd">
<td><p>count</p></td>
<td><p>Returns the number of records.</p></td>
<td><p>CustTable xCT;</p>
<p>int64 iCountRows; ;</p>
<p>Select COUNT(RecID) from xCT;</p>
<p>iCountRows = xCT.RecID;</p></td>
</tr>
<tr class="even">
<td><p>crossCompany</p></td>
<td><p>Returns data for all companies that the user is authorized to read from. (A container can be added to reduce the number of companies involved.)</p></td>
<td><p>CustTable custTable;</p>
<p>container conCompanies = ['dat','dmo'];</p>
<p>;</p>
<p>select crossCompany :conCompanies</p>
<p>    * from custTable;</p></td>
</tr>
<tr class="odd">
<td><p>desc</p></td>
<td><p>An option on the order by or group by clause. The sorting is descending.</p></td>
<td><p>select * from custTable</p>
<p>    order by Name desc;</p></td>
</tr>
<tr class="even">
<td><p>exists</p></td>
<td><p>A method that returns a Boolean value and a join clause.</p></td>
<td><p>while select AccountNum, Name from custTable</p>
<p>    order by AccountNum</p>
<p>    exists join * from ctr</p>
<p>    where (ctr.AccountNum ==</p>
<p>      custTable.AccountNum)</p></td>
</tr>
<tr class="odd">
<td><p>firstFast</p></td>
<td><p>A priority hint. The first row appears more quickly but the total return time for this option might be slower. The firstFast hint is automatically issued from all forms, but is rarely used directly from X++.</p></td>
<td><p>select firstFast custTable</p>
<p>    order by AccountNum;</p></td>
</tr>
<tr class="even">
<td><p>firstOnly</p></td>
<td><p>Speeds up the fetch. Instructs MorphX to fetch only the first record.</p></td>
<td><p>static InventTable find(</p>
<p>    ItemId   itemId,</p>
<p>    boolean  update = false)</p>
<p>{</p>
<p>    InventTable inventTable;</p>
<p>    ;</p>
<p>    inventTable.selectForUpdate</p>
<p>        (update);</p>
<p>    if (itemId)</p>
<p>    {</p>
<p>         select firstonly inventTable</p>
<p>            index hint ItemIdx</p>
<p>            where inventTable.itemId</p>
<p>                == itemId;</p>
<p>    }</p>
<p>    return inventTable;</p>
<p>}</p></td>
</tr>
<tr class="odd">
<td><p>firstOnly10</p></td>
<td><p>Same as firstOnly, except returns 10 rows instead of one.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>firstOnly100</p></td>
<td><p>Same as firstOnly, except returns 100 rows instead of one.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>firstOnly1000</p></td>
<td><p>Same as firstOnly, except returns 1000 rows instead of one.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>forceLiterals</p></td>
<td>
    
> [!note]  
> <P>You are advised not to use the forceLiterals keyword in X++ select statements, because it could expose code to an SQL injection security threat.</P>

<p>forceLiterals instructs the kernel to reveal the actual values that are used in where clauses to the Microsoft SQL Server database at the time of optimization.</p>
<p>forceLiterals and forcePlaceholders are mutually exclusive.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>forceNestedLoop</p></td>
<td><p>Forces the Microsoft SQL Server database to use a nested-loop algorithm to process a particular SQL statement containing a join algorithm. This means that a record from the first table is fetched before any records from the second table are fetched. Typically, other join algorithms, such as hash-joins and merge-joins, would be considered. This keyword is often combined with the forceSelectOrder keyword.</p></td>
<td><p>while select forceSelectOrder</p>
<p>    forceNestedLoop inventTransThis</p>
<p>    index hint TransIdIdx</p>
<p>    where inventTransThis.InventTransId</p>
<p>        == inventTrans.InventTransId</p>
<p>        &amp;&amp; inventTransThis.StatusIssue</p>
<p>        &lt;= StatusIssue::ReservOrdered</p></td>
</tr>
<tr class="even">
<td><p>forcePlaceholders</p></td>
<td><p>Instructs the kernel not to reveal the actual values used in where clauses to the SQL Server database at the time of optimization. This is the default in all statements that are not join statements.</p>
<p>The advantage of using this keyword is that the kernel can reuse the access plan for other similar statements with other search values. The disadvantage is that the access plan is computed without taking into consideration that data distribution might not be even. The access plan is an on-average access plan.</p>
<p>forcePlaceholders and forceLiterals are mutually exclusive.</p></td>
<td><p>static void forcePlaceHoldersExample(Args _args)</p>
<p>{</p>
<p>    SalesTable salesTable;</p>
<p>    SalesLine salesLine;</p>
<p>    ;</p>
<p>    while select forcePlaceholders salesLine</p>
<p>        join salesTable</p>
<p>           where salesTable.SalesId ==</p>
<p>            salesLine.SalesId</p>
<p>               &amp;&amp; salesTable.SalesId == '10'</p>
<p>    {</p>
<p>        //more code</p>
<p>    }</p>
<p>}</p></td>
</tr>
<tr class="odd">
<td><p>forceSelectOrder</p></td>
<td><p>Forces the SQL Server database to access the tables in a join in the specified order. If two tables are joined, the first table in the statement is always accessed first. This keyword is often combined with the forceNestedLoop keyword.</p></td>
<td><p>display ForecastHasPurch hasForecastPurch()</p>
<p>{</p>
<p>    ForecastPurch   forecastPurch;</p>
<p>    InventDim       inventDim;</p>
<p>    ;</p>
<p>    select firstOnly forcePlaceholders</p>
<p>        forceSelectOrder recId</p>
<p>        from forecastPurch</p>
<p>        index hint ItemIdx</p>
<p>        where forecastPurch.itemId == this.itemId</p>
<p>    exists join inventDim</p>
<p>        index hint DimIdIdx</p>
<p>        where inventDim.inventDimId ==</p>
<p>            forecastPurch.inventDimId</p>
<p>        &amp;&amp; inventDim.configId == this.configId;</p>
<p>    return forecastPurch.recId;</p>
<p>}</p></td>
</tr>
<tr class="even">
<td><p>forUpdate</p></td>
<td><p>Selects records exclusively for update. Depending on the underlying database, the records may be locked for other users.</p></td>
<td><p>ttsBegin;</p>
<p>while select forUpdate ledgerJournalTrans</p>
<p>    index hint NumVoucherIdx</p>
<p>    where ledgerJournalTrans.journalNum ==</p>
<p>    _journalNum &amp;&amp;</p>
<p>    ledgerJournalTrans.voucher == _voucher</p>
<p>{</p>
<p>    ledgerJournalTrans.doDelete();</p>
<p>    counter++;</p>
<p>}</p>
<p>if (counter</p>
<p>    &amp;&amp; ledgerJournalTable.journalType</p>
<p>    != LedgerJournalType::Periodic)</p>
<p>{</p>
<p>    NumberSeq::release(</p>
<p>      ledgerJournalTable.voucherSeries,</p>
<p>      _voucher);</p>
<p>}</p>
<p>ttsCommit;</p></td>
</tr>
<tr class="odd">
<td><p>group by</p></td>
<td><p>Instructs the database to group selected records by fields.</p></td>
<td><p>CustTable custTable;</p>
<p>;</p>
<p>while select sum(CreditMax) from custTable</p>
<p>    group by CustGroup</p>
<p>{</p>
<p>    print custTable.CustGroup, &quot; &quot;,custTable.CreditMax;</p>
<p>}</p></td>
</tr>
<tr class="even">
<td><p>index</p></td>
<td><p>Instructs the database to sort the selected records as defined by the index.</p></td>
<td><p>CustTable custTable;</p>
<p>;</p>
<p>while select AccountNum, Name from custTable</p>
<p>    index AccountIdx</p>
<p>{</p>
<p>    print custTable.AccountNum, &quot; &quot;, custTable.Name;</p>
<p>}</p></td>
</tr>
<tr class="odd">
<td><p>index hint</p></td>
<td><p>Gives the database a hint to use this index to sort the selected records as defined by the index. The database can ignore the hint.</p>

> [!note]  
> <P>A wrong index hint can have a big performance impact. Index hints should only be applied to SQL statements that do not have dynamic where clauses or order by clauses, and where the effect of the hint can be verified.</P>

</td>
<td><p>while select forUpdate ledgerJournalTrans</p>
<p>    index hint NumVoucherIdx</p>
<p>    where ledgerJournalTrans.journalNum</p>
<p>        == _journalNum</p></td>
</tr>
<tr class="even">
<td><p>join</p></td>
<td><p>Used to join tables on a column that is common to both tables. The join criteria are specified in the where clause because there is no on keyword in X++ SQL.</p>
<p>Reduces the number of SQL statements that are needed if you want to loop through a table and update transactions in a related table.</p>
<p>For example, if you process 500 records in a table, and want to update related records in another table, and use a nested while select to do this, there will be 501 trips to the database. If you use a join, there will be a single trip to the database.</p></td>
<td><p>while select ledgerTable</p>
<p>    join ledgerTrans</p>
<p>        where ledgerTrans.accountNum ==</p>
<p>            ledgerTable.accountNum</p>
<p>    {</p>
<p>        amountMST += ledgerTrans.amountMST;</p>
<p>    }</p></td>
</tr>
<tr class="odd">
<td><p>maxof</p></td>
<td><p>Returns the maximum of the fields.</p></td>
<td><p>CustTable custTable;</p>
<p>;</p>
<p>select maxof(CreditMax) from custTable;</p></td>
</tr>
<tr class="even">
<td><p>minof</p></td>
<td><p>Returns the minimum of the fields.</p></td>
<td><p>CustTable custTable;</p>
<p>;</p>
<p>select minof(CreditMax) from custTable;</p></td>
</tr>
<tr class="odd">
<td><p>noFetch</p></td>
<td><p>Indicates that no records are to be fetched at present. This is typically used when the result of the select is passed on to another application object, for example, a query that performs the actual fetch.</p></td>
<td><p>select noFetch custTable</p>
<p>    order by AccountNum</p></td>
</tr>
<tr class="even">
<td><p>notExists</p></td>
<td><p>Chosen only if there are no posts.</p></td>
<td><p>while select AccountNum, Name from custTable</p>
<p>    order by AccountNum</p>
<p>    notExists join * from ctr</p>
<p>    where (ctr.AccountNum ==</p>
<p>        custTable.AccountNum)</p></td>
</tr>
<tr class="odd">
<td><p>optimisticLock</p></td>
<td><p>Forces a statement to run with Optimistic Concurrency Control even if a different value is set on the table.</p>
<p>For more information, see <a href="optimistic-concurrency-control.md">Optimistic Concurrency Control</a>.</p></td>
<td><p>select optimisticLock custTable</p>
<p>    where custTable.AccountNum &gt; '1000'</p></td>
</tr>
<tr class="even">
<td><p>order by</p></td>
<td><p>Instructs the database to sort the selected records by fields in the order by list.</p></td>
<td><p>select * from custTable</p>
<p>    order by accountNum desc</p>
<p>    where custTable.AccountNum &gt; &quot;100&quot;;</p></td>
</tr>
<tr class="odd">
<td><p>outer</p></td>
<td><p>Returns all rows from the first-named table, including rows that have no match in the second-named table. This is a left outer join, although there is no left keyword. There is no right outer join in X++ SQL.</p></td>
<td>

```X++
while select AccountNum
 from custTable
 order by AccountNum
 outer join * from custBankAccount
 where custBankAccount.AccountNum ==
    custTable.AccountNum
{
 print custTable.AccountNum,
    &quot; , &quot;, custBankAccount.DlvMode;
}
pause;
```
</td>
</tr>
<tr class="even">
<td><p>pessimisticLock</p></td>
<td><p>Forces a statement to run with Pessimistic Concurrency Control even if a different value is set on the table.</p>
<p>For more information, see <a href="optimistic-concurrency-control.md">Optimistic Concurrency Control</a>.</p></td>
<td><p>select pessimisticLock custTable</p>
<p>    where custTable.AccountNum &gt; '1000';</p></td>
</tr>
<tr class="odd">
<td><p>repeatableRead</p></td>
<td><p>Specifies that no other transactions can modify data that has been read by logic inside the current transaction, until after the current transaction completes.</p>
<p>An explicit transaction completes at either ttsAbort or at the outermost ttsCommit.</p>
<p>For a stand-alone select statement, the transaction duration is the duration of the select command. However, the database sometimes enforces the equivalent of repeatableRead in individual select statements even without this keyword appearing in your X++ code (depending on how the database decides to scan the tables).</p></td>
<td><p>For more information, see the documentation for the underlying relational database product.</p></td>
</tr>
<tr class="even">
<td><p>reverse</p></td>
<td><p>Records are returned in reverse order.</p></td>
<td><p>select reverse custTable</p>
<p>    order by AccountNum;</p></td>
</tr>
<tr class="odd">
<td><p>sum</p></td>
<td><p>Returns the sum of the fields. Can be used to sum all accounts, order lines, and so on.</p></td>
<td><p>CustTable custTable;</p>
<p>;</p>
<p>select sum(CreditMax) from custTable;</p></td>
</tr>
<tr class="even">
<td><p>validTimeState</p></td>
<td><p>Filters rows from a table that has its <strong>ValidTimeStateFieldType</strong> property set to a value other than <strong>None</strong>. For more information, see <a href="valid-time-state-tables-and-date-effective-data.md">Valid Time State Tables and Date Effective Data</a>.</p></td>
<td>

```X++
static void VtsJob1(Args _args)
{
    // A VTS table in AX 2012.
    CustPackingSlipTransHistory xrec1;
    utcDateTime myDateFrom , myDateTo;
    anytype myAnytype = -1;
    myDateFrom = DateTimeUtil::utcNow();
    myDateTo = myDateFrom;
    SELECT 
        validTimeState(myDateFrom, myDateTo)
        FROM xrec1;
    myAnytype = xrec1.getFieldValue(&quot;RecId&quot;);
    info(myAnytype);
}
```

</td>
</tr>
</tbody>
</table>


## See also

[Select Statement Examples](select-statement-examples.md)

[Select Statements](select-statements.md)

[while select Statements](while-select-statements.md)

[X++ Standards: select Statements](x-standards-select-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

