---
title: 'Best Practice Performance Optimizations: Swapping Arrays to Disk'
TOCTitle: 'Performance Optimizations: Swapping Arrays to Disk'
ms:assetid: affdd249-d05a-4a56-af03-032d871578a9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa855880(v=AX.60)
ms:contentKeyID: 35249734
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practice Performance Optimizations: Swapping Arrays to Disk 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you declare an array, one of your options is to specify how many array items are to be held in memory. The remaining array items are swapped to disk.


> [!NOTE]
> <P>Use this option with caution, as it could lead to excessive disk swapping or excessive memory usage.</P>



A dynamic array is sized according to the largest index ever used in the array. For example, if you use an index of 1000 in an array, the size of the array is set to 1000. If you then use an index of 500, the array size remains 1000.

The general rules are:

  - If you use all or nearly all entries in an array, set the memory option to a large number or do not set the option at all.

  - If you use few, non-consecutive entries in the array, set the memory option to a small number, such as 1.

  - If you use record IDs as indexes, set the memory option to 1. Record IDs are typically very large integers. When you use them as indexes, the size of your dynamic arrays grows unacceptably large.
    
    For example:
    
    MyTable myTable;
    
    boolean foundRecord\[,1\];
    
    ;
    
    while select myTable
    
        where myTable ...
    
    {
    
        foundRecord\[myTable.RecId\] = true;
    
        ...
    
    }

## See also

[Arrays](arrays.md)

[X++ Standards: Arrays](x-standards-arrays.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

