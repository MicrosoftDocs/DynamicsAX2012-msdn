---
title: Clustered Indexes
TOCTitle: Clustered Indexes
ms:assetid: 3000d837-df49-434e-b304-25ae069353a2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa623224(v=AX.60)
ms:contentKeyID: 35241981
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Clustered Indexes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Organizing your tables with a clustered index usually has performance advantages. The general rules are as follows:

  - If only one index is created on the table, make it clustered. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

  - Create a clustered index on the key on all group and main tables.


> [!NOTE]
> <P>The ClusteredIndex table property determines which index on a table is clustered.</P>



Carefully consider how to cluster your transaction tables. They have many records and receive many database operations. There is a great potential to improve speed and reduce memory usage.

It's advantageous if records are usually inserted at the end of the index, for example, if the index contains the current date as part of the key.

The advantages of having a cluster index are as follows:

  - Search results are quicker when records are retrieved by the cluster index, especially if records are retrieved sequentially along the index.

  - Other indexes that use fields that are a part of the cluster index might use less data space.

  - Fewer files in the database; data is clustered in the same file as the clustering index. This reduces the space used on the disk and in the cache.

The disadvantages of having a cluster index are as follows:

  - It takes longer to update records (but only when the fields in the clustering index are changed).

  - More data space might be used for other indexes that use fields that are not part of the cluster index if the clustering index is wider than approximately 20 characters).

Avoid clustering index constructions where there is a risk that many concurrent inserts will happen on almost the same clustering index value. They will be directed to the same page, resulting in more frequent page splits, which will result in locks and thus lead to poorer performance. Ensure that the inserts are distributed throughout the clustering index.


> [!NOTE]
> <P>Clustered indexes are referred to as Index Organized Tables in Oracle and Cluster Indexes in SQL.</P>



## See also

[Best Practices for Indexes](best-practices-for-indexes.md)

[How to: Create an Index](how-to-create-an-index.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

