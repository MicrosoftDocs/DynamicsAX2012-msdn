---
title: 'X++ Standards: Arrays'
TOCTitle: 'X++ Standards: Arrays'
ms:assetid: 14c69938-62b8-4aa8-95db-0b5f7e267198
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa587589(v=AX.60)
ms:contentKeyID: 35240607
ms.date: 05/18/2015
mtps_version: v=AX.60
description: Learn best practices for using the memory option in arrays with Microsoft Dynamics AX 2012. Optimize RAM usage and improve read performance.
---

# X++ Standards: Arrays 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes the best practice for using the memory option in arrays. For more information, see [Arrays](arrays.md).

The memory option is the optional second array declaration option. It specifies how many consecutive entries in the array will be held in memory at a particular time. The rest will reside on disk (a cached temporary file, indexed by the array index).

Dynamic arrays are sized according to the maximum index used.


> [!TIP]
> <P>Use the memory option to limit the amount of RAM used to hold the data of the array when you work with high numbered indexes (and large cells).</P>



If you use all (or nearly all) of the entries in an array, set the memory option to a large number, or do not set it at all.

If you only use a few of the entries in the array, set the memory option to a small number, such as 1.

## Read Performance

If you consider using the memory option on an array where you use all (or almost all) of the entries, the look up performance should be considered.

If you traverse an array sequentially, such as with an index of 1, 2, 3, ..., n, you will probably not experience any read performance problems. The cell data blocks will be read sequentially from disk and they will be read to the end before the next block is read (disk reads will be number of entries/memory option size).

If you traverse an array randomly (such as with an index of 300, 20, 5, 250, n, ..., 50) the cell data will also be read from disk randomly, so you may experience read performance problems (disk reads could be as high as the number of entries).

### ![Aa587589.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa587589.collapse_all(en-us,AX.60).gif")Example 1

MyTable myTable;

boolean foundRecord\[,1\];

;

while select myTable

where myTable

...

{

foundRecord\[myTable.recId\] = true;

...

}

### ![Aa587589.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa587589.collapse_all(en-us,AX.60).gif")Example 2

CustTable custTable;

CustAccount foundAccount\[\];

int i;

;

while select custTable

where custTable

...

{

i++;

foundAccount\[i\] = custTable.AccountNum;

...

}

### ![Aa587589.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa587589.collapse_all(en-us,AX.60).gif")Example 3

Name foundName\[,100\];

int i;

;

while select custTable

where custTable

...

{

i++;

foundName\[i\] = custTable.Name;

}

## See also

[X++ Coding Standards](x-coding-standards.md)

[Arrays](arrays.md)

[Best Practice Performance Optimizations: Swapping Arrays to Disk](best-practice-performance-optimizations-swapping-arrays-to-disk.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

