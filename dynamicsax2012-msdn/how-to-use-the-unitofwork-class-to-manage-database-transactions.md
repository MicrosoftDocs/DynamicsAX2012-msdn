---
title: 'How to: Use the UnitOfWork Class to Manage Database Transactions'
TOCTitle: 'How to: Use the UnitOfWork Class to Manage Database Transactions'
ms:assetid: 728d33b9-cd06-4dd5-9c5d-886f161555a9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg846338(v=AX.60)
ms:contentKeyID: 35245897
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use the UnitOfWork Class to Manage Database Transactions 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the UnitOfWork class to manage database transactions. You give a series of specific individual rows to a UnitOfWork object, in the form of table buffer variables. The UnitOfWork object successfully processes each row, or it rejects all changes. The UnitOfWork class automatically determines the correct sequence of delete, insert, and then update operations on tables that are linked by a foreign key relationship.

An X++ SQL delete\_from statement can affect sets of rows, as defined by conditions that are specified in its where clause. In contrast, the UnitOfWork class cannot support set based operations. The UnitOfWork class operates only on the specific rows that it is given.

The UnitOfWork class automatically propagates the primary key value to the corresponding foreign key field, when the row with the foreign key field is inserted.


> [!NOTE]
> <P>The SystemSequence class, with its suspendRecIds method, offers another technique for propagating primary key values to foreign key fields. However, it is better to use the UnitOfWork class in most situations. One situation where the SystemSequence technique might be better is when a field must always contain a contiguous, unbroken sequence of numbers. For more information, see <A href="https://msdn.microsoft.com/en-us/library/gg957903(v=ax.60)">systemSequence Class</A>.</P>



## Prerequisites

To understand this topic, it helps you to first understand the following:

  - [How to: Create Tables](how-to-create-tables.md) – explains how to create a table and its fields.

  - [How to: Add a Relation to a Table](how-to-add-a-relation-to-a-table.md) – explains how to add a foreign key, and explains the **RelatedTableRole** property of each relation node.

## Call Patterns for the UnitOfWork Class

There is a recurring pattern in the common uses of the UnitOfWork class. The call pattern for inserts is first to add one record at a time to your constructed UnitOfWork object. You add records for insert by calling the insertOnSaveChanges method. You can call this method multiple times in succession. After all the inserts have been added, you call the saveChanges method to persist the inserts to the database.

For updates and deletes, you must begin by using the X++ SQL select statement to retrieve the records from the database, and then put each into a table buffer. You must use the optimisticLock keyword on the select statement.

The pattern is similar for updates and deletes, except the records are added by calling the updateOnSaveChanges method. For deletes call the deleteOnSaveChanges method. You can add inserts, updates, and deletes in succession, in any sequence, and then call the saveChanges method.

## Scenario for the Code Example

The code example in a following section performs SQL data operations on two tables. One table has a foreign key field that corresponds to the primary key field of the other table.

The fields for the parent table TabSale are as follows:

  - RecId – the primary key.

  - SaleName

  - SaleComment

The fields for the child table TabLineItemOfSale are as follows:

  - RecId – the primary key.

  - LiosName

  - LiosComment

  - MasterSaleRecIdFky – the foreign key.

## Code Example for the UnitOfWork Class

The following table lists the major lines of code in the subsequent code example, in the same order as they occur in the example.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Line of code</p></th>
<th><p>Comment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>tSale.Name = &quot;Big&quot;;</p></td>
<td><p>Populate a parent row that will be inserted.</p></td>
</tr>
<tr class="even">
<td><p>tLineIos.Name = &quot;Chair&quot;;</p></td>
<td><p>Populate a child row that will be inserted.</p></td>
</tr>
<tr class="odd">
<td><p>tLineIos.masterSale(tSale);</p></td>
<td><p>The masterSale method is added by the system when the foreign key relationship is established in the AOT, although you control the name with property values. The method helps the UnitOfWork object to propagate primary key values to their corresponding foreign key fields.</p>
<p>For more information, see <a href="how-to-add-a-relation-to-a-table.md">How to: Add a Relation to a Table</a>.</p></td>
</tr>
<tr class="even">
<td><p>uow.insertOnSaveChanges(tSale);</p></td>
<td><p>This method causes the UnitOfWork object to store the table buffer in memory, and to insert the buffer record when uow.saveChanges is soon called.</p></td>
</tr>
<tr class="odd">
<td><p>uow.insertOnSaveChanges(tLineIos);</p></td>
<td><p>This method causes the UnitOfWork object to store the table buffer in memory, and to insert the buffer record when uow.saveChanges is soon called.</p></td>
</tr>
<tr class="even">
<td><p>uow.saveChanges();</p></td>
<td><p>This method processes all the table buffers that are stored from the earlier calls to uow.insertOnSaveChanges.</p></td>
</tr>
<tr class="odd">
<td><p>select optimisticLock ... from tLineIos ... ;</p></td>
<td><p>The optimisticLock keyword is necessary if the table buffer tLineIos is going to be passed into the UnitOfWork object for delete or update.</p></td>
</tr>
<tr class="even">
<td><p>uow.updateOnSaveChanges(tLineIos);</p></td>
<td><p>This table buffer was populated with a row from the database. Of course, a call to uow.saveChanges(); soon follows.</p></td>
</tr>
</tbody>
</table>


### ![Gg846338.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg846338.collapse_all(en-us,AX.60).gif")Code for the X++ Method

The following X++ code sample demonstrates the UnitOfWork class.

```X++
    // X++, a method on a class. Not a job.
    server static public void RunTheUowDemoMethod()
    {
        UnitOfWork uow = new UnitOfWork();
        TabSale           tSale;    // Buffer for parent table.
        TabLineItemOfSale tLineIos; // Buffer for child  table.
        int64 i64MasterSaleRecIdFky;
    
        // Delete all rows, without using UoW.
        delete_from tLineIos;
        delete_from tSale;
    
        // Prepare a parent row for insert.
        // We let the system assign a RecId value, the primary key.
        tSale.SaleName = "Big";
        tSale.SaleComment = "A row in the parent table.";
    
        // Prepare a child row for insert.
        // Again, we let the system assign a RecId value, the primary key.
        // We also let the system assign SaleRecIdFky foreign key value!
        tLineIos.LiosName = "Chair";
        tLineIos.LiosComment = "To sit in.";
    
        // Method name is the RelatedTableRole property value.
        tLineIos.masterSale(tSale);
    
        // Prepare the UoW to do the inserts.
        uow.insertOnSaveChanges(tSale);
        uow.insertOnSaveChanges(tLineIos);
    
        // Before saving changes, prepare more inserts.
        // Add a second child to the current parent record.
        tLineIos.LiosName = "Desk";
        tLineIos.LiosComment = "To work at.";
        tLineIos.masterSale(tSale);
        uow.insertOnSaveChanges(tLineIos);
    
        // Add a second pair of parent + child records.
        tSale.SaleName = "Small";
        tSale.SaleComment = "Another row in the parent table.";
        tLineIos.LiosName = "Shirt";
        tLineIos.LiosComment = "To wear.";
        tLineIos.masterSale(tSale);
        uow.insertOnSaveChanges(tSale);
        uow.insertOnSaveChanges(tLineIos);
    
        // Make the changes to the SQL database, and commit.
        uow.saveChanges();
        //------------------------------------
    
        // Read the newly inserted child row.
        // Use optimistic concurrency, in case OccEnabled=No on the table.
        select optimisticLock
            LiosComment, MasterSaleRecIdFky
            from tLineIos
            where tLineIos.LiosName == "Desk";
    
        i64MasterSaleRecIdFky = tLineIos.MasterSaleRecIdFky;
    
        tLineIos.LiosComment =
            tLineIos.LiosComment + " Appended.";
    
        // Prepare the UoW to do the update. Then update.
        uow.updateonSaveChanges(tLineIos);
        uow.saveChanges();
    
        // All changes are complete. Display the results.
        tLineIos = null;
        tSale = null;
    
        select LiosName, LiosComment, RecId, MasterSaleRecIdFky
            from tLineIos
            where tLineIos.LiosName == "Desk";
    
        select SaleName, SaleComment, RecId
            from tSale
            where tSale.RecId == i64MasterSaleRecIdFky;
    
        // Display the parent RecId and the matching child foreign key.
        info(strFmt("TabSale:  RecId=%1 , SaleName=%2",
            tSale.RecId, tSale.SaleName));
        info(strFmt("TabLineItemOfSale:  MasterSaleRecIdFky=%1 , LiosName=%2 , RecId=%3 , LiosComment=%4",
            tLineIos.MasterSaleRecIdFky, tLineIos.LiosName, tLineIos.RecId, tLineIos.LiosComment));
    }
```

The following lines of output were displayed in the **Infolog** by the previous program.

TabSale: RecId=5637144847 , SaleName=Big

TabLineItemOfSale: MasterSaleRecIdFky=5637144847 , LiosName=Desk , RecId=5637144849 , LiosComment=To work at. Appended.

## Special Factors

The following table lists special factors to consider when you use the UnitOfWork class.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Factor</p></th>
<th><p>Comment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server tier is required.</p></td>
<td><p>The UnitOfWork class can be instantiated only on the server tier. Therefore in the previous code example, the method declaration includes the X++ keyword server. As an alternative, the class that contains the static RunTheUowDemoMethod method can have its <strong>RunOn</strong> property set to <strong>Server</strong>. Your X++ job, in a client tier session, can run the method with the line of code MyClass::RunTheUowDemoMethod();.</p></td>
</tr>
<tr class="even">
<td><p>UnitOfWork requires optimistic concurrency.</p></td>
<td><p>The saveChanges method throws an exception if pessimistic concurrency is in effect for any table buffer that the UnitOfWork object has accumulated. Every table has the <strong>OccEnabled</strong> property, and for new tables the default value is <strong>Yes</strong>, meaning that optimistic concurrency is in effect unless it is temporarily overridden.</p>
<p>If a table has its <strong>OccEnabled</strong> property set to <strong>No</strong>, you must temporarily override that setting in the table buffer. You can temporarily override the concurrency setting in the following ways:</p>
<ul>
<li><p>All table buffers inherit the concurrencyModel method from the xRecord class. The concurrencyModel method can be assigned the ConcurrencyModel::Optimistic enum value.</p></li>
<li><p>If the table buffer is populated by a select statement, the optimisticLock keyword can be added to the select statement.</p></li>
</ul>
<p>For more information about optimistic and pessimistic concurrencies, see <a href="optimistic-concurrency-control.md">Optimistic Concurrency Control</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Database transaction is implicit and automatic.</p></td>
<td><p>The saveChanges method automatically begins a database transaction when its starts. It automatically commits the changes to the database when it finishes. For a given call to the saveChanges method, if any one of its accumulated changes is rejected, all its changes are rejected and rolled back, and the database is left unchanged.</p>
<p>The in-memory table buffers of your X++ code are also rolled back. After the rollback, any table buffer that was given to the insertOnSaveChanges method is reinitialized to null. Also, no updates are made to any table buffer that was given to updateOnSaveChanges.</p></td>
</tr>
<tr class="even">
<td><p>Matching each child record to its parent record.</p></td>
<td><p>By calling the insertOnSaveChanges method multiple times, you can prepare several pairs of parent and child records before you call the saveChanges method. Multiple pairs are prepared in the previous code example. The UnitOfWork object tracks which parent record each child record depends on, by using the information passed in to the masterSale method.</p>
<p>The masterSale method automatically obtains its name from the <strong>RelatedTableRole</strong> property value on the relation node in the AOT. The masterSale method is automatically created when you select the foreign key option for the relation node. In the AOT, the navigation for that is <strong>AOT</strong> &gt; <strong>Data Dictionary</strong> &gt; <strong>Tables</strong> &gt; <strong>TabLineItemOfSale</strong> &gt; <strong>Relations</strong> &gt; <strong>New Relation</strong> &gt; <strong>New</strong> &gt; <strong>New ForeignKey</strong> (not &gt; <strong>Normal</strong>). For more information, see <a href="how-to-add-a-relation-to-a-table.md">How to: Add a Relation to a Table</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Keep transaction size small.</p></td>
<td><p>As a general principle of database access, it is recommended that all transactions be kept small. Large transactions can lock resources that other threads might need. Performance can decline if too many threads get blocked while they wait for resources, and some threads could become deadlocked. Therefore, try to call the saveChanges method often, rather than calling the insertOnSaveChanges method many times before you call the saveChanges method. However, at the other extreme, it might be inefficient to call the saveChanges method after every call to the insertOnSaveChanges method. Seek a balance.</p></td>
</tr>
<tr class="even">
<td><p>The UnitOfWork class does not bypass record level security (RLS).</p></td>
<td><p>The UnitOfWork class does not bypass RLS.</p></td>
</tr>
<tr class="odd">
<td><p>UnitOfWork class does not support temporary tables.</p></td>
<td><p>The UnitOfWork class does not support temporary tables.</p></td>
</tr>
</tbody>
</table>


## See also

[Data Integrity](data-integrity.md)

[Transaction Integrity](transaction-integrity.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

