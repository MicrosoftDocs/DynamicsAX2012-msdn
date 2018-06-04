---
title: Multiple Array Indexes
TOCTitle: Multiple Array Indexes
ms:assetid: 700e74b9-54b5-45fd-acce-b5ab89b57549
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa673457(v=AX.60)
ms:contentKeyID: 35244881
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Multiple Array Indexes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Some languages, such as C++ and C\#, allow you to declare arrays with more than one index; that is, to define "arrays of arrays." You cannot directly create multiple array indexes in X++ - only one-dimensional arrays are supported. However, you can implement multiple indexes by using the following scheme.

If you wanted to declare an array with two dimensions, for example, for holding an amount earned by country by dimension, and there were 10 countries and 3 dimensions, declare the following:

real earning\[10, 3\];

This is not possible in Microsoft Dynamics AX. Instead, you can define a one-dimensional array with the number of elements that is the product of the elements in each dimension:

real earnings\[10\*3\];

To refer to earnings\[i,j\], write:

earnings\[(i-1)\*3 +j\]

You could wrap this into a macro:

\#localmacro.earningIndex

(%1-1)\*3+%2

\#endmacro

And then write:

earnings\[\#earningIndex(i,j)\]

The previous scheme can be extended to any number of dimensions. The element a\[i1, i2, ..., ik\] can be accessed by computing the offset into an array containing (d1\*d2\*...\*dk) elements:

(i1 - 1)\*d2\*d3\*..\*dk +

(i2 - 1)\*d3\*d4\*...\*dk + .... +

(ik-1 -1)\*dk +

(ik-1)

## See also

[Arrays](arrays.md)

[Collection Classes in Microsoft Dynamics AX](collection-classes-in-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

