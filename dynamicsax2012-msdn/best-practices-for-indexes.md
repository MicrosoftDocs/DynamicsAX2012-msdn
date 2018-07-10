---
title: Best Practices for Indexes
TOCTitle: Indexes
ms:assetid: 17e24a97-8ab9-4667-bfae-2c93f82333bc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa617587(v=AX.60)
ms:contentKeyID: 35241352
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Indexes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The basic rules for index design are as follows:

  - Assign a unique index to each table.

  - Add as few indexes as possible and maintain query performance.

  - Strongly consider designating one of the indexes as the cluster index.

An error will be displayed if an index is overlapped by another index, and the other is enabled and doesn't have a configuration key. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon") An error will also be displayed if an index is created with no fields in it. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

## Using the Key

If the table has a key, create a unique index on the fields in the key (set the AllowDuplicates property to No). The database system ensures the uniqueness of the key.

## When to Create an Index

The advantages of indexes are as follows:

  - Their use in queries usually results in much better performance.

  - They make it possible to quickly retrieve (fetch) data.

  - They can be used for sorting. A post-fetch-sort operation can be eliminated.

  - Unique indexes guarantee uniquely identifiable records in the database.

The disadvantages of indexes are as follows:

  - They decrease performance on inserts, updates, and deletes.

  - They take up space (this increases with the number of fields used and the length of the fields).

  - Some databases will monocase values in fields that are indexed.

You should only create indexes when they are actually needed.

Take care not to add an index on something that has already been indexed. If you need a more detailed index, you can add fields to an existing index as long as it is not a unique index.


> [!TIP]
> <P>It is more time-consuming to change fields at the beginning of an index than at the end of an index. If fields in an index are updated frequently, place these at the end of the index.</P>



## Index Hints

When you use index hints, verify them with performance tests. The optimizer might be able to find a more efficient hint.

The following examples show finding ledger transactions in account number, transaction date order.

Last weeks' (few days) transactions on all the (many) Profit & Loss accounts.

```X++
select ledgerTrans
    index hint DateIdx
    order by accountNum, transDate
    where ledgerTrans.accountNum >= '40000'   
        &&  ledgerTrans.accountNum <= '99999'   
        &&  ledgerTrans.transDate  >= 26\04\1999 
        &&  ledgerTrans.transDate  <= 02\05\1999;  
```

Transactions for the whole year (many dates) on (the few) liquid assets accounts.

```X++
select ledgerTrans
        index hint ACDate
        order by accountNum, transDate
        where ledgerTrans.accountNum >= '11100'   
            &&  ledgerTrans.accountNum <= '11190'   
            &&  ledgerTrans.transDate  >= 01\07\1999 
            &&  ledgerTrans.transDate  <= 30\06\2000;
```

## See also

[Best Practices for Index Properties](best-practices-for-index-properties.md)

[Clustered Indexes](clustered-indexes.md)

[Unique Indexes](unique-indexes.md)

[Full Text Index Overview](full-text-index-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

