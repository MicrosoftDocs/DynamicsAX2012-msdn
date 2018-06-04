---
title: Single-record Caching
TOCTitle: Single-record Caching
ms:assetid: 5896db77-3af6-4a36-96f7-9b1208c38126
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb314693(v=AX.60)
ms:contentKeyID: 35244337
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Single-record Caching 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Record caching is enabled for a table when all the following statements are true:

  - The **CacheLookup** property on the table is enabled by setting it to one of the following values:  
     **NotInTTS**, **Found**, **FoundAndEmpty**.

  - The record buffer disableCache method has not been called with a parameter of true.

Records are cached for all unique indexes when all the following criteria are met:

  - The table is cached by having its **CacheLookup** property set to **NotInTTS**, **Found**, or **FoundAndEmpty**.

  - The select statement that selects the records uses an equal operator (==) on the caching key. The fields in the where clause of the select statement match the fields in any unique index.

## Cache Location

Caches are used on both the client and the Application Object Server (AOS). The Microsoft Dynamics AX runtime manages the cache by removing old records when new records are added to the cache.

### ![Bb314693.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314693.collapse_all(en-us,AX.60).gif")Client Cache

A client-side cache can be used only by the client. The client cache is used when a select is executed from the client tier. If no record is found in the client cache, the client then searches the server cache for the record. If the record is not located in the server cache, it is retrieved from the database. You can configure the number of records to be maintained in the cache by using the **Server configuration** form. The form is found in the application workspace at:  
 **System administration** \> **Area page** \> **Setup** \> **System** \> **Server configuration**. In this form, continue to:  
 **Performance Optimization** \> **Performance Settings** \> **Client record cache factor**.


> [!NOTE]
> <P>To give an idea of scale, prior to Microsoft Dynamics AX 2012 the maximum number of table records in the client cache was permanently set at 100 records per table, for a given company.</P>



### ![Bb314693.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314693.collapse_all(en-us,AX.60).gif")Server Cache

A server-side cache can be used by any connection to the server. The server cache is used when a select is executed on the server tier. If no record is found in the server-side cache, the record is retrieved from the database. You can configure the maximum number of records that are maintained in a server cache by using the **Cache Limits** section of the **Server configuration** form. The default value is 2000 records for a given company per table group or per Application Object Server (AOS).

### ![Bb314693.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314693.collapse_all(en-us,AX.60).gif")Configuring the Cache Sizes

You can configure the size of the cache by navigating to the **Server configuration** form. This form is found in the application workspace at:  
 **System administration** \> **Area page** \> **Setup** \> **System** \> **Server configuration**.

On the form, the cache configuration items are at:  
 **Performance Optimizations** \> **Performance Settings**.

There the cache settings can be modified for all instances of the AOS, or for only the current instance of the AOS.

## Enhanced Caching Functionality

The following table describes enhanced caching features that were added in Microsoft Dynamics AX 2012.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extras okay in Where clause</p></td>
<td><p>An X++ Select statement can have a Where clause that contains equality tests on all fields of any unique index, plus additional tests of other fields. The additional tests must be added with the &amp;&amp; operator, not with ||. Such additional tests no longer prevent the caching mechanisms from improving performance. The following X++ select statement is an example of such a join.</p>
<p>select * from tabCustTable <br />
 where tabCustTable.AccountNum == &quot;4000&quot; &amp;&amp; <br />
 tabCustTable.CustGroup == &quot;Gold&quot;;</p></td>
</tr>
<tr class="even">
<td><p>join is supported</p></td>
<td><p>An X++ Select statement that joins tables can now be included in the caching processes. The Where clause must contain an equality test on a caching index. The following X++ select statement is an example of such a join.</p>
<p>select from tabCustTable join tabCustGroup <br />
 where tabCustTable.AccountNum == &quot;4000&quot; &amp;&amp; <br />
 tabCustTable.CustGroup == tabCustGroup.CustGroup;</p>
<p>The preceding Select Join would cause the following Select to be serviced by the cache:</p>
<p>select from tabCustGroup <br />
 where tabCustGroup.CustGroup == &quot;Gold&quot;;</p></td>
</tr>
<tr class="odd">
<td><p>Cross-company queries</p></td>
<td><p>Queries that use the <a href="cross-company-data-access.md">crossCompany</a> keyword of X++ are supported for caching when there is only a single company involved.</p></td>
</tr>
<tr class="even">
<td><p>container field type</p></td>
<td><p>The container field type is now supported for caching, when the container field has a unique index based on it.</p></td>
</tr>
<tr class="odd">
<td><p>Table inheritance</p></td>
<td><p>Data queries against tables that support <a href="table-inheritance-overview.md">table inheritance</a> are serviceable by the cache.</p></td>
</tr>
<tr class="even">
<td><p>Valid Time State tables</p></td>
<td><p><a href="valid-time-state-tables-and-date-effective-data.md">Valid time state</a> tables are supported by the caching mechanisms.</p></td>
</tr>
</tbody>
</table>


## CacheLookup Property

The **CacheLookup** property of the table defines how and when records are cached as shown in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong>CacheLookup</strong> property value</p></th>
<th><p>Result</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>None</p></td>
<td><p>No data is cached or retrieved from the cache for this table.</p>
<p>This property value should be used for tables that are heavily updated or where it's unacceptable to read outdated data.</p></td>
</tr>
<tr class="even">
<td><p>NotInTTS</p></td>
<td><p>All successful caching key selects are cached.</p>
<p>When in a transaction (after ttsBegin), no caches made outside the transaction are used. When inside a transaction, the record is read once from database and subsequently from the cache. The record is select-locked when read in a transaction, which ensures that the record cached is not updated while the transaction is active.</p>
<p>A typical example of the NotInTTS property is on the CustTable in the Microsoft Dynamics AX application. It is acceptable to read outdated data from the cache outside a transaction, but when data is used for validation or creating references, it is ensured that the data is real-time.</p></td>
</tr>
<tr class="odd">
<td><p>Found</p></td>
<td><p>All successful caching key selects are cached. All caching key selects are returned from the cache if the record exists there. A select forUpdate in a transaction forces reading from the database and replaces the record in the cache.</p>
<p>This is typically used for static (lookup) tables, such as Unit, where the record usually exists.</p></td>
</tr>
<tr class="even">
<td><p>FoundAndEmpty</p></td>
<td><p>All selects on caching keys are cached, including selects that are not returning data.</p>
<p>All caching key selects are returned from caching if the record exists there, or the record is marked as nonexistent in the cache. A select forUpdate in a transaction forces reading from the database and replaces the record in the cache.</p>
<p>An example of FoundAndEmpty record caching is in the Discount table in the Microsoft Dynamics AX standard application. By default, the Discount table has no records. By using a FoundAndEmpty cache on this table, the keys that are queried for but not found are stored in the cache. Subsequent queries for these same non-existent records can be answered from the cache without a round trip to the database.</p></td>
</tr>
<tr class="odd">
<td><p>EntireTable</p></td>
<td><p>Creates a set-based cache on the server. The entire table is cached as soon as at least one record is selected from the table. For more information, see <a href="set-based-caching.md">Set-based Caching</a>.</p></td>
</tr>
</tbody>
</table>


## Transaction Boundaries for Caching

The Found and FoundAndEmpty caches across transaction boundaries. The NotInTTS cache is newly created inside a transaction. The following code example is from Greef, Pontoppidan, et al. 2006. *Inside Microsoft Dynamics AX 4.0*. 445. Redmond: Microsoft Press. This example, modified for the purposes of this topic, demonstrates how records are retrieved from the cache when the table's **CacheLookup** property is set to NotInTTS, and the **PrimaryIndex** property is set to a unique index on the AccountNum field.

    static void NotInTTSCache(Args _args) // X++, in AOT > Jobs.
    {
        CustTable custTable;
        ;
        // The query looks for a record in the cache.
        // If the record does not exist in the cache,
        // the query accesses the database.
        select custTable
            where custTable.AccountNum == '4000';
    
        // The transaction starts.
        ttsbegin;
    
        // The cache is not used. The query accesses the database
        // and a record is placed in the cache.
        select custTable
            where custTable.AccountNum == '4000';
    
        // The query uses the database because 
        // the forupdate keyword is used.
        select forupdate custTable
            where custTable.AccountNum == '4000';
    
        // The query uses the cache and not the database.
        select custTable
            where custTable.AccountNum == '4000';
    
        // The query uses the cache because
        // the forupdate keyword was used previously.
        select forupdate custTable
            where custTable.AccountNum == '4000';
    
        // The transaction is committed.
        ttscommit;
    
        // The query will use the cache.
        select custTable
            where custTable.AccountNum == '4000'; 
    }

Reproduced by permission from Greef, Pontoppidan, et al, *Inside Microsoft Dynamics AX 4.0* (Redmond, WA: Microsoft Press, 2006), 445.


> [!NOTE]
> <P>More code examples for caching can be found in chapter 12 of <EM>Inside Microsoft Dynamics AX 2009</EM>, ISBN: 978-0-7356-2645-4.</P>



If the table’s **CacheLookup** property was set to **Found** or **FoundAndEmpty**, the first select statement inside the transaction (after the TTSBegin statement) would retrieve the record from the cache.

## Code Example to Demonstrate Performance

The following X++ code example is a job that selects one record from the CustTable table numerous times in two loops. Caching is disabled for the first loop by a call to the disableCache method. Caching is enabled for the second loop. The comment at the end of the code displays the timed results. The results show that the first loop took 148 seconds to complete, whereas the second loop took only 1 second.

    static void SingleRecordCachePerfTest3Job(Args _args) // X++, under AOT > Jobs.
    {
        /***
           PROPERTIES OF CUSTTABLE TABLE (in Microsoft Dynamics AX 2012):
        Field AccountNum is Mandatory (not nullable).
        Field Party is Mandatory (not nullable).
        Unique index AccountIdx is on one field, AccountNum.
        Unique index Party is on one field, Party.
        Property PrimaryIndex = AccountIdx (just on AccountNum).
        Property CacheLookup = Found.
        ***/
        
        CustTable tabCust;
        str 10 singletonValue = "4001"; // tabCust.AccountNum field value.
        //int64 singletonValue  = 987654321; // tabCust.Party field value.
        int nLoops = 65536;
        int i;
        int nSecsSinceMidnight[4];
    
        // Prime the demo with one retrieval.
        select
        from
            tabCust
        where
            tabCust.AccountNum == singletonValue; // Unique index on this field.
    
    
        tabCust.disableCache(true); // do Not use the cache.
        
        nSecsSinceMidnight[1] = timeNow();
        for (i=0; i < nLoops; i++)
        {
            select
                from
                    tabCust
                where
                    tabCust.AccountNum == singletonValue; // Unique index on this field.
        }
        nSecsSinceMidnight[2] = timeNow();
        
        tabCust.disableCache(false); // Do use the cache!
        
        for (i=0; i < nLoops; i++)
        {
            select
                from
                    tabCust
                where
                    tabCust.AccountNum == singletonValue;
        }
        nSecsSinceMidnight[3] = timeNow();
        
        info( strFmt("Time1: %1", nSecsSinceMidnight[1] ));
        info( strFmt("Time2: %1", nSecsSinceMidnight[2] ));
        info( strFmt("Time3: %1", nSecsSinceMidnight[3] ));
    }
    /*****  Infolog display
    Message (07:44:11 am)
    Time1: 31301
    Time2: 31449
    Time3: 31450
    *****/

In the preceding X++ job, caching occurs because there is a unique index on the AccountNum field.

Message (08:56:13 am)   
 Time1: 32108   
 Time2: 32146   
 Time3: 32183

### ![Bb314693.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314693.collapse_all(en-us,AX.60).gif")Client and AOS CPU Workloads

In the preceding code example there are two loops. During the first loop when the cache is not being used, the central processing unit (CPU) of the server computer is very busy with processing for the AX32serv.exe AOS process. During the second loop when the cache is being used, the CPU of the client computer is very busy with processing for the AX32.exe client process.

## See also

[Record Caching](record-caching.md)

[Set-based Caching](set-based-caching.md)

[Table Properties](https://msdn.microsoft.com/en-us/library/aa871620\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

