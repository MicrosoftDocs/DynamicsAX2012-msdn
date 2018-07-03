---
title: Set-based Caching
TOCTitle: Set-based Caching
ms:assetid: 418a33f2-113b-457d-9996-5dc2f6ce4349
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb314630(v=AX.60)
ms:contentKeyID: 35242950
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Set-based Caching 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, groups of records can be cached all at once with set-based caching. Set-based caching can be implemented in two ways:

  - At design time, by setting the table's CacheLookup property to EntireTable.

  - In code, by using the RecordViewCache class.

## EntireTable Cache

When you set a table's CacheLookup property to EntireTable, all the records in the table are placed in the cache after the first select. This type of caching follows the rules of single record caching. This means that the SELECT statement WHERE clause must include equality tests on all fields of the unique index that is defined in the table's PrimaryIndex property.

The EntireTable cache is located on the server and is shared by all connections to the Application Object Server (AOS). If a select is made on the client tier to a table that is EntireTable cached, it first looks in its own cache and then searches the server-side EntireTable cache. An EntireTable cache is created for each table for a given company. If you have two selects on the same table for different companies the entire table is cached twice.


> [!NOTE]
> <P>Avoid using EntireTable caches for large tables because once the cache size reaches 128 KB the cache is moved from memory to disk. A disk search is much slower than an in-memory search.</P>



For more information about EntireTable caching, see *Inside Microsoft Dynamics AX 4.0*, Chapter 17.

### ![Bb314630.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314630.collapse_all(en-us,AX.60).gif")Flushing the Cache

An EntireTable cache is flushed whenever an insert, update, or delete is made to the table. At the same time, the AOS notifies other AOSs that their caches of the same table must be flushed. After the cache is flushed, a subsequent select on the table causes the entire table to be cached again. Therefore, avoid caching any table that's frequently updated. Regardless of when updates are made, EntireTable caches are flushed every 24 hours by the AOS.

The X++ language has the flush [keyword](x-keywords.md). Suppose that a table’s **CacheLookup** property is set to **EntireTable**. Further suppose that you update the data in a table by using a mechanism, such as the \[Statement\] class, that bypasses the AOS. In this scenario you should flush the table’s cache immediately after the data update.

### ![Bb314630.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314630.collapse_all(en-us,AX.60).gif")firstOnly Keyword

Suppose that an X++ SQL select statement uses the firstOnly keyword. If the select is satisfied by the table’s **EntireTable** cache, the firstOnly keyword is ignored.

## RecordViewCache Cache

Set-based caching is implemented in code by using the RecordViewCache class. You must first create a record buffer using the nofetch statement and then pass the record buffer to the RecordViewCache class when it's instantiated.

The cache is created on the server and is only accessible by the process that creates the cache object. Once the cache is instantiated, all select statements are issued against the cache, as shown in the following X++ job code (from *Inside Dynamics AX 4.0*, Chapter 17, page 450).

   ```X++
   static void RecordViewCache(Args _args)
    {
        CustTrans       custTrans;
        RecordViewCache recordViewCache;
        ;
        // Define records to cache.
        select nofetch custTrans
           where custTrans.AccountNum == '4000';
    
        // Cache the records.
        recordViewCache = new RecordViewCache(custTrans);
    
        // Use cache.
        select firstonly custTrans
            where custTrans.AccountNum == '4000' &&
                  custTrans.CurrencyCode == 'USD';
    }
   ```

Due to concurrency issues, the forUpdate keyword on the instantiating X++ SELECT statement should only be used when all of the records in the result set will be updated. Otherwise it's a better strategy to use select forUpdate only for the records that are to be updated.

The RecordViewCache class is used in a select when the select is from a table that's cached, the select statement doesn't participate in a join and the select WHERE clause matches the WHERE clause with which the RecordViewCache was instantiated.

The cache created by the RecordViewCache class stores records in a linked list. Therefore Microsoft Dynamics AX searches the cache sequentially for records that match the search criteria. If the SELECT statement contains an ORDER BY clause, a temporary index is placed on the cache and the runtime uses the index when searching records.

For more information about the RecordViewCache class, see *Inside Microsoft Dynamics AX 4.0*, Chapter 17.

## See also

[Record Caching](record-caching.md)

[Single-record Caching](single-record-caching.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

